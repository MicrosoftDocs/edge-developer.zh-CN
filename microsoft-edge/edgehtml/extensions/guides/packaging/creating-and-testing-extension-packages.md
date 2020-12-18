---
ms.assetid: 5eefa3d8-8626-4486-bd90-1361400d6468
description: 了解如何手动打包 Microsoft Edge 扩展并测试它以查看其打包是否正确。
title: 创建和测试扩展包
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员， 打包
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 44316f4dd47b3b6b26014ff24673ddfd16a72ddb
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232608"
---
# 创建和测试 Microsoft Edge 扩展 AppX 程序包  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

Microsoft Edge 扩展打包为 AppX，类似于打包通用 Windows 应用的方式。 自 Windows 10 周年更新起，AppX 引入了一个新架构，允许 AppX 将 Microsoft Edge 扩展作为其内容。

如果你已了解如何创建 Microsoft Edge 扩展 AppX，可以跳到使用 [ManifoldJS](./using-manifoldjs-to-package-extensions.md) 打包扩展，以了解如何使用基于 Node.js 的工具执行所有这些操作！

> [!NOTE]
> 将 Microsoft Edge 扩展提交到 Microsoft Store 目前是一项受限功能。 创建、打包和测试扩展后，请在扩展提交表单上 [提交请求](https://aka.ms/extension-request)。

## 准备提交文件夹

若要准备你的扩展以提交，你需要创建具有以下结构的文件夹：

![文件夹结构的图像。 "我的扩展"文件夹内AppxManifest.xml、扩展文件夹和资产文件夹](./../../media/packaging_folder-structure.png)

在文件夹的根目录下，应包含AppXManifest.xml文件。 此文件用于指定包的内容和布局。

你还应该有一个 Assets 文件夹，其中包含在 Microsoft Store 中使用的 UI 资产，以及一个扩展文件夹，其中包含扩展名的文件 (脚本、图标等) 。

> [!IMPORTANT]
> 你可以为程序包创建不同的文件夹结构，但文件夹结构必须与 AppXManifest 值匹配。

### AppXManifest.xml
AppXManifest 文件是一个 XML 文档，其中包含系统部署、显示或更新 Windows 应用时需要的信息。 此文件还包括程序包标识、功能和视觉元素。 每个应用包必须包含一个 AppXManifest 文件。

开发人员可以将以下模板用于其AppXManifest.xml文件：

```xml
<?xml version="1.0" encoding="utf-8"?>
<Package
  xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10"
  xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10"
  xmlns:uap3="http://schemas.microsoft.com/appx/manifest/uap/windows10/3"
  IgnorableNamespaces="uap3">

  <Identity
    Name="[REPLACE WITH PACKAGE/IDENTITYNAME]"
    Publisher="[REPLACE WITH PACKAGE/IDENTITY/PUBLISHER]"
    Version="[REPLACE WITH PACKAGE VERSION in the form X.X.X.0]"/>

  <Properties>
    <DisplayName>[REPLACE WITH RESERVED STORE NAME]</DisplayName>
    <PublisherDisplayName>[REPLACE WITH PACKAGE/PROPERTIES/PUBLISHERDISPLAYNAME]</PublisherDisplayName>
    <Logo>[REPLACE WITH RELATIVE PATH TO 50x50 ICON]</Logo>
  </Properties>

  <Dependencies>
    <TargetDeviceFamily Name="Windows.Desktop"
      MinVersion="10.0.14393.0"
      MaxVersionTested="10.0.14800.0" />
  </Dependencies>

  <Resources>
    <Resource Language="en-us"/>
  </Resources>

  <Applications>
    <Application Id="App">
      <uap:VisualElements
        AppListEntry="none"
        DisplayName="[REPLACE WITH RESERVED STORE NAME]"
        Square150x150Logo="[REPLACE WITH RELATIVE PATH TO 150x150 ICON]"
        Square44x44Logo="[REPLACE WITH RELATIVE PATH TO 44x44 ICON]"
        Description="This is the description of the extension"
        BackgroundColor="white">
      </uap:VisualElements>
    <Extensions>
    <uap3:Extension Category="windows.appExtension">
    <uap3:AppExtension Name="com.microsoft.edge.extension"
        Id="EdgeExtension"
        PublicFolder="Extension"
      DisplayName="[REPLACE WITH RESERVED STORE NAME]">
    </uap3:AppExtension>
    </uap3:Extension>
    </Extensions>
 </Application>
</Applications>
</Package>
```  

#### 应用标识模板值
通过 Windows [开发人员中心](./extensions-in-the-windows-dev-center.md#name-reservation) 保留扩展名称后，你将能够查找替换 windows 开发人员中心中的以下值所需的程序包标识AppXManifest.xml：

-   `Name`
-   `Publisher`
-   `DisplayName`
-   `PublisherDisplayName`

可以使用以下步骤访问应用标识页：

1.  导航到 [Windows 开发人员中心](https://developer.microsoft.com/windows/)。
2.  登录到你的开发人员帐户。
3.  导航到仪表板。
4.  选择扩展的名称。
    
    ![扩展列表](./../../media/select-app.png)
    
5.  注册应用后，导航到"应用管理"部分 (下的应用标识) 。
    
    ![应用标识页](./../../media/app-identity.png)
    
现在，可以使用"应用标识"页中的值填充 AppXManifest 模板，如模板中指示：

```xml
<Identity
  Name="37369abigailc.MyExtension"
  Publisher="CN=732F2E5E-B9A6-4243-85F6-A4210F57AA10"
  Version="[REPLACE WITH PACKAGE VERSION in the form X.X.X.0]" />

<Properties>
  <DisplayName>My Extension</DisplayName>
  <PublisherDisplayName>abigailc</PublisherDisplayName>
  <Logo>[REPLACE WITH RELATIVE PATH TO 50x50 ICON]</Logo>
</Properties>
```  

#### JSON 清单模板值
AppXManifest 中的某些值需要匹配 JSON 清单中定义的那些值。 Please update the following values in appxmanifest.xml based on your extension JSON manifest：

-   `Version` - 这是扩展的 JSON 清单中列出的版本。 字符串需要匹配 X.X.X.X 格式，其中最后一个整数必须为 0。 例如 1.2.3.0
    
    ```xml
    <Identity
         Name="37369abigailc.MyExtension"
         Publisher="CN=732F2E5E-B9A6-4243-85F6-A4210F57AA10"
         Version="1.0.0.0" />
    ```  
    
-   `Description` - 这是扩展的 JSON 清单中的说明副本。
    
    ```xml
    <uap:VisualElements
         AppListEntry="none"
         DisplayName="My Extension"
         Square150x150Logo="[REPLACE WITH RELATIVE PATH TO 150x150 ICON]"
         Square44x44Logo="[REPLACE WITH RELATIVE PATH TO 44x44 ICON]"
         Description="This extension will allow you to quickly print by clicking the browser action."
         BackgroundColor="white">
    </uap:VisualElements>
    ```  
    
### 资源文件夹

在"资产"文件夹中，你需要三种不同的图标大小。 这些图标将在 Microsoft Store 和 Windows UI 中使用。 有关这些图标详细信息， [请参阅设计指南](./../design.md#icons-for-packaging) 。

![包含三个图标大小的 assets 文件夹](./../../media/assets-folder.png)

创建必要的 UI 资源后，更新AppXManifest.xml以指向正确的文件：

-   44x44
    
    ```xml
    Square44x44Logo="Assets/icon_44.png"
    ```  
    
-   50x50
    
    ```xml
    <Logo>Assets/icon_50.png</Logo>
    ```  
    
-   150x150
    
    ```xml
    Square150x150Logo="Assets/icon_150.png"
    ```  
    
### 扩展文件夹
复制扩展文件 (将文件夹结构) 扩展文件夹。 请确保 `manifest.json` 在扩展文件夹的根目录下。

![包含所有扩展文件的扩展文件夹](./../../media/extension-folder.png)

### 支持多个区域设置
如果你的扩展支持多种语言，你可能想要使用所需的所有区域设置配置 AppX 程序包，以便正确的本地化图标和说明显示在 Microsoft Store 中。 有关详细信息 [，请参阅本地化](./localizing-extension-packages.md) 扩展包。

### 创建 Appx

若要创建 Appx，你需要查找 makeappx 的路径。 如果位于 64 位计算机上，则通常位于以下位置。

`C:\Program Files (x86)\Windows Kits\10\bin\x64`

执行以下命令，为扩展创建 AppX 包：

`[Path to makeappx] makeappx pack /h SHA256 /d [Path to package folder created in #1] /p [Path to the appx file that you want to create]`

填充路径后，应如下所示：

`C:\Program Files (x86)\Windows Kits\10\bin\x64>makeappx.exe pack /h SHA256 /d "C:\Extension\My Extension" /p C:\Extension\MyExtension.appx`

### 解压缩 Appx
你可能想要解压缩以前生成的 AppX，并使用它作为下一次扩展迭代的起点，或者确认 AppX 已正确创建。

为此，可以执行以下命令解压缩 Microsoft Edge 扩展的 AppX 程序包：

```shell
[Path to makeappx] makeappx unpack /v /p [Path to appx file you want to unpack] /d [Path to the location where you want to create the package folder]
```  

填写后应如下所示：

```text
C:\Program Files (x86)\Windows Kits\10\bin\x64>makeappx.exe unpack /v /p "C:\Extension\MyExtension.appx" /d "C:\Extension\My Extension"
```  

## 测试 AppX 程序包

可以通过在 Microsoft Edge 中旁加载 Microsoft Edge 扩展 AppX 程序包来测试它。 旁加载扩展 AppX 程序包类似于旁加载通用 Windows 应用。 你需要创建用于对程序包进行签名的证书，然后将程序包添加到 Windows。

### 签名

请参阅 [如何创建应用包签名证书](https://msdn.microsoft.com/library/windows/desktop/jj835832.aspx) 以及如何使用 [SignTool](https://msdn.microsoft.com/library/windows/desktop/jj835835.aspx) 对应用包进行签名，获取有关程序包的签名和认证过程的信息。

> [!NOTE]
> 在将扩展包提交到 Microsoft Store 之前，无需对它进行签名;应用商店的提供过程将负责你！

使用创建的证书对程序包进行签名后，本地计算机仍不信任该证书来部署应用包，除非将其安装到本地计算机的受信任证书存储中。 可以使用 Windows Certutil.exe来执行此操作。

若要使用 WindowsCertutil.exe 安装证书，Cmd.exe管理员运行以下命令：

```shell
Certutil -addStore TrustedPeople MyKey.cer
```  

一旦证书不再使用，建议通过从管理员命令提示符运行以下命令将其删除：

```shell
Certutil -delStore TrustedPeople certID
```  

certID 是证书的序列号。 若要确定证书序列号，请运行以下命令：

```shell
Certutil -store TrustedPeople
```  

### 部署
在 PowerShell 中以管理员角色运行以下命令， (Microsoft Edge 扩展 AppX) ：

```powershell
Add-AppxPackage [path to AppX]
```  

## 使用 WebDriver 自动测试

自周年更新起，可以使用 WebDriver 以编程方式在 Microsoft Edge 中旁加载扩展，从而在 Microsoft Edge 在 WebDriver 模式下启动时自动测试扩展。 这将允许你为处理页面上内容的任何扩展设置自动测试，并验证是否展示了正确的行为。

若要旁加载扩展以自动测试，你需要将扩展的文件夹存储在 `%LOCALAPPDATA%\Packages\Microsoft.MicrosoftEdge_8wekyb3d8bbwe\LocalState\` 下。 一旦扩展位于目录中，你将需要创建一个对象， `LocalState` [`EdgeOptions`](https://seleniumhq.github.io/selenium/docs/api/dotnet/html/T_OpenQA_Selenium_Edge_EdgeOptions.htm) 并将其添加到 `extensionPaths` 该对象。 此功能的值是你希望在 Microsoft Edge 以 WebDriver 模式启动时 (的) `LocalState` 的扩展的绝对路径数组。

请查看以下 [C#](https://github.com/scottlow/Ignite2016/blob/master/Ignite%202016%20WebDriver%20Demo/IgniteWebDriverDemo/Program.cs) 文件，了解使用 WebDriver 在 Microsoft Edge 中旁加载扩展的完整示例。

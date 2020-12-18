---
ms.assetid: c4043c1e-15ac-4210-8851-3804c7708f49
description: 了解如何本地化 Microsoft Edge 扩展包，以便它可以在发布时用于多个区域设置。
title: 本地化扩展包
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.custom: seodec18
ms.date: 12/15/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cfa85eda47fd71099bb5d201d1cf85992931228c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232601"
---
# 本地化适用于 Windows 和 Microsoft Store 的 Microsoft Edge 扩展  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

本指南逐步介绍如何本地化 Microsoft Edge 扩展，以便它可以在发布时用于多个区域设置。 若要完全本地化扩展，你将需要遵循 Windows 和 Microsoft Store 的步骤。

如果要本地化 Microsoft Edge 的扩展资源，可以在国际化指南中了解如何使用 i18n [框架](../internationalization.md)。


> [!NOTE]
> 如果你的扩展不支持多种语言，你可以跳到 Microsoft Store 中的本地化 [名称和说明](#localizing-name-and-description-in-the-microsoft-store)。


## 本地化过程概述

要向广大受众提供扩展，第一步是为多种语言配置[AppxManifest。](#configuring-the-appxmanifest) 在 Microsoft Store 中，这将向用户显示你的扩展支持的语言。 如果你希望扩展的名称在 Windows UI 和 [Microsoft Store](#localizing-extension-resources-for-windows-and-the-microsoft-store)中本地化，AppxManifest 中的某些字段也需要更改。


配置 AppxManifest 后，你需要为指示受支持的语言创建 [JSON](#creating-json-string-resources) 字符串资源。 这需要为每种语言创建一个 .resjson 文件，其中每个文件包含该语言的所有 UI 字符串。


创建支持语言的 .resjson 文件后，将需要创建一个 [.pri 资源文件](#creating-the-resources-file)。 这将通过使用 Windows [10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk)随附的**MakePRI**工具的配置文件创建。 

> [!NOTE]
> 如果你仅下载 Windows 10 SDK 以使用 MakePri.exe 工具，则只能选择"适用于桌面应用的 Windows SDK 签名工具"和"适用于 UWP 托管应用的 Windows SDK"功能，以保持下载更轻松。 The MakePri.exe tool will appear in subfolders of C:\Program Files (x86) \Windows Kits\10\bin\10.0.17713.0.


上传扩展后，最后一步是本地化 [Microsoft Store 中的名称和说明](#localizing-name-and-description-in-the-microsoft-store)。

> [!NOTE]
> 将 Microsoft Edge 扩展提交到 Microsoft Store 目前是一项受限功能。 [如果你的请求是](https://aka.ms/extension-request) Microsoft Store 的一部分，请联系我们，我们将考虑你进行将来的更新。



## 配置 AppXManifest

Microsoft Store 中的扩展的"支持的语言"列表基于其 AppXManifest 值生成。 此列表是使用该元素 `Resource` 指定的。


![设置图像 - 语言应用详细信息](./../../media/language-app-details.png)

若要指定扩展支持的语言列表，可以按以下格式添加元素 (此元素将在 Microsoft Store) 中显示对英语、德语 `Resource` `Resource` 和法语的支持：

```xml
<Resources>
    <Resource Language="en-us"/>
    <Resource Language="de-de"/>
    <Resource Language="fr-fr"/>
</Resources>
```

有关 [Microsoft](https://msdn.microsoft.com/windows/uwp/publish/supported-languages) Store 支持的语言/语言代码的信息，请参阅支持的语言。


为了在 AppxManifest 中指定所有公开可见的元素的本地化字符串，你必须使用格式为 `ms-resource:<resource id>` 的资源标识符。

下面的代码段可创建完整的 AppxManifest。 应从本地化的资源文件中检索以下值：

- Properties\DisplayName
- Properties\Description
- Properties\PublisherDisplayName


```xml
<Properties>
    <DisplayName>ms-resource:DisplayName</DisplayName>
    <Description>ms-resource:Description</Description>
    <Logo>Assets\PackageLogo.png</Logo>
    <PublisherDisplayName>ms-resource:PublisherName</PublisherDisplayName>
</Properties>
```

- Applications\Application\VisualElements\DisplayName
- Applications\Application\VisualElements\Description
- Applications\Application\Extensions\Extension\AppExtension\DisplayName

```xml
<Applications>
    <Application Id="App">
      <uap:VisualElements
        AppListEntry="none"
            DisplayName="ms-resource:DisplayName"
       Square150x150Logo="Assets\Square150x150Logo.png"
       Square44x44Logo="Assets\Square44x44Logo.png"
            Description="ms-resource:Description"
        BackgroundColor="transparent">
      </uap:VisualElements>
      <Extensions>
      <uap3:Extension Category="windows.appExtension">
        <uap3:AppExtension Name="com.microsoft.edge.extension"
            Id="MicrosoftTranslate"
            PublicFolder="Extension"
            DisplayName="ms-resource:DisplayName">
        </uap3:AppExtension>
      </uap3:Extension>
      </Extensions>
    </Application>
  </Applications>
```


## 本地化 Windows 和 Microsoft Store 的扩展资源

现在，AppxManifest 已针对多种语言进行配置，在扩展中本地化 UI 和本地化 Windows 和 Microsoft Store 的扩展之间存在一些关键差异。

虽然 Microsoft Edge 扩展不会在 Microsoft Edge 外部运行，但可以在 Windows 中管理它们。 例如，用户可以在"设置"应用中管理其扩展：


![设置图像](./../../media/settings.png)



在 Windows 的"设置"应用中显示扩展的名称来自 AppXManifest。 如果此值用英语硬编码，则名称的英文版本将在非英语 Windows 设备上显示。 如果扩展的品牌仅为英语，可以保留硬编码。


> [!NOTE]
> 如果要在 Windows 中对 Microsoft Edge 扩展使用本地化名称，请确保本地化名称也可用并保留[](./extensions-in-the-windows-dev-center.md#name-reservation)，然后再在 AppXManifest 文件中进行更改。 如果名称未保留，在将最终程序包上载到 Windows 开发人员中心时，将看到以下错误：</br></br>

![语言错误](./../../media/language-error.png)</br></br>


为 JavaScript 扩展定义的基于 i18n 的本地化基础结构仅适用于 Microsoft Edge 环境。

在 Microsoft Edge 外部的 Windows 和 Microsoft Store 中，唯一受支持的本地化框架基于通用 Windows 平台 (UWP) 框架。

尽管我们支持基于 HTML 的 Windows 应用的基于 JSON 的资源，但 JSON 资源的架构与为 JavaScript 扩展定义的架构不匹配。


以下是基于 HTML 的 [Windows 应用中的主要区别](https://msdn.microsoft.com/library/windows/apps/hh465228.aspx)：
-    资源在 .resjson 文件中而不是 .json 文件中指定。
-    应在 AppXManifest 文件中指定支持区域设置，第一个区域设置是默认区域设置。
-    基于 HTML 的 Windows 应用资源使用以下架构：
    ```json
    {
        "greeting"              : "Hello",
        "_greeting.comment"     : "A welcome greeting.",

        "farewell"              : "Goodbye",
        "_farewell.comment"     : "A goodbye."
    }
    ```
    下划线表示的名称/值对是相应字符串资源的注释。
-    .resjson 文件编译为 .pri 文件，这些文件必须在 AppX 程序包创建过程中包含。


### 创建 JSON 字符串资源
有了已配置的 AppxManifest，并突出显示了 i18n 和 UWP 本地化框架之间的差异，你已准备好创建资源文件。

清单中只有一个资源字符串适用于 Microsoft Edge 扩展包。 该字符串通常本地化为 JavaScript 扩展，并且可以轻松映射到 Windows 期望的 `DisplayName` .resjson 文件。 假定这是唯一要本地化的资源，下面是应创建的示例 .resjson 文件：

```json
{
    "DisplayName"              : "Jigsaw",
    "_DisplayName.comment"     : "Name of extension."
}
```

每个 .resjson 文件的资源 ID 需要与 AppXManifest 中使用的 ID 相匹配。 使用上述示例 .resjson 代码段，相应的 AppXManifest 条目应为：

`DisplayName="ms-resource:DisplayName"`

扩展支持的每种语言都应具有相应的 resources.resjson 文件，并置于以下文件夹结构中：

![语言文件夹结构](./../../media/resources-folder.png)


### 创建资源文件
创建所有 .resjson 文件后，即可使用 PRI (创建程序包) 索引。 此文件存储支持的所有语言的资源。 为此，可以使用 Windows 10 SDK 中包含的 **MakePRI** 工具。


首先，你需要创建配置文件。 这将定义资源的默认限定符和平台。 对于此示例，将默认语言设置为英语 (Windows 10) 美国语言。 为此，请创建priconfig.xml根文件夹]中的以下内容的文件：

![文件夹中的 priconfig](./../../media/priconfig.png)


```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<resources targetOsVersion="10.0.0" majorVersion="1">
    <index root="\" startIndexAt="\">
        <default>
            <qualifier name="Language" value="en-US"/>
            <qualifier name="Contrast" value="standard"/>
            <qualifier name="HomeRegion" value="001"/>
            <qualifier name="TargetSize" value="256"/>
            <qualifier name="LayoutDirection" value="LTR"/>
            <qualifier name="Theme" value="dark"/>
            <qualifier name="AlternateForm" value=""/>
            <qualifier name="DXFeatureLevel" value="DX9"/>
            <qualifier name="Configuration" value=""/>
            <qualifier name="DeviceFamily" value="Universal"/>
            <qualifier name="Custom" value=""/>
        </default>
        <indexer-config type="folder" foldernameAsQualifier="true" filenameAsQualifier="true" qualifierDelimiter="."/>
        <indexer-config type="resw" convertDotsToSlashes="true" initialPath=""/>
        <indexer-config type="resjson" initialPath=""/>
        <indexer-config type="PRI"/>
    </index>
</resources>
```

现在，可以使用配置文件和 MakePRI 工具创建 resources.pri 文件。 对于此示例，项目的根位置为 [根文件夹]。


```cmd
MakePRI new /pr [Root folder] /cf [Root folder]\priconfig.xml /mn [Root folder]\AppxManifest.xml /of [Root folder]\resources.pri /o
```

现在，根文件夹中应该有一个 resources.pri 文件：

![资源文件夹](./../../media/resources.png)


## 在 Microsoft Store 中本地化名称和说明

尝试上传完整的本地化程序包后，Windows 开发人员中心将检测是否支持多种语言，并检查您是否具有对应的本地化名称和说明。 如果缺少任何本地化值，你的提交将一直被阻止，直到你提供这些值。

如果你只对提供 Microsoft Store (而非 Windows) 的本地化名称和说明感兴趣，可以通过保留扩展的所有本地化名称来 [这样做](./extensions-in-the-windows-dev-center.md#name-reservation)。


保留其他本地化名称后，可以创建更新的提交。 在说明部分中，你可以管理 Microsoft Store 一览的其他语言：

![日语应用说明 - 管理](./../../media/manage-description-languages.png)

选择"管理其他语言"后，你将选择想要添加到 Microsoft Store 一览的语言。 新语言将在"说明"部分显示为"其他说明语言"。

可以单击"说明"部分中的单个链接，为每种语言提供本地化名称和说明、发行说明和可视资源。 不会从 AppXManifest 中提取 Microsoft Store 的说明。 需要在 Windows 开发人员中心中手动输入每个本地化说明：

![日语应用说明](./../../media/japanese-app-description.png)

提交本地化说明并发布扩展后，在 Microsoft Store 中访问扩展的本地化页面的任何人都可以看到以下 UI：

![日式 Windows 应用商店](./../../media/japanese-windows-store.png)
 

## AppxManifest 示例

### 非本地化的 AppxManifest
以下示例显示未本地化且仅支持"en-us"区域设置的 AppxManifest。


```xml
<?xml version="1.0" encoding="utf-8"?>
<Package
    xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10"
    xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10"
    xmlns:uap3="http://schemas.microsoft.com/appx/manifest/uap/windows10/3"
    IgnorableNamespaces="uap3">
    <Identity
        Name="63533cct23.Jigsaw"
        Publisher="CN=932A7C4A-0308-4632-9E2F-5931E8F02B7C"
        Version="1.3.0.0" />

    <Properties>
        <DisplayName>Jigsaw</DisplayName>
        <PublisherDisplayName>cct23</PublisherDisplayName>
        <Logo>Assets\icon-50.png</Logo>
    </Properties>

    <Dependencies>
        <TargetDeviceFamily Name="Windows.Desktop" MinVersion="10.0.14393.0" MaxVersionTested="10.0.14800.0" />
    </Dependencies>

    <Resources>
        <Resource Language="en-us" />
    </Resources>

    <Applications>
        <Application Id="App">
            <uap:VisualElements
                AppListEntry="none"
                DisplayName="Jigsaw"
                Square150x150Logo="Assets\icon-150.png"
                Square44x44Logo="Assets\icon-44.png"
                Description="This is a jigsaw puzzle app"
                BackgroundColor="transparent">
            </uap:VisualElements>
            <Extensions>
                <uap3:Extension Category="windows.appExtension">
                    <uap3:AppExtension
                        Name="com.microsoft.edge.extension"
                        Id="EdgeExtension"
                        PublicFolder="Extension"
                        DisplayName="Jigsaw">
                        <uap3:Properties>
                            <Capabilities>
                                <Capability Name="websiteContent"/>
                                <Capability Name="websiteInfo"/>
                                <Capability Name="browserStorage"/>
                            </Capabilities>
                        </uap3:Properties>
                    </uap3:AppExtension>
                </uap3:Extension>
            </Extensions>
        </Application>
    </Applications>
</Package>
```


#### 本地化的 AppxManifest
此 AppxManifest 示例针对除"en-us"之外的其他八个区域设置进行本地化。 请注意 `ms-resource:<resource id>` 以下事件：


```xml
<?xml version="1.0" encoding="utf-8"?>
<Package
    xmlns="http://schemas.microsoft.com/appx/manifest/foundation/windows10"
    xmlns:uap="http://schemas.microsoft.com/appx/manifest/uap/windows10"
    xmlns:uap3="http://schemas.microsoft.com/appx/manifest/uap/windows10/3"
    IgnorableNamespaces="uap3">
    <Identity
        Name="63533cct23.Jigsaw"
        Publisher="CN=932A7C4A-0308-4632-9E2F-5931E8F02B7C"
        Version="1.3.0.0" />

    <Properties>
        <DisplayName>ms-resource:DisplayName</DisplayName>
        <PublisherDisplayName>cct23</PublisherDisplayName>
        <Logo>Assets\icon-50.png</Logo>
    </Properties>

    <Dependencies>
        <TargetDeviceFamily Name="Windows.Desktop" MinVersion="10.0.14393.0" MaxVersionTested="10.0.14800.0" />
    </Dependencies>

    <Resources>
        <Resource Language="en-us" />
        <Resource Language="de" />
        <Resource Language="en" />
        <Resource Language="en-gb" />
        <Resource Language="es" />
        <Resource Language="fr" />
        <Resource Language="it" />
        <Resource Language="ja" />
        <Resource Language="zh-cn" />
    </Resources>

    <Applications>
        <Application Id="App">
            <uap:VisualElements
                AppListEntry="none"
                DisplayName="ms-resource:DisplayName"
                Square150x150Logo="Assets\icon-150.png"
                Square44x44Logo="Assets\icon-44.png"
                Description="ms-resource:Description"
                BackgroundColor="transparent">
            </uap:VisualElements>
            <Extensions>
                <uap3:Extension Category="windows.appExtension">
                    <uap3:AppExtension
                        Name="com.microsoft.edge.extension"
                        Id="EdgeExtension"
                        PublicFolder="Extension"
                        DisplayName="ms-resource:DisplayName">
                        <uap3:Properties>
                            <Capabilities>
                                <Capability Name="websiteContent"/>
                                <Capability Name="websiteInfo"/>
                                <Capability Name="browserStorage"/>
                            </Capabilities>
                        </uap3:Properties>
                    </uap3:AppExtension>
                </uap3:Extension>
            </Extensions>
        </Application>
    </Applications>
</Package>
```

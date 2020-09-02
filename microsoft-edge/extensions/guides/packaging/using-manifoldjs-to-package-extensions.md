---
ms.assetid: c4397525-b978-4dc2-89bc-2198b3069742
description: 了解如何使用 ManifoldJS 的 "打开源 Node.js" 工具将您的 Microsoft Edge 扩展打包在一个贴中。
title: 使用 ManifoldJS 打包扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/20/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.custom: seodec18
ms.openlocfilehash: 83aa57ae0e4ae302b1360be50e5158782b6fbb76
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986204"
---
# 使用 ManifoldJS 创建扩展 AppX 程序包  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

ManifoldJS 是一个开放的源 Node.js 工具，可让你快速轻松地创建可用于提交到 Microsoft Store 的程序包。  

如果你在扩展中使用本机消息，则应跳过以下文章并转到 [Microsoft Edge 中的本机消息](../native-messaging.md#creating-an-extension-with-native-messaging) ，以进行打包说明。  

在开始之前，您仍需要阅读以下文章。  

*   [Windows 开发人员中心扩展](./extensions-in-the-windows-dev-center.md)  
*   [本地化扩展包](./localizing-extension-packages.md)  

> [!NOTE]
> 将 Microsoft Edge 扩展提交到 Microsoft Store 目前是受限制的功能。  创建、打包和测试扩展后，请提交我们的 [扩展提交表单](https://developer.microsoft.com/microsoft-edge/extensions/requests)上的申请。  

## 安装 Node.js 和 ManifoldJS  

您需要做的第一件工作是安装 [Node.js LTS](https://nodejs.org/en/download)。  
一旦拥有节点，从命令行 (首选 PowerShell) 中，运行以下命令以安装 ManifoldJS。  

```shell
npm install -g manifoldjs
```  

若要验证是否已正确安装 ManifoldJS，请 `manifoldjs` 从命令行运行。 如果 ManifoldJS 无法识别，请将 `%APPDATA%\npm` 其添加到路径变量。  

## 用 ManifoldJS 打包  

若要启动打包过程，你需要打开一个命令行，并将目录更改为打包扩展的目标文件夹。  

例如：

```shell
cd C:\manifoldJSTest
```  

> [!NOTE]
> `manifoldjs`命令在当前目录中输出并覆盖内容。  

现在你位于目标文件夹中，然后运行以下命令。  

```shell
manifoldjs -l debug -p edgeextension -f edgeextension -m path\to\manifest.json
```  

该 `mainifoldjs` 命令可以分解为以下部分。  

:::row:::
   :::column span="1":::
      `-l debug`  
   :::column-end:::
   :::column span="2":::
      将日志级别更改为 `debug` ，以获得完整打印。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-p edgeextension`  
   :::column-end:::
   :::column span="2":::
      将运行转换的唯一平台设置为 `edgeextension` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-f edgeextension`  
   :::column-end:::
   :::column span="2":::
      告诉程序清单格式是一种 `edgeextension` 格式，而不是在验证失败时不在意。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-m \path\to\manifest.json`  
   :::column-end:::
   :::column span="2":::
      要转换的扩展清单的路径。  
   :::column-end:::
:::row-end:::  

在 ManifoldJS 完成运行后，你将拥有一个具有下列内容的文件夹。  

```text
┌ My Extension
└┬ edgeextension
 ├- generationInfo.json
 └┬ manifest
  ├- appxmanifest.xml
  ├┬ Assets
  |├- Square150x150Logo.png
  |├- Square44x44Logo.png
  |└- StoreLogo.png    
  └┬ Extension
   ├- manifest.json
   └- popup.html
```  
<!-- 
    My Extension
        edgeextension
            generationInfo.json
            manifest
                   appxmanifest.xml
                Assets
                    Square150x150Logo.png
                    Square44x44Logo.png
                    StoreLogo.png    
                Extension
                    manifest.json
                    popup.html
                    ...
                ...
-->  

generationInfo.json file 是通过运行 ManifoldJS 生成的日志，不会包含在扩展程序包中。 `manifest`将仅打包文件夹的内容。 在清单文件夹中，资源文件夹包含将在 Windows 和 Microsoft Store UI 中使用的图像，而扩展文件夹中包含您的扩展的内容。  

既然你拥有正确的文件，你将需要在文件夹中编辑生成的 Package.appxmanifest 文件 `manifest` 。 如果扩展名的 manifest.js文件具有 "name" 字段的国际化字符串，则在 ManifoldJS 运行后，最上层文件夹的名称将没有下划线并包含 "MSG"。

例如，具有以下字段的文件上的 manifest.js`"name"` 。  

```shell
"name" : "__MSG_appName__"
```  

将拥有一个属于的清单文件夹 `\<CURRENT DIRECTORY>\MSGappName\edgeextension\manifest` 。  

在 Package.appxmanifest 文件中，你将需要：  

 *   按 [此处](./creating-and-testing-extension-packages.md#app-identity-template-values)所述替换所需的标识字段和 PublisherDisplayName 字段。 请注意，如果仅出于测试目的或企业分发进行打包，则可以使用占位符值，而不是注册 Windows 开发人员中心帐户。  
 *   将 "资源" 文件夹中的占位符图标替换为具有相同大小 (150x150、50x50、44x44) 和名称的扩展名的图标。 有关这些图标的使用位置的信息，请参阅 [设计](./../design.md#icons-for-packaging) 指南。  
 *   如果您的扩展已本地化，请遵循整个 " [本地化 Microsoft Edge 扩展](./localizing-extension-packages.md) 指南"。 如果它未本地化，请仅阅读 [Microsoft Store 部分中的本地化名称和说明](./localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) 。  

`appxmanifest.xml`文件被排序后，运行以下命令创建程序包。  

```shell
manifoldjs -l debug -p edgeextension package <EXTENSION NAME>\edgeextension\manifest\
```  

您的程序包现在将位于 edgeextension 文件夹中的 **程序包** 文件夹中。 有关如何旁加载新程序包的详细信息，请参阅创建和测试扩展程序包的 [测试](./creating-and-testing-extension-packages.md#testing-an-appx-package) 部分。  

一旦您的软件包经过测试，就可以在我们的 [扩展提交表单](https://aka.ms/extension-request) 上提交请求，以便将其提交到 Microsoft Store。  

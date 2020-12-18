---
ms.assetid: c4397525-b978-4dc2-89bc-2198b3069742
description: 了解如何使用 ManifoldJS（一款开源工具）Node.js Microsoft Edge 扩展。
title: 使用 ManifoldJS 打包扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 151a8b2ababb25e0964a6fbc2696b5fdc059d084
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232593"
---
# 使用 ManifoldJS 创建扩展 AppX 程序包  

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]  

ManifoldJS 是一个开源Node.js工具，可让你快速轻松地创建一个程序包，然后可用于提交到 Microsoft Store。  

如果在扩展中使用本机消息传递，应跳过以下文章并转到 [Microsoft Edge](../native-messaging.md#creating-an-extension-with-native-messaging) 中的本机消息传递，以打包指令。  

在开始使用之前，你仍然需要阅读以下文章。  

*   [Windows 开发人员中心扩展](./extensions-in-the-windows-dev-center.md)  
*   [本地化扩展包](./localizing-extension-packages.md)  

> [!NOTE]
> 将 Microsoft Edge 扩展提交到 Microsoft Store 目前是一项受限功能。  创建、打包和测试扩展后，请在扩展提交表单上 [提交请求](https://developer.microsoft.com/microsoft-edge/extensions/requests)。  

## 安装 Node.js 和 ManifoldJS  

需要执行的第一个操作是安装[LTSNode.js LTS。](https://nodejs.org/en/download)  
拥有 Node 后，从命令行 (最好是 PowerShell) ，运行以下命令以安装 ManifoldJS。  

```shell
npm install -g manifoldjs
```  

若要验证是否正确安装了 ManifoldJS，请 `manifoldjs` 从命令行运行。 如果 ManifoldJS 无法识别，请 `%APPDATA%\npm` 添加到 PATH 变量中。  

## 使用 ManifoldJS 打包  

若要开始打包过程，需要打开命令行，将目录更改为将成为打包扩展目标的文件夹。  

例如：

```shell
cd C:\manifoldJSTest
```  

> [!NOTE]
> `manifoldjs`该命令在当前目录中输出并覆盖内容。  

现在，你已在你的目标文件夹中，请运行以下命令。  

```shell
manifoldjs -l debug -p edgeextension -f edgeextension -m path\to\manifest.json
```  

该命令 `mainifoldjs` 可细分为以下部分。  

:::row:::
   :::column span="1":::
      `-l debug`  
   :::column-end:::
   :::column span="2":::
      更改日志级别 `debug` 以完全打印。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-p edgeextension`  
   :::column-end:::
   :::column span="2":::
      将运行转换的唯一平台设置到 `edgeextension` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `-f edgeextension`  
   :::column-end:::
   :::column span="2":::
      告知程序清单的格式是一种格式，而不要关心 `edgeextension` 其是否未通过验证。  
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

ManifoldJS 运行完成后，你将有一个包含以下内容的文件夹。  

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

文件generationInfo.js是运行 ManifoldJS 生成的日志，不会包含在扩展包中。 仅打包文件夹 `manifest` 的内容。 在清单文件夹中，Assets 文件夹包含将在 Windows 和 Microsoft Store UI 中使用的图像，而扩展文件夹包含扩展的内容。  

现在你拥有正确的文件，你将需要编辑文件夹中生成的 AppXManifest `manifest` 文件。 如果扩展名manifest.js文件上具有"name"字段的国际化字符串，则一旦 ManifoldJS 运行，最顶层文件夹的名称将没有下划线，并包括"MSG"。

例如，在manifest.js字段的文件上创建 `"name"` 一个字段。  

```shell
"name" : "__MSG_appName__"
```  

将具有一个清单文件夹，该文件夹在 `\<CURRENT DIRECTORY>\MSGappName\edgeextension\manifest` 。  

在 AppXManifest 文件中，将需要：  

 *   替换所需的 Identity 字段和 PublisherDisplayName 字段，如此处 [所述](./creating-and-testing-extension-packages.md#app-identity-template-values)。 请注意，如果你仅打包用于测试或企业分发，可以使用占位符值，而不是注册 Windows 开发人员中心帐户。  
 *   将"资源"文件夹中的占位符图标替换为扩展的图标，其大小 (150x150、50x50、44x44) 和名称。 有关 [使用这些](./../design.md#icons-for-packaging) 图标的信息，请参阅设计指南。  
 *   如果扩展已本地化，请按照整个 [本地化 Microsoft Edge 扩展指南](./localizing-extension-packages.md) 操作。 如果未本地化，则只读取 [Microsoft Store](./localizing-extension-packages.md#localizing-name-and-description-in-the-microsoft-store) 部分中的本地化名称和说明。  

整理 `appxmanifest.xml` 文件后，运行以下命令以创建程序包。  

```shell
manifoldjs -l debug -p edgeextension package <EXTENSION NAME>\edgeextension\manifest\
```  

你的程序包现在将位于 edgeextension 文件夹内的程序包文件夹中。 **** 若要详细了解如何旁加载新程序包，请参阅"创建和测试扩展[](./creating-and-testing-extension-packages.md#testing-an-appx-package)包的测试"部分。  

测试程序包后，请随时在我们的扩展提交表单上提交请求，以考虑将其[](https://aka.ms/extension-request)发布到 Microsoft Store。  

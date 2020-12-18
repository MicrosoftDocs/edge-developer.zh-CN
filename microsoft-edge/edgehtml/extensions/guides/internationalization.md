---
description: 使你的扩展可供不同的语言访问，并借助国际化指南测试语言字符串。
title: 扩展 - 国际化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: bbbc847ebd2103cba2eca8a791009b4e72f93a6f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232628"
---
# <span data-ttu-id="8f656-104">国际化</span><span class="sxs-lookup"><span data-stu-id="8f656-104">Internationalization</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="8f656-105">为了使你的扩展可供各种不同人员访问，请务必考虑其他国家/地区进行开发。</span><span class="sxs-lookup"><span data-stu-id="8f656-105">In order to make your extension accessible to a variety of different people, it is important to develop with other countries in mind.</span></span> <span data-ttu-id="8f656-106">Microsoft Edge 扩展允许你向扩展中添加不同的语言字符串，以便可以轻松地更改其语言。</span><span class="sxs-lookup"><span data-stu-id="8f656-106">Microsoft Edge extensions allows you to add different language strings to your extensions so that their language can easily be changed.</span></span>

<span data-ttu-id="8f656-107">有关使扩展国际化的信息，请查看 MDN 的 [国际化指南](https://developer.mozilla.org/Add-ons/WebExtensions/Internationalization)。</span><span class="sxs-lookup"><span data-stu-id="8f656-107">For more information on internationalizing your extension, check out MDN's [Internationalization guide](https://developer.mozilla.org/Add-ons/WebExtensions/Internationalization).</span></span>


## <span data-ttu-id="8f656-108">测试语言</span><span class="sxs-lookup"><span data-stu-id="8f656-108">Testing languages</span></span>

<span data-ttu-id="8f656-109">若要测试语言字符串，首先需要将 Windows 显示语言设置为要测试的语言。</span><span class="sxs-lookup"><span data-stu-id="8f656-109">To test your language strings, you first need to set the Windows display language to the language that you want to test for.</span></span>

<span data-ttu-id="8f656-110">按照以下步骤更改 Windows 显示语言：</span><span class="sxs-lookup"><span data-stu-id="8f656-110">Follow the steps below to change the Windows display language:</span></span>

1. <span data-ttu-id="8f656-111">打开"设置"应用。</span><span class="sxs-lookup"><span data-stu-id="8f656-111">Open the Settings app.</span></span>

   ![设置应用程序](./../media/loc-settings.png)
2. <span data-ttu-id="8f656-113">选择"时间&语言"。</span><span class="sxs-lookup"><span data-stu-id="8f656-113">Select "Time & language".</span></span>
3. <span data-ttu-id="8f656-114">选择"&语言"。</span><span class="sxs-lookup"><span data-stu-id="8f656-114">Select "Region & language".</span></span>
4. <span data-ttu-id="8f656-115">选择"+ 添加语言"，将语言添加到可能的语言列表中。</span><span class="sxs-lookup"><span data-stu-id="8f656-115">Select "+ Add a language" to add the language to the list of possible languages.</span></span>
5. <span data-ttu-id="8f656-116">从"语言"列表中选择要测试的语言。</span><span class="sxs-lookup"><span data-stu-id="8f656-116">Choose the language from the "Languages" list that you want to test.</span></span>
6. <span data-ttu-id="8f656-117">选择"设置为默认值"按钮 (可能需要重启电脑) 。</span><span class="sxs-lookup"><span data-stu-id="8f656-117">Select the "Set as default" button (you may need to restart your PC).</span></span>
7. <span data-ttu-id="8f656-118">打开 Microsoft Edge 并验证为区域设置定义的字符串是否按预期显示。</span><span class="sxs-lookup"><span data-stu-id="8f656-118">Open Microsoft Edge and verify that the strings defined for the locale appear as expected.</span></span>

<span data-ttu-id="8f656-119">通过使用 [NavigatorLanguage.language](https://developer.mozilla.org/docs/Web/API/NavigatorLanguage/language) 属性，可以验证 Microsoft Edge 确定为 Windows 显示语言的语言是否正确。</span><span class="sxs-lookup"><span data-stu-id="8f656-119">By using the [NavigatorLanguage.language](https://developer.mozilla.org/docs/Web/API/NavigatorLanguage/language) property, you can verify that the language Microsoft Edge has determined to be the Windows display language is correct.</span></span>

<span data-ttu-id="8f656-120">单击下面的 CodePen 中的按钮，查看浏览器的显示语言。</span><span class="sxs-lookup"><span data-stu-id="8f656-120">Click the button in the CodePen below to see the display language of your browser.</span></span>

<iframe height='300' scrolling='no' title='<span data-ttu-id="8f656-121">获取区域设置</span><span class="sxs-lookup"><span data-stu-id="8f656-121">Get locale</span></span>' src='//codepen.io/MSEdgeDev/embed/VaRWwR/?height=300&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="8f656-122">请参阅在 CodePen 上通过 <a href='https://codepen.io/MSEdgeDev/pen/VaRWwR/'> </a> MSEdgeDev <a href='http://codepen.io/MSEdgeDev'> (@MSEdgeDev) </a> <a href='http://codepen.io'> 获取区域设置 </a> 。</span><span class="sxs-lookup"><span data-stu-id="8f656-122">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/VaRWwR/'>Get locale</a>by MSEdgeDev (<a href='http://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='http://codepen.io'>CodePen</a>.</span></span>
</iframe>

---
description: 使您的扩展可用于不同语言，并通过国际化指南测试语言字符串。
title: 扩展-国际化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: d1f553d0e3e39192e68665fe6720daa811777c0b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563266"
---
# <span data-ttu-id="542e2-104">国际化</span><span class="sxs-lookup"><span data-stu-id="542e2-104">Internationalization</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="542e2-105">为了使您的扩展可供各种不同的人员使用，请务必与其他国家/地区的人员进行开发。</span><span class="sxs-lookup"><span data-stu-id="542e2-105">In order to make your extension accessible to a variety of different people, it is important to develop with other countries in mind.</span></span> <span data-ttu-id="542e2-106">Microsoft Edge 扩展允许你将不同的语言字符串添加到你的扩展名，以便可以轻松更改其语言。</span><span class="sxs-lookup"><span data-stu-id="542e2-106">Microsoft Edge extensions allows you to add different language strings to your extensions so that their language can easily be changed.</span></span>

<span data-ttu-id="542e2-107">有关对扩展进行国际化的详细信息，请查看 MDN 的[国际化指南](https://developer.mozilla.org/Add-ons/WebExtensions/Internationalization)。</span><span class="sxs-lookup"><span data-stu-id="542e2-107">For more information on internationalizing your extension, check out MDN's [Internationalization guide](https://developer.mozilla.org/Add-ons/WebExtensions/Internationalization).</span></span>


## <span data-ttu-id="542e2-108">测试语言</span><span class="sxs-lookup"><span data-stu-id="542e2-108">Testing languages</span></span>

<span data-ttu-id="542e2-109">若要测试语言字符串，首先需要将 Windows 显示语言设置为要测试的语言。</span><span class="sxs-lookup"><span data-stu-id="542e2-109">To test your language strings, you first need to set the Windows display language to the language that you want to test for.</span></span>

<span data-ttu-id="542e2-110">请按照下列步骤更改 Windows 显示语言：</span><span class="sxs-lookup"><span data-stu-id="542e2-110">Follow the steps below to change the Windows display language:</span></span>

1. <span data-ttu-id="542e2-111">打开 "设置" 应用。</span><span class="sxs-lookup"><span data-stu-id="542e2-111">Open the Settings app.</span></span>

   ![设置应用程序](./../media/loc-settings.png)
2. <span data-ttu-id="542e2-113">选择 "时间 & 语言"。</span><span class="sxs-lookup"><span data-stu-id="542e2-113">Select "Time & language".</span></span>
3. <span data-ttu-id="542e2-114">选择 "区域 & 语言"。</span><span class="sxs-lookup"><span data-stu-id="542e2-114">Select "Region & language".</span></span>
4. <span data-ttu-id="542e2-115">选择 "+ 添加语言" 将语言添加到可能语言的列表。</span><span class="sxs-lookup"><span data-stu-id="542e2-115">Select "+ Add a language" to add the language to the list of possible languages.</span></span>
5. <span data-ttu-id="542e2-116">从 "语言" 列表中选择要测试的语言。</span><span class="sxs-lookup"><span data-stu-id="542e2-116">Choose the language from the "Languages" list that you want to test.</span></span>
6. <span data-ttu-id="542e2-117">选择 "设为默认值" 按钮（可能需要重启电脑）。</span><span class="sxs-lookup"><span data-stu-id="542e2-117">Select the "Set as default" button (you may need to restart your PC).</span></span>
7. <span data-ttu-id="542e2-118">打开 Microsoft Edge 并验证为区域设置定义的字符串是否按预期方式显示。</span><span class="sxs-lookup"><span data-stu-id="542e2-118">Open Microsoft Edge and verify that the strings defined for the locale appear as expected.</span></span>

<span data-ttu-id="542e2-119">通过使用[NavigatorLanguage](https://developer.mozilla.org/docs/Web/API/NavigatorLanguage/language)属性，你可以验证 Microsoft Edge 是否已确定为 Windows 显示语言的语言是正确的。</span><span class="sxs-lookup"><span data-stu-id="542e2-119">By using the [NavigatorLanguage.language](https://developer.mozilla.org/docs/Web/API/NavigatorLanguage/language) property, you can verify that the language Microsoft Edge has determined to be the Windows display language is correct.</span></span>

<span data-ttu-id="542e2-120">单击以下 CodePen 中的按钮以查看浏览器的显示语言。</span><span class="sxs-lookup"><span data-stu-id="542e2-120">Click the button in the CodePen below to see the display language of your browser.</span></span>

<iframe height='300' scrolling='no' title='<span data-ttu-id="542e2-121">获取区域设置</span><span class="sxs-lookup"><span data-stu-id="542e2-121">Get locale</span></span>' src='//codepen.io/MSEdgeDev/embed/VaRWwR/?height=300&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="542e2-122">请参阅 <a href='https://codepen.io/MSEdgeDev/pen/VaRWwR/'> </a> CodePen 上的 "通过 MSEdgeDev （ <a href='http://codepen.io/MSEdgeDev'> @MSEdgeDev）获取区域设置" </a> <a href='http://codepen.io'> </a> 。</span><span class="sxs-lookup"><span data-stu-id="542e2-122">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/VaRWwR/'>Get locale</a>by MSEdgeDev (<a href='http://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='http://codepen.io'>CodePen</a>.</span></span>
</iframe>

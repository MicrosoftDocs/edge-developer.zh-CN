---
description: Make your extension accessible for different languages and test your language strings with the internationalization guide.
title: Extensions - Internationalization
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, web development, html, css, javascript, developer
ms.openlocfilehash: d1f553d0e3e39192e68665fe6720daa811777c0b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563266"
---
# <span data-ttu-id="20931-104">Internationalization</span><span class="sxs-lookup"><span data-stu-id="20931-104">Internationalization</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="20931-105">In order to make your extension accessible to a variety of different people, it is important to develop with other countries in mind.</span><span class="sxs-lookup"><span data-stu-id="20931-105">In order to make your extension accessible to a variety of different people, it is important to develop with other countries in mind.</span></span> <span data-ttu-id="20931-106">Microsoft Edge extensions allows you to add different language strings to your extensions so that their language can easily be changed.</span><span class="sxs-lookup"><span data-stu-id="20931-106">Microsoft Edge extensions allows you to add different language strings to your extensions so that their language can easily be changed.</span></span>

<span data-ttu-id="20931-107">For more information on internationalizing your extension, check out MDN's [Internationalization guide](https://developer.mozilla.org/Add-ons/WebExtensions/Internationalization).</span><span class="sxs-lookup"><span data-stu-id="20931-107">For more information on internationalizing your extension, check out MDN's [Internationalization guide](https://developer.mozilla.org/Add-ons/WebExtensions/Internationalization).</span></span>


## <span data-ttu-id="20931-108">Testing languages</span><span class="sxs-lookup"><span data-stu-id="20931-108">Testing languages</span></span>

<span data-ttu-id="20931-109">To test your language strings, you first need to set the Windows display language to the language that you want to test for.</span><span class="sxs-lookup"><span data-stu-id="20931-109">To test your language strings, you first need to set the Windows display language to the language that you want to test for.</span></span>

<span data-ttu-id="20931-110">Follow the steps below to change the Windows display language:</span><span class="sxs-lookup"><span data-stu-id="20931-110">Follow the steps below to change the Windows display language:</span></span>

1. <span data-ttu-id="20931-111">Open the Settings app.</span><span class="sxs-lookup"><span data-stu-id="20931-111">Open the Settings app.</span></span>

   ![settings application](./../media/loc-settings.png)
2. <span data-ttu-id="20931-113">Select "Time & language".</span><span class="sxs-lookup"><span data-stu-id="20931-113">Select "Time & language".</span></span>
3. <span data-ttu-id="20931-114">Select "Region & language".</span><span class="sxs-lookup"><span data-stu-id="20931-114">Select "Region & language".</span></span>
4. <span data-ttu-id="20931-115">Select "+ Add a language" to add the language to the list of possible languages.</span><span class="sxs-lookup"><span data-stu-id="20931-115">Select "+ Add a language" to add the language to the list of possible languages.</span></span>
5. <span data-ttu-id="20931-116">Choose the language from the "Languages" list that you want to test.</span><span class="sxs-lookup"><span data-stu-id="20931-116">Choose the language from the "Languages" list that you want to test.</span></span>
6. <span data-ttu-id="20931-117">Select the "Set as default" button (you may need to restart your PC).</span><span class="sxs-lookup"><span data-stu-id="20931-117">Select the "Set as default" button (you may need to restart your PC).</span></span>
7. <span data-ttu-id="20931-118">Open Microsoft Edge and verify that the strings defined for the locale appear as expected.</span><span class="sxs-lookup"><span data-stu-id="20931-118">Open Microsoft Edge and verify that the strings defined for the locale appear as expected.</span></span>

<span data-ttu-id="20931-119">By using the [NavigatorLanguage.language](https://developer.mozilla.org/docs/Web/API/NavigatorLanguage/language) property, you can verify that the language Microsoft Edge has determined to be the Windows display language is correct.</span><span class="sxs-lookup"><span data-stu-id="20931-119">By using the [NavigatorLanguage.language](https://developer.mozilla.org/docs/Web/API/NavigatorLanguage/language) property, you can verify that the language Microsoft Edge has determined to be the Windows display language is correct.</span></span>

<span data-ttu-id="20931-120">Click the button in the CodePen below to see the display language of your browser.</span><span class="sxs-lookup"><span data-stu-id="20931-120">Click the button in the CodePen below to see the display language of your browser.</span></span>

<iframe height='300' scrolling='no' title='<span data-ttu-id="20931-121">Get locale</span><span class="sxs-lookup"><span data-stu-id="20931-121">Get locale</span></span>' src='//codepen.io/MSEdgeDev/embed/VaRWwR/?height=300&theme-id=23761&default-tab=result&embed-version=2&editable=true' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="20931-122">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/VaRWwR/'>Get locale</a>by MSEdgeDev (<a href='http://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='http://codepen.io'>CodePen</a>.</span><span class="sxs-lookup"><span data-stu-id="20931-122">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/VaRWwR/'>Get locale</a>by MSEdgeDev (<a href='http://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='http://codepen.io'>CodePen</a>.</span></span>
</iframe>

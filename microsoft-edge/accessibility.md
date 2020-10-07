---
ms.assetid: 1e5c42a7-4604-46ac-ad7b-a65390e5b36a
description: Learn how to build, design, and test accessible websites within Microsoft Edge.
title: Accessibility
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: accessibility, accessibility for developers, accessible websites, edge, web development, ARIA, developer, UIA, UI Automation
ms.openlocfilehash: 6ad95e9c250aa6a4a61ca09470cea86efd715427
ms.sourcegitcommit: 9169d784485e3cb0b1987a8f395c4bb688bd9b2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "10583103"
---
# Accessibility  

> "\[T\]he impact of disability is radically changed on the Web because the Web removes barriers to communication and interaction that many people face in the physical world." [(Accessibility | W3C)][W3CAccessibility]  

The [World Health Organization][WHODisabilities] defines disability as "a mismatch in interaction between the features of a person's body and the features of the environment in which they live".  Disabilities range from situational disabilities, like limited mobility while holding a baby or bright sunlight on a phone, to other physical, auditory, visual, or age-related impairments.  

Designing websites and other technologies for inclusion creates an experience enjoyable by every person.  Inclusive design and web accessibility empowers and assists everyone to use the web.  

Here are some best practices, code samples, and further resources for you to learn more about [Designing][AccessibilityDesign], [Building][AccessibilityBuild], and [Testing][AccessibilityTest] accessible websites in Microsoft Edge.  

## Accessibility in Microsoft Edge  

In Microsoft Edge, we introduced modern [UI Automation API][WindowsWin32AutoEntryui] \(UIA API\).  The change to UIA was a major investment in browser accessibility, and it lays the foundation for a more inclusive web experience for users who depend on assistive technology in Windows 10.  Users also benefit from the evergreen nature of the Chromium engine.  

The accessibility system in Microsoft Edge inherently supports modern web standards including ARIA, HTML5, and CSS3.  The following diagram of the simplified browser pipeline follows webpage content into an accessible presentation layer.  

:::image type="complex" source="./media/accessibilityarchitecture.png" alt-text="Content transformed to the engine model is projected into visual and accessibility views that are presented either as visual or accessible presentation&quot;:::
   Figure 1.  Content transformed to the engine model is projected into visual and accessibility views that are presented either as visual or accessible presentation
:::image-end:::

<!--![Figure 1.  Content transformed to the engine model is projected into visual and accessibility views that are presented either as visual or accessible presentation][ImageAccessibilityArchitecture]  -->  

The Microsoft Edge team works with the W3C and other browser vendors on an ongoing basis to ensure that new web platform features have sufficient built-in accessibility.  

For information on which new HTML5 features are accessibly supported by Microsoft Edge, visit [HTML5Accessibility][HTML5Accessibility].  

## Resources  

#### Microsoft Windows UI Automation Blog  

The [Microsoft Windows UI Automation blog][ArchiveBlogsWinuiautomation] covers topics related to the Windows Automation API.  

#### Web Accessibility Initiative (WAI)  

The [Web Accessibility Initiative (WAI)][W3CWaiHome] provided bt the W3C is an effort to help improve the accessibility of the web.  The site provides a variety of resources for [Getting Started with Web Accessibility][W3CWaiGettingstartedOverview], [Designing for Inclusion][W3CWaiFundamentals], [tutorials and presentations][W3CWaiTeachAdvocate], and more.  


<!-- image links -->  

<!--[ImageAccessibilityArchitecture]: ./media/accessibilityarchitecture.png &quot;Figure 1: Content transformed to the engine model is projected into visual and accessibility views that are presented either as visual or accessible presentation&quot;  -->  

<!-- links -->  

[AccessibilityBuild]: ./accessibility/build.md &quot;Building Accessible Websites&quot;  
[AccessibilityDesign]: ./accessibility/design.md &quot;Designing Accessible Websites&quot;  
[AccessibilityTest]: ./accessibility/test.md &quot;Accessibility Testing&quot;  

[WindowsWin32AutoEntryui]: /windows/win32/winauto/entry-uiauto-win32 &quot;UI Automation&quot;  

[ArchiveBlogsWinuiautomation]: /archive/blogs/winuiautomation/ &quot;Microsoft Windows UI Automation Blog&quot;  

[HTML5Accessibility]: https://html5accessibility.com &quot;HTML5 Accessibility&quot;  

[W3CAccessibility]: https://w3.org/standards/webdesign/accessibility &quot;Accessibility | W3C&quot;  
[W3CWaiFundamentals]: https://w3.org/wai/fundamentals/accessibility-intro &quot;Introduction to Web Accessibility | Web Accessibility Initiative (WAI) | W3C&quot;  
[W3CWaiGettingstartedOverview]: https://w3.org/wai/gettingstarted/Overview &quot;Getting Started: Making a Web Site Accessible | Web Accessibility Initiative (WAI) | W3C&quot;  
[W3CWaiHome]: https://w3.org/wai &quot;Web Accessibility Initiative (WAI) | W3C&quot;  
[W3CWaiTeachAdvocate]: https://w3.org/wai/teach-advocate &quot;Teach and Advocate Overview | Web Accessibility Initiative (WAI) | W3C&quot;  

[WHODisabilities]: https://who.int/topics/disabilities &quot;Disabilities | WHO"  


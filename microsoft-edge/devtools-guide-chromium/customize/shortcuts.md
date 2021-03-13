---
description: 将 DevTools 中的键盘快捷方式与代码Visual Studio匹配
title: 在 Microsoft Edge DevTools 中自定义键盘快捷方式
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/10/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， 开发工具， 自定义， 快捷方式， 键盘， visual studio 代码
ms.openlocfilehash: ec48b075ff6741e0905e963993e7ca4e5dabe714
ms.sourcegitcommit: e29cd1c393fc1f433dba8c3d8f260b425ade63a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408283"
---
# <a name="customize-keyboard-shortcuts-in-the-microsoft-edge-devtools"></a>在 Microsoft Edge DevTools 中自定义键盘快捷方式  

" **设置"** 中的" [快捷方式"][DevToolsCustomizeSettings] 页提供了 [DevTools][DevToolsShortcuts] 中的键盘快捷方式列表，以及自定义 [快捷方式的功能](#match-keyboard-shortcuts-in-the-devtools-to-microsoft-visual-studio-code)。  若要导航到 **"快捷方式"** 页，请完成以下步骤。  

1.  [打开 DevTools][DevtoolsOpenMain]。  
1.  打开 [设置][DevToolsCustomizeSettings]。
    *   选择 `Shift` + `?` 。  
1.  导航到 **"快捷方式"** 页。  
    
    :::image type="complex" source="../media/settings-shortcuts.msft.png" alt-text=""设置"中的"快捷方式"页" lightbox="../media/settings-shortcuts.msft.png":::
       " **设置"中的** "快捷方式 **"页**  
    :::image-end:::  
    
## <a name="match-keyboard-shortcuts-in-the-devtools-to-microsoft-visual-studio-code"></a>将 DevTools 中的键盘快捷方式与 Microsoft Visual Studio代码匹配  

若要匹配 Microsoft Edge DevTools 中的键盘快捷方式以执行 Visual Studio [Code][VisualStudioCode]中的等效操作，请完成以下步骤。  

1.  导航到 [快捷方式](#customize-keyboard-shortcuts-in-the-microsoft-edge-devtools) 网页。  
1.  Choose the **Match shortcuts from preset** dropdown and change **DevTools (Default) ** to Visual Studio **Code**.  
    
    :::image type="complex" source="../media/match-keyboard-shortcuts-visual-studio-code.msft.png" alt-text="将 DevTools 中的键盘快捷方式与代码Visual Studio匹配" lightbox="../media/match-keyboard-shortcuts-visual-studio-code.msft.png":::
       将 DevTools 中的键盘快捷方式与代码Visual Studio匹配  
    :::image-end:::  
    
例如，若要暂停或继续运行代码 [Visual Studio，][VisualStudioCodeShortcutsKeyboardWindows]请选择 `F5` 。  使用 **DevTools (默认 **) 预设，若要暂停或继续运行脚本，请选择 `F8` 。  当你将预设更改为 **"Visual Studio代码**"时，你现在也可以选择 ，就像在"代码"Visual Studio `F5` [一样][VisualStudioCodeShortcutsKeyboardWindows]。  

## <a name="edit-keyboard-shortcuts-for-any-action-in-the-devtools"></a>编辑 DevTools 中任何操作键盘快捷方式  

若要为 DevTools 中的特定操作自定义键盘快捷方式，请完成以下步骤。  

1.  导航到 [快捷方式](#customize-keyboard-shortcuts-in-the-microsoft-edge-devtools) 网页。  
1.  选择要自定义的操作。  例如，在调试 **器部分中** ，查找并选择 **暂停脚本执行** 操作。  
1.  选择" **编辑** \ (![ EditKeyboardShortcut ](../media/edit-keyboard-shortcut-icon.msft.png) \) "图标。  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png" alt-text="从"设置"中的"快捷方式"页选择要自定义的操作" lightbox="../media/experiments-custom-keyboard-shortcuts-select-action.msft.png":::
       从"设置"中的"快捷方式 ["页选择要](#customize-keyboard-shortcuts-in-the-microsoft-edge-devtools) 自定义 [的操作][DevToolsCustomizeSettings]  
    :::image-end:::  
    
1.  若要将快捷键绑定到操作，请确保操作旁边的文本框具有焦点，然后使用键盘选择快捷键。  
1.  若要将多个快捷方式组合绑定到某个操作，请选择"添加**** 快捷方式"，确保操作旁边的文本框具有焦点，然后使用键盘选择快捷键。  
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png" alt-text="选择要分配给该操作的密钥" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       选择要分配给该操作的密钥  
    :::image-end:::  
    
1.  若要保存新的键盘快捷方式，请选择选中标记 \ (![CheckmarkKeyboardShortcut](../media/checkmark-keyboard-shortcut-icon.msft.png)\) 图标。
    
    :::image type="complex" source="../media/experiments-custom-keyboard-shortcuts-save-shortcut.msft.png" alt-text="选择选中标记图标以保存新的键盘快捷方式" lightbox="../media/experiments-custom-keyboard-shortcuts-enter-key.msft.png":::
       选择选中标记图标以保存新的键盘快捷方式  
    :::image-end:::  
    
1.  选择新的键盘快捷方式以在 DevTools 中触发操作。  
    
在 ["快捷方式"](#customize-keyboard-shortcuts-in-the-microsoft-edge-devtools) 页上 **，自定义键盘** 快捷方式 \ (![ CustomKeyboardShortcut ](../media/custom-keyboard-shortcut-icon.msft.png) \) 图标显示已自定义的键盘快捷方式。  若要重置所有快捷方式，请选择"**还原默认快捷方式"。**  

编辑操作键盘快捷方式时，若要放弃所做的更改，请选择 X \ (![ XKeyboardShortcut ](../media/discard-changes-keyboard-shortcut-icon.msft.png) \) 图标。  若要删除特定操作快捷方式，请选择 Delete **快捷方式** \ (![ DeleteKeyboardShortcut ](../media/delete-keyboard-shortcut-icon.msft.png) \) 图标。  

> [!NOTE]
> 如果当前为一个操作分配了键盘快捷方式，则阻止将其保存为另一个操作。  请改为从上一操作中删除键盘快捷方式，然后将其添加到新操作。  

<!-- links -->  

[DevToolsCustomizeSettings]: ./index.md#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsOpenMain]: ../open/index.md "打开 Microsoft Edge DevTools | Microsoft Docs"  
[DevToolsShortcuts]: ../shortcuts/index.md "Microsoft Edge DevTools 键盘快捷方式|Microsoft Docs"  

[VisualStudioCode]: https://code.visualstudio.com "Microsoft Visual Studio Code"  
[VisualStudioCodeShortcutsKeyboardWindows]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Visual Studio Windows 键盘的键盘快捷方式|Microsoft Visual Studio Code"  

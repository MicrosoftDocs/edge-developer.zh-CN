---
description: 在 Microsoft Edge DevTools 中模拟验证器和调试 WebAuthn。
title: 在 Microsoft Edge DevTools 中模拟验证器并调试 WebAuthn
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 3200f22485bfd642a37a7d34ac727b8da4500d06
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231179"
---
# 在 Microsoft Edge DevTools 中模拟验证器并调试 WebAuthn  

使用 Microsoft Edge DevTools 中的 **WebAuthn** 工具创建基于软件的虚拟验证器并与之交互，而不是使用物理验证器调试网站或应用中的 Web 身份验证。  

## 开始之前  

Web 身份验证的一个入门位置是 [Web 身份验证 API 规范][GithubW3cWebauthn]。  

## 设置 WebAuthn 工具  

1.  导航到使用 WebAuthn 的网页，如以下演示网站。  
    
    [webauthndemo.appspot.com][AppspotWebauthndemo]  
    
1.  登录到网站。  
1.  [打开 DevTools。][DevtoolsGuideChromiumOpen]  
1.  若要打开**WebAuthn**工具，请选择"自定义和控制**DevTools** \ (`...` \) 图标>**更多工具**  >  **WebAuthn。**  
    
    :::image type="complex" source="../media/webauthn-webauthn-tab.msft.png" alt-text="WebAuthn 工具" lightbox="../media/webauthn-webauthn-tab.msft.png":::
       **WebAuthn** 工具  
    :::image-end:::  
    
1.  在 **WebAuthn** 工具中，打开" **启用虚拟验证器环境"复选框** 。  
1.  启用后，将显示名为 **"新建验证器"的新** 节。  
    
    :::image type="complex" source="../media/webauthn-enable-virtual-auth.msft.png" alt-text="启用虚拟验证器环境" lightbox="../media/webauthn-enable-virtual-auth.msft.png":::
        **启用虚拟验证器环境**  
    :::image-end:::  
    
1.  在 **"新建验证器** "部分，配置以下选项。  
    
    | 选项 | 值 | 详细信息 |  
    |:--- |:--- |:--- |  
    | `Protocol` | [ctap2][FidoallianceSpecsV20Id20180227ClientToAuthenticatorProtocolHtml] 或 [u2f][FidoallianceSpecsU2fV12Ps20170411OverviewHtml] | 虚拟验证器用于编码和解码的协议 |  
    | `Transport` |   `usb``nfc`、、 `ble` 或 `internal` | 虚拟验证器模拟所选传输以便与客户端进行通信，以获取特定凭据的断言。  有关详细信息，请导航到 [Authenticator 传输枚举][GithubW3cWebauthnEnumTransport] |  
    |  `Supports resident keys` | 使用复选框 (\) 或关闭\) \ | 如果 Web 应用依赖驻留密钥 \ (也称为客户端可发现凭据\) 。  有关详细信息，请导航到 [Resident Key Requirement 枚举][GithubW3cWebauthnEnumResidentkeyrequirement]。 |  
    | `Supports user verification` | 使用复选框 (\) 或关闭\) \ | 如果 Web 应用依赖使用手势形式（如触摸和引脚代码、密码输入或生物识别识别）的本地授权，则打开。  有关详细信息，请导航到 ["用户验证"][GithubW3cWebauthnEnumUserverification] |  
    
1.  选择“添加”按钮****。  
1.  将显示新创建的验证器的新部分。  
    
    :::image type="complex" source="../media/webauthn-authenticator.msft.png" alt-text="Authenticator" lightbox="../media/webauthn-authenticator.msft.png":::
       Authenticator  
    :::image-end:::  
    
**Authenticator**部分包含**Credentials**表。  在将凭据注册到验证器之前，该表为空。  

:::image type="complex" source="../media/webauthn-no-cred.msft.png" alt-text="无凭据" lightbox="../media/webauthn-no-cred.msft.png":::
   无凭据  
:::image-end:::  

## 注册新凭据  

若要注册新凭据，请完成以下步骤。  有关注册新凭据时[Web 身份验证 API][GithubW3cWebauthn]正在执行哪些操作，请导航到"[新建凭据"。][GithubW3cWebauthnSctnCreatecredential]  

1.  在演示网站上，选择 **"注册新凭据"。**  
1.  现在，新凭据将添加到 WebAuthn 工具中的 **Credentials** 表中。  
    
    :::image type="complex" source="../media/webauthn-view-cred.msft.png" alt-text="查看凭据" lightbox="../media/webauthn-view-cred.msft.png":::
       查看凭据  
    :::image-end:::  
    
在演示网站上，选择"验证 **"** 按钮。  确认**Credentials**表中的凭据的 Sign [Count][GithubW3cWebauthnSctnSignCounter]增加了 1，这表示[authenticatorGetAssertion][GithubW3cWebauthnAuthenticatorgetassertion]操作成功。  

## 导出和删除凭据  

若要导出或删除凭据， **请选择"导出** 或删除 **"** 按钮。  

:::image type="complex" source="../media/webauthn-export-remove.msft.png" alt-text="导出或删除凭据" lightbox="../media/webauthn-export-remove.msft.png":::
   导出或删除凭据  
:::image-end:::  

## 重命名验证器  

若要重命名验证器，请完成以下步骤。  

1.  在验证器名称旁边，选择"编辑 **"** 按钮。  
1.  编辑名称，然后选择 **Enter** 保存更改。  

:::image type="complex" source="../media/webauthn-rename.msft.png" alt-text="重命名验证器" lightbox="../media/webauthn-rename.msft.png":::
   重命名验证器  
:::image-end:::  

## 设置活动验证器  

将自动激活新创建的验证器。  若要使用另一个虚拟验证器，请选择验证器旁边的 **"** 活动单选"按钮。  

> [!NOTE]
> DevTools 在任何时间点都只支持一个活动的虚拟验证器。  如果删除活动验证器，则不会自动激活另一个验证器。  

:::image type="complex" source="../media/webauthn-set-active.msft.png" alt-text="设置活动验证器" lightbox="../media/webauthn-set-active.msft.png":::
   设置活动验证器  
:::image-end:::  

## 删除虚拟验证器  

若要删除虚拟验证器，请选择验证器旁边的"删除 **"** 按钮。  

:::image type="complex" source="../media/webauthn-remove-authenticator.msft.png" alt-text="删除验证器" lightbox="../media/webauthn-remove-authenticator.msft.png":::
   删除验证器  
:::image-end:::  

## 联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open/index.md "打开 Microsoft Edge DevTools | Microsoft Docs"  

[AppspotWebauthndemo]: https://webauthndemo.appspot.com "Webauthn 演示 |Appspot"  

[FidoallianceSpecsV20Id20180227ClientToAuthenticatorProtocolHtml]: https://fidoalliance.org/specs/fido-v2.0-id-20180227/fido-client-to-authenticator-protocol-v2.0-id-20180227.html "客户端到验证器协议 (CTAP) |fido 联盟"  
[FidoallianceSpecsU2fV12Ps20170411OverviewHtml]: https://fidoalliance.org/specs/fido-u2f-v1.2-ps-20170411/fido-u2f-overview-v1.2-ps-20170411.html "通用 2nd Factor (U2F) 概述 |fido 联盟"  

[GithubW3cWebauthn]: https://w3c.github.io/webauthn "Web 身份验证：用于访问公钥凭据级别 2 的 API |GitHub"  
[GithubW3cWebauthnAuthenticatorgetassertion]: https://w3c.github.io/webauthn#authenticatorgetassertion "authenticatorGetAssertion 操作 - Web 身份验证：用于访问公钥凭据级别 2 的 API |GitHub"  
[GithubW3cWebauthnEnumTransport]: https://w3c.github.io/webauthn#enum-transport "验证器传输枚举 (enum AuthenticatorTransport) - Web 身份验证：用于访问公钥凭据级别 2 的 API |W3C"  
[GithubW3cWebauthnEnumResidentkeyrequirement]: https://w3c.github.io/webauthn#enum-residentKeyRequirement "Resident Key Requirement 枚举 (枚举 ResidentKeyRequirement) - Web 身份验证：用于访问公钥凭据级别 2 的 API |W3C"  
[GithubW3cWebauthnEnumUserverification]: https://w3c.github.io/webauthn#user-verification "用户验证 - Web 身份验证：用于访问公钥凭据级别 2 的 API |W3C"  
[GithubW3cWebauthnSctnCreatecredential]: https://w3c.github.io/webauthn#sctn-createCredential "创建新的凭据 - PublicKeyCredential 的 [[Create]] (原点、选项、sameOriginWithAncestors) 方法 - Web 身份验证：用于访问公钥凭据级别 2 的 API |GitHub"  
[GithubW3cWebauthnSctnSignCounter]: https://w3c.github.io/webauthn/#sctn-sign-counter "签名计数器注意事项 - Web 身份验证：用于访问公钥凭据级别 2 的 API |GitHub"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/webauthn/index)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  

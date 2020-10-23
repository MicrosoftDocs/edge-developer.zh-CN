---
description: 在 Microsoft Edge DevTools 中模拟 Authenticators 和调试 WebAuthn。
title: 在 Microsoft Edge 中模拟 authenticators 和调试 WebAuthn DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/22/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 6727e9aeea1a51689a80570a2f1c9df880a8c9db
ms.sourcegitcommit: 6e2b26d41a0aa56ac34e6edc7dddd852ddb415b1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2020
ms.locfileid: "11133999"
---
# 在 Microsoft Edge 中模拟 authenticators 和调试 WebAuthn DevTools  

不要在你的网站或应用中使用物理 authenticators 调试 Web 身份验证，请使用 Microsoft Edge DevTools 中的 " **WebAuthn** " 工具创建基于软件的虚拟 authenticators 并与之交互。  

## 开始之前  

Web 身份验证入门的一个绝佳位置是 [Web 身份验证 API 规范][GithubW3cWebauthn]。  

## 设置 "WebAuthn" 工具  

1.  导航到使用 WebAuthn 的网页，例如以下演示网站。  
    
    [webauthndemo.appspot.com][AppspotWebauthndemo]  
    
1.  登录到网站。  
1.  [打开 DevTools][DevtoolsGuideChromiumOpen]。  
1.  若要打开 " **WebAuthn** " 工具，请选择 "**自定义和控制 DevTools** \ (`...` \ ) " 图标 > "**更多工具" 工具**  >  **WebAuthn**。  
    
    :::image type="complex" source="../media/webauthn-webauthn-tab.msft.png" alt-text="WebAuthn 工具" lightbox="../media/webauthn-webauthn-tab.msft.png":::
       **WebAuthn** 工具  
    :::image-end:::  
    
1.  在 " **WebAuthn** 工具" 中，选择 " **启用虚拟身份验证器环境**" 旁边的复选框。  
1.  启用后，将显示名为 " **新建身份验证** 器" 的新分区。  
    
    :::image type="complex" source="../media/webauthn-enable-virtual-auth.msft.png" alt-text="WebAuthn 工具" lightbox="../media/webauthn-enable-virtual-auth.msft.png":::
        **启用虚拟身份验证器环境**  
    :::image-end:::  
    
1.  在 " **新建身份验证** 器" 部分中，配置以下选项。  
    
    | 选项 | Value | 详细信息 |  
    |:--- |:--- |:--- |  
    | `Protocol` | [ctap2][FidoallianceSpecsV20Id20180227ClientToAuthenticatorProtocolHtml] 或 [u2f][FidoallianceSpecsU2fV12Ps20170411OverviewHtml] | 虚拟身份验证器用于编码和解码的协议 |  
    | `Transport` |   `usb`、 `nfc` 、 `ble` 或 `internal` | 虚拟身份验证器模拟所选传输，以便为特定凭据获取断言。  有关详细信息，请导航到 [身份验证器传输枚举][GithubW3cWebauthnEnumTransport] |  
    |  `Supports resident keys` | 使用复选框打开 \ (或关闭 \ )  | 如果你的 web 应用依赖于常驻密钥 \ (也称为客户端可发现凭据 \ ) ，则打开。  有关详细信息，请导航到 " [常驻密钥需求枚举][GithubW3cWebauthnEnumResidentkeyrequirement]"。 |  
    | `Supports user verification` | 使用复选框打开 \ (或关闭 \ )  | 如果你的 web 应用依赖于使用手势形式的本地授权（如触控 + pin 码、密码输入或生物识别识别），则打开。  有关详细信息，请导航到 [用户验证][GithubW3cWebauthnEnumUserverification] |  
    
1.  选择“添加”按钮****。  
1.  将显示新创建的身份验证器的新分区。  
    
    :::image type="complex" source="../media/webauthn-authenticator.msft.png" alt-text="WebAuthn 工具" lightbox="../media/webauthn-authenticator.msft.png":::
       鉴别  
    :::image-end:::  
    
**身份验证**器部分包括一个**凭据**表。  在将凭据注册到身份验证器之前，该表为空。  

:::image type="complex" source="../media/webauthn-no-cred.msft.png" alt-text="WebAuthn 工具" lightbox="../media/webauthn-no-cred.msft.png":::
   无凭据  
:::image-end:::  

## 注册新凭据  

若要注册新凭据，请完成以下步骤。  有关注册新凭据时 [Web 身份验证 API][GithubW3cWebauthn] 正在执行的操作的详细信息，请导航以 [创建新凭据][GithubW3cWebauthnSctnCreatecredential]。  

1.  在演示网站上，选择 " **注册新凭据**"。  
1.  新凭据现在已添加到 "WebAuthn 工具" 的 " **凭据** " 表中。  
    
    :::image type="complex" source="../media/webauthn-view-cred.msft.png" alt-text="WebAuthn 工具" lightbox="../media/webauthn-view-cred.msft.png":::
       查看凭据  
    :::image-end:::  
    
在演示网站上，选择 " **身份验证** " 按钮。  验证**凭据**表中凭据的[签名计数][GithubW3cWebauthnSctnSignCounter]是否增加1，它标记成功的[authenticatorGetAssertion][GithubW3cWebauthnAuthenticatorgetassertion]操作。  

## 导出和删除凭据  

若要导出或删除凭据，请选择 " **导出** " 或 " **删除** " 按钮。  

:::image type="complex" source="../media/webauthn-export-remove.msft.png" alt-text="WebAuthn 工具" lightbox="../media/webauthn-export-remove.msft.png":::
   导出或删除凭据  
:::image-end:::  

## 重命名身份验证器  

若要重命名身份验证器，请完成以下步骤。  

1.  在身份验证器名称旁边，选择 " **编辑** " 按钮。  
1.  编辑名称，然后选择 " **输入** " 以保存更改。  

:::image type="complex" source="../media/webauthn-rename.msft.png" alt-text="WebAuthn 工具" lightbox="../media/webauthn-rename.msft.png":::
   重命名身份验证器  
:::image-end:::  

## 设置活动身份验证器  

新创建的身份验证器将自动激活。  若要使用其他虚拟身份验证器，请选择身份验证器旁边的 **活动** 单选按钮。  

> [!NOTE]
> DevTools 在任意时间点仅支持一个活动的虚拟身份验证器。  如果删除活动身份验证器，则不会自动激活另一个身份验证器。  

:::image type="complex" source="../media/webauthn-set-active.msft.png" alt-text="WebAuthn 工具" lightbox="../media/webauthn-set-active.msft.png":::
   设置活动身份验证器  
:::image-end:::  

## 删除虚拟身份验证器  

若要删除虚拟身份验证器，请选择 "身份验证器" 旁边的 " **删除** " 按钮。  

:::image type="complex" source="../media/webauthn-remove-authenticator.msft.png" alt-text="WebAuthn 工具" lightbox="../media/webauthn-remove-authenticator.msft.png":::
   删除身份验证器  
:::image-end:::  

## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open.md "打开 Microsoft Edge DevTools |Microsoft 文档"  

[AppspotWebauthndemo]: https://webauthndemo.appspot.com "Webauthn 演示 |Appspot"  

[FidoallianceSpecsV20Id20180227ClientToAuthenticatorProtocolHtml]: https://fidoalliance.org/specs/fido-v2.0-id-20180227/fido-client-to-authenticator-protocol-v2.0-id-20180227.html "客户端到身份验证器协议 (CTAP) |fido 联盟"  
[FidoallianceSpecsU2fV12Ps20170411OverviewHtml]: https://fidoalliance.org/specs/fido-u2f-v1.2-ps-20170411/fido-u2f-overview-v1.2-ps-20170411.html "通用第2因素 (U2F) 概述 |fido 联盟"  

[GithubW3cWebauthn]: https://w3c.github.io/webauthn "Web 身份验证：用于访问公钥凭据级别2的 API |GitHub"  
[GithubW3cWebauthnAuthenticatorgetassertion]: https://w3c.github.io/webauthn#authenticatorgetassertion "AuthenticatorGetAssertion 操作-Web 身份验证：用于访问公钥凭据级别2的 API |GitHub"  
[GithubW3cWebauthnEnumTransport]: https://w3c.github.io/webauthn#enum-transport "身份验证器传输枚举 (枚举 AuthenticatorTransport) Web 身份验证：用于访问公钥凭据级别2的 API |W3C"  
[GithubW3cWebauthnEnumResidentkeyrequirement]: https://w3c.github.io/webauthn#enum-residentKeyRequirement "常驻密钥需求枚举 (枚举 ResidentKeyRequirement) Web 身份验证：用于访问公钥凭据的 API 级别 2 |W3C"  
[GithubW3cWebauthnEnumUserverification]: https://w3c.github.io/webauthn#user-verification "用户验证-Web 身份验证：用于访问公钥凭据级别2的 API |W3C"  
[GithubW3cWebauthnSctnCreatecredential]: https://w3c.github.io/webauthn#sctn-createCredential "创建新的凭据-PublicKeyCredential 的 [[创建]] (来源、选项、sameOriginWithAncestors) 方法 Web 身份验证：用于访问公钥凭据的 API 级别 2 |GitHub"  
[GithubW3cWebauthnSctnSignCounter]: https://w3c.github.io/webauthn/#sctn-sign-counter "签名计数器注意事项-Web 身份验证：用于访问公钥凭据级别2的 API |GitHub"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面可在 [此处](https://developers.google.com/web/tools/chrome-devtools/webauthn/index) 找到，并由 [Jecelyn Yeen][JecelynYeen] (开发人员和 DevTools，Chrome \ ) 。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  

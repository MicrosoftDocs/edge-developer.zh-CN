---
description: 了解付款请求 API 如何让 Microsoft Edge 充当存储在云中的商家、消费者和消费者付款方式之间的中介。
title: 付款请求 API - 开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: efcad701fec73f858fa9490f12b094259cd8c793
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232289"
---
# EdgeHTML (付款请求 API)   

> [!NOTE]
> 本文介绍了旧版 Microsoft Edge 中 [支持的工作流][MicrosoftSupport44533505]。  Microsoft Edge \ (Chromium\) 支持基于 Chromium 项目的不同实现付款请求 API。  

电子商务销售额继续以快速的速度增长。  根据 [eMarketer，](https://www.emarketer.com)预计到 2018 年，数字销售额将比 2013 年的水平增长 23%。  虽然消费者和企业享受电子商务销售的便利，但挑战仍然存在。  如今，每个电子商务网站所有者都需要投入时间来开发高质量的付款结帐流和验证规则。  消费者需要导航不同的付款结帐流程，并在他们购买的每一个网站重新输入相同的付款和发货信息。  这对消费者来说可能非常耗时和沮丧，从而导致购物车的购买率很高，并且商家的销售额下降。  商家 [估计](http://baymard.com/lists/cart-abandonment-rate) 放弃 60% 到 70% 的购物车。  

付款 [请求 API](https://w3.org/TR/payment-request) 标准化了付款结帐过程。  此 API 要求 Web 开发人员的自定义更少，并且为使用者提供更快、更一致且更令人困惑的体验。  由于消费者可以从其 Microsoft 帐户选择付款工具和送货地址，因此他们需要输入较少的数据才能完成购买，从而减少完成付款所需的时间和数据输入。  

付款请求 [API](https://w3.org/TR/payment-request) 是一个开放的跨浏览器标准，使浏览器能够充当商家、消费者以及消费者存储在云中的付款方式 \ (（如信用卡\) ）之间的中介。  
  
总之，使用付款请求 [API](https://w3.org/TR/payment-request)时，客户会正常在商家网站上购买。  当准备好付款时，商家网站会调用付款请求**API**创建付款**** 请求，将相关付款信息 \ (如支持的付款方式、购买金额、货币等\) 传递给浏览器。  

:::image type="complex" source="../media/payment_request_construct.png" alt-text="付款请求构造" lightbox="../media/payment_request_construct.png":::
   付款请求构造  
:::image-end:::  

浏览器对用户进行身份验证，使用户能够在文件上选择受支持的付款方式，并处理付款详细信息。  浏览器随后将付款信息详细信息发送回商家网站，以便商家可以完成付款。  除了接收付款信息外，商家还可以选择接收付款请求中的发货 **信息**。  

:::image type="complex" source="../media/payment_response_construct.png" alt-text="付款响应构造" lightbox="../media/payment_response_construct.png":::
   付款响应构造  
:::image-end:::  

若要了解付款请求 API 的实现以及如何使用它的概述，请查看此视频。  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Using-the-Payments-Request-API/player]  

> [!NOTE]
> Microsoft Edge 版本 14992 或更高版本支持付款请求 API。  

## 创建付款请求  

网页 **通常在用户通过** 单击"购买"按钮启动付款流程时创建付款请求。  付款**请求构造函数**[](/previous-versions/mt790440(v=vs.85))包括 methodData、详细信息和选项。  

```javascript
var payment = new PaymentRequest ( 
    methodData,  // required payment method data including payment method identifiers 
    details,     // required transaction information 
    options      // optional information like shipping or contact info to be returned 
); 
```  

[methodData](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)参数包含网站接受的付款方式和网络列表以及任何关联的付款方式特定数据。  在 Microsoft Edge 中，此列表与购物者保存在 Microsoft 帐户中的受支持的付款方式匹配，并会导致付款用户体验中的"付费方式"列表。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_with.png" alt-text="Microsoft Wallet 用户体验中的付费列表" lightbox="../media/pay_with.png":::
         Microsoft **Wallet** 用户体验中的付费列表  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      ```javascript
      var supportedInstruments = [{
          supportedMethods: ['basic-card'],
          data: {
              supportedNetworks: ['visa', 'mastercard', 'amex'],
              supportedTypes: ['credit'] 
          }         
      }]; 
      ```  
   :::column-end:::
:::row-end:::  

[details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)参数包含商家希望与客户传达有关交易的信息。  其中包括订单摘要项目，如总额、税款、发货金额和其他影响付款金额的摘要级别项目。  这些不用作订单行项。  
  
[details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)参数还用于定义客户在需要时可用的送货选项。  更多详细信息包含在下面的"付款 **请求** 及发货"部分。  

每个 [明细](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 行包含货币和金额的标签。  

> [!NOTE]
> 付款 **请求** 不会计算这些金额的总和或总计。  商家网站负责确保行项总数正确。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/show_details.png" alt-text="小计、发货、税款和总详细信息" lightbox="../media/show_details.png":::
         小计、发货、税款和总详细信息  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      ```javascript
      var details = {
          total: {
              label: 'Total (USD)',
              amount: {currency: 'USD', value: '193.98'}
          },
          displayItems: [{
                  label: 'Subtotal',
                  amount: {currency: 'USD', value: '174.99'}
              }, {
                  label: 'Taxes',
                  amount: {currency: "USD", value: '18.99'}
          }],
      };  
      ```  
   :::column-end:::
:::row-end:::  

[PaymentRequest](/previous-versions/mt790440(v=vs.85)) 不支持退款，因此金额应始终为正数;单个列表项可能为负数，例如折扣。  

浏览器将在定义标签时呈现标签，并基于客户区域设置自动呈现正确的货币格式。  请注意，标签应该以与内容相同的语言呈现。  

[options](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)参数定义网页想要从付款请求**返回的数据**。  这还会定义需要收集的数据，包括是否必须寄送、电子邮件地址、电话号码或全部数据。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/email_snippet.png" alt-text="电子邮件地址下拉列表" lightbox="../media/email_snippet.png":::
         电子邮件地址下拉列表  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      ```javascript
      var options =
          {
              requestPayerEmail: true
          }; 
      ```  
   :::column-end:::
:::row-end:::  

## 显示付款请求  

[显示 () ](/previous-versions/mt790448(v=vs.85))方法由网页调用，以允许用户与付款**请求用户界面进行交互**。  show [ () ](/previous-versions/mt790448(v=vs.85)) 方法返回将在用户授权付款请求时解析的 Promise。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_screen_default.png" alt-text="确认和支付详细信息" lightbox="../media/pay_screen_default.png":::
         确认和支付详细信息  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      ```javascript
      paymentRequest.show().then(paymentInstrumentResponse => {
          paymentInstrumentResponse.complete('success').then().catch(error => {
              handlePaymentRequestError(error); 
      });
      ```  
   :::column-end:::
:::row-end:::  

## 中止付款请求  
 
调用 [show ( () ](/previous-versions/mt790437(v=vs.85)) 方法后，网页随时都可以调用中止 [ () ](/previous-versions/mt790448(v=vs.85)) 方法，直到 Promise 解析到该点。  中止 [ () ](/previous-versions/mt790437(v=vs.85)) 方法将导致浏览器中止 **付款请求** 并关闭 **付款请求** 用户界面。  例如，如果用户未在所需时间完成事务，则网页可能会选择中止。  

```javascript
payment.abort();
```  

## 付款响应  
当客户批准付款 **请求时**，付款 **响应** 将返回到网站。  付款 **响应** 包括以下内容：  

 属性      | 说明 | 必需 | 其他信息
|---------------|-----------------|-------|-----------------|
[methodName](/previous-versions/mt790656(v=vs.85)) | 用户选择的付款方式的 ID | Y | |   
[details](/previous-versions/mt790655(v=vs.85)) | 包含商家使用所选付款方式或付款令牌处理交易所需的全部数据的 JSON 对象 | Y | [基本卡片](https://w3c.github.io/payment-method-basic-card) 字典：dictionaryName;cardNumber;expiryMonth;expiryYear;cardSecurityCode;billingAddress; |   
[shippingAddress](/previous-versions/mt790445(v=vs.85)) | 用户选择的送货地址  |  可选。  [requestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions)为必需 `True`  | 地址字典：国家/地区;addressLine;region;city;dependentLocality;postalCode;sortingCode;languageCode;组织;recipient;phone |  
[shippingOption](/previous-versions/mt790446(v=vs.85)) | 所选发货选项的 ID | 可选。  [requestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions)为必需 `True`  | |   
[payerName](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | 用户提供的名称  | 可选。  [requestPayerName](/previous-versions/mt790440(v=vs.85)#PaymentOptions)为时必需 `True` | |  
[payerEmail](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | 用户选择的电子邮件地址 | 可选。  [requestPayerEmail](/previous-versions/mt790440(v=vs.85)#PaymentOptions)为必需 `True`  | |  
[PayerPhone](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | 用户选择的电话号码 | 可选。  [requestPayerPhone 为](/previous-versions/mt790440(v=vs.85)#PaymentOptions)必需 `True` | |  

付款 [响应](/previous-versions/mt790655(v=vs.85)#PaymentRequest_params) 中的详细信息 JSON **对象将** 包含商家处理付款所需的付款数据。  在最简单的形式中，响应将是包含明文支付卡[](https://w3c.github.io/payment-method-basic-card)详细信息的基本卡有效负载。  如果商家已安排其他网关/处理合作伙伴来提供付款支持，则商家可能需要处理器可以处理的有效负载。  这些令牌可以形成处理器/网关令牌或加密的付款方式。  这些付款方式超出了本文档的范围，将在特定于处理者的文档中介绍。  此外，若要接收基本[](https://w3c.github.io/payment-method-basic-card)卡响应，开发人员无需其他加入 Microsoft，与其他可能需要加密密钥载入或请求授权 \ (oAuth\) 的特定于处理器/网关的付款方式不同。  

收到付款 **响应后**，网站会向付款处理者提交付款信息。  处理付款时，浏览器将显示微调框页面。  

:::image type="complex" source="../media/loading_screen.png" alt-text="处理付款时显示的页面" lightbox="../media/loading_screen.png":::
   处理付款时显示的页面  
:::image-end:::  

付款完成后，网页将调用完整的 [ () ](/previous-versions/mt790642(v=vs.85)) 方法，并传递成功 **或** 失败 **的值**。  完整的[ () ](/previous-versions/mt790642(v=vs.85))方法通知浏览器购买已完成，并且应该根据成功或失败的值显示相应的终止 UI**屏幕**。 ****  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_complete.png" alt-text="购买成功时显示的 UI" lightbox="../media/response_payment-request_complete.png":::
         购买成功时显示的 UI  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_failure.png" alt-text="购买失败时显示的 UI" lightbox="../media/response_payment-request_failure.png":::
         购买失败时显示的 UI  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 付款请求（发货）  

### 发货地址  

对于需要寄送物理商品的销售，需要寄送地址。  若要包含送货地址，请 `requestShipping = True` 设置请求 [的选项](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 参数。  

当用户选择或更新送货地址时 [，onshippingaddresschange](/previous-versions/mt790442(v=vs.85)) 事件将运行。  使用事件侦听器的网站将注意到更改，然后可以验证地址、重新计算发货成本和税款，并更新 [shippingOptions](/previous-versions/mt790440(v=vs.85)) 以反映所选 \ (（如果适用）地址的已更改成本和发货选项) 。  

### 发货选项  

可以通过将 [shippingOptions](/previous-versions/mt790440(v=vs.85)) 添加到 details 参数来向客户显示 [发货](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 选项。  可以通过为其中一个发货 `selected = True` 选项设置来建立默认值。  
 
当用户选择或更新 shippingOptions 时 [，onshippingoptionchange](/previous-versions/mt790436(v=vs.85)) 事件将运行。  使用事件侦听器的网站将注意到更改，并可以使用正确的寄送金额更新详细信息参数。 [](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)  

```javascript
var details = {
    total: {
        label: 'Total (USD)',
        amount: {currency: 'USD', value: '193.98'}
    },
    displayItems: [{
         label: 'Subtotal',
         amount: {currency: 'USD', value: '174.99'}
        }, {
            label: 'Shipping',
            amount: {currency: 'USD', value: '0.00'}
        }, {
            label: 'Taxes',
            amount: {currency: "USD", '18.99'}
    }],
    shippingOptions: [{
        id: 'STANDARD',
        label: 'Standard – FREE (5-6 Business days)',
        amount: {currency: 'USD', value: '0.00'},
        selected: true
    }, {
        id: 'EXPEDITED',
        label: 'Two-Day Shipping',
        amount: {currency: 'USD', value: '7.00'}
    }]
};
        
var options = {
    requestShipping: true,
    requestPayerEmail: true
}; 
```  

## API 参考  

[付款请求 API](/previous-versions/mt790447(v=vs.85))  

## 规范
[付款请求 API](https://w3.org/TR/payment-request)

<!-- links -->  

[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具 |Microsoft Docs"  

[MicrosoftSupport44533505]: https://support.microsoft.com/help/4533505 "什么是 Microsoft Edge 旧版？"  

---
description: 了解 Payment Request API 如何使 Microsoft Edge 成为存储在云中的商业、消费者和消费者支付方法之间的中介。
title: 付款请求 API - 开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/20/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: 边缘， Web 开发， html， css， javascript， developer
ms.openlocfilehash: 338940ab6f7e6bb04c6d5a8cc6ff0a198e7afbcc
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941854"
---
# 付款请求 API (EdgeHTML)   

> [!NOTE]
> 本文介绍旧版 Microsoft Edge 支持的 [工作流][MicrosoftSupport44533505]。  Microsoft Edge \ (Chromium\) 支持采用基于 Chromium 项目的不同实现来支付请求 API。  

电子商业销售连续缩小的水平。  通常对于 [eMarketer，2018](https://www.emarketer.com)年，2018 年的销售将从 2013 年度量的级别中增加 23%。  虽然消费者和企业都享受到电子商务销售的方方面，但挑选挑选。  现在每位电子网站所有者都需要完成时间来制定高质量付款流和验证规则。  消费者需要导航不同的付款结清流，然后在他们购于的每个站点上重新输入相同的付款和发货信息。  对于消费者来源并不有些影响，从而导定高度的购货车上限，并会减少商品销售量。  购销车车 [的](http://baymard.com/lists/cart-abandonment-rate) 价值包括 60% 到 70% 购购车车之间的价值。  

付 [款请求 API](https://w3.org/TR/payment-request) 标准化付款结清流程。  此 API 需要进行更少的自定义，并且提供了更快、更一致的体验，因此消费者的体验会减少。  由于消费者可从其 Microsoft 帐户中选择支付检测和送货地址，因此系统需要输入更少的数据才能完成购买，从而减少完成付款所需的时间和数据输入。  

[付款请求 API 是一](https://w3.org/TR/payment-request)种开放的跨浏览器标准，允许浏览器在商业、使用的商品和付款方式 \ (（如信用卡\) 中存储）之间的中介。  
  
总的来，使用 [付款请求 API 时](https://w3.org/TR/payment-request)，客户在商户网站上以正常方式购买。  在准备好支付时，商家网站会调用 **付款请求** API 以创建 **付款请求** 并通过相关付款信息 \ (传递相关付款信息 \ (例如支持的付款方式、购买金额、货币等 ) 。  

:::image type="complex" source="../media/payment_request_construct.png" alt-text="付款请求构造" lightbox="../media/payment_request_construct.png":::
   付款请求构造  
:::image-end:::  

浏览器会对用户进行身份验证，让用户能够对文件选择一种受支持的付款方式，并处理付款详细信息。  然后，浏览器会将付款信息返回到商业网站，以便商业可以完成付款。  除接收付款信息之外，成人还可选择接收付款请求的发 **货信息**。  

:::image type="complex" source="../media/payment_response_construct.png" alt-text="付款响应构造" lightbox="../media/payment_response_construct.png":::
   付款响应构造  
:::image-end:::  

若要查看付款请求 API，以及获取其使用方法概述，请观看此视频。  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Using-the-Payments-Request-API/player]  

> [!NOTE]
> 付款请求 API 在 Microsoft Edge 内部版本 14992 或更高版本中受支持。  

## 创建付款请求  

网页通常 **在用户通过单击"购买** "按钮启动付款流程时创建一个付款请求。  **付款请求构**[造函数包括](/previous-versions/mt790440(v=vs.85))methodData、details 和选项。  

```javascript
var payment = new PaymentRequest ( 
    methodData,  // required payment method data including payment method identifiers 
    details,     // required transaction information 
    options      // optional information like shipping or contact info to be returned 
); 
```  

[methodData](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)参数包含由网站所接受的付款方式和网络的列表，以及任何相关的付款方式特定数据。  在 Microsoft Edge 中，此列表与购户在 Microsoft 帐户中已保存的支持付款方式相匹配，并导致付款用户体验中的"支付方式"列表。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_with.png" alt-text="Microsoft 子钱包用户体验中的列表" lightbox="../media/pay_with.png":::
         Microsoft **子钱包** 用户体验中的列表  
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

[详细信息](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)参数包含与客户开关关于交易的信息。  这些汇总项包括总计、税、运费金额和其他摘要级别项目影响支付金额。  这些不应用用作行项进行排序。  
  
[在需要](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)时，详细信息参数还用于定义可供客户使用的送货选项。  下面包含更多详细信息，包含下**Payment Request**文"发货"部分。  

[每个](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)明细线都包含货币和金额的标签。  

> [!NOTE]
> **付款请求不会**计算这些金额的总和或总数。  商级网站的责任为确保行项总数正确所有。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/show_details.png" alt-text="分类汇总、运送、税款及总细节" lightbox="../media/show_details.png":::
         分类汇总、运送、税款及总细节  
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

[PaymentRequest](/previous-versions/mt790440(v=vs.85)) 不支持退款，所以金额应始终为正数;单个列表项可以为非正数，如折扣。  

当你定义标签时，浏览器将呈现标签，并根据客户的区域设置自动呈现正确的货币格式。  请注意，标签应以与你的内容相同的语言呈现。  

选项 [参数](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 定义网页需要从付款请求返回 **的数据**。  这还定义需要收集的数据，包括发货、电子邮件地址、电话号码还是需要使用所有数据。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/email_snippet.png" alt-text=""电子邮件地址"下拉列表" lightbox="../media/email_snippet.png":::
         "电子邮件地址"下拉列表  
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

显示 [ () ](/previous-versions/mt790448(v=vs.85)) 方法，以允许用户与 **付款请求用户** 界面进行交互。  显示 [ () ](/previous-versions/mt790448(v=vs.85)) 方法将返回在用户授权付款请求时将解除的 Promise。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_screen_default.png" alt-text="确认和付款详细信息" lightbox="../media/pay_screen_default.png":::
         确认和付款详细信息  
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

## 中不记录付款请求  
 
中 [止 () ](/previous-versions/mt790437(v=vs.85)) 方法可在调用 [显示 () 方法后随时调用 () ](/previous-versions/mt790448(v=vs.85)) 方法，直到解析了承诺的位置。  [中 () ](/previous-versions/mt790437(v=vs.85))方法将导致浏览器中符合付款**请求**并**关闭付款请求**用户界面。  例如，如果用户在需要时间内未完成交易，网页可能会选择中间。  

```javascript
payment.abort();
```  

## 付款响应  
当客户批准付 **款请求时**，付款 **响** 应将返回到网站。  **付款响应**包括以下内容：  

 属性      | 说明 | 必需 | 其他信息
|---------------|-----------------|-------|-----------------|
[methodName](/previous-versions/mt790656(v=vs.85)) | 用户选择的付款方式 ID | Y | |   
[details](/previous-versions/mt790655(v=vs.85)) | 包含商业变换机号处理处理交易的所有数据的 JSON 对象 | Y | [基本卡片](https://w3c.github.io/payment-method-basic-card) 字典：cardholderName;cardNumber;expiryMonth;expiryYear;cardSecurityCode;billingAddress; |   
[shippingAddress](/previous-versions/mt790445(v=vs.85)) | 由用户选择的送货地址  |  可选。  需要请求 [Shipping 时的](/previous-versions/mt790440(v=vs.85)#PaymentOptions) 必需服务 `True`  | 地址字典：国家/地区;addressline;区域;城市;dependentLocality;postalCode;sortingCode;languageCode;组织;收件人;手机 |  
[shippingOption](/previous-versions/mt790446(v=vs.85)) | 所选送货选项的 ID | 可选。  需要请求 [Shipping 时的](/previous-versions/mt790440(v=vs.85)#PaymentOptions) 必需服务 `True`  | |   
[payerName](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | 由用户提供的名称  | 可选。  [RequestPayerName 为必](/previous-versions/mt790440(v=vs.85)#PaymentOptions)需 `True` | |  
[payerEmail](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | 用户选择的电子邮件地址 | 可选。  [RequestPayerEmail](/previous-versions/mt790440(v=vs.85)#PaymentOptions)为该要求 `True`  | |  
[PayerPhone](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | 用户选择的电话号码 | 可选。  [当 requestPayerPhone 为必](/previous-versions/mt790440(v=vs.85)#PaymentOptions)需 `True` | |  

[付款](/previous-versions/mt790655(v=vs.85)#PaymentRequest_params)响应中详细的 JSON**对象**将包含处理付款所需的付款数据。  该响应最简单，该响应将是包含清楚性支付卡[Basic Card](https://w3c.github.io/payment-method-basic-card)详细信息的基本卡负载。  如果商主具有附加网关/处理器合作伙伴的方式来为他们提供付款支持，该商家可能需要负载该处理员。  这些可以获取处理器/网关标记或加密的付款方式的形状。  这些支付方式超出了本文档的范围，并且将在文档中被介绍，这些信息仅在特定于处理器的文档中介绍。  此外，若要接收 [基本卡](https://w3c.github.io/payment-method-basic-card) 响应，开发人员不需要对 Microsoft 进行额外培训，这与可能需要加密密钥或请求授权 \ (oAuth\) 的其他处理器/网关特定的付款方法不同。  

在收获付款回复后，**Payment Response**网站会将付款信息提交到其付款处理器。  处理付款时，浏览器将显示一个较进的页面。  

:::image type="complex" source="../media/loading_screen.png" alt-text="处理付款时显示的页面" lightbox="../media/loading_screen.png":::
   处理付款时显示的页面  
:::image-end:::  

付款完成后，该网页将调用 [完整的 () ](/previous-versions/mt790642(v=vs.85)) 方法，并传递成功 **或** 失 **败值**。  [完整的 () ](/previous-versions/mt790642(v=vs.85))方法可通知浏览器完成购买，并应该根据成功或失败的价值显示相应的**终止**UI 屏幕。 **success**  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_complete.png" alt-text="UI 成功显示" lightbox="../media/response_payment-request_complete.png":::
         UI 成功显示  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_failure.png" alt-text="购买失败时显示的 UI" lightbox="../media/response_payment-request_failure.png":::
         购买失败时显示的 UI  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 发送就请求  

### 送货地址  

对于需要送货物理商品的销售，需要送货地址。  若要包含送货地址，请通过 `requestShipping = True` 设置 [请求的选项](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 参数。  

当用户选择或更新送货地址时，将运行 [onshippingaddresschange](/previous-versions/mt790442(v=vs.85)) 事件。  网站使用事件侦听器将知道更改，然后可验证地址、重新计算运费和税收，并更新 [运费选项以](/previous-versions/mt790440(v=vs.85)) 反映地址中所选项的可 (选费用和送货选项（如果适用\) ）。  

### 送货选项  

通过将运货选项添加到[details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)参数，可以向客户显示发[shippingOptions](/previous-versions/mt790440(v=vs.85))货选项。  可以通过为某一送货选项 `selected = True` 设置来创建默认值。  
 
当用户选择或更新运货选项时，将运行 [onshippingOptionChange](/previous-versions/mt790436(v=vs.85)) 事件。  网站使用事件侦听器将知道更改，并可 [使用](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 正确的运送金额更新细节参数。  

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

[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具 |Microsoft 文档"  

[MicrosoftSupport44533505]: https://support.microsoft.com/help/4533505 "什么是 Microsoft Edge？"  

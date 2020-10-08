---
description: 了解 thePayment 请求 APIenables Microsoft Edge 如何在存储在云中的商家、消费者和消费者支付方式之间充当媒介。
title: 付款请求 API-开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/20/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: 338940ab6f7e6bb04c6d5a8cc6ff0a198e7afbcc
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941854"
---
# 付款请求 API (EdgeHTML)   

> [!NOTE]
> 本文介绍 [早期版本的 Microsoft Edge][MicrosoftSupport44533505]中支持的工作流。  Microsoft Edge \ (Chromium \ ) 使用基于 Chromium 项目的不同实现支持付款请求 API。  

电子商务销售继续以快速节奏的速度增长。  根据 [eMarketer](https://www.emarketer.com)，我们预测，2018将按2013中的级别增加23% 的数字销售。  消费者和企业享受电子商务销售的便利，但挑战仍然存在。  如今，每个电子商务网站所有者都需要花费大量时间来开发优质付款结帐流程和验证规则。  消费者需要导航不同的付款结算流程，并在他们购买的每个网站上重新输入相同的支付和运输信息。  对于消费者来说，这可能会非常耗时且令人沮丧，从而提高了购物车的 abandonment，并降低了商家的销售额。  将放弃购买车60% 和70% 之间的商家 [估计](http://baymard.com/lists/cart-abandonment-rate) 。  

[付款请求 API](https://w3.org/TR/payment-request)标准化付款结算流程。  对于 web 开发人员而言，此 API 需要较少的自定义，并且为使用者提供更快、更一致且更一致的体验。  由于消费者可以从其 Microsoft 帐户选择支付方式和送货地址，因此他们需要输入较少的数据来完成购买，从而减少完成付款所需的时间和数据输入。  

[支付请求 API](https://w3.org/TR/payment-request)是一个开放的跨浏览器标准，使浏览器能够充当商家、消费者和支付方式 \ (（如信用卡）之间的媒介，例如，使用者已存储在云中的 ) 。  
  
总而言之，在使用 [付款请求 API](https://w3.org/TR/payment-request)时，客户以正常方式在商家网站上购物。  当准备好支付时，商家网站将调用 **付款请求** API 来创建 **付款请求** 并将相关的付款信息 \ (，例如支持的支付方式、购买金额、货币等 \ ) 浏览器。  

:::image type="complex" source="../media/payment_request_construct.png" alt-text="付款请求构造" lightbox="../media/payment_request_construct.png":::
   付款请求构造  
:::image-end:::  

浏览器对用户进行身份验证，允许用户选择受支持的文件支付方式，并处理付款详细信息。  然后，浏览器会将付款信息的详细信息发送回商家网站，以便商家可以完成付款。  除了接收付款信息，商家还可以选择接收作为 **付款请求**一部分的装运信息。  

:::image type="complex" source="../media/payment_response_construct.png" alt-text="付款请求构造" lightbox="../media/payment_response_construct.png":::
   付款响应构造  
:::image-end:::  

若要查看付款请求 API 的工作方式，并大致了解如何使用它，请查看此视频。  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Using-the-Payments-Request-API/player]  

> [!NOTE]
> Microsoft Edge 内部版本14992或更高版本支持付款请求 API。  

## 创建付款请求  

当用户通过单击 "购买" 按钮启动付款流程时，网页通常会创建 **付款请求** 。  **付款请求**[构造函数](/previous-versions/mt790440(v=vs.85))包括 methodData、详细信息和选项。  

```javascript
var payment = new PaymentRequest ( 
    methodData,  // required payment method data including payment method identifiers 
    details,     // required transaction information 
    options      // optional information like shipping or contact info to be returned 
); 
```  

[MethodData](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)参数包含网站接受的支付方式和网络以及任何关联的付款方式特定数据的列表。  在 Microsoft Edge 中，此列表与购物者在其 Microsoft 帐户中保存的支持支付方式相匹配，并在付款用户体验中产生 "支付方式" 列表。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_with.png" alt-text="付款请求构造" lightbox="../media/pay_with.png":::
         Microsoft 钱包用户体验中的 " **支付方式** " 列表  
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

" [详细信息](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) " 参数包含商家希望向客户传达交易的相关信息。  其中包括影响付款金额的订单汇总项目，如 "总计"、"税金"、"运输金额" 以及其他汇总级别项目。  它们不应作为订单行项目。  
  
" [详细信息](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) " 参数还用于定义在需要时可供客户使用的装运选项。  下面 **的 "发货" 部分包含更** 多详细信息。  

每个 [明细](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 行都包含货币和金额的标签。  

> [!NOTE]
> **付款请求**不会计算这些金额的总和或总额。  由商家的网站负责确保明细项目的总数正确。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/show_details.png" alt-text="付款请求构造" lightbox="../media/show_details.png":::
         小计、运费、税金和总详细信息  
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

[PaymentRequest](/previous-versions/mt790440(v=vs.85)) 不支持退款，因此金额应始终为正数;单个列表项可以是负数，例如折扣。  

浏览器将在你定义标签时呈现这些标签，并根据客户的区域设置自动呈现正确的货币格式。  请注意，标签应呈现为与内容相同的语言。  

[选项](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)参数定义网页希望从**付款请求**返回的数据。  这还会定义需要收集的数据，包括装运、电子邮件地址、电话号码或全部必填。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/email_snippet.png" alt-text="付款请求构造" lightbox="../media/email_snippet.png":::
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

[显示 ( # B1](/previous-versions/mt790448(v=vs.85))方法由网页调用，以允许用户与**付款请求**用户界面进行交互。  [Show ( # B1](/previous-versions/mt790448(v=vs.85))方法将返回一个承诺，该承诺将在用户批准付款请求时得到解决。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_screen_default.png" alt-text="付款请求构造" lightbox="../media/pay_screen_default.png":::
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

## 终止付款请求  
 
在 "[显示" ( # B3](/previous-versions/mt790448(v=vs.85))方法被调用后，任何时候都可以随时调用[Abort ( # B1](/previous-versions/mt790437(v=vs.85))方法，直到解决该承诺的点。  [Abort ( # B1](/previous-versions/mt790437(v=vs.85))方法将导致浏览器中止**付款请求**并关闭**付款请求**用户界面。  例如，如果用户在所需的时间量内未完成事务，则可以选择终止网页。  

```javascript
payment.abort();
```  

## 付款答复  
当客户批准 **付款请求**时，将向网站返回 **付款响应** 。  **付款响应**包括以下内容：  

 属性      | 说明 | 必需 | 其他信息
|---------------|-----------------|-------|-----------------|
[名称](/previous-versions/mt790656(v=vs.85)) | 用户选择的付款方式的 ID | Y | |   
[details](/previous-versions/mt790655(v=vs.85)) | 一个 JSON 对象，其中包含商人使用所选付款方式或付款标记处理交易时所需的所有数据 | Y | [基本卡](https://w3c.github.io/payment-method-basic-card) 词典： cardholderName;cardNumber;expiryMonth;expiryYear;cardSecurityCode;billingAddress; |   
[shippingAddress](/previous-versions/mt790445(v=vs.85)) | 用户选择的装运地址  |  可选。  [RequestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions)时需要 `True`  | 地址词典：国家/地区;addressLine;地区—dependentLocality;邮政编码sortingCode;languageCode;所在收信电话 |  
[shippingOption](/previous-versions/mt790446(v=vs.85)) | 所选装运选项的 ID | 可选。  [RequestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions)时需要 `True`  | |   
[payerName](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | 用户提供的名称  | 可选。  [RequestPayerName](/previous-versions/mt790440(v=vs.85)#PaymentOptions)时需要 `True` | |  
[payerEmail](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | 用户选择的电子邮件地址 | 可选。  [RequestPayerEmail](/previous-versions/mt790440(v=vs.85)#PaymentOptions)时需要 `True`  | |  
[PayerPhone](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | 用户选择的电话号码 | 可选。  [RequestPayerPhone](/previous-versions/mt790440(v=vs.85)#PaymentOptions)时需要 `True` | |  

**付款响应**中的[详细信息](/previous-versions/mt790655(v=vs.85)#PaymentRequest_params)JSON 对象将包含商家处理付款所需的支付数据。  在最简单的形式中，该响应将是包含明文支付卡详细信息的 [基本卡](https://w3c.github.io/payment-method-basic-card) 负载。  如果商家与其他网关/处理器合作伙伴进行了安排以提供付款支持，则商家可能需要处理器可以处理的负载。  它们可以采用处理器/网关令牌或加密付款方式的形状。  这些支付方式超出本文档的范围，将在特定于处理器的文档中介绍。  此外，若要接收 [基本的卡](https://w3c.github.io/payment-method-basic-card) 响应，开发人员不需要额外的 Microsoft 加入 Microsoft，这与其他处理器/网关特定的支付方法（可能需要加密密钥）或请求授权 \ (oAuth \ ) 不同。  

收到 **付款响应**后，网站将向其付款处理者提交付款信息。  在处理付款时，浏览器将显示一个微调框页面。  

:::image type="complex" source="../media/loading_screen.png" alt-text="付款请求构造" lightbox="../media/loading_screen.png":::
   处理付款时显示的页面  
:::image-end:::  

付款完成后，网页将调用 [完整的 ( # B1 ](/previous-versions/mt790642(v=vs.85)) 方法并传递 **成功** 或 **失败**的值。  [完整的 ( # B1](/previous-versions/mt790642(v=vs.85))方法通知浏览器购买已完成，并且根据**成功**或**失败**的值，应显示相应的终止 UI 屏幕。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_complete.png" alt-text="付款请求构造" lightbox="../media/response_payment-request_complete.png":::
         购买成功时显示的 UI  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_failure.png" alt-text="付款请求构造" lightbox="../media/response_payment-request_failure.png":::
         当购买失败时显示的 UI  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 带装运的付款请求  

### 送货地址  

对于需要装运实际货物的销售，需要装运地址。  若要包括装运地址，请 `requestShipping = True` 在请求的 " [选项](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) " 参数中设置。  

当用户选择或更新送货地址时，将运行 [onshippingaddresschange](/previous-versions/mt790442(v=vs.85)) 事件。  使用事件侦听器的网站将知道更改，然后可以验证地址、重新计算运输成本和税款，并更新 [shippingOptions](/previous-versions/mt790440(v=vs.85)) 以反映所选地址的已更改的费用和送货选项 (\ ) 。  

### 送货选项  

通过将 [shippingOptions](/previous-versions/mt790440(v=vs.85)) 添加到 [详细信息](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 参数，可以向客户显示装运选项。  可通过 `selected = True` 为其中一个装运选项设置来建立默认值。  
 
当用户选择或更新 shippingOptions 时，将运行 [onshippingoptionchange](/previous-versions/mt790436(v=vs.85)) 事件。  使用事件侦听器的网站将知道所做的更改，并且可以使用正确的运输金额更新 [详细信息](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 参数。  

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

## 书
[付款请求 API](https://w3.org/TR/payment-request)

<!-- links -->  

[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  

[MicrosoftSupport44533505]: https://support.microsoft.com/help/4533505 "什么是 Microsoft Edge 旧版？"  

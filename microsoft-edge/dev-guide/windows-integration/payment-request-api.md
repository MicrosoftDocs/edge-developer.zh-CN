---
description: 了解 thePayment 请求 APIenables Microsoft Edge 如何在存储在云中的商家、消费者和消费者支付方式之间充当媒介。
title: 开发人员指南-付款请求 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: 75c596570a222336a4ba0c371acb8770f97804ee
ms.sourcegitcommit: e690bb4d1cb9e73c93b468c9f55d91ea6fb6c654
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/10/2020
ms.locfileid: "10564611"
---
# 付款请求 API

电子商务销售继续以快速节奏的速度增长。 根据[eMarketer](https://www.emarketer.com/)，我们预测，2018将按2013中的级别增加23% 的数字销售。  消费者和企业享受电子商务销售的便利，但挑战仍然存在。  如今，每个电子商务网站所有者都需要花费大量时间来开发优质付款结帐流程和验证规则。  消费者需要导航不同的付款结算流程，并在他们购买的每个网站上重新输入相同的支付和运输信息。  对于消费者来说，这可能会非常耗时且令人沮丧，从而提高了购物车的 abandonment，并降低了商家的销售额。 将放弃购买车60% 和70% 之间的商家[估计](http://baymard.com/lists/cart-abandonment-rate)。      

[付款请求 API](https://w3.org/TR/payment-request/)标准化付款结算流程。 对于 web 开发人员而言，此 API 需要较少的自定义，并且为使用者提供更快、更一致且更一致的体验。  由于消费者可以从其 Microsoft 帐户选择支付方式和送货地址，因此他们需要输入较少的数据来完成购买，从而减少完成付款所需的时间和数据输入。   

[支付请求 API](https://w3.org/TR/payment-request/)是一个开放的跨浏览器标准，使浏览器能够充当消费者、消费者以及消费者在云中存储的支付方式（例如信用卡）之间的媒介。 
  
总而言之，在使用[付款请求 API](https://w3.org/TR/payment-request/)时，客户以正常方式在商家网站上购物。  当准备好支付时，商家网站将调用**付款请求**API 来创建**付款请求**，并将相关的付款信息（如支持的支付方式、购买金额、货币等）传递到浏览器。

![付款请求构造](./../media/payment_request_construct.png)

浏览器对用户进行身份验证，允许用户选择受支持的文件支付方式，并处理付款详细信息。 然后，浏览器会将付款信息的详细信息发送回商家网站，以便商家可以完成付款。  除了接收付款信息，商家还可以选择接收作为**付款请求**一部分的装运信息。  

![付款响应构造](./../media/payment_response_construct.png)

若要查看付款请求 API 的工作方式，并大致了解如何使用它，请查看此视频。

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Using-the-Payments-Request-API/player]


> [!NOTE]
> "付款请求" API 在 Microsoft Edge 内部版本 14992 + 中受支持。


## 创建付款请求 
当用户通过单击 "购买" 按钮启动付款流程时，网页通常会创建**付款请求**。  **付款请求**[构造函数](https://msdn.microsoft.com/library/mt790440)包括 methodData、详细信息和选项。 

```js
var payment = new PaymentRequest ( 
    methodData,  // required payment method data including payment method identifiers 
    details,     // required transaction information 
    options      // optional information like shipping or contact info to be returned 
); 
```

该 [`methodData`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 参数包含网站接受的付款方式和网络以及任何关联的付款方式特定数据的列表。 在 Microsoft Edge 中，此列表与购物者在其 Microsoft 帐户中保存的支持支付方式相匹配，并在付款用户体验中产生 "支付方式" 列表。

![Microsoft 钱包用户体验中的 "支付方式" 列表](./../media/pay_with.png)

```js
var supportedInstruments = [{
    supportedMethods: ['basic-card'],
    data: {
        supportedNetworks: ['visa', 'mastercard', 'amex'],
        supportedTypes: ['credit'] 
    }         
}]; 
```

该 [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 参数包含商家希望向客户传达交易的相关信息。  其中包括影响付款金额的订单汇总项目，如 "总计"、"税金"、"运输金额" 以及其他汇总级别项目。 它们不应作为订单行项目。 
  
该 [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 参数还用于定义在需要时可供客户使用的装运选项。  下面**的 "发货" 部分包含更**多详细信息。 

每 [`detail`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 行都包含货币和金额的标签。  

> [!NOTE]
> **付款请求**不会计算这些金额的总和或总额。  由商家的网站负责确保明细项目的总数正确。   


![小计、运费、税金和总详细信息](./../media/show_details.png)

```js
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

[`PaymentRequest`](https://msdn.microsoft.com/library/mt790440)不支持退款，因此金额应始终为正数;单个列表项可以是负数，例如折扣。 

浏览器将在你定义标签时呈现这些标签，并根据客户的区域设置自动呈现正确的货币格式。 请注意，标签应呈现为与内容相同的语言。 

该 [`options`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 参数定义网页希望从**付款请求**返回的数据。 这还定义需要收集的数据，包括是否需要装运、电子邮件地址和/或电话号码。

![电子邮件地址下拉列表](./../media/email_snippet.png)


```js
var options =
    {
        requestPayerEmail: true
    }; 
``` 

## 显示付款请求

该 [`show()`](https://msdn.microsoft.com/library/mt790448) 方法由网页调用，以允许用户与**付款请求**用户界面进行交互。  该 [`show()`](https://msdn.microsoft.com/library/mt790448) 方法返回将在用户批准付款请求时解决的承诺。  

```js
paymentRequest.show().then(paymentInstrumentResponse => {

paymentInstrumentResponse.complete('success').then().catch(error => {
    handlePaymentRequestError(error); 
});
```

![确认和支付详细信息](./../media/pay_screen_default.png)

## 终止付款请求
 
在 [`abort()`](https://msdn.microsoft.com/library/mt790437) 调用该方法后的任何时候，都可以在网页上调用该方法 [`show()`](https://msdn.microsoft.com/library/mt790448) ，直到解决该承诺的点。  此 [`abort()`](https://msdn.microsoft.com/library/mt790437) 方法将导致浏览器中止**付款请求**并关闭**付款请求**用户界面。  例如，如果用户在所需的时间量内未完成事务，则可以选择终止网页。

```js
payment.abort();
``` 

## 付款答复
当客户批准**付款请求**时，将向网站返回**付款响应**。 **付款响应**包括以下内容： 

 属性      | 说明 | 必需 | 其他信息
|---------------|-----------------|-------|-----------------|
[`methodName`](https://msdn.microsoft.com/library/mt790656) | 用户选择的付款方式的 ID | Y | | 
[`details`](https://msdn.microsoft.com/library/mt790655) | 一个 JSON 对象，其中包含商人使用所选付款方式或付款标记处理交易时所需的所有数据 | Y | [基本卡](https://go.microsoft.com/fwlink/?linkid=834965)词典： cardholderName;cardNumber;expiryMonth;expiryYear;cardSecurityCode;billingAddress; | 
[`shippingAddress`](https://msdn.microsoft.com/library/mt790445) | 用户选择的装运地址  |  可选。 当 [`requestShipping`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) 为**True**时需要  | 地址词典：国家/地区;addressLine;地区—dependentLocality;邮政编码sortingCode;languageCode;所在收信电话 |
[`shippingOption`](https://msdn.microsoft.com/library/mt790446) | 所选装运选项的 ID | 可选。 当 [`requestShipping`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) 为**True**时需要  | | 
[`payerName`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) | 用户提供的名称  | 可选。 当 [`requestPayerName`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) 为**True**时需要 | |
[`payerEmail`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) | 用户选择的电子邮件地址 | 可选。 当 [`requestPayerEmail`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) 为**True**时需要  | |
[`PayerPhone`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) | 用户选择的电话号码 | 可选。 当 [`requestPayerPhone`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) 为**True**时需要 | |

[`details`](https://msdn.microsoft.com/library/mt790655#PaymentRequest_params)**付款响应**中的 JSON 对象将包含商家处理付款所需的支付数据。 在最简单的形式中，该响应将是包含明文支付卡详细信息的[基本卡](https://go.microsoft.com/fwlink/?linkid=834965)负载。 如果商家与其他网关/处理器合作伙伴进行了安排以提供付款支持，则商家可能需要处理器可以处理的负载。 它们可以采用处理器/网关令牌或加密付款方式的形状。 这些支付方式超出本文档的范围，将在特定于处理器的文档中介绍。 此外，若要接收[基本的卡](https://go.microsoft.com/fwlink/?linkid=834965)响应，开发人员不需要额外的 Microsoft 加入 Microsoft，这与其他处理器/网关特定的付款方式（可能需要加密密钥加入或请求授权（oauth））不同。 

收到**付款响应**后，网站将向其付款处理者提交付款信息。  在处理付款时，浏览器将显示一个微调框页面。

![处理付款时显示的页面](./../media/loading_screen.png)

付款完成后，网页将调用该 [`complete()`](https://msdn.microsoft.com/library/mt790642) 方法并传递**成功**或**失败**的值。  该 [`complete()`](https://msdn.microsoft.com/library/mt790642) 方法通知浏览器购买已完成，应根据**成功**或**失败**的值显示相应的终止 UI 屏幕。 

![当采购成功时显示的 UI 当 ](./../media/response_payment-request_complete.png)
![ 购买失败时显示的 ui](./../media/response_payment-request_failure.png)

## 带装运的付款请求

### 送货地址

对于需要装运实际货物的销售，需要装运地址。  若要包括装运地址，请 `requestShipping = True` 在请求的参数中设置 [`options`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 。   

当用户选择或更新装运地址时， [`onshippingaddresschange`](https://msdn.microsoft.com/library/mt790442) 将运行该事件。  使用事件侦听器的网站将知道所做的更改，然后可以验证地址、重新计算运费和税款以及更新， [`shippingOptions`](https://msdn.microsoft.com/library/mt790440) 以反映所选地址可用的已更改的成本和运输选项（如果适用）。 

### 送货选项 

通过向该参数添加，可以向客户显示装运选项 [`shippingOptions`](https://msdn.microsoft.com/library/mt790440) [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 。  可通过 `selected = True` 为其中一个装运选项设置来建立默认值。 
 
当用户选择或更新 shippingOptions 时， [`onshippingoptionchange`](https://msdn.microsoft.com/library/mt790436) 将运行该事件。  使用事件侦听器的网站将知道所做的更改，并且可以使用 [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 正确的运输金额更新参数。   

```js
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
[付款请求 API](https://msdn.microsoft.com/library/mt790447)

## 书
[付款请求 API](https://w3.org/TR/payment-request/)

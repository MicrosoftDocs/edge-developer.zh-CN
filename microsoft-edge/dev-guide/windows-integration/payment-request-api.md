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
# <span data-ttu-id="f4c9c-104">付款请求 API</span><span class="sxs-lookup"><span data-stu-id="f4c9c-104">Payment Request API</span></span>

<span data-ttu-id="f4c9c-105">电子商务销售继续以快速节奏的速度增长。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-105">E-commerce sales continue growing at a rapid pace.</span></span> <span data-ttu-id="f4c9c-106">根据[eMarketer](https://www.emarketer.com/)，我们预测，2018将按2013中的级别增加23% 的数字销售。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-106">According to [eMarketer](https://www.emarketer.com/), by 2018 digital sales are forecasted to increase by 23% from the levels measured in 2013.</span></span>  <span data-ttu-id="f4c9c-107">消费者和企业享受电子商务销售的便利，但挑战仍然存在。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-107">While consumers and businesses enjoy the convenience of e-commerce sales, challenges remain.</span></span>  <span data-ttu-id="f4c9c-108">如今，每个电子商务网站所有者都需要花费大量时间来开发优质付款结帐流程和验证规则。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-108">Today each e-commerce website owner needs to invest time to develop high quality payment checkout flows and validation rules.</span></span>  <span data-ttu-id="f4c9c-109">消费者需要导航不同的付款结算流程，并在他们购买的每个网站上重新输入相同的支付和运输信息。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-109">Consumers need to navigate different payment checkout flows and re-enter the same payment and shipping information on every site where they shop.</span></span>  <span data-ttu-id="f4c9c-110">对于消费者来说，这可能会非常耗时且令人沮丧，从而提高了购物车的 abandonment，并降低了商家的销售额。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-110">This can be time consuming and frustrating for consumers, leading to a high rate of shopping cart abandonment and decreased sales for merchants.</span></span> <span data-ttu-id="f4c9c-111">将放弃购买车60% 和70% 之间的商家[估计](http://baymard.com/lists/cart-abandonment-rate)。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-111">Merchants [estimate](http://baymard.com/lists/cart-abandonment-rate) between 60% and 70% of shopping carts are abandoned.</span></span>      

<span data-ttu-id="f4c9c-112">[付款请求 API](https://w3.org/TR/payment-request/)标准化付款结算流程。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-112">The [Payment Request API](https://w3.org/TR/payment-request/) standardizes the payment checkout process.</span></span> <span data-ttu-id="f4c9c-113">对于 web 开发人员而言，此 API 需要较少的自定义，并且为使用者提供更快、更一致且更一致的体验。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-113">This API requires less customization for web developers and provides a faster, more consistent, and therefore, less confusing experience for consumers.</span></span>  <span data-ttu-id="f4c9c-114">由于消费者可以从其 Microsoft 帐户选择支付方式和送货地址，因此他们需要输入较少的数据来完成购买，从而减少完成付款所需的时间和数据输入。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-114">Because consumers can select payment instruments and shipping addresses from their Microsoft account, they are required to enter less data to complete purchases which reduces the time and data entry required to complete a payment.</span></span>   

<span data-ttu-id="f4c9c-115">[支付请求 API](https://w3.org/TR/payment-request/)是一个开放的跨浏览器标准，使浏览器能够充当消费者、消费者以及消费者在云中存储的支付方式（例如信用卡）之间的媒介。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-115">The [Payment Request API](https://w3.org/TR/payment-request/) is an open, cross-browser standard that enables browsers to act as an intermediary between merchants, consumers, and the payment methods (e.g. credit cards) that consumers have stored in the cloud.</span></span> 
  
<span data-ttu-id="f4c9c-116">总而言之，在使用[付款请求 API](https://w3.org/TR/payment-request/)时，客户以正常方式在商家网站上购物。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-116">In summary, when using the [Payment Request API](https://w3.org/TR/payment-request/), customers shop on merchant websites as normal.</span></span>  <span data-ttu-id="f4c9c-117">当准备好支付时，商家网站将调用**付款请求**API 来创建**付款请求**，并将相关的付款信息（如支持的支付方式、购买金额、货币等）传递到浏览器。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-117">When ready to pay, the merchant website calls the **Payment Request** API to create a **Payment Request** and passes the relevant payment information (e.g. supported payment methods, purchase amount, currency, etc.) to the browser.</span></span>

![付款请求构造](./../media/payment_request_construct.png)

<span data-ttu-id="f4c9c-119">浏览器对用户进行身份验证，允许用户选择受支持的文件支付方式，并处理付款详细信息。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-119">The browser authenticates the user, enables the user to select a supported payment method on file, and processes the payment details.</span></span> <span data-ttu-id="f4c9c-120">然后，浏览器会将付款信息的详细信息发送回商家网站，以便商家可以完成付款。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-120">The browser then sends the payment information details back to the merchant website, so that the merchant can complete the payment.</span></span>  <span data-ttu-id="f4c9c-121">除了接收付款信息，商家还可以选择接收作为**付款请求**一部分的装运信息。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-121">In addition to receiving payment information, the merchant can also elect to receive shipping information as part of the **Payment Request**.</span></span>  

![付款响应构造](./../media/payment_response_construct.png)

<span data-ttu-id="f4c9c-123">若要查看付款请求 API 的工作方式，并大致了解如何使用它，请查看此视频。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-123">To see the Payment Request API in action, as well as get an overview of how to use it, check out this video.</span></span>

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Using-the-Payments-Request-API/player]


> [!NOTE]
> <span data-ttu-id="f4c9c-124">"付款请求" API 在 Microsoft Edge 内部版本 14992 + 中受支持。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-124">The Payment Request API is supported in Microsoft Edge build 14992+.</span></span>


## <span data-ttu-id="f4c9c-125">创建付款请求</span><span class="sxs-lookup"><span data-stu-id="f4c9c-125">Creating a Payment Request</span></span> 
<span data-ttu-id="f4c9c-126">当用户通过单击 "购买" 按钮启动付款流程时，网页通常会创建**付款请求**。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-126">Web pages create a **Payment Request** typically when the user initiates a payment process by clicking a "buy" button.</span></span>  <span data-ttu-id="f4c9c-127">**付款请求**[构造函数](https://msdn.microsoft.com/library/mt790440)包括 methodData、详细信息和选项。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-127">The **Payment Request** [constructor](https://msdn.microsoft.com/library/mt790440) includes methodData, details, and options.</span></span> 

```js
var payment = new PaymentRequest ( 
    methodData,  // required payment method data including payment method identifiers 
    details,     // required transaction information 
    options      // optional information like shipping or contact info to be returned 
); 
```

<span data-ttu-id="f4c9c-128">该 [`methodData`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 参数包含网站接受的付款方式和网络以及任何关联的付款方式特定数据的列表。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-128">The [`methodData`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) parameter contains a list of the payment methods and networks accepted by the website and any associated payment method specific data.</span></span> <span data-ttu-id="f4c9c-129">在 Microsoft Edge 中，此列表与购物者在其 Microsoft 帐户中保存的支持支付方式相匹配，并在付款用户体验中产生 "支付方式" 列表。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-129">In Microsoft Edge, this list is matched with the supported payment methods that the shopper has saved in their Microsoft account and results in the "pay with" list in the payment user experience.</span></span>

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

<span data-ttu-id="f4c9c-131">该 [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 参数包含商家希望向客户传达交易的相关信息。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-131">The [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) parameter contains information that the merchant wishes to convey to the customer about the transaction.</span></span>  <span data-ttu-id="f4c9c-132">其中包括影响付款金额的订单汇总项目，如 "总计"、"税金"、"运输金额" 以及其他汇总级别项目。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-132">These include order summary items like total, tax, shipping amount, and other summary level items impacting the payment amount.</span></span> <span data-ttu-id="f4c9c-133">它们不应作为订单行项目。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-133">These are not intended to be order line items.</span></span> 
  
<span data-ttu-id="f4c9c-134">该 [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 参数还用于定义在需要时可供客户使用的装运选项。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-134">The [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) parameter is also used to define shipping options available to the customer when required.</span></span>  <span data-ttu-id="f4c9c-135">下面**的 "发货" 部分包含更**多详细信息。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-135">More details are included in the **Payment Request** with Shipping section below.</span></span> 

<span data-ttu-id="f4c9c-136">每 [`detail`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 行都包含货币和金额的标签。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-136">Each [`detail`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) line includes a label for the currency and the amount.</span></span>  

> [!NOTE]
> <span data-ttu-id="f4c9c-137">**付款请求**不会计算这些金额的总和或总额。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-137">The **Payment Request** does not calculate the sum or total of these amounts.</span></span>  <span data-ttu-id="f4c9c-138">由商家的网站负责确保明细项目的总数正确。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-138">It is the responsibility of the merchant's website to ensure that the line items total correctly.</span></span>   


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

<span data-ttu-id="f4c9c-140">[`PaymentRequest`](https://msdn.microsoft.com/library/mt790440)不支持退款，因此金额应始终为正数;单个列表项可以是负数，例如折扣。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-140">[`PaymentRequest`](https://msdn.microsoft.com/library/mt790440) does not support refunds, so the amounts should always be positive; individual list items can be negative, such as discounts.</span></span> 

<span data-ttu-id="f4c9c-141">浏览器将在你定义标签时呈现这些标签，并根据客户的区域设置自动呈现正确的货币格式。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-141">The browser will render the labels as you define them and automatically render the correct currency formatting based on the customer's locale.</span></span> <span data-ttu-id="f4c9c-142">请注意，标签应呈现为与内容相同的语言。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-142">Note that the labels should be rendered in the same language as your content.</span></span> 

<span data-ttu-id="f4c9c-143">该 [`options`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 参数定义网页希望从**付款请求**返回的数据。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-143">The [`options`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) parameter defines data the web page wants returned from the **Payment Request**.</span></span> <span data-ttu-id="f4c9c-144">这还定义需要收集的数据，包括是否需要装运、电子邮件地址和/或电话号码。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-144">This also defines the data that needs to be collected, including if shipping, email address, and/or phone number are required.</span></span>

![电子邮件地址下拉列表](./../media/email_snippet.png)


```js
var options =
    {
        requestPayerEmail: true
    }; 
``` 

## <span data-ttu-id="f4c9c-146">显示付款请求</span><span class="sxs-lookup"><span data-stu-id="f4c9c-146">Showing the Payment Request</span></span>

<span data-ttu-id="f4c9c-147">该 [`show()`](https://msdn.microsoft.com/library/mt790448) 方法由网页调用，以允许用户与**付款请求**用户界面进行交互。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-147">The [`show()`](https://msdn.microsoft.com/library/mt790448) method is called by the web page to allow the user to interact with the **Payment Request** user interface.</span></span>  <span data-ttu-id="f4c9c-148">该 [`show()`](https://msdn.microsoft.com/library/mt790448) 方法返回将在用户批准付款请求时解决的承诺。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-148">The [`show()`](https://msdn.microsoft.com/library/mt790448) method returns a Promise that will be resolved when the user authorizes the payment request.</span></span>  

```js
paymentRequest.show().then(paymentInstrumentResponse => {

paymentInstrumentResponse.complete('success').then().catch(error => {
    handlePaymentRequestError(error); 
});
```

![确认和支付详细信息](./../media/pay_screen_default.png)

## <span data-ttu-id="f4c9c-150">终止付款请求</span><span class="sxs-lookup"><span data-stu-id="f4c9c-150">Aborting a Payment Request</span></span>
 
<span data-ttu-id="f4c9c-151">在 [`abort()`](https://msdn.microsoft.com/library/mt790437) 调用该方法后的任何时候，都可以在网页上调用该方法 [`show()`](https://msdn.microsoft.com/library/mt790448) ，直到解决该承诺的点。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-151">The [`abort()`](https://msdn.microsoft.com/library/mt790437) method can be called by the web page any time after the [`show()`](https://msdn.microsoft.com/library/mt790448) method is called, up until the point where the Promise is resolved.</span></span>  <span data-ttu-id="f4c9c-152">此 [`abort()`](https://msdn.microsoft.com/library/mt790437) 方法将导致浏览器中止**付款请求**并关闭**付款请求**用户界面。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-152">The [`abort()`](https://msdn.microsoft.com/library/mt790437) method will cause the browser to abort the **Payment Request** and close the **Payment Request** user interface.</span></span>  <span data-ttu-id="f4c9c-153">例如，如果用户在所需的时间量内未完成事务，则可以选择终止网页。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-153">For example, a web page may choose to abort if the user did not complete the transaction in the required amount of time.</span></span>

```js
payment.abort();
``` 

## <span data-ttu-id="f4c9c-154">付款答复</span><span class="sxs-lookup"><span data-stu-id="f4c9c-154">Payment Response</span></span>
<span data-ttu-id="f4c9c-155">当客户批准**付款请求**时，将向网站返回**付款响应**。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-155">When the customer approves the **Payment Request**, a **Payment Response** is returned to the website.</span></span> <span data-ttu-id="f4c9c-156">**付款响应**包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="f4c9c-156">The **Payment Response** includes the following:</span></span> 

 <span data-ttu-id="f4c9c-157">属性</span><span class="sxs-lookup"><span data-stu-id="f4c9c-157">Property</span></span>      | <span data-ttu-id="f4c9c-158">说明</span><span class="sxs-lookup"><span data-stu-id="f4c9c-158">Description</span></span> | <span data-ttu-id="f4c9c-159">必需</span><span class="sxs-lookup"><span data-stu-id="f4c9c-159">Required</span></span> | <span data-ttu-id="f4c9c-160">其他信息</span><span class="sxs-lookup"><span data-stu-id="f4c9c-160">Additional Info</span></span>
|---------------|-----------------|-------|-----------------|
[`methodName`](https://msdn.microsoft.com/library/mt790656) | <span data-ttu-id="f4c9c-161">用户选择的付款方式的 ID</span><span class="sxs-lookup"><span data-stu-id="f4c9c-161">The ID for the payment method selected by the user</span></span> | <span data-ttu-id="f4c9c-162">Y</span><span class="sxs-lookup"><span data-stu-id="f4c9c-162">Y</span></span> | | 
[`details`](https://msdn.microsoft.com/library/mt790655) | <span data-ttu-id="f4c9c-163">一个 JSON 对象，其中包含商人使用所选付款方式或付款标记处理交易时所需的所有数据</span><span class="sxs-lookup"><span data-stu-id="f4c9c-163">A JSON object that includes all of the data the merchant requires to process the transaction using the selected payment method or a payment token</span></span> | <span data-ttu-id="f4c9c-164">Y</span><span class="sxs-lookup"><span data-stu-id="f4c9c-164">Y</span></span> | <span data-ttu-id="f4c9c-165">[基本卡](https://go.microsoft.com/fwlink/?linkid=834965)词典： cardholderName;cardNumber;expiryMonth;expiryYear;cardSecurityCode;billingAddress;</span><span class="sxs-lookup"><span data-stu-id="f4c9c-165">[Basic Card](https://go.microsoft.com/fwlink/?linkid=834965) Dictionary: cardholderName; cardNumber; expiryMonth; expiryYear; cardSecurityCode; billingAddress;</span></span> | 
[`shippingAddress`](https://msdn.microsoft.com/library/mt790445) | <span data-ttu-id="f4c9c-166">用户选择的装运地址</span><span class="sxs-lookup"><span data-stu-id="f4c9c-166">The shipping address selected by the user</span></span>  |  <span data-ttu-id="f4c9c-167">可选。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-167">Optional.</span></span> <span data-ttu-id="f4c9c-168">当 [`requestShipping`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) 为**True**时需要</span><span class="sxs-lookup"><span data-stu-id="f4c9c-168">Required when [`requestShipping`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) is **True**</span></span>  | <span data-ttu-id="f4c9c-169">地址词典：国家/地区;addressLine;地区—dependentLocality;邮政编码sortingCode;languageCode;所在收信电话</span><span class="sxs-lookup"><span data-stu-id="f4c9c-169">Address dictionary: country; addressLine; region; city; dependentLocality; postalCode; sortingCode; languageCode; organization; recipient; phone</span></span> |
[`shippingOption`](https://msdn.microsoft.com/library/mt790446) | <span data-ttu-id="f4c9c-170">所选装运选项的 ID</span><span class="sxs-lookup"><span data-stu-id="f4c9c-170">The ID for the selected shipping option</span></span> | <span data-ttu-id="f4c9c-171">可选。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-171">Optional.</span></span> <span data-ttu-id="f4c9c-172">当 [`requestShipping`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) 为**True**时需要</span><span class="sxs-lookup"><span data-stu-id="f4c9c-172">Required when [`requestShipping`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) is **True**</span></span>  | | 
[`payerName`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) | <span data-ttu-id="f4c9c-173">用户提供的名称</span><span class="sxs-lookup"><span data-stu-id="f4c9c-173">The name provided by the user</span></span>  | <span data-ttu-id="f4c9c-174">可选。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-174">Optional.</span></span> <span data-ttu-id="f4c9c-175">当 [`requestPayerName`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) 为**True**时需要</span><span class="sxs-lookup"><span data-stu-id="f4c9c-175">Required when [`requestPayerName`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) is **True**</span></span> | |
[`payerEmail`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) | <span data-ttu-id="f4c9c-176">用户选择的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="f4c9c-176">The email address selected by the user</span></span> | <span data-ttu-id="f4c9c-177">可选。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-177">Optional.</span></span> <span data-ttu-id="f4c9c-178">当 [`requestPayerEmail`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) 为**True**时需要</span><span class="sxs-lookup"><span data-stu-id="f4c9c-178">Required when [`requestPayerEmail`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) is **True**</span></span>  | |
[`PayerPhone`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) | <span data-ttu-id="f4c9c-179">用户选择的电话号码</span><span class="sxs-lookup"><span data-stu-id="f4c9c-179">The phone number selected by the user</span></span> | <span data-ttu-id="f4c9c-180">可选。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-180">Optional.</span></span> <span data-ttu-id="f4c9c-181">当 [`requestPayerPhone`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) 为**True**时需要</span><span class="sxs-lookup"><span data-stu-id="f4c9c-181">Required when [`requestPayerPhone`](https://msdn.microsoft.com/library/mt790440#PaymentOptions) is **True**</span></span> | |

<span data-ttu-id="f4c9c-182">[`details`](https://msdn.microsoft.com/library/mt790655#PaymentRequest_params)**付款响应**中的 JSON 对象将包含商家处理付款所需的支付数据。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-182">The [`details`](https://msdn.microsoft.com/library/mt790655#PaymentRequest_params) JSON object in the **Payment Response** will contain the payment data required by the merchant to process a payment.</span></span> <span data-ttu-id="f4c9c-183">在最简单的形式中，该响应将是包含明文支付卡详细信息的[基本卡](https://go.microsoft.com/fwlink/?linkid=834965)负载。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-183">In its simplest form, the response will be a [Basic Card](https://go.microsoft.com/fwlink/?linkid=834965) payload containing cleartext payment card details.</span></span> <span data-ttu-id="f4c9c-184">如果商家与其他网关/处理器合作伙伴进行了安排以提供付款支持，则商家可能需要处理器可以处理的负载。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-184">Where merchants have arrangements with additional gateway/processor partners for them to provide payments support, the merchant may require a payload the processor can handle.</span></span> <span data-ttu-id="f4c9c-185">它们可以采用处理器/网关令牌或加密付款方式的形状。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-185">These can take the shape of a processor/gateway token or an encrypted payment instrument.</span></span> <span data-ttu-id="f4c9c-186">这些支付方式超出本文档的范围，将在特定于处理器的文档中介绍。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-186">These payment methods are outside the scope of this document and will be covered in documentation specific to the processor.</span></span> <span data-ttu-id="f4c9c-187">此外，若要接收[基本的卡](https://go.microsoft.com/fwlink/?linkid=834965)响应，开发人员不需要额外的 Microsoft 加入 Microsoft，这与其他处理器/网关特定的付款方式（可能需要加密密钥加入或请求授权（oauth））不同。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-187">Additionally, to receive a [Basic Card](https://go.microsoft.com/fwlink/?linkid=834965) response, no additional onboarding to Microsoft is required by the developer, unlike other processor/gateway specific payment methods which may require encryption key onboarding or request authorization (oauth).</span></span> 

<span data-ttu-id="f4c9c-188">收到**付款响应**后，网站将向其付款处理者提交付款信息。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-188">Upon receiving the **Payment Response**, the website submits the payment information to their payment processor.</span></span>  <span data-ttu-id="f4c9c-189">在处理付款时，浏览器将显示一个微调框页面。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-189">The browser will display a spinner page while the payment is being processed.</span></span>

![处理付款时显示的页面](./../media/loading_screen.png)

<span data-ttu-id="f4c9c-191">付款完成后，网页将调用该 [`complete()`](https://msdn.microsoft.com/library/mt790642) 方法并传递**成功**或**失败**的值。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-191">Once the payment is complete, the web page calls the [`complete()`](https://msdn.microsoft.com/library/mt790642) method and passes a value of **success** or **fail**.</span></span>  <span data-ttu-id="f4c9c-192">该 [`complete()`](https://msdn.microsoft.com/library/mt790642) 方法通知浏览器购买已完成，应根据**成功**或**失败**的值显示相应的终止 UI 屏幕。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-192">The [`complete()`](https://msdn.microsoft.com/library/mt790642) method informs the browser that the purchase is finished and the appropriate terminating UI screen should be shown depending on the value of **success** or **fail**.</span></span> 

![<span data-ttu-id="f4c9c-193">当采购成功时显示的 UI 当 ](./../media/response_payment-request_complete.png)
![ 购买失败时显示的 ui</span><span class="sxs-lookup"><span data-stu-id="f4c9c-193">The UI displayed when the purchase succeeded](./../media/response_payment-request_complete.png)
![The UI displayed when the purchase failed</span></span>](./../media/response_payment-request_failure.png)

## <span data-ttu-id="f4c9c-194">带装运的付款请求</span><span class="sxs-lookup"><span data-stu-id="f4c9c-194">Payment Request with Shipping</span></span>

### <span data-ttu-id="f4c9c-195">送货地址</span><span class="sxs-lookup"><span data-stu-id="f4c9c-195">Shipping Address</span></span>

<span data-ttu-id="f4c9c-196">对于需要装运实际货物的销售，需要装运地址。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-196">For sales that require shipping physical goods, a shipping address is required.</span></span>  <span data-ttu-id="f4c9c-197">若要包括装运地址，请 `requestShipping = True` 在请求的参数中设置 [`options`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-197">To include a shipping address, set `requestShipping = True` in the [`options`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) parameter of the request.</span></span>   

<span data-ttu-id="f4c9c-198">当用户选择或更新装运地址时， [`onshippingaddresschange`](https://msdn.microsoft.com/library/mt790442) 将运行该事件。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-198">When the user selects or updates the shipping address, the [`onshippingaddresschange`](https://msdn.microsoft.com/library/mt790442) event will run.</span></span>  <span data-ttu-id="f4c9c-199">使用事件侦听器的网站将知道所做的更改，然后可以验证地址、重新计算运费和税款以及更新， [`shippingOptions`](https://msdn.microsoft.com/library/mt790440) 以反映所选地址可用的已更改的成本和运输选项（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-199">The website, using an event listener, will be aware of the change and can then validate the address, re-calculate shipping costs and taxes, and update [`shippingOptions`](https://msdn.microsoft.com/library/mt790440) to reflect the changed costs and shipping options available for the address selected (if applicable).</span></span> 

### <span data-ttu-id="f4c9c-200">送货选项</span><span class="sxs-lookup"><span data-stu-id="f4c9c-200">Shipping Options</span></span> 

<span data-ttu-id="f4c9c-201">通过向该参数添加，可以向客户显示装运选项 [`shippingOptions`](https://msdn.microsoft.com/library/mt790440) [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-201">Shipping options can be presented to the customer by adding [`shippingOptions`](https://msdn.microsoft.com/library/mt790440) to the [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) parameter.</span></span>  <span data-ttu-id="f4c9c-202">可通过 `selected = True` 为其中一个装运选项设置来建立默认值。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-202">A default can be established by setting `selected = True` for one of the shipping options.</span></span> 
 
<span data-ttu-id="f4c9c-203">当用户选择或更新 shippingOptions 时， [`onshippingoptionchange`](https://msdn.microsoft.com/library/mt790436) 将运行该事件。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-203">When the user selects or updates the shippingOptions, the [`onshippingoptionchange`](https://msdn.microsoft.com/library/mt790436) event will run.</span></span>  <span data-ttu-id="f4c9c-204">使用事件侦听器的网站将知道所做的更改，并且可以使用 [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) 正确的运输金额更新参数。</span><span class="sxs-lookup"><span data-stu-id="f4c9c-204">The website, using an event listener, will be aware of the change and can update the [`details`](https://msdn.microsoft.com/library/mt790440#PaymentRequest_params) parameter with the correct shipping amount.</span></span>   

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

## <span data-ttu-id="f4c9c-205">API 参考</span><span class="sxs-lookup"><span data-stu-id="f4c9c-205">API Reference</span></span>
[<span data-ttu-id="f4c9c-206">付款请求 API</span><span class="sxs-lookup"><span data-stu-id="f4c9c-206">Payment Request API</span></span>](https://msdn.microsoft.com/library/mt790447)

## <span data-ttu-id="f4c9c-207">书</span><span class="sxs-lookup"><span data-stu-id="f4c9c-207">Specification</span></span>
[<span data-ttu-id="f4c9c-208">付款请求 API</span><span class="sxs-lookup"><span data-stu-id="f4c9c-208">Payment Request API</span></span>](https://w3.org/TR/payment-request/)

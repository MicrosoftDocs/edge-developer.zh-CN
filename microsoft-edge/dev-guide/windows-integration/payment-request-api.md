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
# <span data-ttu-id="47db4-104">付款请求 API (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="47db4-104">Payment Request API (EdgeHTML)</span></span>  

> [!NOTE]
> <span data-ttu-id="47db4-105">本文介绍 [早期版本的 Microsoft Edge][MicrosoftSupport44533505]中支持的工作流。</span><span class="sxs-lookup"><span data-stu-id="47db4-105">This article describes the workflow supported in the [legacy version of Microsoft Edge][MicrosoftSupport44533505].</span></span>  <span data-ttu-id="47db4-106">Microsoft Edge \ (Chromium \ ) 使用基于 Chromium 项目的不同实现支持付款请求 API。</span><span class="sxs-lookup"><span data-stu-id="47db4-106">Microsoft Edge \(Chromium\) supports the Payment Request API with a different implementation based on the Chromium project.</span></span>  

<span data-ttu-id="47db4-107">电子商务销售继续以快速节奏的速度增长。</span><span class="sxs-lookup"><span data-stu-id="47db4-107">E-commerce sales continue growing at a rapid pace.</span></span>  <span data-ttu-id="47db4-108">根据 [eMarketer](https://www.emarketer.com)，我们预测，2018将按2013中的级别增加23% 的数字销售。</span><span class="sxs-lookup"><span data-stu-id="47db4-108">According to [eMarketer](https://www.emarketer.com), by 2018 digital sales are forecasted to increase by 23% from the levels measured in 2013.</span></span>  <span data-ttu-id="47db4-109">消费者和企业享受电子商务销售的便利，但挑战仍然存在。</span><span class="sxs-lookup"><span data-stu-id="47db4-109">While consumers and businesses enjoy the convenience of e-commerce sales, challenges remain.</span></span>  <span data-ttu-id="47db4-110">如今，每个电子商务网站所有者都需要花费大量时间来开发优质付款结帐流程和验证规则。</span><span class="sxs-lookup"><span data-stu-id="47db4-110">Today each e-commerce website owner needs to invest time to develop high quality payment checkout flows and validation rules.</span></span>  <span data-ttu-id="47db4-111">消费者需要导航不同的付款结算流程，并在他们购买的每个网站上重新输入相同的支付和运输信息。</span><span class="sxs-lookup"><span data-stu-id="47db4-111">Consumers need to navigate different payment checkout flows and re-enter the same payment and shipping information on every site where they shop.</span></span>  <span data-ttu-id="47db4-112">对于消费者来说，这可能会非常耗时且令人沮丧，从而提高了购物车的 abandonment，并降低了商家的销售额。</span><span class="sxs-lookup"><span data-stu-id="47db4-112">This can be time consuming and frustrating for consumers, leading to a high rate of shopping cart abandonment and decreased sales for merchants.</span></span>  <span data-ttu-id="47db4-113">将放弃购买车60% 和70% 之间的商家 [估计](http://baymard.com/lists/cart-abandonment-rate) 。</span><span class="sxs-lookup"><span data-stu-id="47db4-113">Merchants [estimate](http://baymard.com/lists/cart-abandonment-rate) between 60% and 70% of shopping carts are abandoned.</span></span>  

<span data-ttu-id="47db4-114">[付款请求 API](https://w3.org/TR/payment-request)标准化付款结算流程。</span><span class="sxs-lookup"><span data-stu-id="47db4-114">The [Payment Request API](https://w3.org/TR/payment-request) standardizes the payment checkout process.</span></span>  <span data-ttu-id="47db4-115">对于 web 开发人员而言，此 API 需要较少的自定义，并且为使用者提供更快、更一致且更一致的体验。</span><span class="sxs-lookup"><span data-stu-id="47db4-115">This API requires less customization for web developers and provides a faster, more consistent, and therefore, less confusing experience for consumers.</span></span>  <span data-ttu-id="47db4-116">由于消费者可以从其 Microsoft 帐户选择支付方式和送货地址，因此他们需要输入较少的数据来完成购买，从而减少完成付款所需的时间和数据输入。</span><span class="sxs-lookup"><span data-stu-id="47db4-116">Because consumers can select payment instruments and shipping addresses from their Microsoft account, they are required to enter less data to complete purchases which reduces the time and data entry required to complete a payment.</span></span>  

<span data-ttu-id="47db4-117">[支付请求 API](https://w3.org/TR/payment-request)是一个开放的跨浏览器标准，使浏览器能够充当商家、消费者和支付方式 \ (（如信用卡）之间的媒介，例如，使用者已存储在云中的 ) 。</span><span class="sxs-lookup"><span data-stu-id="47db4-117">The [Payment Request API](https://w3.org/TR/payment-request) is an open, cross-browser standard that enables browsers to act as an intermediary between merchants, consumers, and the payment methods \(such as credit cards\) that consumers have stored in the cloud.</span></span>  
  
<span data-ttu-id="47db4-118">总而言之，在使用 [付款请求 API](https://w3.org/TR/payment-request)时，客户以正常方式在商家网站上购物。</span><span class="sxs-lookup"><span data-stu-id="47db4-118">In summary, when using the [Payment Request API](https://w3.org/TR/payment-request), customers shop on merchant websites as normal.</span></span>  <span data-ttu-id="47db4-119">当准备好支付时，商家网站将调用 **付款请求** API 来创建 **付款请求** 并将相关的付款信息 \ (，例如支持的支付方式、购买金额、货币等 \ ) 浏览器。</span><span class="sxs-lookup"><span data-stu-id="47db4-119">When ready to pay, the merchant website calls the **Payment Request** API to create a **Payment Request** and passes the relevant payment information \(such as supported payment methods, purchase amount, currency, and so on\) to the browser.</span></span>  

:::image type="complex" source="../media/payment_request_construct.png" alt-text="付款请求构造" lightbox="../media/payment_request_construct.png":::
   <span data-ttu-id="47db4-121">付款请求构造</span><span class="sxs-lookup"><span data-stu-id="47db4-121">Payment request construct</span></span>  
:::image-end:::  

<span data-ttu-id="47db4-122">浏览器对用户进行身份验证，允许用户选择受支持的文件支付方式，并处理付款详细信息。</span><span class="sxs-lookup"><span data-stu-id="47db4-122">The browser authenticates the user, enables the user to select a supported payment method on file, and processes the payment details.</span></span>  <span data-ttu-id="47db4-123">然后，浏览器会将付款信息的详细信息发送回商家网站，以便商家可以完成付款。</span><span class="sxs-lookup"><span data-stu-id="47db4-123">The browser then sends the payment information details back to the merchant website, so that the merchant can complete the payment.</span></span>  <span data-ttu-id="47db4-124">除了接收付款信息，商家还可以选择接收作为 **付款请求**一部分的装运信息。</span><span class="sxs-lookup"><span data-stu-id="47db4-124">In addition to receiving payment information, the merchant can also elect to receive shipping information as part of the **Payment Request**.</span></span>  

:::image type="complex" source="../media/payment_response_construct.png" alt-text="付款请求构造" lightbox="../media/payment_response_construct.png":::
   <span data-ttu-id="47db4-126">付款响应构造</span><span class="sxs-lookup"><span data-stu-id="47db4-126">Payment response construct</span></span>  
:::image-end:::  

<span data-ttu-id="47db4-127">若要查看付款请求 API 的工作方式，并大致了解如何使用它，请查看此视频。</span><span class="sxs-lookup"><span data-stu-id="47db4-127">To see the Payment Request API in action, as well as get an overview of how to use it, check out this video.</span></span>  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Using-the-Payments-Request-API/player]  

> [!NOTE]
> <span data-ttu-id="47db4-128">Microsoft Edge 内部版本14992或更高版本支持付款请求 API。</span><span class="sxs-lookup"><span data-stu-id="47db4-128">The Payment Request API is supported in Microsoft Edge build 14992 or newer.</span></span>  

## <span data-ttu-id="47db4-129">创建付款请求</span><span class="sxs-lookup"><span data-stu-id="47db4-129">Creating a Payment Request</span></span>  

<span data-ttu-id="47db4-130">当用户通过单击 "购买" 按钮启动付款流程时，网页通常会创建 **付款请求** 。</span><span class="sxs-lookup"><span data-stu-id="47db4-130">Web pages create a **Payment Request** typically when the user initiates a payment process by clicking a "buy" button.</span></span>  <span data-ttu-id="47db4-131">**付款请求**[构造函数](/previous-versions/mt790440(v=vs.85))包括 methodData、详细信息和选项。</span><span class="sxs-lookup"><span data-stu-id="47db4-131">The **Payment Request** [constructor](/previous-versions/mt790440(v=vs.85)) includes methodData, details, and options.</span></span>  

```javascript
var payment = new PaymentRequest ( 
    methodData,  // required payment method data including payment method identifiers 
    details,     // required transaction information 
    options      // optional information like shipping or contact info to be returned 
); 
```  

<span data-ttu-id="47db4-132">[MethodData](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)参数包含网站接受的支付方式和网络以及任何关联的付款方式特定数据的列表。</span><span class="sxs-lookup"><span data-stu-id="47db4-132">The [methodData](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter contains a list of the payment methods and networks accepted by the website and any associated payment method specific data.</span></span>  <span data-ttu-id="47db4-133">在 Microsoft Edge 中，此列表与购物者在其 Microsoft 帐户中保存的支持支付方式相匹配，并在付款用户体验中产生 "支付方式" 列表。</span><span class="sxs-lookup"><span data-stu-id="47db4-133">In Microsoft Edge, this list is matched with the supported payment methods that the shopper has saved in their Microsoft account and results in the "pay with" list in the payment user experience.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_with.png" alt-text="付款请求构造" lightbox="../media/pay_with.png":::
         <span data-ttu-id="47db4-135">Microsoft 钱包用户体验中的 " **支付方式** " 列表</span><span class="sxs-lookup"><span data-stu-id="47db4-135">The **pay with** list in the Microsoft Wallet user experience</span></span>  
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

<span data-ttu-id="47db4-136">" [详细信息](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) " 参数包含商家希望向客户传达交易的相关信息。</span><span class="sxs-lookup"><span data-stu-id="47db4-136">The [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter contains information that the merchant wishes to convey to the customer about the transaction.</span></span>  <span data-ttu-id="47db4-137">其中包括影响付款金额的订单汇总项目，如 "总计"、"税金"、"运输金额" 以及其他汇总级别项目。</span><span class="sxs-lookup"><span data-stu-id="47db4-137">These include order summary items like total, tax, shipping amount, and other summary level items impacting the payment amount.</span></span>  <span data-ttu-id="47db4-138">它们不应作为订单行项目。</span><span class="sxs-lookup"><span data-stu-id="47db4-138">These are not intended to be order line items.</span></span>  
  
<span data-ttu-id="47db4-139">" [详细信息](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) " 参数还用于定义在需要时可供客户使用的装运选项。</span><span class="sxs-lookup"><span data-stu-id="47db4-139">The [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter is also used to define shipping options available to the customer when required.</span></span>  <span data-ttu-id="47db4-140">下面 **的 "发货" 部分包含更** 多详细信息。</span><span class="sxs-lookup"><span data-stu-id="47db4-140">More details are included in the **Payment Request** with Shipping section below.</span></span>  

<span data-ttu-id="47db4-141">每个 [明细](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 行都包含货币和金额的标签。</span><span class="sxs-lookup"><span data-stu-id="47db4-141">Each [detail](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) line includes a label for the currency and the amount.</span></span>  

> [!NOTE]
> <span data-ttu-id="47db4-142">**付款请求**不会计算这些金额的总和或总额。</span><span class="sxs-lookup"><span data-stu-id="47db4-142">The **Payment Request** does not calculate the sum or total of these amounts.</span></span>  <span data-ttu-id="47db4-143">由商家的网站负责确保明细项目的总数正确。</span><span class="sxs-lookup"><span data-stu-id="47db4-143">It is the responsibility of the merchant's website to ensure that the line items total correctly.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/show_details.png" alt-text="付款请求构造" lightbox="../media/show_details.png":::
         <span data-ttu-id="47db4-145">小计、运费、税金和总详细信息</span><span class="sxs-lookup"><span data-stu-id="47db4-145">Subtotal, shipping, taxes, and total details</span></span>  
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

<span data-ttu-id="47db4-146">[PaymentRequest](/previous-versions/mt790440(v=vs.85)) 不支持退款，因此金额应始终为正数;单个列表项可以是负数，例如折扣。</span><span class="sxs-lookup"><span data-stu-id="47db4-146">[PaymentRequest](/previous-versions/mt790440(v=vs.85)) does not support refunds, so the amounts should always be positive; individual list items can be negative, such as discounts.</span></span>  

<span data-ttu-id="47db4-147">浏览器将在你定义标签时呈现这些标签，并根据客户的区域设置自动呈现正确的货币格式。</span><span class="sxs-lookup"><span data-stu-id="47db4-147">The browser will render the labels as you define them and automatically render the correct currency formatting based on the customer's locale.</span></span>  <span data-ttu-id="47db4-148">请注意，标签应呈现为与内容相同的语言。</span><span class="sxs-lookup"><span data-stu-id="47db4-148">Note that the labels should be rendered in the same language as your content.</span></span>  

<span data-ttu-id="47db4-149">[选项](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)参数定义网页希望从**付款请求**返回的数据。</span><span class="sxs-lookup"><span data-stu-id="47db4-149">The [options](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter defines data the web page wants returned from the **Payment Request**.</span></span>  <span data-ttu-id="47db4-150">这还会定义需要收集的数据，包括装运、电子邮件地址、电话号码或全部必填。</span><span class="sxs-lookup"><span data-stu-id="47db4-150">This also defines the data that needs to be collected, including if shipping, email address, phone number or all are required.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/email_snippet.png" alt-text="付款请求构造" lightbox="../media/email_snippet.png":::
         <span data-ttu-id="47db4-152">电子邮件地址下拉列表</span><span class="sxs-lookup"><span data-stu-id="47db4-152">Email address dropdown</span></span>  
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

## <span data-ttu-id="47db4-153">显示付款请求</span><span class="sxs-lookup"><span data-stu-id="47db4-153">Showing the Payment Request</span></span>  

<span data-ttu-id="47db4-154">[显示 ( # B1](/previous-versions/mt790448(v=vs.85))方法由网页调用，以允许用户与**付款请求**用户界面进行交互。</span><span class="sxs-lookup"><span data-stu-id="47db4-154">The [show()](/previous-versions/mt790448(v=vs.85)) method is called by the web page to allow the user to interact with the **Payment Request** user interface.</span></span>  <span data-ttu-id="47db4-155">[Show ( # B1](/previous-versions/mt790448(v=vs.85))方法将返回一个承诺，该承诺将在用户批准付款请求时得到解决。</span><span class="sxs-lookup"><span data-stu-id="47db4-155">The [show()](/previous-versions/mt790448(v=vs.85)) method returns a Promise that will be resolved when the user authorizes the payment request.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_screen_default.png" alt-text="付款请求构造" lightbox="../media/pay_screen_default.png":::
         <span data-ttu-id="47db4-157">确认和支付详细信息</span><span class="sxs-lookup"><span data-stu-id="47db4-157">Confirm and pay details</span></span>  
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

## <span data-ttu-id="47db4-158">终止付款请求</span><span class="sxs-lookup"><span data-stu-id="47db4-158">Aborting a Payment Request</span></span>  
 
<span data-ttu-id="47db4-159">在 "[显示" ( # B3](/previous-versions/mt790448(v=vs.85))方法被调用后，任何时候都可以随时调用[Abort ( # B1](/previous-versions/mt790437(v=vs.85))方法，直到解决该承诺的点。</span><span class="sxs-lookup"><span data-stu-id="47db4-159">The [abort()](/previous-versions/mt790437(v=vs.85)) method can be called by the web page any time after the [show()](/previous-versions/mt790448(v=vs.85)) method is called, up until the point where the Promise is resolved.</span></span>  <span data-ttu-id="47db4-160">[Abort ( # B1](/previous-versions/mt790437(v=vs.85))方法将导致浏览器中止**付款请求**并关闭**付款请求**用户界面。</span><span class="sxs-lookup"><span data-stu-id="47db4-160">The [abort()](/previous-versions/mt790437(v=vs.85)) method will cause the browser to abort the **Payment Request** and close the **Payment Request** user interface.</span></span>  <span data-ttu-id="47db4-161">例如，如果用户在所需的时间量内未完成事务，则可以选择终止网页。</span><span class="sxs-lookup"><span data-stu-id="47db4-161">For example, a web page may choose to abort if the user did not complete the transaction in the required amount of time.</span></span>  

```javascript
payment.abort();
```  

## <span data-ttu-id="47db4-162">付款答复</span><span class="sxs-lookup"><span data-stu-id="47db4-162">Payment Response</span></span>  
<span data-ttu-id="47db4-163">当客户批准 **付款请求**时，将向网站返回 **付款响应** 。</span><span class="sxs-lookup"><span data-stu-id="47db4-163">When the customer approves the **Payment Request**, a **Payment Response** is returned to the website.</span></span>  <span data-ttu-id="47db4-164">**付款响应**包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="47db4-164">The **Payment Response** includes the following:</span></span>  

 <span data-ttu-id="47db4-165">属性</span><span class="sxs-lookup"><span data-stu-id="47db4-165">Property</span></span>      | <span data-ttu-id="47db4-166">说明</span><span class="sxs-lookup"><span data-stu-id="47db4-166">Description</span></span> | <span data-ttu-id="47db4-167">必需</span><span class="sxs-lookup"><span data-stu-id="47db4-167">Required</span></span> | <span data-ttu-id="47db4-168">其他信息</span><span class="sxs-lookup"><span data-stu-id="47db4-168">Additional Info</span></span>
|---------------|-----------------|-------|-----------------|
[<span data-ttu-id="47db4-169">名称</span><span class="sxs-lookup"><span data-stu-id="47db4-169">methodName</span></span>](/previous-versions/mt790656(v=vs.85)) | <span data-ttu-id="47db4-170">用户选择的付款方式的 ID</span><span class="sxs-lookup"><span data-stu-id="47db4-170">The ID for the payment method selected by the user</span></span> | <span data-ttu-id="47db4-171">Y</span><span class="sxs-lookup"><span data-stu-id="47db4-171">Y</span></span> | |   
[<span data-ttu-id="47db4-172">details</span><span class="sxs-lookup"><span data-stu-id="47db4-172">details</span></span>](/previous-versions/mt790655(v=vs.85)) | <span data-ttu-id="47db4-173">一个 JSON 对象，其中包含商人使用所选付款方式或付款标记处理交易时所需的所有数据</span><span class="sxs-lookup"><span data-stu-id="47db4-173">A JSON object that includes all of the data the merchant requires to process the transaction using the selected payment method or a payment token</span></span> | <span data-ttu-id="47db4-174">Y</span><span class="sxs-lookup"><span data-stu-id="47db4-174">Y</span></span> | <span data-ttu-id="47db4-175">[基本卡](https://w3c.github.io/payment-method-basic-card) 词典： cardholderName;cardNumber;expiryMonth;expiryYear;cardSecurityCode;billingAddress;</span><span class="sxs-lookup"><span data-stu-id="47db4-175">[Basic Card](https://w3c.github.io/payment-method-basic-card) Dictionary:  cardholderName; cardNumber; expiryMonth; expiryYear; cardSecurityCode; billingAddress;</span></span> |   
[<span data-ttu-id="47db4-176">shippingAddress</span><span class="sxs-lookup"><span data-stu-id="47db4-176">shippingAddress</span></span>](/previous-versions/mt790445(v=vs.85)) | <span data-ttu-id="47db4-177">用户选择的装运地址</span><span class="sxs-lookup"><span data-stu-id="47db4-177">The shipping address selected by the user</span></span>  |  <span data-ttu-id="47db4-178">可选。</span><span class="sxs-lookup"><span data-stu-id="47db4-178">Optional.</span></span>  <span data-ttu-id="47db4-179">[RequestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions)时需要</span><span class="sxs-lookup"><span data-stu-id="47db4-179">Required when [requestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True`  | <span data-ttu-id="47db4-180">地址词典：国家/地区;addressLine;地区—dependentLocality;邮政编码sortingCode;languageCode;所在收信电话</span><span class="sxs-lookup"><span data-stu-id="47db4-180">Address dictionary:  country; addressLine; region; city; dependentLocality; postalCode; sortingCode; languageCode; organization; recipient; phone</span></span> |  
[<span data-ttu-id="47db4-181">shippingOption</span><span class="sxs-lookup"><span data-stu-id="47db4-181">shippingOption</span></span>](/previous-versions/mt790446(v=vs.85)) | <span data-ttu-id="47db4-182">所选装运选项的 ID</span><span class="sxs-lookup"><span data-stu-id="47db4-182">The ID for the selected shipping option</span></span> | <span data-ttu-id="47db4-183">可选。</span><span class="sxs-lookup"><span data-stu-id="47db4-183">Optional.</span></span>  <span data-ttu-id="47db4-184">[RequestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions)时需要</span><span class="sxs-lookup"><span data-stu-id="47db4-184">Required when [requestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True`  | |   
[<span data-ttu-id="47db4-185">payerName</span><span class="sxs-lookup"><span data-stu-id="47db4-185">payerName</span></span>](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | <span data-ttu-id="47db4-186">用户提供的名称</span><span class="sxs-lookup"><span data-stu-id="47db4-186">The name provided by the user</span></span>  | <span data-ttu-id="47db4-187">可选。</span><span class="sxs-lookup"><span data-stu-id="47db4-187">Optional.</span></span>  <span data-ttu-id="47db4-188">[RequestPayerName](/previous-versions/mt790440(v=vs.85)#PaymentOptions)时需要</span><span class="sxs-lookup"><span data-stu-id="47db4-188">Required when [requestPayerName](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True` | |  
[<span data-ttu-id="47db4-189">payerEmail</span><span class="sxs-lookup"><span data-stu-id="47db4-189">payerEmail</span></span>](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | <span data-ttu-id="47db4-190">用户选择的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="47db4-190">The email address selected by the user</span></span> | <span data-ttu-id="47db4-191">可选。</span><span class="sxs-lookup"><span data-stu-id="47db4-191">Optional.</span></span>  <span data-ttu-id="47db4-192">[RequestPayerEmail](/previous-versions/mt790440(v=vs.85)#PaymentOptions)时需要</span><span class="sxs-lookup"><span data-stu-id="47db4-192">Required when [requestPayerEmail](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True`  | |  
[<span data-ttu-id="47db4-193">PayerPhone</span><span class="sxs-lookup"><span data-stu-id="47db4-193">PayerPhone</span></span>](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | <span data-ttu-id="47db4-194">用户选择的电话号码</span><span class="sxs-lookup"><span data-stu-id="47db4-194">The phone number selected by the user</span></span> | <span data-ttu-id="47db4-195">可选。</span><span class="sxs-lookup"><span data-stu-id="47db4-195">Optional.</span></span>  <span data-ttu-id="47db4-196">[RequestPayerPhone](/previous-versions/mt790440(v=vs.85)#PaymentOptions)时需要</span><span class="sxs-lookup"><span data-stu-id="47db4-196">Required when [requestPayerPhone](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True` | |  

<span data-ttu-id="47db4-197">**付款响应**中的[详细信息](/previous-versions/mt790655(v=vs.85)#PaymentRequest_params)JSON 对象将包含商家处理付款所需的支付数据。</span><span class="sxs-lookup"><span data-stu-id="47db4-197">The [details](/previous-versions/mt790655(v=vs.85)#PaymentRequest_params) JSON object in the **Payment Response** will contain the payment data required by the merchant to process a payment.</span></span>  <span data-ttu-id="47db4-198">在最简单的形式中，该响应将是包含明文支付卡详细信息的 [基本卡](https://w3c.github.io/payment-method-basic-card) 负载。</span><span class="sxs-lookup"><span data-stu-id="47db4-198">In its simplest form, the response will be a [Basic Card](https://w3c.github.io/payment-method-basic-card) payload containing cleartext payment card details.</span></span>  <span data-ttu-id="47db4-199">如果商家与其他网关/处理器合作伙伴进行了安排以提供付款支持，则商家可能需要处理器可以处理的负载。</span><span class="sxs-lookup"><span data-stu-id="47db4-199">Where merchants have arrangements with additional gateway/processor partners for them to provide payments support, the merchant may require a payload the processor can handle.</span></span>  <span data-ttu-id="47db4-200">它们可以采用处理器/网关令牌或加密付款方式的形状。</span><span class="sxs-lookup"><span data-stu-id="47db4-200">These can take the shape of a processor/gateway token or an encrypted payment instrument.</span></span>  <span data-ttu-id="47db4-201">这些支付方式超出本文档的范围，将在特定于处理器的文档中介绍。</span><span class="sxs-lookup"><span data-stu-id="47db4-201">These payment methods are outside the scope of this document and will be covered in documentation specific to the processor.</span></span>  <span data-ttu-id="47db4-202">此外，若要接收 [基本的卡](https://w3c.github.io/payment-method-basic-card) 响应，开发人员不需要额外的 Microsoft 加入 Microsoft，这与其他处理器/网关特定的支付方法（可能需要加密密钥）或请求授权 \ (oAuth \ ) 不同。</span><span class="sxs-lookup"><span data-stu-id="47db4-202">Additionally, to receive a [Basic Card](https://w3c.github.io/payment-method-basic-card) response, no additional onboarding to Microsoft is required by the developer, unlike other processor/gateway specific payment methods which may require encryption key onboarding or request authorization \(oAuth\).</span></span>  

<span data-ttu-id="47db4-203">收到 **付款响应**后，网站将向其付款处理者提交付款信息。</span><span class="sxs-lookup"><span data-stu-id="47db4-203">Upon receiving the **Payment Response**, the website submits the payment information to their payment processor.</span></span>  <span data-ttu-id="47db4-204">在处理付款时，浏览器将显示一个微调框页面。</span><span class="sxs-lookup"><span data-stu-id="47db4-204">The browser will display a spinner page while the payment is being processed.</span></span>  

:::image type="complex" source="../media/loading_screen.png" alt-text="付款请求构造" lightbox="../media/loading_screen.png":::
   <span data-ttu-id="47db4-206">处理付款时显示的页面</span><span class="sxs-lookup"><span data-stu-id="47db4-206">The page displayed when the payment is being processed</span></span>  
:::image-end:::  

<span data-ttu-id="47db4-207">付款完成后，网页将调用 [完整的 ( # B1 ](/previous-versions/mt790642(v=vs.85)) 方法并传递 **成功** 或 **失败**的值。</span><span class="sxs-lookup"><span data-stu-id="47db4-207">Once the payment is complete, the web page calls the [complete()](/previous-versions/mt790642(v=vs.85)) method and passes a value of **success** or **fail**.</span></span>  <span data-ttu-id="47db4-208">[完整的 ( # B1](/previous-versions/mt790642(v=vs.85))方法通知浏览器购买已完成，并且根据**成功**或**失败**的值，应显示相应的终止 UI 屏幕。</span><span class="sxs-lookup"><span data-stu-id="47db4-208">The [complete()](/previous-versions/mt790642(v=vs.85)) method informs the browser that the purchase is finished and the appropriate terminating UI screen should be shown depending on the value of **success** or **fail**.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_complete.png" alt-text="付款请求构造" lightbox="../media/response_payment-request_complete.png":::
         <span data-ttu-id="47db4-210">购买成功时显示的 UI</span><span class="sxs-lookup"><span data-stu-id="47db4-210">The UI displayed when the purchase succeeded</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_failure.png" alt-text="付款请求构造" lightbox="../media/response_payment-request_failure.png":::
         <span data-ttu-id="47db4-212">当购买失败时显示的 UI</span><span class="sxs-lookup"><span data-stu-id="47db4-212">The UI displayed when the purchase failed</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="47db4-213">带装运的付款请求</span><span class="sxs-lookup"><span data-stu-id="47db4-213">Payment Request with Shipping</span></span>  

### <span data-ttu-id="47db4-214">送货地址</span><span class="sxs-lookup"><span data-stu-id="47db4-214">Shipping Address</span></span>  

<span data-ttu-id="47db4-215">对于需要装运实际货物的销售，需要装运地址。</span><span class="sxs-lookup"><span data-stu-id="47db4-215">For sales that require shipping physical goods, a shipping address is required.</span></span>  <span data-ttu-id="47db4-216">若要包括装运地址，请 `requestShipping = True` 在请求的 " [选项](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) " 参数中设置。</span><span class="sxs-lookup"><span data-stu-id="47db4-216">To include a shipping address, set `requestShipping = True` in the [options](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter of the request.</span></span>  

<span data-ttu-id="47db4-217">当用户选择或更新送货地址时，将运行 [onshippingaddresschange](/previous-versions/mt790442(v=vs.85)) 事件。</span><span class="sxs-lookup"><span data-stu-id="47db4-217">When the user selects or updates the shipping address, the [onshippingaddresschange](/previous-versions/mt790442(v=vs.85)) event will run.</span></span>  <span data-ttu-id="47db4-218">使用事件侦听器的网站将知道更改，然后可以验证地址、重新计算运输成本和税款，并更新 [shippingOptions](/previous-versions/mt790440(v=vs.85)) 以反映所选地址的已更改的费用和送货选项 (\ ) 。</span><span class="sxs-lookup"><span data-stu-id="47db4-218">The website, using an event listener, will be aware of the change and can then validate the address, re-calculate shipping costs and taxes, and update [shippingOptions](/previous-versions/mt790440(v=vs.85)) to reflect the changed costs and shipping options available for the address selected \(if applicable\).</span></span>  

### <span data-ttu-id="47db4-219">送货选项</span><span class="sxs-lookup"><span data-stu-id="47db4-219">Shipping Options</span></span>  

<span data-ttu-id="47db4-220">通过将 [shippingOptions](/previous-versions/mt790440(v=vs.85)) 添加到 [详细信息](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 参数，可以向客户显示装运选项。</span><span class="sxs-lookup"><span data-stu-id="47db4-220">Shipping options can be presented to the customer by adding [shippingOptions](/previous-versions/mt790440(v=vs.85)) to the [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter.</span></span>  <span data-ttu-id="47db4-221">可通过 `selected = True` 为其中一个装运选项设置来建立默认值。</span><span class="sxs-lookup"><span data-stu-id="47db4-221">A default can be established by setting `selected = True` for one of the shipping options.</span></span>  
 
<span data-ttu-id="47db4-222">当用户选择或更新 shippingOptions 时，将运行 [onshippingoptionchange](/previous-versions/mt790436(v=vs.85)) 事件。</span><span class="sxs-lookup"><span data-stu-id="47db4-222">When the user selects or updates the shippingOptions, the [onshippingoptionchange](/previous-versions/mt790436(v=vs.85)) event will run.</span></span>  <span data-ttu-id="47db4-223">使用事件侦听器的网站将知道所做的更改，并且可以使用正确的运输金额更新 [详细信息](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 参数。</span><span class="sxs-lookup"><span data-stu-id="47db4-223">The website, using an event listener, will be aware of the change and can update the [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter with the correct shipping amount.</span></span>  

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

## <span data-ttu-id="47db4-224">API 参考</span><span class="sxs-lookup"><span data-stu-id="47db4-224">API Reference</span></span>  

[<span data-ttu-id="47db4-225">付款请求 API</span><span class="sxs-lookup"><span data-stu-id="47db4-225">Payment Request API</span></span>](/previous-versions/mt790447(v=vs.85))  

## <span data-ttu-id="47db4-226">书</span><span class="sxs-lookup"><span data-stu-id="47db4-226">Specification</span></span>
[<span data-ttu-id="47db4-227">付款请求 API</span><span class="sxs-lookup"><span data-stu-id="47db4-227">Payment Request API</span></span>](https://w3.org/TR/payment-request)

<!-- links -->  

[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  

[MicrosoftSupport44533505]: https://support.microsoft.com/help/4533505 "什么是 Microsoft Edge 旧版？"  

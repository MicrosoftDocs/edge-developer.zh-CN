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
# <span data-ttu-id="b1975-104">EdgeHTML (付款请求 API) </span><span class="sxs-lookup"><span data-stu-id="b1975-104">Payment Request API (EdgeHTML)</span></span>  

> [!NOTE]
> <span data-ttu-id="b1975-105">本文介绍了旧版 Microsoft Edge 中 [支持的工作流][MicrosoftSupport44533505]。</span><span class="sxs-lookup"><span data-stu-id="b1975-105">This article describes the workflow supported in the [legacy version of Microsoft Edge][MicrosoftSupport44533505].</span></span>  <span data-ttu-id="b1975-106">Microsoft Edge \ (Chromium\) 支持基于 Chromium 项目的不同实现付款请求 API。</span><span class="sxs-lookup"><span data-stu-id="b1975-106">Microsoft Edge \(Chromium\) supports the Payment Request API with a different implementation based on the Chromium project.</span></span>  

<span data-ttu-id="b1975-107">电子商务销售额继续以快速的速度增长。</span><span class="sxs-lookup"><span data-stu-id="b1975-107">E-commerce sales continue growing at a rapid pace.</span></span>  <span data-ttu-id="b1975-108">根据 [eMarketer，](https://www.emarketer.com)预计到 2018 年，数字销售额将比 2013 年的水平增长 23%。</span><span class="sxs-lookup"><span data-stu-id="b1975-108">According to [eMarketer](https://www.emarketer.com), by 2018 digital sales are forecasted to increase by 23% from the levels measured in 2013.</span></span>  <span data-ttu-id="b1975-109">虽然消费者和企业享受电子商务销售的便利，但挑战仍然存在。</span><span class="sxs-lookup"><span data-stu-id="b1975-109">While consumers and businesses enjoy the convenience of e-commerce sales, challenges remain.</span></span>  <span data-ttu-id="b1975-110">如今，每个电子商务网站所有者都需要投入时间来开发高质量的付款结帐流和验证规则。</span><span class="sxs-lookup"><span data-stu-id="b1975-110">Today each e-commerce website owner needs to invest time to develop high quality payment checkout flows and validation rules.</span></span>  <span data-ttu-id="b1975-111">消费者需要导航不同的付款结帐流程，并在他们购买的每一个网站重新输入相同的付款和发货信息。</span><span class="sxs-lookup"><span data-stu-id="b1975-111">Consumers need to navigate different payment checkout flows and re-enter the same payment and shipping information on every site where they shop.</span></span>  <span data-ttu-id="b1975-112">这对消费者来说可能非常耗时和沮丧，从而导致购物车的购买率很高，并且商家的销售额下降。</span><span class="sxs-lookup"><span data-stu-id="b1975-112">This can be time consuming and frustrating for consumers, leading to a high rate of shopping cart abandonment and decreased sales for merchants.</span></span>  <span data-ttu-id="b1975-113">商家 [估计](http://baymard.com/lists/cart-abandonment-rate) 放弃 60% 到 70% 的购物车。</span><span class="sxs-lookup"><span data-stu-id="b1975-113">Merchants [estimate](http://baymard.com/lists/cart-abandonment-rate) between 60% and 70% of shopping carts are abandoned.</span></span>  

<span data-ttu-id="b1975-114">付款 [请求 API](https://w3.org/TR/payment-request) 标准化了付款结帐过程。</span><span class="sxs-lookup"><span data-stu-id="b1975-114">The [Payment Request API](https://w3.org/TR/payment-request) standardizes the payment checkout process.</span></span>  <span data-ttu-id="b1975-115">此 API 要求 Web 开发人员的自定义更少，并且为使用者提供更快、更一致且更令人困惑的体验。</span><span class="sxs-lookup"><span data-stu-id="b1975-115">This API requires less customization for web developers and provides a faster, more consistent, and therefore, less confusing experience for consumers.</span></span>  <span data-ttu-id="b1975-116">由于消费者可以从其 Microsoft 帐户选择付款工具和送货地址，因此他们需要输入较少的数据才能完成购买，从而减少完成付款所需的时间和数据输入。</span><span class="sxs-lookup"><span data-stu-id="b1975-116">Because consumers can select payment instruments and shipping addresses from their Microsoft account, they are required to enter less data to complete purchases which reduces the time and data entry required to complete a payment.</span></span>  

<span data-ttu-id="b1975-117">付款请求 [API](https://w3.org/TR/payment-request) 是一个开放的跨浏览器标准，使浏览器能够充当商家、消费者以及消费者存储在云中的付款方式 \ (（如信用卡\) ）之间的中介。</span><span class="sxs-lookup"><span data-stu-id="b1975-117">The [Payment Request API](https://w3.org/TR/payment-request) is an open, cross-browser standard that enables browsers to act as an intermediary between merchants, consumers, and the payment methods \(such as credit cards\) that consumers have stored in the cloud.</span></span>  
  
<span data-ttu-id="b1975-118">总之，使用付款请求 [API](https://w3.org/TR/payment-request)时，客户会正常在商家网站上购买。</span><span class="sxs-lookup"><span data-stu-id="b1975-118">In summary, when using the [Payment Request API](https://w3.org/TR/payment-request), customers shop on merchant websites as normal.</span></span>  <span data-ttu-id="b1975-119">当准备好付款时，商家网站会调用付款请求**API**创建付款\*\*\*\* 请求，将相关付款信息 \ (如支持的付款方式、购买金额、货币等\) 传递给浏览器。</span><span class="sxs-lookup"><span data-stu-id="b1975-119">When ready to pay, the merchant website calls the **Payment Request** API to create a **Payment Request** and passes the relevant payment information \(such as supported payment methods, purchase amount, currency, and so on\) to the browser.</span></span>  

:::image type="complex" source="../media/payment_request_construct.png" alt-text="付款请求构造" lightbox="../media/payment_request_construct.png":::
   <span data-ttu-id="b1975-121">付款请求构造</span><span class="sxs-lookup"><span data-stu-id="b1975-121">Payment request construct</span></span>  
:::image-end:::  

<span data-ttu-id="b1975-122">浏览器对用户进行身份验证，使用户能够在文件上选择受支持的付款方式，并处理付款详细信息。</span><span class="sxs-lookup"><span data-stu-id="b1975-122">The browser authenticates the user, enables the user to select a supported payment method on file, and processes the payment details.</span></span>  <span data-ttu-id="b1975-123">浏览器随后将付款信息详细信息发送回商家网站，以便商家可以完成付款。</span><span class="sxs-lookup"><span data-stu-id="b1975-123">The browser then sends the payment information details back to the merchant website, so that the merchant can complete the payment.</span></span>  <span data-ttu-id="b1975-124">除了接收付款信息外，商家还可以选择接收付款请求中的发货 **信息**。</span><span class="sxs-lookup"><span data-stu-id="b1975-124">In addition to receiving payment information, the merchant can also elect to receive shipping information as part of the **Payment Request**.</span></span>  

:::image type="complex" source="../media/payment_response_construct.png" alt-text="付款响应构造" lightbox="../media/payment_response_construct.png":::
   <span data-ttu-id="b1975-126">付款响应构造</span><span class="sxs-lookup"><span data-stu-id="b1975-126">Payment response construct</span></span>  
:::image-end:::  

<span data-ttu-id="b1975-127">若要了解付款请求 API 的实现以及如何使用它的概述，请查看此视频。</span><span class="sxs-lookup"><span data-stu-id="b1975-127">To see the Payment Request API in action, as well as get an overview of how to use it, check out this video.</span></span>  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Using-the-Payments-Request-API/player]  

> [!NOTE]
> <span data-ttu-id="b1975-128">Microsoft Edge 版本 14992 或更高版本支持付款请求 API。</span><span class="sxs-lookup"><span data-stu-id="b1975-128">The Payment Request API is supported in Microsoft Edge build 14992 or newer.</span></span>  

## <span data-ttu-id="b1975-129">创建付款请求</span><span class="sxs-lookup"><span data-stu-id="b1975-129">Creating a Payment Request</span></span>  

<span data-ttu-id="b1975-130">网页 **通常在用户通过** 单击"购买"按钮启动付款流程时创建付款请求。</span><span class="sxs-lookup"><span data-stu-id="b1975-130">Web pages create a **Payment Request** typically when the user initiates a payment process by clicking a "buy" button.</span></span>  <span data-ttu-id="b1975-131">付款**请求构造函数**[](/previous-versions/mt790440(v=vs.85))包括 methodData、详细信息和选项。</span><span class="sxs-lookup"><span data-stu-id="b1975-131">The **Payment Request** [constructor](/previous-versions/mt790440(v=vs.85)) includes methodData, details, and options.</span></span>  

```javascript
var payment = new PaymentRequest ( 
    methodData,  // required payment method data including payment method identifiers 
    details,     // required transaction information 
    options      // optional information like shipping or contact info to be returned 
); 
```  

<span data-ttu-id="b1975-132">[methodData](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)参数包含网站接受的付款方式和网络列表以及任何关联的付款方式特定数据。</span><span class="sxs-lookup"><span data-stu-id="b1975-132">The [methodData](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter contains a list of the payment methods and networks accepted by the website and any associated payment method specific data.</span></span>  <span data-ttu-id="b1975-133">在 Microsoft Edge 中，此列表与购物者保存在 Microsoft 帐户中的受支持的付款方式匹配，并会导致付款用户体验中的"付费方式"列表。</span><span class="sxs-lookup"><span data-stu-id="b1975-133">In Microsoft Edge, this list is matched with the supported payment methods that the shopper has saved in their Microsoft account and results in the "pay with" list in the payment user experience.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_with.png" alt-text="Microsoft Wallet 用户体验中的付费列表" lightbox="../media/pay_with.png":::
         <span data-ttu-id="b1975-135">Microsoft **Wallet** 用户体验中的付费列表</span><span class="sxs-lookup"><span data-stu-id="b1975-135">The **pay with** list in the Microsoft Wallet user experience</span></span>  
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

<span data-ttu-id="b1975-136">[details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)参数包含商家希望与客户传达有关交易的信息。</span><span class="sxs-lookup"><span data-stu-id="b1975-136">The [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter contains information that the merchant wishes to convey to the customer about the transaction.</span></span>  <span data-ttu-id="b1975-137">其中包括订单摘要项目，如总额、税款、发货金额和其他影响付款金额的摘要级别项目。</span><span class="sxs-lookup"><span data-stu-id="b1975-137">These include order summary items like total, tax, shipping amount, and other summary level items impacting the payment amount.</span></span>  <span data-ttu-id="b1975-138">这些不用作订单行项。</span><span class="sxs-lookup"><span data-stu-id="b1975-138">These are not intended to be order line items.</span></span>  
  
<span data-ttu-id="b1975-139">[details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)参数还用于定义客户在需要时可用的送货选项。</span><span class="sxs-lookup"><span data-stu-id="b1975-139">The [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter is also used to define shipping options available to the customer when required.</span></span>  <span data-ttu-id="b1975-140">更多详细信息包含在下面的"付款 **请求** 及发货"部分。</span><span class="sxs-lookup"><span data-stu-id="b1975-140">More details are included in the **Payment Request** with Shipping section below.</span></span>  

<span data-ttu-id="b1975-141">每个 [明细](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 行包含货币和金额的标签。</span><span class="sxs-lookup"><span data-stu-id="b1975-141">Each [detail](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) line includes a label for the currency and the amount.</span></span>  

> [!NOTE]
> <span data-ttu-id="b1975-142">付款 **请求** 不会计算这些金额的总和或总计。</span><span class="sxs-lookup"><span data-stu-id="b1975-142">The **Payment Request** does not calculate the sum or total of these amounts.</span></span>  <span data-ttu-id="b1975-143">商家网站负责确保行项总数正确。</span><span class="sxs-lookup"><span data-stu-id="b1975-143">It is the responsibility of the merchant's website to ensure that the line items total correctly.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/show_details.png" alt-text="小计、发货、税款和总详细信息" lightbox="../media/show_details.png":::
         <span data-ttu-id="b1975-145">小计、发货、税款和总详细信息</span><span class="sxs-lookup"><span data-stu-id="b1975-145">Subtotal, shipping, taxes, and total details</span></span>  
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

<span data-ttu-id="b1975-146">[PaymentRequest](/previous-versions/mt790440(v=vs.85)) 不支持退款，因此金额应始终为正数;单个列表项可能为负数，例如折扣。</span><span class="sxs-lookup"><span data-stu-id="b1975-146">[PaymentRequest](/previous-versions/mt790440(v=vs.85)) does not support refunds, so the amounts should always be positive; individual list items can be negative, such as discounts.</span></span>  

<span data-ttu-id="b1975-147">浏览器将在定义标签时呈现标签，并基于客户区域设置自动呈现正确的货币格式。</span><span class="sxs-lookup"><span data-stu-id="b1975-147">The browser will render the labels as you define them and automatically render the correct currency formatting based on the customer's locale.</span></span>  <span data-ttu-id="b1975-148">请注意，标签应该以与内容相同的语言呈现。</span><span class="sxs-lookup"><span data-stu-id="b1975-148">Note that the labels should be rendered in the same language as your content.</span></span>  

<span data-ttu-id="b1975-149">[options](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)参数定义网页想要从付款请求**返回的数据**。</span><span class="sxs-lookup"><span data-stu-id="b1975-149">The [options](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter defines data the web page wants returned from the **Payment Request**.</span></span>  <span data-ttu-id="b1975-150">这还会定义需要收集的数据，包括是否必须寄送、电子邮件地址、电话号码或全部数据。</span><span class="sxs-lookup"><span data-stu-id="b1975-150">This also defines the data that needs to be collected, including if shipping, email address, phone number or all are required.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/email_snippet.png" alt-text="电子邮件地址下拉列表" lightbox="../media/email_snippet.png":::
         <span data-ttu-id="b1975-152">电子邮件地址下拉列表</span><span class="sxs-lookup"><span data-stu-id="b1975-152">Email address dropdown</span></span>  
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

## <span data-ttu-id="b1975-153">显示付款请求</span><span class="sxs-lookup"><span data-stu-id="b1975-153">Showing the Payment Request</span></span>  

<span data-ttu-id="b1975-154">[显示 () ](/previous-versions/mt790448(v=vs.85))方法由网页调用，以允许用户与付款**请求用户界面进行交互**。</span><span class="sxs-lookup"><span data-stu-id="b1975-154">The [show()](/previous-versions/mt790448(v=vs.85)) method is called by the web page to allow the user to interact with the **Payment Request** user interface.</span></span>  <span data-ttu-id="b1975-155">show [ () ](/previous-versions/mt790448(v=vs.85)) 方法返回将在用户授权付款请求时解析的 Promise。</span><span class="sxs-lookup"><span data-stu-id="b1975-155">The [show()](/previous-versions/mt790448(v=vs.85)) method returns a Promise that will be resolved when the user authorizes the payment request.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_screen_default.png" alt-text="确认和支付详细信息" lightbox="../media/pay_screen_default.png":::
         <span data-ttu-id="b1975-157">确认和支付详细信息</span><span class="sxs-lookup"><span data-stu-id="b1975-157">Confirm and pay details</span></span>  
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

## <span data-ttu-id="b1975-158">中止付款请求</span><span class="sxs-lookup"><span data-stu-id="b1975-158">Aborting a Payment Request</span></span>  
 
<span data-ttu-id="b1975-159">调用 [show ( () ](/previous-versions/mt790437(v=vs.85)) 方法后，网页随时都可以调用中止 [ () ](/previous-versions/mt790448(v=vs.85)) 方法，直到 Promise 解析到该点。</span><span class="sxs-lookup"><span data-stu-id="b1975-159">The [abort()](/previous-versions/mt790437(v=vs.85)) method can be called by the web page any time after the [show()](/previous-versions/mt790448(v=vs.85)) method is called, up until the point where the Promise is resolved.</span></span>  <span data-ttu-id="b1975-160">中止 [ () ](/previous-versions/mt790437(v=vs.85)) 方法将导致浏览器中止 **付款请求** 并关闭 **付款请求** 用户界面。</span><span class="sxs-lookup"><span data-stu-id="b1975-160">The [abort()](/previous-versions/mt790437(v=vs.85)) method will cause the browser to abort the **Payment Request** and close the **Payment Request** user interface.</span></span>  <span data-ttu-id="b1975-161">例如，如果用户未在所需时间完成事务，则网页可能会选择中止。</span><span class="sxs-lookup"><span data-stu-id="b1975-161">For example, a web page may choose to abort if the user did not complete the transaction in the required amount of time.</span></span>  

```javascript
payment.abort();
```  

## <span data-ttu-id="b1975-162">付款响应</span><span class="sxs-lookup"><span data-stu-id="b1975-162">Payment Response</span></span>  
<span data-ttu-id="b1975-163">当客户批准付款 **请求时**，付款 **响应** 将返回到网站。</span><span class="sxs-lookup"><span data-stu-id="b1975-163">When the customer approves the **Payment Request**, a **Payment Response** is returned to the website.</span></span>  <span data-ttu-id="b1975-164">付款 **响应** 包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="b1975-164">The **Payment Response** includes the following:</span></span>  

 <span data-ttu-id="b1975-165">属性</span><span class="sxs-lookup"><span data-stu-id="b1975-165">Property</span></span>      | <span data-ttu-id="b1975-166">说明</span><span class="sxs-lookup"><span data-stu-id="b1975-166">Description</span></span> | <span data-ttu-id="b1975-167">必需</span><span class="sxs-lookup"><span data-stu-id="b1975-167">Required</span></span> | <span data-ttu-id="b1975-168">其他信息</span><span class="sxs-lookup"><span data-stu-id="b1975-168">Additional Info</span></span>
|---------------|-----------------|-------|-----------------|
[<span data-ttu-id="b1975-169">methodName</span><span class="sxs-lookup"><span data-stu-id="b1975-169">methodName</span></span>](/previous-versions/mt790656(v=vs.85)) | <span data-ttu-id="b1975-170">用户选择的付款方式的 ID</span><span class="sxs-lookup"><span data-stu-id="b1975-170">The ID for the payment method selected by the user</span></span> | <span data-ttu-id="b1975-171">Y</span><span class="sxs-lookup"><span data-stu-id="b1975-171">Y</span></span> | |   
[<span data-ttu-id="b1975-172">details</span><span class="sxs-lookup"><span data-stu-id="b1975-172">details</span></span>](/previous-versions/mt790655(v=vs.85)) | <span data-ttu-id="b1975-173">包含商家使用所选付款方式或付款令牌处理交易所需的全部数据的 JSON 对象</span><span class="sxs-lookup"><span data-stu-id="b1975-173">A JSON object that includes all of the data the merchant requires to process the transaction using the selected payment method or a payment token</span></span> | <span data-ttu-id="b1975-174">Y</span><span class="sxs-lookup"><span data-stu-id="b1975-174">Y</span></span> | <span data-ttu-id="b1975-175">[基本卡片](https://w3c.github.io/payment-method-basic-card) 字典：dictionaryName;cardNumber;expiryMonth;expiryYear;cardSecurityCode;billingAddress;</span><span class="sxs-lookup"><span data-stu-id="b1975-175">[Basic Card](https://w3c.github.io/payment-method-basic-card) Dictionary:  cardholderName; cardNumber; expiryMonth; expiryYear; cardSecurityCode; billingAddress;</span></span> |   
[<span data-ttu-id="b1975-176">shippingAddress</span><span class="sxs-lookup"><span data-stu-id="b1975-176">shippingAddress</span></span>](/previous-versions/mt790445(v=vs.85)) | <span data-ttu-id="b1975-177">用户选择的送货地址</span><span class="sxs-lookup"><span data-stu-id="b1975-177">The shipping address selected by the user</span></span>  |  <span data-ttu-id="b1975-178">可选。</span><span class="sxs-lookup"><span data-stu-id="b1975-178">Optional.</span></span>  <span data-ttu-id="b1975-179">[requestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions)为必需</span><span class="sxs-lookup"><span data-stu-id="b1975-179">Required when [requestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True`  | <span data-ttu-id="b1975-180">地址字典：国家/地区;addressLine;region;city;dependentLocality;postalCode;sortingCode;languageCode;组织;recipient;phone</span><span class="sxs-lookup"><span data-stu-id="b1975-180">Address dictionary:  country; addressLine; region; city; dependentLocality; postalCode; sortingCode; languageCode; organization; recipient; phone</span></span> |  
[<span data-ttu-id="b1975-181">shippingOption</span><span class="sxs-lookup"><span data-stu-id="b1975-181">shippingOption</span></span>](/previous-versions/mt790446(v=vs.85)) | <span data-ttu-id="b1975-182">所选发货选项的 ID</span><span class="sxs-lookup"><span data-stu-id="b1975-182">The ID for the selected shipping option</span></span> | <span data-ttu-id="b1975-183">可选。</span><span class="sxs-lookup"><span data-stu-id="b1975-183">Optional.</span></span>  <span data-ttu-id="b1975-184">[requestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions)为必需</span><span class="sxs-lookup"><span data-stu-id="b1975-184">Required when [requestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True`  | |   
[<span data-ttu-id="b1975-185">payerName</span><span class="sxs-lookup"><span data-stu-id="b1975-185">payerName</span></span>](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | <span data-ttu-id="b1975-186">用户提供的名称</span><span class="sxs-lookup"><span data-stu-id="b1975-186">The name provided by the user</span></span>  | <span data-ttu-id="b1975-187">可选。</span><span class="sxs-lookup"><span data-stu-id="b1975-187">Optional.</span></span>  <span data-ttu-id="b1975-188">[requestPayerName](/previous-versions/mt790440(v=vs.85)#PaymentOptions)为时必需</span><span class="sxs-lookup"><span data-stu-id="b1975-188">Required when [requestPayerName](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True` | |  
[<span data-ttu-id="b1975-189">payerEmail</span><span class="sxs-lookup"><span data-stu-id="b1975-189">payerEmail</span></span>](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | <span data-ttu-id="b1975-190">用户选择的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="b1975-190">The email address selected by the user</span></span> | <span data-ttu-id="b1975-191">可选。</span><span class="sxs-lookup"><span data-stu-id="b1975-191">Optional.</span></span>  <span data-ttu-id="b1975-192">[requestPayerEmail](/previous-versions/mt790440(v=vs.85)#PaymentOptions)为必需</span><span class="sxs-lookup"><span data-stu-id="b1975-192">Required when [requestPayerEmail](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True`  | |  
[<span data-ttu-id="b1975-193">PayerPhone</span><span class="sxs-lookup"><span data-stu-id="b1975-193">PayerPhone</span></span>](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | <span data-ttu-id="b1975-194">用户选择的电话号码</span><span class="sxs-lookup"><span data-stu-id="b1975-194">The phone number selected by the user</span></span> | <span data-ttu-id="b1975-195">可选。</span><span class="sxs-lookup"><span data-stu-id="b1975-195">Optional.</span></span>  <span data-ttu-id="b1975-196">[requestPayerPhone 为](/previous-versions/mt790440(v=vs.85)#PaymentOptions)必需</span><span class="sxs-lookup"><span data-stu-id="b1975-196">Required when [requestPayerPhone](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True` | |  

<span data-ttu-id="b1975-197">付款 [响应](/previous-versions/mt790655(v=vs.85)#PaymentRequest_params) 中的详细信息 JSON **对象将** 包含商家处理付款所需的付款数据。</span><span class="sxs-lookup"><span data-stu-id="b1975-197">The [details](/previous-versions/mt790655(v=vs.85)#PaymentRequest_params) JSON object in the **Payment Response** will contain the payment data required by the merchant to process a payment.</span></span>  <span data-ttu-id="b1975-198">在最简单的形式中，响应将是包含明文支付卡[](https://w3c.github.io/payment-method-basic-card)详细信息的基本卡有效负载。</span><span class="sxs-lookup"><span data-stu-id="b1975-198">In its simplest form, the response will be a [Basic Card](https://w3c.github.io/payment-method-basic-card) payload containing cleartext payment card details.</span></span>  <span data-ttu-id="b1975-199">如果商家已安排其他网关/处理合作伙伴来提供付款支持，则商家可能需要处理器可以处理的有效负载。</span><span class="sxs-lookup"><span data-stu-id="b1975-199">Where merchants have arrangements with additional gateway/processor partners for them to provide payments support, the merchant may require a payload the processor can handle.</span></span>  <span data-ttu-id="b1975-200">这些令牌可以形成处理器/网关令牌或加密的付款方式。</span><span class="sxs-lookup"><span data-stu-id="b1975-200">These can take the shape of a processor/gateway token or an encrypted payment instrument.</span></span>  <span data-ttu-id="b1975-201">这些付款方式超出了本文档的范围，将在特定于处理者的文档中介绍。</span><span class="sxs-lookup"><span data-stu-id="b1975-201">These payment methods are outside the scope of this document and will be covered in documentation specific to the processor.</span></span>  <span data-ttu-id="b1975-202">此外，若要接收基本[](https://w3c.github.io/payment-method-basic-card)卡响应，开发人员无需其他加入 Microsoft，与其他可能需要加密密钥载入或请求授权 \ (oAuth\) 的特定于处理器/网关的付款方式不同。</span><span class="sxs-lookup"><span data-stu-id="b1975-202">Additionally, to receive a [Basic Card](https://w3c.github.io/payment-method-basic-card) response, no additional onboarding to Microsoft is required by the developer, unlike other processor/gateway specific payment methods which may require encryption key onboarding or request authorization \(oAuth\).</span></span>  

<span data-ttu-id="b1975-203">收到付款 **响应后**，网站会向付款处理者提交付款信息。</span><span class="sxs-lookup"><span data-stu-id="b1975-203">Upon receiving the **Payment Response**, the website submits the payment information to their payment processor.</span></span>  <span data-ttu-id="b1975-204">处理付款时，浏览器将显示微调框页面。</span><span class="sxs-lookup"><span data-stu-id="b1975-204">The browser will display a spinner page while the payment is being processed.</span></span>  

:::image type="complex" source="../media/loading_screen.png" alt-text="处理付款时显示的页面" lightbox="../media/loading_screen.png":::
   <span data-ttu-id="b1975-206">处理付款时显示的页面</span><span class="sxs-lookup"><span data-stu-id="b1975-206">The page displayed when the payment is being processed</span></span>  
:::image-end:::  

<span data-ttu-id="b1975-207">付款完成后，网页将调用完整的 [ () ](/previous-versions/mt790642(v=vs.85)) 方法，并传递成功 **或** 失败 **的值**。</span><span class="sxs-lookup"><span data-stu-id="b1975-207">Once the payment is complete, the web page calls the [complete()](/previous-versions/mt790642(v=vs.85)) method and passes a value of **success** or **fail**.</span></span>  <span data-ttu-id="b1975-208">完整的[ () ](/previous-versions/mt790642(v=vs.85))方法通知浏览器购买已完成，并且应该根据成功或失败的值显示相应的终止 UI**屏幕**。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b1975-208">The [complete()](/previous-versions/mt790642(v=vs.85)) method informs the browser that the purchase is finished and the appropriate terminating UI screen should be shown depending on the value of **success** or **fail**.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_complete.png" alt-text="购买成功时显示的 UI" lightbox="../media/response_payment-request_complete.png":::
         <span data-ttu-id="b1975-210">购买成功时显示的 UI</span><span class="sxs-lookup"><span data-stu-id="b1975-210">The UI displayed when the purchase succeeded</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_failure.png" alt-text="购买失败时显示的 UI" lightbox="../media/response_payment-request_failure.png":::
         <span data-ttu-id="b1975-212">购买失败时显示的 UI</span><span class="sxs-lookup"><span data-stu-id="b1975-212">The UI displayed when the purchase failed</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="b1975-213">付款请求（发货）</span><span class="sxs-lookup"><span data-stu-id="b1975-213">Payment Request with Shipping</span></span>  

### <span data-ttu-id="b1975-214">发货地址</span><span class="sxs-lookup"><span data-stu-id="b1975-214">Shipping Address</span></span>  

<span data-ttu-id="b1975-215">对于需要寄送物理商品的销售，需要寄送地址。</span><span class="sxs-lookup"><span data-stu-id="b1975-215">For sales that require shipping physical goods, a shipping address is required.</span></span>  <span data-ttu-id="b1975-216">若要包含送货地址，请 `requestShipping = True` 设置请求 [的选项](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 参数。</span><span class="sxs-lookup"><span data-stu-id="b1975-216">To include a shipping address, set `requestShipping = True` in the [options](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter of the request.</span></span>  

<span data-ttu-id="b1975-217">当用户选择或更新送货地址时 [，onshippingaddresschange](/previous-versions/mt790442(v=vs.85)) 事件将运行。</span><span class="sxs-lookup"><span data-stu-id="b1975-217">When the user selects or updates the shipping address, the [onshippingaddresschange](/previous-versions/mt790442(v=vs.85)) event will run.</span></span>  <span data-ttu-id="b1975-218">使用事件侦听器的网站将注意到更改，然后可以验证地址、重新计算发货成本和税款，并更新 [shippingOptions](/previous-versions/mt790440(v=vs.85)) 以反映所选 \ (（如果适用）地址的已更改成本和发货选项) 。</span><span class="sxs-lookup"><span data-stu-id="b1975-218">The website, using an event listener, will be aware of the change and can then validate the address, re-calculate shipping costs and taxes, and update [shippingOptions](/previous-versions/mt790440(v=vs.85)) to reflect the changed costs and shipping options available for the address selected \(if applicable\).</span></span>  

### <span data-ttu-id="b1975-219">发货选项</span><span class="sxs-lookup"><span data-stu-id="b1975-219">Shipping Options</span></span>  

<span data-ttu-id="b1975-220">可以通过将 [shippingOptions](/previous-versions/mt790440(v=vs.85)) 添加到 details 参数来向客户显示 [发货](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 选项。</span><span class="sxs-lookup"><span data-stu-id="b1975-220">Shipping options can be presented to the customer by adding [shippingOptions](/previous-versions/mt790440(v=vs.85)) to the [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter.</span></span>  <span data-ttu-id="b1975-221">可以通过为其中一个发货 `selected = True` 选项设置来建立默认值。</span><span class="sxs-lookup"><span data-stu-id="b1975-221">A default can be established by setting `selected = True` for one of the shipping options.</span></span>  
 
<span data-ttu-id="b1975-222">当用户选择或更新 shippingOptions 时 [，onshippingoptionchange](/previous-versions/mt790436(v=vs.85)) 事件将运行。</span><span class="sxs-lookup"><span data-stu-id="b1975-222">When the user selects or updates the shippingOptions, the [onshippingoptionchange](/previous-versions/mt790436(v=vs.85)) event will run.</span></span>  <span data-ttu-id="b1975-223">使用事件侦听器的网站将注意到更改，并可以使用正确的寄送金额更新详细信息参数。 [](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)</span><span class="sxs-lookup"><span data-stu-id="b1975-223">The website, using an event listener, will be aware of the change and can update the [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter with the correct shipping amount.</span></span>  

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

## <span data-ttu-id="b1975-224">API 参考</span><span class="sxs-lookup"><span data-stu-id="b1975-224">API Reference</span></span>  

[<span data-ttu-id="b1975-225">付款请求 API</span><span class="sxs-lookup"><span data-stu-id="b1975-225">Payment Request API</span></span>](/previous-versions/mt790447(v=vs.85))  

## <span data-ttu-id="b1975-226">规范</span><span class="sxs-lookup"><span data-stu-id="b1975-226">Specification</span></span>
[<span data-ttu-id="b1975-227">付款请求 API</span><span class="sxs-lookup"><span data-stu-id="b1975-227">Payment Request API</span></span>](https://w3.org/TR/payment-request)

<!-- links -->  

[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具 |Microsoft Docs"  

[MicrosoftSupport44533505]: https://support.microsoft.com/help/4533505 "什么是 Microsoft Edge 旧版？"  

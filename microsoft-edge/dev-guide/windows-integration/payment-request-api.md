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
# <span data-ttu-id="67bda-104">付款请求 API (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="67bda-104">Payment Request API (EdgeHTML)</span></span>  

> [!NOTE]
> <span data-ttu-id="67bda-105">本文介绍旧版 Microsoft Edge 支持的 [工作流][MicrosoftSupport44533505]。</span><span class="sxs-lookup"><span data-stu-id="67bda-105">This article describes the workflow supported in the [legacy version of Microsoft Edge][MicrosoftSupport44533505].</span></span>  <span data-ttu-id="67bda-106">Microsoft Edge \ (Chromium\) 支持采用基于 Chromium 项目的不同实现来支付请求 API。</span><span class="sxs-lookup"><span data-stu-id="67bda-106">Microsoft Edge \(Chromium\) supports the Payment Request API with a different implementation based on the Chromium project.</span></span>  

<span data-ttu-id="67bda-107">电子商业销售连续缩小的水平。</span><span class="sxs-lookup"><span data-stu-id="67bda-107">E-commerce sales continue growing at a rapid pace.</span></span>  <span data-ttu-id="67bda-108">通常对于 [eMarketer，2018](https://www.emarketer.com)年，2018 年的销售将从 2013 年度量的级别中增加 23%。</span><span class="sxs-lookup"><span data-stu-id="67bda-108">According to [eMarketer](https://www.emarketer.com), by 2018 digital sales are forecasted to increase by 23% from the levels measured in 2013.</span></span>  <span data-ttu-id="67bda-109">虽然消费者和企业都享受到电子商务销售的方方面，但挑选挑选。</span><span class="sxs-lookup"><span data-stu-id="67bda-109">While consumers and businesses enjoy the convenience of e-commerce sales, challenges remain.</span></span>  <span data-ttu-id="67bda-110">现在每位电子网站所有者都需要完成时间来制定高质量付款流和验证规则。</span><span class="sxs-lookup"><span data-stu-id="67bda-110">Today each e-commerce website owner needs to invest time to develop high quality payment checkout flows and validation rules.</span></span>  <span data-ttu-id="67bda-111">消费者需要导航不同的付款结清流，然后在他们购于的每个站点上重新输入相同的付款和发货信息。</span><span class="sxs-lookup"><span data-stu-id="67bda-111">Consumers need to navigate different payment checkout flows and re-enter the same payment and shipping information on every site where they shop.</span></span>  <span data-ttu-id="67bda-112">对于消费者来源并不有些影响，从而导定高度的购货车上限，并会减少商品销售量。</span><span class="sxs-lookup"><span data-stu-id="67bda-112">This can be time consuming and frustrating for consumers, leading to a high rate of shopping cart abandonment and decreased sales for merchants.</span></span>  <span data-ttu-id="67bda-113">购销车车 [的](http://baymard.com/lists/cart-abandonment-rate) 价值包括 60% 到 70% 购购车车之间的价值。</span><span class="sxs-lookup"><span data-stu-id="67bda-113">Merchants [estimate](http://baymard.com/lists/cart-abandonment-rate) between 60% and 70% of shopping carts are abandoned.</span></span>  

<span data-ttu-id="67bda-114">付 [款请求 API](https://w3.org/TR/payment-request) 标准化付款结清流程。</span><span class="sxs-lookup"><span data-stu-id="67bda-114">The [Payment Request API](https://w3.org/TR/payment-request) standardizes the payment checkout process.</span></span>  <span data-ttu-id="67bda-115">此 API 需要进行更少的自定义，并且提供了更快、更一致的体验，因此消费者的体验会减少。</span><span class="sxs-lookup"><span data-stu-id="67bda-115">This API requires less customization for web developers and provides a faster, more consistent, and therefore, less confusing experience for consumers.</span></span>  <span data-ttu-id="67bda-116">由于消费者可从其 Microsoft 帐户中选择支付检测和送货地址，因此系统需要输入更少的数据才能完成购买，从而减少完成付款所需的时间和数据输入。</span><span class="sxs-lookup"><span data-stu-id="67bda-116">Because consumers can select payment instruments and shipping addresses from their Microsoft account, they are required to enter less data to complete purchases which reduces the time and data entry required to complete a payment.</span></span>  

<span data-ttu-id="67bda-117">[付款请求 API 是一](https://w3.org/TR/payment-request)种开放的跨浏览器标准，允许浏览器在商业、使用的商品和付款方式 \ (（如信用卡\) 中存储）之间的中介。</span><span class="sxs-lookup"><span data-stu-id="67bda-117">The [Payment Request API](https://w3.org/TR/payment-request) is an open, cross-browser standard that enables browsers to act as an intermediary between merchants, consumers, and the payment methods \(such as credit cards\) that consumers have stored in the cloud.</span></span>  
  
<span data-ttu-id="67bda-118">总的来，使用 [付款请求 API 时](https://w3.org/TR/payment-request)，客户在商户网站上以正常方式购买。</span><span class="sxs-lookup"><span data-stu-id="67bda-118">In summary, when using the [Payment Request API](https://w3.org/TR/payment-request), customers shop on merchant websites as normal.</span></span>  <span data-ttu-id="67bda-119">在准备好支付时，商家网站会调用 **付款请求** API 以创建 **付款请求** 并通过相关付款信息 \ (传递相关付款信息 \ (例如支持的付款方式、购买金额、货币等 ) 。</span><span class="sxs-lookup"><span data-stu-id="67bda-119">When ready to pay, the merchant website calls the **Payment Request** API to create a **Payment Request** and passes the relevant payment information \(such as supported payment methods, purchase amount, currency, and so on\) to the browser.</span></span>  

:::image type="complex" source="../media/payment_request_construct.png" alt-text="付款请求构造" lightbox="../media/payment_request_construct.png":::
   <span data-ttu-id="67bda-121">付款请求构造</span><span class="sxs-lookup"><span data-stu-id="67bda-121">Payment request construct</span></span>  
:::image-end:::  

<span data-ttu-id="67bda-122">浏览器会对用户进行身份验证，让用户能够对文件选择一种受支持的付款方式，并处理付款详细信息。</span><span class="sxs-lookup"><span data-stu-id="67bda-122">The browser authenticates the user, enables the user to select a supported payment method on file, and processes the payment details.</span></span>  <span data-ttu-id="67bda-123">然后，浏览器会将付款信息返回到商业网站，以便商业可以完成付款。</span><span class="sxs-lookup"><span data-stu-id="67bda-123">The browser then sends the payment information details back to the merchant website, so that the merchant can complete the payment.</span></span>  <span data-ttu-id="67bda-124">除接收付款信息之外，成人还可选择接收付款请求的发 **货信息**。</span><span class="sxs-lookup"><span data-stu-id="67bda-124">In addition to receiving payment information, the merchant can also elect to receive shipping information as part of the **Payment Request**.</span></span>  

:::image type="complex" source="../media/payment_response_construct.png" alt-text="付款响应构造" lightbox="../media/payment_response_construct.png":::
   <span data-ttu-id="67bda-126">付款响应构造</span><span class="sxs-lookup"><span data-stu-id="67bda-126">Payment response construct</span></span>  
:::image-end:::  

<span data-ttu-id="67bda-127">若要查看付款请求 API，以及获取其使用方法概述，请观看此视频。</span><span class="sxs-lookup"><span data-stu-id="67bda-127">To see the Payment Request API in action, as well as get an overview of how to use it, check out this video.</span></span>  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Using-the-Payments-Request-API/player]  

> [!NOTE]
> <span data-ttu-id="67bda-128">付款请求 API 在 Microsoft Edge 内部版本 14992 或更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="67bda-128">The Payment Request API is supported in Microsoft Edge build 14992 or newer.</span></span>  

## <span data-ttu-id="67bda-129">创建付款请求</span><span class="sxs-lookup"><span data-stu-id="67bda-129">Creating a Payment Request</span></span>  

<span data-ttu-id="67bda-130">网页通常 **在用户通过单击"购买** "按钮启动付款流程时创建一个付款请求。</span><span class="sxs-lookup"><span data-stu-id="67bda-130">Web pages create a **Payment Request** typically when the user initiates a payment process by clicking a "buy" button.</span></span>  <span data-ttu-id="67bda-131">**付款请求构**[造函数包括](/previous-versions/mt790440(v=vs.85))methodData、details 和选项。</span><span class="sxs-lookup"><span data-stu-id="67bda-131">The **Payment Request** [constructor](/previous-versions/mt790440(v=vs.85)) includes methodData, details, and options.</span></span>  

```javascript
var payment = new PaymentRequest ( 
    methodData,  // required payment method data including payment method identifiers 
    details,     // required transaction information 
    options      // optional information like shipping or contact info to be returned 
); 
```  

<span data-ttu-id="67bda-132">[methodData](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)参数包含由网站所接受的付款方式和网络的列表，以及任何相关的付款方式特定数据。</span><span class="sxs-lookup"><span data-stu-id="67bda-132">The [methodData](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter contains a list of the payment methods and networks accepted by the website and any associated payment method specific data.</span></span>  <span data-ttu-id="67bda-133">在 Microsoft Edge 中，此列表与购户在 Microsoft 帐户中已保存的支持付款方式相匹配，并导致付款用户体验中的"支付方式"列表。</span><span class="sxs-lookup"><span data-stu-id="67bda-133">In Microsoft Edge, this list is matched with the supported payment methods that the shopper has saved in their Microsoft account and results in the "pay with" list in the payment user experience.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_with.png" alt-text="Microsoft 子钱包用户体验中的列表" lightbox="../media/pay_with.png":::
         <span data-ttu-id="67bda-135">Microsoft **子钱包** 用户体验中的列表</span><span class="sxs-lookup"><span data-stu-id="67bda-135">The **pay with** list in the Microsoft Wallet user experience</span></span>  
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

<span data-ttu-id="67bda-136">[详细信息](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)参数包含与客户开关关于交易的信息。</span><span class="sxs-lookup"><span data-stu-id="67bda-136">The [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter contains information that the merchant wishes to convey to the customer about the transaction.</span></span>  <span data-ttu-id="67bda-137">这些汇总项包括总计、税、运费金额和其他摘要级别项目影响支付金额。</span><span class="sxs-lookup"><span data-stu-id="67bda-137">These include order summary items like total, tax, shipping amount, and other summary level items impacting the payment amount.</span></span>  <span data-ttu-id="67bda-138">这些不应用用作行项进行排序。</span><span class="sxs-lookup"><span data-stu-id="67bda-138">These are not intended to be order line items.</span></span>  
  
<span data-ttu-id="67bda-139">[在需要](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)时，详细信息参数还用于定义可供客户使用的送货选项。</span><span class="sxs-lookup"><span data-stu-id="67bda-139">The [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter is also used to define shipping options available to the customer when required.</span></span>  <span data-ttu-id="67bda-140">下面包含更多详细信息，包含下**Payment Request**文"发货"部分。</span><span class="sxs-lookup"><span data-stu-id="67bda-140">More details are included in the **Payment Request** with Shipping section below.</span></span>  

<span data-ttu-id="67bda-141">[每个](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)明细线都包含货币和金额的标签。</span><span class="sxs-lookup"><span data-stu-id="67bda-141">Each [detail](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) line includes a label for the currency and the amount.</span></span>  

> [!NOTE]
> <span data-ttu-id="67bda-142">**付款请求不会**计算这些金额的总和或总数。</span><span class="sxs-lookup"><span data-stu-id="67bda-142">The **Payment Request** does not calculate the sum or total of these amounts.</span></span>  <span data-ttu-id="67bda-143">商级网站的责任为确保行项总数正确所有。</span><span class="sxs-lookup"><span data-stu-id="67bda-143">It is the responsibility of the merchant's website to ensure that the line items total correctly.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/show_details.png" alt-text="分类汇总、运送、税款及总细节" lightbox="../media/show_details.png":::
         <span data-ttu-id="67bda-145">分类汇总、运送、税款及总细节</span><span class="sxs-lookup"><span data-stu-id="67bda-145">Subtotal, shipping, taxes, and total details</span></span>  
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

<span data-ttu-id="67bda-146">[PaymentRequest](/previous-versions/mt790440(v=vs.85)) 不支持退款，所以金额应始终为正数;单个列表项可以为非正数，如折扣。</span><span class="sxs-lookup"><span data-stu-id="67bda-146">[PaymentRequest](/previous-versions/mt790440(v=vs.85)) does not support refunds, so the amounts should always be positive; individual list items can be negative, such as discounts.</span></span>  

<span data-ttu-id="67bda-147">当你定义标签时，浏览器将呈现标签，并根据客户的区域设置自动呈现正确的货币格式。</span><span class="sxs-lookup"><span data-stu-id="67bda-147">The browser will render the labels as you define them and automatically render the correct currency formatting based on the customer's locale.</span></span>  <span data-ttu-id="67bda-148">请注意，标签应以与你的内容相同的语言呈现。</span><span class="sxs-lookup"><span data-stu-id="67bda-148">Note that the labels should be rendered in the same language as your content.</span></span>  

<span data-ttu-id="67bda-149">选项 [参数](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 定义网页需要从付款请求返回 **的数据**。</span><span class="sxs-lookup"><span data-stu-id="67bda-149">The [options](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter defines data the web page wants returned from the **Payment Request**.</span></span>  <span data-ttu-id="67bda-150">这还定义需要收集的数据，包括发货、电子邮件地址、电话号码还是需要使用所有数据。</span><span class="sxs-lookup"><span data-stu-id="67bda-150">This also defines the data that needs to be collected, including if shipping, email address, phone number or all are required.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/email_snippet.png" alt-text=""电子邮件地址"下拉列表" lightbox="../media/email_snippet.png":::
         <span data-ttu-id="67bda-152">"电子邮件地址"下拉列表</span><span class="sxs-lookup"><span data-stu-id="67bda-152">Email address dropdown</span></span>  
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

## <span data-ttu-id="67bda-153">显示付款请求</span><span class="sxs-lookup"><span data-stu-id="67bda-153">Showing the Payment Request</span></span>  

<span data-ttu-id="67bda-154">显示 [ () ](/previous-versions/mt790448(v=vs.85)) 方法，以允许用户与 **付款请求用户** 界面进行交互。</span><span class="sxs-lookup"><span data-stu-id="67bda-154">The [show()](/previous-versions/mt790448(v=vs.85)) method is called by the web page to allow the user to interact with the **Payment Request** user interface.</span></span>  <span data-ttu-id="67bda-155">显示 [ () ](/previous-versions/mt790448(v=vs.85)) 方法将返回在用户授权付款请求时将解除的 Promise。</span><span class="sxs-lookup"><span data-stu-id="67bda-155">The [show()](/previous-versions/mt790448(v=vs.85)) method returns a Promise that will be resolved when the user authorizes the payment request.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_screen_default.png" alt-text="确认和付款详细信息" lightbox="../media/pay_screen_default.png":::
         <span data-ttu-id="67bda-157">确认和付款详细信息</span><span class="sxs-lookup"><span data-stu-id="67bda-157">Confirm and pay details</span></span>  
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

## <span data-ttu-id="67bda-158">中不记录付款请求</span><span class="sxs-lookup"><span data-stu-id="67bda-158">Aborting a Payment Request</span></span>  
 
<span data-ttu-id="67bda-159">中 [止 () ](/previous-versions/mt790437(v=vs.85)) 方法可在调用 [显示 () 方法后随时调用 () ](/previous-versions/mt790448(v=vs.85)) 方法，直到解析了承诺的位置。</span><span class="sxs-lookup"><span data-stu-id="67bda-159">The [abort()](/previous-versions/mt790437(v=vs.85)) method can be called by the web page any time after the [show()](/previous-versions/mt790448(v=vs.85)) method is called, up until the point where the Promise is resolved.</span></span>  <span data-ttu-id="67bda-160">[中 () ](/previous-versions/mt790437(v=vs.85))方法将导致浏览器中符合付款**请求**并**关闭付款请求**用户界面。</span><span class="sxs-lookup"><span data-stu-id="67bda-160">The [abort()](/previous-versions/mt790437(v=vs.85)) method will cause the browser to abort the **Payment Request** and close the **Payment Request** user interface.</span></span>  <span data-ttu-id="67bda-161">例如，如果用户在需要时间内未完成交易，网页可能会选择中间。</span><span class="sxs-lookup"><span data-stu-id="67bda-161">For example, a web page may choose to abort if the user did not complete the transaction in the required amount of time.</span></span>  

```javascript
payment.abort();
```  

## <span data-ttu-id="67bda-162">付款响应</span><span class="sxs-lookup"><span data-stu-id="67bda-162">Payment Response</span></span>  
<span data-ttu-id="67bda-163">当客户批准付 **款请求时**，付款 **响** 应将返回到网站。</span><span class="sxs-lookup"><span data-stu-id="67bda-163">When the customer approves the **Payment Request**, a **Payment Response** is returned to the website.</span></span>  <span data-ttu-id="67bda-164">**付款响应**包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="67bda-164">The **Payment Response** includes the following:</span></span>  

 <span data-ttu-id="67bda-165">属性</span><span class="sxs-lookup"><span data-stu-id="67bda-165">Property</span></span>      | <span data-ttu-id="67bda-166">说明</span><span class="sxs-lookup"><span data-stu-id="67bda-166">Description</span></span> | <span data-ttu-id="67bda-167">必需</span><span class="sxs-lookup"><span data-stu-id="67bda-167">Required</span></span> | <span data-ttu-id="67bda-168">其他信息</span><span class="sxs-lookup"><span data-stu-id="67bda-168">Additional Info</span></span>
|---------------|-----------------|-------|-----------------|
[<span data-ttu-id="67bda-169">methodName</span><span class="sxs-lookup"><span data-stu-id="67bda-169">methodName</span></span>](/previous-versions/mt790656(v=vs.85)) | <span data-ttu-id="67bda-170">用户选择的付款方式 ID</span><span class="sxs-lookup"><span data-stu-id="67bda-170">The ID for the payment method selected by the user</span></span> | <span data-ttu-id="67bda-171">Y</span><span class="sxs-lookup"><span data-stu-id="67bda-171">Y</span></span> | |   
[<span data-ttu-id="67bda-172">details</span><span class="sxs-lookup"><span data-stu-id="67bda-172">details</span></span>](/previous-versions/mt790655(v=vs.85)) | <span data-ttu-id="67bda-173">包含商业变换机号处理处理交易的所有数据的 JSON 对象</span><span class="sxs-lookup"><span data-stu-id="67bda-173">A JSON object that includes all of the data the merchant requires to process the transaction using the selected payment method or a payment token</span></span> | <span data-ttu-id="67bda-174">Y</span><span class="sxs-lookup"><span data-stu-id="67bda-174">Y</span></span> | <span data-ttu-id="67bda-175">[基本卡片](https://w3c.github.io/payment-method-basic-card) 字典：cardholderName;cardNumber;expiryMonth;expiryYear;cardSecurityCode;billingAddress;</span><span class="sxs-lookup"><span data-stu-id="67bda-175">[Basic Card](https://w3c.github.io/payment-method-basic-card) Dictionary:  cardholderName; cardNumber; expiryMonth; expiryYear; cardSecurityCode; billingAddress;</span></span> |   
[<span data-ttu-id="67bda-176">shippingAddress</span><span class="sxs-lookup"><span data-stu-id="67bda-176">shippingAddress</span></span>](/previous-versions/mt790445(v=vs.85)) | <span data-ttu-id="67bda-177">由用户选择的送货地址</span><span class="sxs-lookup"><span data-stu-id="67bda-177">The shipping address selected by the user</span></span>  |  <span data-ttu-id="67bda-178">可选。</span><span class="sxs-lookup"><span data-stu-id="67bda-178">Optional.</span></span>  <span data-ttu-id="67bda-179">需要请求 [Shipping 时的](/previous-versions/mt790440(v=vs.85)#PaymentOptions) 必需服务</span><span class="sxs-lookup"><span data-stu-id="67bda-179">Required when [requestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True`  | <span data-ttu-id="67bda-180">地址字典：国家/地区;addressline;区域;城市;dependentLocality;postalCode;sortingCode;languageCode;组织;收件人;手机</span><span class="sxs-lookup"><span data-stu-id="67bda-180">Address dictionary:  country; addressLine; region; city; dependentLocality; postalCode; sortingCode; languageCode; organization; recipient; phone</span></span> |  
[<span data-ttu-id="67bda-181">shippingOption</span><span class="sxs-lookup"><span data-stu-id="67bda-181">shippingOption</span></span>](/previous-versions/mt790446(v=vs.85)) | <span data-ttu-id="67bda-182">所选送货选项的 ID</span><span class="sxs-lookup"><span data-stu-id="67bda-182">The ID for the selected shipping option</span></span> | <span data-ttu-id="67bda-183">可选。</span><span class="sxs-lookup"><span data-stu-id="67bda-183">Optional.</span></span>  <span data-ttu-id="67bda-184">需要请求 [Shipping 时的](/previous-versions/mt790440(v=vs.85)#PaymentOptions) 必需服务</span><span class="sxs-lookup"><span data-stu-id="67bda-184">Required when [requestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True`  | |   
[<span data-ttu-id="67bda-185">payerName</span><span class="sxs-lookup"><span data-stu-id="67bda-185">payerName</span></span>](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | <span data-ttu-id="67bda-186">由用户提供的名称</span><span class="sxs-lookup"><span data-stu-id="67bda-186">The name provided by the user</span></span>  | <span data-ttu-id="67bda-187">可选。</span><span class="sxs-lookup"><span data-stu-id="67bda-187">Optional.</span></span>  <span data-ttu-id="67bda-188">[RequestPayerName 为必](/previous-versions/mt790440(v=vs.85)#PaymentOptions)需</span><span class="sxs-lookup"><span data-stu-id="67bda-188">Required when [requestPayerName](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True` | |  
[<span data-ttu-id="67bda-189">payerEmail</span><span class="sxs-lookup"><span data-stu-id="67bda-189">payerEmail</span></span>](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | <span data-ttu-id="67bda-190">用户选择的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="67bda-190">The email address selected by the user</span></span> | <span data-ttu-id="67bda-191">可选。</span><span class="sxs-lookup"><span data-stu-id="67bda-191">Optional.</span></span>  <span data-ttu-id="67bda-192">[RequestPayerEmail](/previous-versions/mt790440(v=vs.85)#PaymentOptions)为该要求</span><span class="sxs-lookup"><span data-stu-id="67bda-192">Required when [requestPayerEmail](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True`  | |  
[<span data-ttu-id="67bda-193">PayerPhone</span><span class="sxs-lookup"><span data-stu-id="67bda-193">PayerPhone</span></span>](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | <span data-ttu-id="67bda-194">用户选择的电话号码</span><span class="sxs-lookup"><span data-stu-id="67bda-194">The phone number selected by the user</span></span> | <span data-ttu-id="67bda-195">可选。</span><span class="sxs-lookup"><span data-stu-id="67bda-195">Optional.</span></span>  <span data-ttu-id="67bda-196">[当 requestPayerPhone 为必](/previous-versions/mt790440(v=vs.85)#PaymentOptions)需</span><span class="sxs-lookup"><span data-stu-id="67bda-196">Required when [requestPayerPhone](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True` | |  

<span data-ttu-id="67bda-197">[付款](/previous-versions/mt790655(v=vs.85)#PaymentRequest_params)响应中详细的 JSON**对象**将包含处理付款所需的付款数据。</span><span class="sxs-lookup"><span data-stu-id="67bda-197">The [details](/previous-versions/mt790655(v=vs.85)#PaymentRequest_params) JSON object in the **Payment Response** will contain the payment data required by the merchant to process a payment.</span></span>  <span data-ttu-id="67bda-198">该响应最简单，该响应将是包含清楚性支付卡[Basic Card](https://w3c.github.io/payment-method-basic-card)详细信息的基本卡负载。</span><span class="sxs-lookup"><span data-stu-id="67bda-198">In its simplest form, the response will be a [Basic Card](https://w3c.github.io/payment-method-basic-card) payload containing cleartext payment card details.</span></span>  <span data-ttu-id="67bda-199">如果商主具有附加网关/处理器合作伙伴的方式来为他们提供付款支持，该商家可能需要负载该处理员。</span><span class="sxs-lookup"><span data-stu-id="67bda-199">Where merchants have arrangements with additional gateway/processor partners for them to provide payments support, the merchant may require a payload the processor can handle.</span></span>  <span data-ttu-id="67bda-200">这些可以获取处理器/网关标记或加密的付款方式的形状。</span><span class="sxs-lookup"><span data-stu-id="67bda-200">These can take the shape of a processor/gateway token or an encrypted payment instrument.</span></span>  <span data-ttu-id="67bda-201">这些支付方式超出了本文档的范围，并且将在文档中被介绍，这些信息仅在特定于处理器的文档中介绍。</span><span class="sxs-lookup"><span data-stu-id="67bda-201">These payment methods are outside the scope of this document and will be covered in documentation specific to the processor.</span></span>  <span data-ttu-id="67bda-202">此外，若要接收 [基本卡](https://w3c.github.io/payment-method-basic-card) 响应，开发人员不需要对 Microsoft 进行额外培训，这与可能需要加密密钥或请求授权 \ (oAuth\) 的其他处理器/网关特定的付款方法不同。</span><span class="sxs-lookup"><span data-stu-id="67bda-202">Additionally, to receive a [Basic Card](https://w3c.github.io/payment-method-basic-card) response, no additional onboarding to Microsoft is required by the developer, unlike other processor/gateway specific payment methods which may require encryption key onboarding or request authorization \(oAuth\).</span></span>  

<span data-ttu-id="67bda-203">在收获付款回复后，**Payment Response**网站会将付款信息提交到其付款处理器。</span><span class="sxs-lookup"><span data-stu-id="67bda-203">Upon receiving the **Payment Response**, the website submits the payment information to their payment processor.</span></span>  <span data-ttu-id="67bda-204">处理付款时，浏览器将显示一个较进的页面。</span><span class="sxs-lookup"><span data-stu-id="67bda-204">The browser will display a spinner page while the payment is being processed.</span></span>  

:::image type="complex" source="../media/loading_screen.png" alt-text="处理付款时显示的页面" lightbox="../media/loading_screen.png":::
   <span data-ttu-id="67bda-206">处理付款时显示的页面</span><span class="sxs-lookup"><span data-stu-id="67bda-206">The page displayed when the payment is being processed</span></span>  
:::image-end:::  

<span data-ttu-id="67bda-207">付款完成后，该网页将调用 [完整的 () ](/previous-versions/mt790642(v=vs.85)) 方法，并传递成功 **或** 失 **败值**。</span><span class="sxs-lookup"><span data-stu-id="67bda-207">Once the payment is complete, the web page calls the [complete()](/previous-versions/mt790642(v=vs.85)) method and passes a value of **success** or **fail**.</span></span>  <span data-ttu-id="67bda-208">[完整的 () ](/previous-versions/mt790642(v=vs.85))方法可通知浏览器完成购买，并应该根据成功或失败的价值显示相应的**终止**UI 屏幕。 **success**</span><span class="sxs-lookup"><span data-stu-id="67bda-208">The [complete()](/previous-versions/mt790642(v=vs.85)) method informs the browser that the purchase is finished and the appropriate terminating UI screen should be shown depending on the value of **success** or **fail**.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_complete.png" alt-text="UI 成功显示" lightbox="../media/response_payment-request_complete.png":::
         <span data-ttu-id="67bda-210">UI 成功显示</span><span class="sxs-lookup"><span data-stu-id="67bda-210">The UI displayed when the purchase succeeded</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_failure.png" alt-text="购买失败时显示的 UI" lightbox="../media/response_payment-request_failure.png":::
         <span data-ttu-id="67bda-212">购买失败时显示的 UI</span><span class="sxs-lookup"><span data-stu-id="67bda-212">The UI displayed when the purchase failed</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="67bda-213">发送就请求</span><span class="sxs-lookup"><span data-stu-id="67bda-213">Payment Request with Shipping</span></span>  

### <span data-ttu-id="67bda-214">送货地址</span><span class="sxs-lookup"><span data-stu-id="67bda-214">Shipping Address</span></span>  

<span data-ttu-id="67bda-215">对于需要送货物理商品的销售，需要送货地址。</span><span class="sxs-lookup"><span data-stu-id="67bda-215">For sales that require shipping physical goods, a shipping address is required.</span></span>  <span data-ttu-id="67bda-216">若要包含送货地址，请通过 `requestShipping = True` 设置 [请求的选项](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 参数。</span><span class="sxs-lookup"><span data-stu-id="67bda-216">To include a shipping address, set `requestShipping = True` in the [options](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter of the request.</span></span>  

<span data-ttu-id="67bda-217">当用户选择或更新送货地址时，将运行 [onshippingaddresschange](/previous-versions/mt790442(v=vs.85)) 事件。</span><span class="sxs-lookup"><span data-stu-id="67bda-217">When the user selects or updates the shipping address, the [onshippingaddresschange](/previous-versions/mt790442(v=vs.85)) event will run.</span></span>  <span data-ttu-id="67bda-218">网站使用事件侦听器将知道更改，然后可验证地址、重新计算运费和税收，并更新 [运费选项以](/previous-versions/mt790440(v=vs.85)) 反映地址中所选项的可 (选费用和送货选项（如果适用\) ）。</span><span class="sxs-lookup"><span data-stu-id="67bda-218">The website, using an event listener, will be aware of the change and can then validate the address, re-calculate shipping costs and taxes, and update [shippingOptions](/previous-versions/mt790440(v=vs.85)) to reflect the changed costs and shipping options available for the address selected \(if applicable\).</span></span>  

### <span data-ttu-id="67bda-219">送货选项</span><span class="sxs-lookup"><span data-stu-id="67bda-219">Shipping Options</span></span>  

<span data-ttu-id="67bda-220">通过将运货选项添加到[details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params)参数，可以向客户显示发[shippingOptions](/previous-versions/mt790440(v=vs.85))货选项。</span><span class="sxs-lookup"><span data-stu-id="67bda-220">Shipping options can be presented to the customer by adding [shippingOptions](/previous-versions/mt790440(v=vs.85)) to the [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter.</span></span>  <span data-ttu-id="67bda-221">可以通过为某一送货选项 `selected = True` 设置来创建默认值。</span><span class="sxs-lookup"><span data-stu-id="67bda-221">A default can be established by setting `selected = True` for one of the shipping options.</span></span>  
 
<span data-ttu-id="67bda-222">当用户选择或更新运货选项时，将运行 [onshippingOptionChange](/previous-versions/mt790436(v=vs.85)) 事件。</span><span class="sxs-lookup"><span data-stu-id="67bda-222">When the user selects or updates the shippingOptions, the [onshippingoptionchange](/previous-versions/mt790436(v=vs.85)) event will run.</span></span>  <span data-ttu-id="67bda-223">网站使用事件侦听器将知道更改，并可 [使用](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) 正确的运送金额更新细节参数。</span><span class="sxs-lookup"><span data-stu-id="67bda-223">The website, using an event listener, will be aware of the change and can update the [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter with the correct shipping amount.</span></span>  

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

## <span data-ttu-id="67bda-224">API 参考</span><span class="sxs-lookup"><span data-stu-id="67bda-224">API Reference</span></span>  

[<span data-ttu-id="67bda-225">付款请求 API</span><span class="sxs-lookup"><span data-stu-id="67bda-225">Payment Request API</span></span>](/previous-versions/mt790447(v=vs.85))  

## <span data-ttu-id="67bda-226">规范</span><span class="sxs-lookup"><span data-stu-id="67bda-226">Specification</span></span>
[<span data-ttu-id="67bda-227">付款请求 API</span><span class="sxs-lookup"><span data-stu-id="67bda-227">Payment Request API</span></span>](https://w3.org/TR/payment-request)

<!-- links -->  

[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具 |Microsoft 文档"  

[MicrosoftSupport44533505]: https://support.microsoft.com/help/4533505 "什么是 Microsoft Edge？"  

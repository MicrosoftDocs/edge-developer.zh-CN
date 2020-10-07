---
description: Learn how thePayment Request APIenables Microsoft Edge to act as an intermediary between merchants, consumers, and consumer payment methods stored in the cloud.
title: Payment Request API - Dev guide
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/20/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: edge, web development, html, css, javascript, developer
ms.openlocfilehash: 338940ab6f7e6bb04c6d5a8cc6ff0a198e7afbcc
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941854"
---
# <span data-ttu-id="d1eaa-104">Payment Request API (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="d1eaa-104">Payment Request API (EdgeHTML)</span></span>  

> [!NOTE]
> <span data-ttu-id="d1eaa-105">This article describes the workflow supported in the [legacy version of Microsoft Edge][MicrosoftSupport44533505].</span><span class="sxs-lookup"><span data-stu-id="d1eaa-105">This article describes the workflow supported in the [legacy version of Microsoft Edge][MicrosoftSupport44533505].</span></span>  <span data-ttu-id="d1eaa-106">Microsoft Edge \(Chromium\) supports the Payment Request API with a different implementation based on the Chromium project.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-106">Microsoft Edge \(Chromium\) supports the Payment Request API with a different implementation based on the Chromium project.</span></span>  

<span data-ttu-id="d1eaa-107">E-commerce sales continue growing at a rapid pace.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-107">E-commerce sales continue growing at a rapid pace.</span></span>  <span data-ttu-id="d1eaa-108">According to [eMarketer](https://www.emarketer.com), by 2018 digital sales are forecasted to increase by 23% from the levels measured in 2013.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-108">According to [eMarketer](https://www.emarketer.com), by 2018 digital sales are forecasted to increase by 23% from the levels measured in 2013.</span></span>  <span data-ttu-id="d1eaa-109">While consumers and businesses enjoy the convenience of e-commerce sales, challenges remain.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-109">While consumers and businesses enjoy the convenience of e-commerce sales, challenges remain.</span></span>  <span data-ttu-id="d1eaa-110">Today each e-commerce website owner needs to invest time to develop high quality payment checkout flows and validation rules.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-110">Today each e-commerce website owner needs to invest time to develop high quality payment checkout flows and validation rules.</span></span>  <span data-ttu-id="d1eaa-111">Consumers need to navigate different payment checkout flows and re-enter the same payment and shipping information on every site where they shop.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-111">Consumers need to navigate different payment checkout flows and re-enter the same payment and shipping information on every site where they shop.</span></span>  <span data-ttu-id="d1eaa-112">This can be time consuming and frustrating for consumers, leading to a high rate of shopping cart abandonment and decreased sales for merchants.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-112">This can be time consuming and frustrating for consumers, leading to a high rate of shopping cart abandonment and decreased sales for merchants.</span></span>  <span data-ttu-id="d1eaa-113">Merchants [estimate](http://baymard.com/lists/cart-abandonment-rate) between 60% and 70% of shopping carts are abandoned.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-113">Merchants [estimate](http://baymard.com/lists/cart-abandonment-rate) between 60% and 70% of shopping carts are abandoned.</span></span>  

<span data-ttu-id="d1eaa-114">The [Payment Request API](https://w3.org/TR/payment-request) standardizes the payment checkout process.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-114">The [Payment Request API](https://w3.org/TR/payment-request) standardizes the payment checkout process.</span></span>  <span data-ttu-id="d1eaa-115">This API requires less customization for web developers and provides a faster, more consistent, and therefore, less confusing experience for consumers.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-115">This API requires less customization for web developers and provides a faster, more consistent, and therefore, less confusing experience for consumers.</span></span>  <span data-ttu-id="d1eaa-116">Because consumers can select payment instruments and shipping addresses from their Microsoft account, they are required to enter less data to complete purchases which reduces the time and data entry required to complete a payment.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-116">Because consumers can select payment instruments and shipping addresses from their Microsoft account, they are required to enter less data to complete purchases which reduces the time and data entry required to complete a payment.</span></span>  

<span data-ttu-id="d1eaa-117">The [Payment Request API](https://w3.org/TR/payment-request) is an open, cross-browser standard that enables browsers to act as an intermediary between merchants, consumers, and the payment methods \(such as credit cards\) that consumers have stored in the cloud.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-117">The [Payment Request API](https://w3.org/TR/payment-request) is an open, cross-browser standard that enables browsers to act as an intermediary between merchants, consumers, and the payment methods \(such as credit cards\) that consumers have stored in the cloud.</span></span>  
  
<span data-ttu-id="d1eaa-118">In summary, when using the [Payment Request API](https://w3.org/TR/payment-request), customers shop on merchant websites as normal.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-118">In summary, when using the [Payment Request API](https://w3.org/TR/payment-request), customers shop on merchant websites as normal.</span></span>  <span data-ttu-id="d1eaa-119">When ready to pay, the merchant website calls the **Payment Request** API to create a **Payment Request** and passes the relevant payment information \(such as supported payment methods, purchase amount, currency, and so on\) to the browser.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-119">When ready to pay, the merchant website calls the **Payment Request** API to create a **Payment Request** and passes the relevant payment information \(such as supported payment methods, purchase amount, currency, and so on\) to the browser.</span></span>  

:::image type="complex" source="../media/payment_request_construct.png" alt-text="Payment request construct" lightbox="../media/payment_request_construct.png":::
   <span data-ttu-id="d1eaa-121">Payment request construct</span><span class="sxs-lookup"><span data-stu-id="d1eaa-121">Payment request construct</span></span>  
:::image-end:::  

<span data-ttu-id="d1eaa-122">The browser authenticates the user, enables the user to select a supported payment method on file, and processes the payment details.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-122">The browser authenticates the user, enables the user to select a supported payment method on file, and processes the payment details.</span></span>  <span data-ttu-id="d1eaa-123">The browser then sends the payment information details back to the merchant website, so that the merchant can complete the payment.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-123">The browser then sends the payment information details back to the merchant website, so that the merchant can complete the payment.</span></span>  <span data-ttu-id="d1eaa-124">In addition to receiving payment information, the merchant can also elect to receive shipping information as part of the **Payment Request**.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-124">In addition to receiving payment information, the merchant can also elect to receive shipping information as part of the **Payment Request**.</span></span>  

:::image type="complex" source="../media/payment_response_construct.png" alt-text="Payment request construct" lightbox="../media/payment_response_construct.png":::
   <span data-ttu-id="d1eaa-126">Payment response construct</span><span class="sxs-lookup"><span data-stu-id="d1eaa-126">Payment response construct</span></span>  
:::image-end:::  

<span data-ttu-id="d1eaa-127">To see the Payment Request API in action, as well as get an overview of how to use it, check out this video.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-127">To see the Payment Request API in action, as well as get an overview of how to use it, check out this video.</span></span>  

> [!VIDEO https://channel9.msdn.com/Blogs/One-Dev-Minute/Using-the-Payments-Request-API/player]  

> [!NOTE]
> <span data-ttu-id="d1eaa-128">The Payment Request API is supported in Microsoft Edge build 14992 or newer.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-128">The Payment Request API is supported in Microsoft Edge build 14992 or newer.</span></span>  

## <span data-ttu-id="d1eaa-129">Creating a Payment Request</span><span class="sxs-lookup"><span data-stu-id="d1eaa-129">Creating a Payment Request</span></span>  

<span data-ttu-id="d1eaa-130">Web pages create a **Payment Request** typically when the user initiates a payment process by clicking a "buy" button.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-130">Web pages create a **Payment Request** typically when the user initiates a payment process by clicking a "buy" button.</span></span>  <span data-ttu-id="d1eaa-131">The **Payment Request** [constructor](/previous-versions/mt790440(v=vs.85)) includes methodData, details, and options.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-131">The **Payment Request** [constructor](/previous-versions/mt790440(v=vs.85)) includes methodData, details, and options.</span></span>  

```javascript
var payment = new PaymentRequest ( 
    methodData,  // required payment method data including payment method identifiers 
    details,     // required transaction information 
    options      // optional information like shipping or contact info to be returned 
); 
```  

<span data-ttu-id="d1eaa-132">The [methodData](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter contains a list of the payment methods and networks accepted by the website and any associated payment method specific data.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-132">The [methodData](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter contains a list of the payment methods and networks accepted by the website and any associated payment method specific data.</span></span>  <span data-ttu-id="d1eaa-133">In Microsoft Edge, this list is matched with the supported payment methods that the shopper has saved in their Microsoft account and results in the "pay with" list in the payment user experience.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-133">In Microsoft Edge, this list is matched with the supported payment methods that the shopper has saved in their Microsoft account and results in the "pay with" list in the payment user experience.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_with.png" alt-text="Payment request construct" lightbox="../media/pay_with.png":::
         <span data-ttu-id="d1eaa-135">The **pay with** list in the Microsoft Wallet user experience</span><span class="sxs-lookup"><span data-stu-id="d1eaa-135">The **pay with** list in the Microsoft Wallet user experience</span></span>  
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

<span data-ttu-id="d1eaa-136">The [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter contains information that the merchant wishes to convey to the customer about the transaction.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-136">The [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter contains information that the merchant wishes to convey to the customer about the transaction.</span></span>  <span data-ttu-id="d1eaa-137">These include order summary items like total, tax, shipping amount, and other summary level items impacting the payment amount.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-137">These include order summary items like total, tax, shipping amount, and other summary level items impacting the payment amount.</span></span>  <span data-ttu-id="d1eaa-138">These are not intended to be order line items.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-138">These are not intended to be order line items.</span></span>  
  
<span data-ttu-id="d1eaa-139">The [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter is also used to define shipping options available to the customer when required.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-139">The [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter is also used to define shipping options available to the customer when required.</span></span>  <span data-ttu-id="d1eaa-140">More details are included in the **Payment Request** with Shipping section below.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-140">More details are included in the **Payment Request** with Shipping section below.</span></span>  

<span data-ttu-id="d1eaa-141">Each [detail](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) line includes a label for the currency and the amount.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-141">Each [detail](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) line includes a label for the currency and the amount.</span></span>  

> [!NOTE]
> <span data-ttu-id="d1eaa-142">The **Payment Request** does not calculate the sum or total of these amounts.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-142">The **Payment Request** does not calculate the sum or total of these amounts.</span></span>  <span data-ttu-id="d1eaa-143">It is the responsibility of the merchant's website to ensure that the line items total correctly.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-143">It is the responsibility of the merchant's website to ensure that the line items total correctly.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/show_details.png" alt-text="Payment request construct" lightbox="../media/show_details.png":::
         <span data-ttu-id="d1eaa-145">Subtotal, shipping, taxes, and total details</span><span class="sxs-lookup"><span data-stu-id="d1eaa-145">Subtotal, shipping, taxes, and total details</span></span>  
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

<span data-ttu-id="d1eaa-146">[PaymentRequest](/previous-versions/mt790440(v=vs.85)) does not support refunds, so the amounts should always be positive; individual list items can be negative, such as discounts.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-146">[PaymentRequest](/previous-versions/mt790440(v=vs.85)) does not support refunds, so the amounts should always be positive; individual list items can be negative, such as discounts.</span></span>  

<span data-ttu-id="d1eaa-147">The browser will render the labels as you define them and automatically render the correct currency formatting based on the customer's locale.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-147">The browser will render the labels as you define them and automatically render the correct currency formatting based on the customer's locale.</span></span>  <span data-ttu-id="d1eaa-148">Note that the labels should be rendered in the same language as your content.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-148">Note that the labels should be rendered in the same language as your content.</span></span>  

<span data-ttu-id="d1eaa-149">The [options](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter defines data the web page wants returned from the **Payment Request**.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-149">The [options](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter defines data the web page wants returned from the **Payment Request**.</span></span>  <span data-ttu-id="d1eaa-150">This also defines the data that needs to be collected, including if shipping, email address, phone number or all are required.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-150">This also defines the data that needs to be collected, including if shipping, email address, phone number or all are required.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/email_snippet.png" alt-text="Payment request construct" lightbox="../media/email_snippet.png":::
         <span data-ttu-id="d1eaa-152">Email address dropdown</span><span class="sxs-lookup"><span data-stu-id="d1eaa-152">Email address dropdown</span></span>  
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

## <span data-ttu-id="d1eaa-153">Showing the Payment Request</span><span class="sxs-lookup"><span data-stu-id="d1eaa-153">Showing the Payment Request</span></span>  

<span data-ttu-id="d1eaa-154">The [show()](/previous-versions/mt790448(v=vs.85)) method is called by the web page to allow the user to interact with the **Payment Request** user interface.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-154">The [show()](/previous-versions/mt790448(v=vs.85)) method is called by the web page to allow the user to interact with the **Payment Request** user interface.</span></span>  <span data-ttu-id="d1eaa-155">The [show()](/previous-versions/mt790448(v=vs.85)) method returns a Promise that will be resolved when the user authorizes the payment request.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-155">The [show()](/previous-versions/mt790448(v=vs.85)) method returns a Promise that will be resolved when the user authorizes the payment request.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/pay_screen_default.png" alt-text="Payment request construct" lightbox="../media/pay_screen_default.png":::
         <span data-ttu-id="d1eaa-157">Confirm and pay details</span><span class="sxs-lookup"><span data-stu-id="d1eaa-157">Confirm and pay details</span></span>  
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

## <span data-ttu-id="d1eaa-158">Aborting a Payment Request</span><span class="sxs-lookup"><span data-stu-id="d1eaa-158">Aborting a Payment Request</span></span>  
 
<span data-ttu-id="d1eaa-159">The [abort()](/previous-versions/mt790437(v=vs.85)) method can be called by the web page any time after the [show()](/previous-versions/mt790448(v=vs.85)) method is called, up until the point where the Promise is resolved.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-159">The [abort()](/previous-versions/mt790437(v=vs.85)) method can be called by the web page any time after the [show()](/previous-versions/mt790448(v=vs.85)) method is called, up until the point where the Promise is resolved.</span></span>  <span data-ttu-id="d1eaa-160">The [abort()](/previous-versions/mt790437(v=vs.85)) method will cause the browser to abort the **Payment Request** and close the **Payment Request** user interface.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-160">The [abort()](/previous-versions/mt790437(v=vs.85)) method will cause the browser to abort the **Payment Request** and close the **Payment Request** user interface.</span></span>  <span data-ttu-id="d1eaa-161">For example, a web page may choose to abort if the user did not complete the transaction in the required amount of time.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-161">For example, a web page may choose to abort if the user did not complete the transaction in the required amount of time.</span></span>  

```javascript
payment.abort();
```  

## <span data-ttu-id="d1eaa-162">Payment Response</span><span class="sxs-lookup"><span data-stu-id="d1eaa-162">Payment Response</span></span>  
<span data-ttu-id="d1eaa-163">When the customer approves the **Payment Request**, a **Payment Response** is returned to the website.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-163">When the customer approves the **Payment Request**, a **Payment Response** is returned to the website.</span></span>  <span data-ttu-id="d1eaa-164">The **Payment Response** includes the following:</span><span class="sxs-lookup"><span data-stu-id="d1eaa-164">The **Payment Response** includes the following:</span></span>  

 <span data-ttu-id="d1eaa-165">Property</span><span class="sxs-lookup"><span data-stu-id="d1eaa-165">Property</span></span>      | <span data-ttu-id="d1eaa-166">说明</span><span class="sxs-lookup"><span data-stu-id="d1eaa-166">Description</span></span> | <span data-ttu-id="d1eaa-167">Required</span><span class="sxs-lookup"><span data-stu-id="d1eaa-167">Required</span></span> | <span data-ttu-id="d1eaa-168">Additional Info</span><span class="sxs-lookup"><span data-stu-id="d1eaa-168">Additional Info</span></span>
|---------------|-----------------|-------|-----------------|
[<span data-ttu-id="d1eaa-169">methodName</span><span class="sxs-lookup"><span data-stu-id="d1eaa-169">methodName</span></span>](/previous-versions/mt790656(v=vs.85)) | <span data-ttu-id="d1eaa-170">The ID for the payment method selected by the user</span><span class="sxs-lookup"><span data-stu-id="d1eaa-170">The ID for the payment method selected by the user</span></span> | <span data-ttu-id="d1eaa-171">Y</span><span class="sxs-lookup"><span data-stu-id="d1eaa-171">Y</span></span> | |   
[<span data-ttu-id="d1eaa-172">details</span><span class="sxs-lookup"><span data-stu-id="d1eaa-172">details</span></span>](/previous-versions/mt790655(v=vs.85)) | <span data-ttu-id="d1eaa-173">A JSON object that includes all of the data the merchant requires to process the transaction using the selected payment method or a payment token</span><span class="sxs-lookup"><span data-stu-id="d1eaa-173">A JSON object that includes all of the data the merchant requires to process the transaction using the selected payment method or a payment token</span></span> | <span data-ttu-id="d1eaa-174">Y</span><span class="sxs-lookup"><span data-stu-id="d1eaa-174">Y</span></span> | <span data-ttu-id="d1eaa-175">[Basic Card](https://w3c.github.io/payment-method-basic-card) Dictionary:  cardholderName; cardNumber; expiryMonth; expiryYear; cardSecurityCode; billingAddress;</span><span class="sxs-lookup"><span data-stu-id="d1eaa-175">[Basic Card](https://w3c.github.io/payment-method-basic-card) Dictionary:  cardholderName; cardNumber; expiryMonth; expiryYear; cardSecurityCode; billingAddress;</span></span> |   
[<span data-ttu-id="d1eaa-176">shippingAddress</span><span class="sxs-lookup"><span data-stu-id="d1eaa-176">shippingAddress</span></span>](/previous-versions/mt790445(v=vs.85)) | <span data-ttu-id="d1eaa-177">The shipping address selected by the user</span><span class="sxs-lookup"><span data-stu-id="d1eaa-177">The shipping address selected by the user</span></span>  |  <span data-ttu-id="d1eaa-178">Optional.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-178">Optional.</span></span>  <span data-ttu-id="d1eaa-179">Required when [requestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span><span class="sxs-lookup"><span data-stu-id="d1eaa-179">Required when [requestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True`  | <span data-ttu-id="d1eaa-180">Address dictionary:  country; addressLine; region; city; dependentLocality; postalCode; sortingCode; languageCode; organization; recipient; phone</span><span class="sxs-lookup"><span data-stu-id="d1eaa-180">Address dictionary:  country; addressLine; region; city; dependentLocality; postalCode; sortingCode; languageCode; organization; recipient; phone</span></span> |  
[<span data-ttu-id="d1eaa-181">shippingOption</span><span class="sxs-lookup"><span data-stu-id="d1eaa-181">shippingOption</span></span>](/previous-versions/mt790446(v=vs.85)) | <span data-ttu-id="d1eaa-182">The ID for the selected shipping option</span><span class="sxs-lookup"><span data-stu-id="d1eaa-182">The ID for the selected shipping option</span></span> | <span data-ttu-id="d1eaa-183">Optional.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-183">Optional.</span></span>  <span data-ttu-id="d1eaa-184">Required when [requestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span><span class="sxs-lookup"><span data-stu-id="d1eaa-184">Required when [requestShipping](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True`  | |   
[<span data-ttu-id="d1eaa-185">payerName</span><span class="sxs-lookup"><span data-stu-id="d1eaa-185">payerName</span></span>](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | <span data-ttu-id="d1eaa-186">The name provided by the user</span><span class="sxs-lookup"><span data-stu-id="d1eaa-186">The name provided by the user</span></span>  | <span data-ttu-id="d1eaa-187">Optional.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-187">Optional.</span></span>  <span data-ttu-id="d1eaa-188">Required when [requestPayerName](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span><span class="sxs-lookup"><span data-stu-id="d1eaa-188">Required when [requestPayerName](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True` | |  
[<span data-ttu-id="d1eaa-189">payerEmail</span><span class="sxs-lookup"><span data-stu-id="d1eaa-189">payerEmail</span></span>](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | <span data-ttu-id="d1eaa-190">The email address selected by the user</span><span class="sxs-lookup"><span data-stu-id="d1eaa-190">The email address selected by the user</span></span> | <span data-ttu-id="d1eaa-191">Optional.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-191">Optional.</span></span>  <span data-ttu-id="d1eaa-192">Required when [requestPayerEmail](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span><span class="sxs-lookup"><span data-stu-id="d1eaa-192">Required when [requestPayerEmail](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True`  | |  
[<span data-ttu-id="d1eaa-193">PayerPhone</span><span class="sxs-lookup"><span data-stu-id="d1eaa-193">PayerPhone</span></span>](/previous-versions/mt790440(v=vs.85)#PaymentOptions) | <span data-ttu-id="d1eaa-194">The phone number selected by the user</span><span class="sxs-lookup"><span data-stu-id="d1eaa-194">The phone number selected by the user</span></span> | <span data-ttu-id="d1eaa-195">Optional.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-195">Optional.</span></span>  <span data-ttu-id="d1eaa-196">Required when [requestPayerPhone](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span><span class="sxs-lookup"><span data-stu-id="d1eaa-196">Required when [requestPayerPhone](/previous-versions/mt790440(v=vs.85)#PaymentOptions) is</span></span> `True` | |  

<span data-ttu-id="d1eaa-197">The [details](/previous-versions/mt790655(v=vs.85)#PaymentRequest_params) JSON object in the **Payment Response** will contain the payment data required by the merchant to process a payment.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-197">The [details](/previous-versions/mt790655(v=vs.85)#PaymentRequest_params) JSON object in the **Payment Response** will contain the payment data required by the merchant to process a payment.</span></span>  <span data-ttu-id="d1eaa-198">In its simplest form, the response will be a [Basic Card](https://w3c.github.io/payment-method-basic-card) payload containing cleartext payment card details.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-198">In its simplest form, the response will be a [Basic Card](https://w3c.github.io/payment-method-basic-card) payload containing cleartext payment card details.</span></span>  <span data-ttu-id="d1eaa-199">Where merchants have arrangements with additional gateway/processor partners for them to provide payments support, the merchant may require a payload the processor can handle.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-199">Where merchants have arrangements with additional gateway/processor partners for them to provide payments support, the merchant may require a payload the processor can handle.</span></span>  <span data-ttu-id="d1eaa-200">These can take the shape of a processor/gateway token or an encrypted payment instrument.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-200">These can take the shape of a processor/gateway token or an encrypted payment instrument.</span></span>  <span data-ttu-id="d1eaa-201">These payment methods are outside the scope of this document and will be covered in documentation specific to the processor.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-201">These payment methods are outside the scope of this document and will be covered in documentation specific to the processor.</span></span>  <span data-ttu-id="d1eaa-202">Additionally, to receive a [Basic Card](https://w3c.github.io/payment-method-basic-card) response, no additional onboarding to Microsoft is required by the developer, unlike other processor/gateway specific payment methods which may require encryption key onboarding or request authorization \(oAuth\).</span><span class="sxs-lookup"><span data-stu-id="d1eaa-202">Additionally, to receive a [Basic Card](https://w3c.github.io/payment-method-basic-card) response, no additional onboarding to Microsoft is required by the developer, unlike other processor/gateway specific payment methods which may require encryption key onboarding or request authorization \(oAuth\).</span></span>  

<span data-ttu-id="d1eaa-203">Upon receiving the **Payment Response**, the website submits the payment information to their payment processor.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-203">Upon receiving the **Payment Response**, the website submits the payment information to their payment processor.</span></span>  <span data-ttu-id="d1eaa-204">The browser will display a spinner page while the payment is being processed.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-204">The browser will display a spinner page while the payment is being processed.</span></span>  

:::image type="complex" source="../media/loading_screen.png" alt-text="Payment request construct" lightbox="../media/loading_screen.png":::
   <span data-ttu-id="d1eaa-206">The page displayed when the payment is being processed</span><span class="sxs-lookup"><span data-stu-id="d1eaa-206">The page displayed when the payment is being processed</span></span>  
:::image-end:::  

<span data-ttu-id="d1eaa-207">Once the payment is complete, the web page calls the [complete()](/previous-versions/mt790642(v=vs.85)) method and passes a value of **success** or **fail**.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-207">Once the payment is complete, the web page calls the [complete()](/previous-versions/mt790642(v=vs.85)) method and passes a value of **success** or **fail**.</span></span>  <span data-ttu-id="d1eaa-208">The [complete()](/previous-versions/mt790642(v=vs.85)) method informs the browser that the purchase is finished and the appropriate terminating UI screen should be shown depending on the value of **success** or **fail**.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-208">The [complete()](/previous-versions/mt790642(v=vs.85)) method informs the browser that the purchase is finished and the appropriate terminating UI screen should be shown depending on the value of **success** or **fail**.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_complete.png" alt-text="Payment request construct" lightbox="../media/response_payment-request_complete.png":::
         <span data-ttu-id="d1eaa-210">The UI displayed when the purchase succeeded</span><span class="sxs-lookup"><span data-stu-id="d1eaa-210">The UI displayed when the purchase succeeded</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/response_payment-request_failure.png" alt-text="Payment request construct" lightbox="../media/response_payment-request_failure.png":::
         <span data-ttu-id="d1eaa-212">The UI displayed when the purchase failed</span><span class="sxs-lookup"><span data-stu-id="d1eaa-212">The UI displayed when the purchase failed</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="d1eaa-213">Payment Request with Shipping</span><span class="sxs-lookup"><span data-stu-id="d1eaa-213">Payment Request with Shipping</span></span>  

### <span data-ttu-id="d1eaa-214">Shipping Address</span><span class="sxs-lookup"><span data-stu-id="d1eaa-214">Shipping Address</span></span>  

<span data-ttu-id="d1eaa-215">For sales that require shipping physical goods, a shipping address is required.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-215">For sales that require shipping physical goods, a shipping address is required.</span></span>  <span data-ttu-id="d1eaa-216">To include a shipping address, set `requestShipping = True` in the [options](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter of the request.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-216">To include a shipping address, set `requestShipping = True` in the [options](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter of the request.</span></span>  

<span data-ttu-id="d1eaa-217">When the user selects or updates the shipping address, the [onshippingaddresschange](/previous-versions/mt790442(v=vs.85)) event will run.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-217">When the user selects or updates the shipping address, the [onshippingaddresschange](/previous-versions/mt790442(v=vs.85)) event will run.</span></span>  <span data-ttu-id="d1eaa-218">The website, using an event listener, will be aware of the change and can then validate the address, re-calculate shipping costs and taxes, and update [shippingOptions](/previous-versions/mt790440(v=vs.85)) to reflect the changed costs and shipping options available for the address selected \(if applicable\).</span><span class="sxs-lookup"><span data-stu-id="d1eaa-218">The website, using an event listener, will be aware of the change and can then validate the address, re-calculate shipping costs and taxes, and update [shippingOptions](/previous-versions/mt790440(v=vs.85)) to reflect the changed costs and shipping options available for the address selected \(if applicable\).</span></span>  

### <span data-ttu-id="d1eaa-219">Shipping Options</span><span class="sxs-lookup"><span data-stu-id="d1eaa-219">Shipping Options</span></span>  

<span data-ttu-id="d1eaa-220">Shipping options can be presented to the customer by adding [shippingOptions](/previous-versions/mt790440(v=vs.85)) to the [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-220">Shipping options can be presented to the customer by adding [shippingOptions](/previous-versions/mt790440(v=vs.85)) to the [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter.</span></span>  <span data-ttu-id="d1eaa-221">A default can be established by setting `selected = True` for one of the shipping options.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-221">A default can be established by setting `selected = True` for one of the shipping options.</span></span>  
 
<span data-ttu-id="d1eaa-222">When the user selects or updates the shippingOptions, the [onshippingoptionchange](/previous-versions/mt790436(v=vs.85)) event will run.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-222">When the user selects or updates the shippingOptions, the [onshippingoptionchange](/previous-versions/mt790436(v=vs.85)) event will run.</span></span>  <span data-ttu-id="d1eaa-223">The website, using an event listener, will be aware of the change and can update the [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter with the correct shipping amount.</span><span class="sxs-lookup"><span data-stu-id="d1eaa-223">The website, using an event listener, will be aware of the change and can update the [details](/previous-versions/mt790440(v=vs.85)#PaymentRequest_params) parameter with the correct shipping amount.</span></span>  

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

## <span data-ttu-id="d1eaa-224">API Reference</span><span class="sxs-lookup"><span data-stu-id="d1eaa-224">API Reference</span></span>  

[<span data-ttu-id="d1eaa-225">Payment Request API</span><span class="sxs-lookup"><span data-stu-id="d1eaa-225">Payment Request API</span></span>](/previous-versions/mt790447(v=vs.85))  

## <span data-ttu-id="d1eaa-226">Specification</span><span class="sxs-lookup"><span data-stu-id="d1eaa-226">Specification</span></span>
[<span data-ttu-id="d1eaa-227">Payment Request API</span><span class="sxs-lookup"><span data-stu-id="d1eaa-227">Payment Request API</span></span>](https://w3.org/TR/payment-request)

<!-- links -->  

[DevtoolsGuideChromium]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) Developer Tools | Microsoft Docs"  

[MicrosoftSupport44533505]: https://support.microsoft.com/help/4533505 "What is Microsoft Edge Legacy?"  

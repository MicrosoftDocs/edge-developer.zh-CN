---
description: 公开操作是否已成功完成或失败
title: MSWebViewAsyncOperation 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: d6e03af2a0205938f19120076aa0ad622539d7e5
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752120"
---
# <span data-ttu-id="5a76e-104">MSWebViewAsyncOperation 对象</span><span class="sxs-lookup"><span data-stu-id="5a76e-104">MSWebViewAsyncOperation object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="5a76e-105">公开操作是否已成功完成或失败。</span><span class="sxs-lookup"><span data-stu-id="5a76e-105">Exposes whether the operation completed successfully or failed.</span></span>  

## <span data-ttu-id="5a76e-106">事件</span><span class="sxs-lookup"><span data-stu-id="5a76e-106">Events</span></span>  

### <span data-ttu-id="5a76e-107">完成</span><span class="sxs-lookup"><span data-stu-id="5a76e-107">complete</span></span>  

<span data-ttu-id="5a76e-108">指示操作已完成。</span><span class="sxs-lookup"><span data-stu-id="5a76e-108">Indicates that the operation completed.</span></span>  

```javascript
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
MSWebViewAsyncOperation.addEventListener("complete", handler);
MSWebViewAsyncOperation.removeEventListener("complete", handler);
```  

#### <span data-ttu-id="5a76e-109">事件信息</span><span class="sxs-lookup"><span data-stu-id="5a76e-109">Event Information</span></span>  

|  |  |  
|:--- |:--- |  
| **<span data-ttu-id="5a76e-110">接口</span><span class="sxs-lookup"><span data-stu-id="5a76e-110">Interface</span></span>** | **<span data-ttu-id="5a76e-111">事件</span><span class="sxs-lookup"><span data-stu-id="5a76e-111">Event</span></span>** |  
| **<span data-ttu-id="5a76e-112">同步</span><span class="sxs-lookup"><span data-stu-id="5a76e-112">Synchronous</span></span>** |<span data-ttu-id="5a76e-113">是</span><span class="sxs-lookup"><span data-stu-id="5a76e-113">Yes</span></span> |  
| **<span data-ttu-id="5a76e-114">气泡</span><span class="sxs-lookup"><span data-stu-id="5a76e-114">Bubbles</span></span>** |<span data-ttu-id="5a76e-115">否</span><span class="sxs-lookup"><span data-stu-id="5a76e-115">No</span></span> |   
| **<span data-ttu-id="5a76e-116">可取消</span><span class="sxs-lookup"><span data-stu-id="5a76e-116">Cancelable</span></span>** |<span data-ttu-id="5a76e-117">否</span><span class="sxs-lookup"><span data-stu-id="5a76e-117">No</span></span> |  

### <span data-ttu-id="5a76e-118">错误</span><span class="sxs-lookup"><span data-stu-id="5a76e-118">error</span></span>  

<span data-ttu-id="5a76e-119">指示操作出现错误。</span><span class="sxs-lookup"><span data-stu-id="5a76e-119">Indicates that there was an error with the operation.</span></span>  

```javascript
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
MSWebViewAsyncOperation.addEventListener("error", handler);
MSWebViewAsyncOperation.removeEventListener("error", handler);
```  

#### <span data-ttu-id="5a76e-120">事件信息</span><span class="sxs-lookup"><span data-stu-id="5a76e-120">Event Information</span></span>  

|  |  |  
|:--- |:--- |  
| **<span data-ttu-id="5a76e-121">接口</span><span class="sxs-lookup"><span data-stu-id="5a76e-121">Interface</span></span>** | **<span data-ttu-id="5a76e-122">事件</span><span class="sxs-lookup"><span data-stu-id="5a76e-122">Event</span></span>** |  
| **<span data-ttu-id="5a76e-123">同步</span><span class="sxs-lookup"><span data-stu-id="5a76e-123">Synchronous</span></span>** | <span data-ttu-id="5a76e-124">是</span><span class="sxs-lookup"><span data-stu-id="5a76e-124">Yes</span></span> |  
| **<span data-ttu-id="5a76e-125">气泡</span><span class="sxs-lookup"><span data-stu-id="5a76e-125">Bubbles</span></span>** | <span data-ttu-id="5a76e-126">否</span><span class="sxs-lookup"><span data-stu-id="5a76e-126">No</span></span> |  
| **<span data-ttu-id="5a76e-127">可取消</span><span class="sxs-lookup"><span data-stu-id="5a76e-127">Cancelable</span></span>** | <span data-ttu-id="5a76e-128">否</span><span class="sxs-lookup"><span data-stu-id="5a76e-128">No</span></span> |  

## <span data-ttu-id="5a76e-129">方法</span><span class="sxs-lookup"><span data-stu-id="5a76e-129">Methods</span></span>  

### <span data-ttu-id="5a76e-130">start</span><span class="sxs-lookup"><span data-stu-id="5a76e-130">start</span></span>  

<span data-ttu-id="5a76e-131">调用以启动异步任务。</span><span class="sxs-lookup"><span data-stu-id="5a76e-131">Called to start the async task.</span></span>  

```javascript
MSWebViewAsyncOperation.start();
```  

### <span data-ttu-id="5a76e-132">参数</span><span class="sxs-lookup"><span data-stu-id="5a76e-132">Parameters</span></span>  

<span data-ttu-id="5a76e-133">此方法没有参数。</span><span class="sxs-lookup"><span data-stu-id="5a76e-133">This method does not have parameters.</span></span>  

### <span data-ttu-id="5a76e-134">返回值</span><span class="sxs-lookup"><span data-stu-id="5a76e-134">Return value</span></span>  

<span data-ttu-id="5a76e-135">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="5a76e-135">This method does not return a value.</span></span>  

## <span data-ttu-id="5a76e-136">属性</span><span class="sxs-lookup"><span data-stu-id="5a76e-136">Properties</span></span>  

### <span data-ttu-id="5a76e-137">错误</span><span class="sxs-lookup"><span data-stu-id="5a76e-137">error</span></span>  

<span data-ttu-id="5a76e-138">出现的错误。</span><span class="sxs-lookup"><span data-stu-id="5a76e-138">The error that occurred.</span></span>  

<span data-ttu-id="5a76e-139">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="5a76e-139">This property is read-only.</span></span>  

```javascript
var error = MSWebViewAsyncOperation.error;
```  

#### <span data-ttu-id="5a76e-140">属性值</span><span class="sxs-lookup"><span data-stu-id="5a76e-140">Property value</span></span>  

<span data-ttu-id="5a76e-141">类型： **DOMError**</span><span class="sxs-lookup"><span data-stu-id="5a76e-141">Type: **DOMError**</span></span>  

### <span data-ttu-id="5a76e-142">oncomplete</span><span class="sxs-lookup"><span data-stu-id="5a76e-142">oncomplete</span></span>  

<span data-ttu-id="5a76e-143">**完整**的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="5a76e-143">The **complete** event handler.</span></span>  

```javascript
var oncomplete = MSWebViewAsyncOperation.oncomplete;
```  

#### <span data-ttu-id="5a76e-144">属性值</span><span class="sxs-lookup"><span data-stu-id="5a76e-144">Property value</span></span>  

<span data-ttu-id="5a76e-145">类型： **EventHandler**</span><span class="sxs-lookup"><span data-stu-id="5a76e-145">Type: **EventHandler**</span></span>  

### <span data-ttu-id="5a76e-146">onerror</span><span class="sxs-lookup"><span data-stu-id="5a76e-146">onerror</span></span>  

<span data-ttu-id="5a76e-147">**错误**事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="5a76e-147">The **error** event handler.</span></span>  

```javascript
var onerror = MSWebViewAsyncOperation.onerror;
```  

#### <span data-ttu-id="5a76e-148">属性值</span><span class="sxs-lookup"><span data-stu-id="5a76e-148">Property value</span></span>  

<span data-ttu-id="5a76e-149">类型： **EventHandler**</span><span class="sxs-lookup"><span data-stu-id="5a76e-149">Type: **EventHandler**</span></span>  

### <span data-ttu-id="5a76e-150">readyState</span><span class="sxs-lookup"><span data-stu-id="5a76e-150">readyState</span></span>  

<span data-ttu-id="5a76e-151">描述对象的准备状态。</span><span class="sxs-lookup"><span data-stu-id="5a76e-151">Describes the ready state of the object.</span></span>  

<span data-ttu-id="5a76e-152">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="5a76e-152">This property is read-only.</span></span>  

```javascript
var readyState = MSWebViewAsyncOperation.readyState;
```  

#### <span data-ttu-id="5a76e-153">属性值</span><span class="sxs-lookup"><span data-stu-id="5a76e-153">Property value</span></span>  

<span data-ttu-id="5a76e-154">类型：**无符号的短**</span><span class="sxs-lookup"><span data-stu-id="5a76e-154">Type: **unsigned short**</span></span>  

### <span data-ttu-id="5a76e-155">结果</span><span class="sxs-lookup"><span data-stu-id="5a76e-155">result</span></span>  

<span data-ttu-id="5a76e-156">操作的结果。</span><span class="sxs-lookup"><span data-stu-id="5a76e-156">The result of the operation.</span></span>  

<span data-ttu-id="5a76e-157">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="5a76e-157">This property is read-only.</span></span>  

```javascript
var result = MSWebViewAsyncOperation.result;
```  

#### <span data-ttu-id="5a76e-158">属性值</span><span class="sxs-lookup"><span data-stu-id="5a76e-158">Property value</span></span>  

<span data-ttu-id="5a76e-159">类型：任何</span><span class="sxs-lookup"><span data-stu-id="5a76e-159">Type: any</span></span>  

### <span data-ttu-id="5a76e-160">target</span><span class="sxs-lookup"><span data-stu-id="5a76e-160">target</span></span>  

<span data-ttu-id="5a76e-161">操作的目标。</span><span class="sxs-lookup"><span data-stu-id="5a76e-161">The target of the operation.</span></span>  

<span data-ttu-id="5a76e-162">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="5a76e-162">This property is read-only.</span></span>  

```javascript
var target = MSWebViewAsyncOperation.target;
```  

#### <span data-ttu-id="5a76e-163">属性值</span><span class="sxs-lookup"><span data-stu-id="5a76e-163">Property value</span></span>  

<span data-ttu-id="5a76e-164">类型： [ **MSHTMLWebViewElement**](../webview.md)</span><span class="sxs-lookup"><span data-stu-id="5a76e-164">Type: [**MSHTMLWebViewElement**](../webview.md)</span></span>  

### <span data-ttu-id="5a76e-165">类型</span><span class="sxs-lookup"><span data-stu-id="5a76e-165">type</span></span>  

<span data-ttu-id="5a76e-166">操作的类型。</span><span class="sxs-lookup"><span data-stu-id="5a76e-166">The type of the operation.</span></span>  

<span data-ttu-id="5a76e-167">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="5a76e-167">This property is read-only.</span></span>  

```javascript
var type = MSWebViewAsyncOperation.type;
```  

#### <span data-ttu-id="5a76e-168">属性值</span><span class="sxs-lookup"><span data-stu-id="5a76e-168">Property value</span></span>  

<span data-ttu-id="5a76e-169">类型：**无符号的短**</span><span class="sxs-lookup"><span data-stu-id="5a76e-169">Type: **unsigned short**</span></span>  

---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: cc3cf67a03f81acc546ab17fded5d7430496033f
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652941"
---
# interface ICoreWebView2HttpHeadersCollectionIterator 

```
interface ICoreWebView2HttpHeadersCollectionIterator
  : public IUnknown
```

HTTP 标头集合的迭代器。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_HasCurrentHeader](#get_hascurrentheader) | 当迭代器未用完标题时，则为 True。
[GetCurrentHeader](#getcurrentheader) | 获取迭代器的当前 HTTP 标头的名称和值。
[MoveNext](#movenext) | 将迭代器移动到集合中的下一个 HTTP 标头。

请参阅[ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md)和[ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md)。 
```cpp
std::wstring RequestHeadersToJsonString(ICoreWebView2HttpRequestHeaders* requestHeaders)
{
    wil::com_ptr<ICoreWebView2HttpHeadersCollectionIterator> iterator;
    CHECK_FAILURE(requestHeaders->GetIterator(&iterator));
    BOOL hasCurrent = FALSE;
    std::wstring result = L"[";

    while (SUCCEEDED(iterator->get_HasCurrentHeader(&hasCurrent)) && hasCurrent)
    {
        wil::unique_cotaskmem_string name;
        wil::unique_cotaskmem_string value;

        CHECK_FAILURE(iterator->GetCurrentHeader(&name, &value));
        result += L"{\"name\": " + EncodeQuote(name.get())
            + L", \"value\": " + EncodeQuote(value.get()) + L"}";

        BOOL hasNext = FALSE;
        CHECK_FAILURE(iterator->MoveNext(&hasNext));
        if (hasNext)
        {
            result += L", ";
        }
    }

    return result + L"]";
}
```

## 成员

#### get_HasCurrentHeader 

当迭代器未用完标题时，则为 True。

> public HRESULT [get_HasCurrentHeader](#get_hascurrentheader)（BOOL * hasCurrent）

如果迭代器循环的目标集合为空或迭代程序已超过集合末尾，则为 false。

#### GetCurrentHeader 

获取迭代器的当前 HTTP 标头的名称和值。

> 公共 HRESULT [GetCurrentHeader](#getcurrentheader)（LPWSTR * NAME，LPWSTR * value）

如果对 MoveNext 的最后一次调用设置 has_next 为 FALSE，此方法将失败。

#### MoveNext 

将迭代器移动到集合中的下一个 HTTP 标头。

> 公共 HRESULT [MoveNext](#movenext)（BOOL * hasNext）

如果没有更多的 HTTP 标头，则 hasNext 参数将设置为 FALSE。 在此情况下，如果调用 GetCurrentHeader 方法，则该方法将失败。


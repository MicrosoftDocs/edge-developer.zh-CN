---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2HttpHeadersCollectionIterator
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2HttpHeadersCollectionIterator
ms.openlocfilehash: da1b9f3dbf9ba0ebd309e1017fe4e7f7e6526941
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011318"
---
# 0.9.579-接口 ICoreWebView2HttpHeadersCollectionIterator 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

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

请参阅 [ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) 和 [ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md)。 
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

> 公共 HRESULT [get_HasCurrentHeader](#get_hascurrentheader) (BOOL * hasCurrent) 

如果迭代器循环的目标集合为空或迭代程序已超过集合末尾，则为 false。

#### GetCurrentHeader 

获取迭代器的当前 HTTP 标头的名称和值。

> public HRESULT [GetCurrentHeader](#getcurrentheader) (LPWSTR * NAME，LPWSTR * value) 

如果对 MoveNext 的最后一次调用设置 has_next 为 FALSE，此方法将失败。

#### MoveNext 

将迭代器移动到集合中的下一个 HTTP 标头。

> 公共 HRESULT [MoveNext](#movenext) (BOOL * hasNext) 

如果没有更多的 HTTP 标头，则 hasNext 参数将设置为 FALSE。 在此情况下，如果调用 GetCurrentHeader 方法，则该方法将失败。


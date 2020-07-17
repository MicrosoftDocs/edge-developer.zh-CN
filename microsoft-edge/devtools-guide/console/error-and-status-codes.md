---
ms.assetid: 961ca575-6b93-4367-a72b-f3f02e5b9568
description: 常见控制台代码和建议修补程序引用
title: DevTools - 控制台错误和状态代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/10/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools, 控制台代码
ms.custom: seodec18
ms.localizationpriority: high
ms.openlocfilehash: 1daa4e2a02802763ad75db91d06bd785fea9ec08
ms.sourcegitcommit: 1e33cd41e5afb2e6dbdc19353011ff6c2b019f9c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2020
ms.locfileid: "10866062"
---
# 控制台错误和状态代码  

此引用可帮助你解释来自 DevTools [控制台](../console.md)的错误和状态消息。  使用下表按前缀 \(其中“x”表示 0&ndash;9 的数字\) 查找代码：

| 代码前缀 | 领域 | 描述 |  
|:--- | :--- |:--- |  
| [CSP143xx](#csp-codes) | 内容安全策略 | 使用 `Content-Security-Policy` HTTP 标头阻止的资源。  |  
| [CSS31xx](#css-codes) | 样式表 | 与 *Web 开放字体格式* \(WOFF\) 和*嵌入的 OpenType* \(EOT\) 字体源及主机服务器问题相关的错误。  |  
| [HTML1112-1300](#html-codes) | HTML | 其中大多数是特定于 Microsoft Internet Explorer 概念的旧版代码，如*文档模式*和*兼容性视图*。  |  
| [HTML1400-1532](#html5-parser-warnings) | HTML5 分析 | HTML5 分析程序引发的验证警告。  |  
| [HTTP](#http-codes) | 服务器错误和状态 | 从远程服务器返回的代码，用于响应 HTTP 请求。  |  
| [SCRIPT10xx](#javascript-syntax-errors) | JavaScript 语法错误 | 当其中一个 JavaScript 语句的结构违反一个或多个语法规则时，将出现此错误。  |  
| [SCRIPT50xx](#javascript-run-time-errors) | JavaScript 运行时错误 | 当脚本尝试执行系统无法执行的操作时，将出现此错误。  |  
| [SEC71xx](#security-codes) | 安全性 | 反映 Microsoft Edge 强制执行的安全条件，例如*混合内容*和*跟踪保护*。  |  
| [SVG560x](#svg-codes) | 可缩放的向量图形 |  目前不支持广泛的 SVG 调试，但出于调试目的，提供了一些控制台消息。  |  
| WebGL11_xxx | WebGL | 来自 WebGL 上下文的错误消息。  另请参阅 [GLSL 错误](https://msdn.microsoft.com/library/dn611835.aspx)。  |  
| [XML5xxx](#xml-codes) | XML | XML 分析和验证中的错误。  |  

## CSP 代码  

使用 `Content-Security-Policy` HTTP 标头阻止的资源将通过 DevTools 控制台报告，也可以选择将其报告回服务器。

| 代码 | 消息 | 描述 | 建议的修补程序 |
|:--- |:--- |:--- |:--- |
| CSP14301 | “未能分析 \[策略类型\]，因为 \<the reason for canceling the operation\> -- 策略将被忽略。” | 指定的安全策略类型 \(例如 script-src、base-uri\) 由于确定的原因失败，将被忽略。  | 请确保在单个指令中列出特定类型的所有必需资源。  例如，在 `script-src https://host1.com; script-src https://host2.com` 中，第二个指令将被忽略。  以下内容正确地将两个源指定为有效：`script-src https://host1.com https://host2.com`。  |
| CSP14302 | “未能分析 \[源 URL\] 处指令 \[指令类型\] \[策略类型\] 中的源 -- 源将被忽略。”                                                         | 大多数 CSP 指令需要一个或多个内容源 \(表明可从中加载内容的 URL\)。  此错误指向一个策略，该策略的一个指令包含尝试分析时失败的源 URL。  | 查看指定指令中定义的内容源 \(通常是 URL\)，可在指定的策略类型中找到它。  更正或替换源 URL 或删除指令。  <br /> *\*策略应包含一个 default-src 策略指令，当其他资源类型没有自己的策略时，它是一种备用策略。* |
| CSP14303 | “[策略类型] 策略为空。” | 策略类型 \(例如，HTTP 标头中的内容安全策略\) 为空。  | 可在 [http://content-security-policy.com](http://content-security-policy.com) 找到设置内容安全策略的快速参考。  |
| CSP14304 | “\[策略类型\] 源中指令 \[指令类型\] 的未知源 \[源 URL\] 将被忽略。” | 所标识指令中的批准 \(安全\) 内容来源未知，将被忽略。  | 选中标识为 \(通常是 URL\) 的内容源，确保其正确性。  |
| CSP14305 | “\[策略类型\] 源中指令[指令类型]的不支持源 \[源 URL\] 将被忽略。” | 此指令中列出的源 \(URL、关键字或数据\) 不受支持，将被忽略。  | 源网站的地址可能包含可选的前导通配符 \(星号字符，`*`\)。  例如，http://`*`.foo.com or mail.foo.com:*。  主机由空格分隔。  源也可能是关键字 \(none、self、unsafe-inline 和 unsafe-eval 均受支持\) 或数据 \(data:URIs、mediastream:URIs\)。  |
| CSP14306 | “没有为 \[策略类型\] 的指令 \[指令类型\] 指定源 - 这等同于使用“none”，并且将会阻止下载此类型的所有资源。” | 给出一个指令而未列出任何要访问的安全内容的源，就像不允许下载指令中指定的任何类型的资源一样。  | 源可以是一个或多个 Internet 主机名或 IP 地址，也可以是可选的 URL 方案和/或端口号。  |
| CSP14307 | “已为 \[策略类型\] 的指令 \[指令类型\] 提供了源 [源 URL]。” | 此指令中列出了重复源 \(URL、关键字或数据\)，将被忽略。  | 删除标识的重复源。  |
| CSP14308 | “未能在 [指令名称] 的 \[策略类型\] 中分析指令。” | 无法识别指令。  有关如何编写支持的指令的指导，请参阅 [http://content-security-policy.com](http://content-security-policy.com/)。  | 指令必须用分号分隔。  例如，如果你的应用程序从内容交付网络 \(例如，`https://cdn.example.net`\) 加载所有资源，并且你知道你不需要带框架的内容或任何插件，则策略可能如下所示：`Content-Security-Policy: default-src https://cdn.example.net; child-src 'none'; object-src 'none'.` *\*指令之间用分号分隔，指令中的源仅应使用空格分隔。* |
| CSP14309 | “\[策略类型\] 中 \[指令名称\] 的未知指令 -- 指令将被忽略。” | CSP 策略中设置的指令未知，将被忽略。  | 有关支持的指令的列表，请参阅 [http://content-security-policy.com](http://content-security-policy.com/)。  |
| CSP14310 | “\[策略类型\] 中 [指令名称] 的不支持指令 -- 指令将被忽略。” | 在策略类型 \(例如，`Content-Security-policy-Report-Only` 标题字段\) 中进行分析时发现一个指令，该指令不受支持，将被忽略。  有关支持的指令，请参阅 [http://content-security-policy.com](http://content-security-policy.com/)。  | 删除不受支持的指令。  **注意**：\<meta\> 元素或 `Content-Security-policy-Report-Only` 标题字段中不支持某些指令。  |
| CSP14311 | “\[策略类型\] 中已提供的指令 \[指令名称\] -- 重复指令将被忽略。” | 分析过程中发现重复指令，将忽略第二个指令及其源表达式。  | 删除重复脚本。  |
| CSP14312 | “在 [策略类型] 中，资源违反了指令[指令名称]：[目标 uri]。  将阻止资源。” | 在本示例中：“资源违反了主机定义的策略: 内联脚本中的指令 'script-src ms-appx: data: 'unsafe-eval'。  将阻止资源。” | 由于“主机定义”的策略中有 `'script-src ms-appx: data: 'unsafe-eval'` 指令，已阻止内联脚本 \(目标 URI\)。  <br /> 作者需要将所有内联脚本和样式移出行，因为用户代理无法确定攻击者是否插入了内联脚本。  删除内联脚本，并将其放在外部文件中。  |
| CSP14313 | “在 [策略类型] 中，资源违反了指令[指令名称]：[目标 uri]。  由于策略是“仅报告”，将不会阻止资源。” | 已确定资源违反了 `Content-Security-policy-Report-Only` 标头字段中指定的指令。  由于它采用 `Report-Only` 策略类型，因此不会阻止资源。  | 如果为了保护网站而应阻止此资源，请将指令移入 Content-Security-policy 标头字段。  |
| CSP14314 | “未能将策略冲突报告发送到 [目标目的地 URI]，因为 [取消操作的原因]。” | 报告违反策略时出现问题，应确定指定要向其发送报告的目标目的地以及未发送的原因。  | `report-uri` 指令指定当违反内容安全策略时，浏览器将用于发送报告的 URL。  ** 不能在 \<meta\> 标记中使用它。* |
| CSP14315 | “未能强制执行 [策略类型] 中的沙盒指令，因为 [取消操作的原因]。” | 由于所指定的原因，沙箱指令失败。  此指令对页面可以执行的操作（而不是页面可以加载的资源）采取限制。  如果存在沙盒指令，则会将页面视为在 iframe 内加载。  它可能会阻止弹出窗口和插件并阻止执行脚本。  | 将沙盒值保留为空，以便就地保留所有限制，或者添加以下值：`allow-forms`、`allow-same-origin`、`allow-scripts` 和 `allow-top-navigation`。  **\<meta\> 元素或 `Content-Security-policy-Report-Only` 标头字段中不支持沙盒指令。* |
| CSP14316 | “由于主机替代，将允许脚本 eval。” | 包含 `script-src` 或 `default-src` 指令后，除非分别指定 `unsafe-inline` 和 `unsafe-eval`，否则将禁用内联脚本和 `eval()`。  | `'unsafe-eval'` 允许使用 `eval()` 和类似的方法从字符串创建代码。  必须包含单引号。  ***注意**：这是不安全的，可能会使你的网站面临跨网站脚本漏洞风险。* |
| CSP14317 | “由于主机替代，将允许框架 [源名称]。” | 已允许标识的源框架，因为主机 CSP 策略中存在覆盖集。  | 策略可能包含 nonce 源表达式，这意味着源只能在一种情况下使用，并且在每次传输策略时，服务器都必须为该指令生成一个新值。  Nonce 将覆盖它们所处的指令的限制。  |

> [!NOTE]
> 对于用户受信任的安全区域中的网站，Microsoft Edge 不检查样式表的 MIME 类型。  

## CSS 代码  

以下错误采用 CSS31xx 格式，与 *Web 开放字体格式* \(WOFF\) 和*嵌入的 OpenType* \(EOT\) 字体源及主机服务器问题相关。  

| 代码 | 消息 | 描述 | 建议的修补程序 |
|:--- |:--- |:--- |:--- |
| CSS3111 | “@font-face 遇到未知错误” | “Web 开放字体格式 \(WOFF\)”和级联样式表 \(CSS\) 字体的“嵌入的 OpenType 字体 \(EOT\)”遇到未知问题。  | 检查 WOFF 字体来源。  尝试使用替代字体或来源，确定是否可以重现该问题。  |
| CSS3112 | “@font-face 未通过 WOFF 完整性检查” | Web 开放字体格式 (WOFF) 字体可能已损坏、不完整或格式不正确。  | 检查字体来源。  尝试使用已知正确的字体或来源，确定是否可以重现该问题。  |
| CSS3113 | “文档原点与 EOT 根字符串之间的 @font-face 不匹配” | 无法使用该字体，因为嵌入的 OpenType (EOT) 字体中的 URL (rootstring) 与使用该字体的文档的域不匹配。  | EOT 根字符串中的 URL 校验和可能不正确，表明字体 URL 已损坏或已更改。  确保该字体已获得许可，或者对使用该字体的网站具有权限。  |
| CSS3114 | “@font-face 未通过 OpenType 嵌入权限检查。  权限必须为“可安装”。” | 字体没有通过当前网页安装的权限。  | 获取用于嵌入字体的适当权限或许可证。  |
| CSS3115 | “@font-face 无法加载无效的 OpenType 字体”。 | 字体对此用途无效。  | 获取当前和有效字体的权限或许可证。  |
| CSS3116 | “@font-face 的跨原点请求失败。  无 Access-Control-Allow-Origin 标头。” | 可能未针对跨域访问对字体进行配置。  | 该字体不是通过与文档的相同来源提供的。  请确保使用“Access-Control-Allow-Origin”HTTP 标头让提供字体的主机允许使用该字体。                        |
| CSS3117 | “@font-face 的跨原点请求失败。  资源访问受限制。” | 可能未正确配置“Access-Control-Allow-Origin”标头，或者字体主机可能不允许你的页面使用此字体。  | 确保资源具有正确的权限和已正确配置的 HTTP 响应头，对提供字体的主机上的原点具有跨域访问权限。  |
| CSS3118 | “未能创建新的样式表。  文档中的样式表数量超过 \[最大数\] 个。” | Microsoft Edge 在呈现页面的过程中创建了超过 4095 个样式表对象。  | 这可能是由于 JavaScript 进程失去控制，也可能是生成系统出错。  减少正在生成的样式表对象数量。  |
| CSS3119 | “媒体 query -ms-view-state 已被弃用。  -ms-view-state 媒体查询可能已更改或无法在 Windows 8.1 后发布。  请改用 max-width 和 min-width 查询。” | CSS 中包含 `-ms-view-state` 媒体查询。  | 使用 max-width 和 min-width。  |

## HTML 代码

以下代码采用 HTML1xxx 格式，如 HTML1115。  其中很多是特定于 Internet Explorer 概念的旧版代码，如*文档模式*和*兼容性视图*。  

| 代码 | 消息 | 描述 | 建议的修补程序 |  
| :--- |:--- |:--- |:--- |  
| HTML1112 | “代码页从 \[编码\] 重启为 \[编码\]” | 指定的代码页与服务器的代码页不同。  | 使用与服务器相同的代码页，避免此错误。  |  
| HTML1113 | “文档模式从 \[模式\] 重启为 \[模式\]” | 网页所需的文档模式与浏览器当前设置的模式不同。  | 当用户从其他页面浏览，超出开发人员的控制范围时，可能会出现此消息。  |  
| HTML1114 | “来自 \[域\] 的代码页 \[编码\] 重叠，与来自 \[域\] 的代码页 \[编码\] 冲突” | HTTP \(来自服务器\) 和 HTML \(页面内\) 标头中指定的代码页不同。  | 更改其中一个代码页，使其匹配。  |  
| HTML1115 | “忽略了 X-UA-Compatible META 标记 \(`[META tag]`\)，因为文档模式已完成” | 通常将 META 标记置于“Script”或“Style”声明后，这是页面的固定文档模式。  | 尽早将 X-UA-Compatible META 标记移到标头中。  最好让它紧跟 \<title\> 和字符集值。  |  
| HTML1116 | “因更早的 X-UA-Compatible META 标记 \(`[META tag]`\) 缘故忽略 X-UA-Compatible META 标记 \(`[META tag]`\)” | 源代码的 \<head\> 部分有多个“X-UA-Compatible”“META”标记。  | 删除所有其他“X-UA-Compatible META”标记，只保留一个，并确保尽早将它包含在标头中。  最好让它紧跟 \<title\> 和字符集值。  |  
| HTML1121 | “不允许使用“代码页 \[编码\]，仅允许使用代码页 \[编码\]。” | 网页中的内容调用的字符编码在此上下文中不允许使用。  | 确保所有内容都使用消息中指定的允许编码。  |  
| HTML1122 | “Internet Explorer 正在企业模式下模拟 IE8 运行” | 网页当前在企业模式下呈现，这是模拟 Windows Internet Explorer 8 的过程。  | 此模式是 IT 管理部门针对特定网站配置的。  如果某个用户需要在一个网页上禁用此模式，请清除“工具”菜单上的“企业模式”选项。  有关企业模式管理的详细信息，请参阅 [IT 文档](https://technet.microsoft.com/library/dn640687.aspx)。  |  
| HTML1201 | “`[domain]` 网站已添加到兼容性视图中。” | 用户已选择当前网站的“兼容性视图”**** 按钮，或通过“兼容性视图设置”**** 添加了该网站。  | 由用户发起。  |  
| HTML1202 | “`[domain]` 正在兼容性视图中运行，因为已选中“在兼容性视图中显示 Intranet 网站”。” | 用户已选中“兼容性视图设置”**** 中的“在兼容性视图中显示 Intranet 网站”**** 复选框。  | 用户需要按 Alt + T，选择“兼容性视图设置”****，然后清除“在兼容性视图中显示 Intranet 网站”**** 复选框。  |  
| HTML1203 | “`[domain]` 已配置为通过组策略在兼容性视图中运行。” | 网络管理员已指定在兼容性视图中运行网页。  | 需要与网络管理员联系。  |  
| HTML1204 | “`[domain]` 正在兼容性视图中运行，因为已选中“在兼容性视图中显示所有网站”。” | 用户已选中“兼容性视图设置”**** 中的“在兼容性视图中显示所有网站”**** 复选框。  | 用户需要按 Alt + T，选择“兼容性视图设置”****，然后清除“在兼容性视图中显示所有网站”**** 复选框。  |  
| HTML1300 | “已执行导航” | 已导航到新页面，或已刷新当前页面。  | 这是通知性消息，不是错误。  |  

## HTML5 分析器警告  

在 HTML 分析期间执行的验证过程中，可能会出现以下警告。  这些警告不一定表示页面已损坏，但根据 HTML5 标准判断提供的 HTML 无效。  遵循早期版本的 HTML 或 XHTML 规范创建的内容在 HTML5 中可能无效，尤其是与使用 DOCTYPE 相关的内容。

这些警告通常表示字符缺失或多余，以及标记不匹配。  解决这些警告的问题时，与旧版浏览器的兼容性以及网页对 HTML5 标准的遵循情况应会得到改进。  为帮助确定警告的来源，它包括行和字符偏移信息，以及指向已发现问题所在位置的链接。

| 代码     | 消息 |  
| :--- |:--- |  
| HTML1400 | “数字字符引用开头出现不符合要求的字符。  应为 [0-9]。” |  
| HTML1401 | “十六进制数字字符引用开头出现不符合要求的字符。  应为 [0-9]、[a-f] 或 [A-F]。” |  
| HTML1402 | “字符引用缺少结尾分号‘;’。” |  
| HTML1403 | “数字字符引用未解析为有效字符。” |  
| HTML1404 | “无法识别的命名字符引用。” |  
| HTML1405 | “无效字符: U+0000 NULL。  不应使用 Null 字符。” |  
| HTML1406 | “开始标记: <? 无效。  不能将问号作为开始标记。” |  
| HTML1407 | “标记名称无效。  第一个字符应与 [a-zA-Z] 匹配。” |  
| HTML1408 | “结束标记 \</\> 无效。  结束标记不能为空。” |  
| HTML1409 | “属性名称字符无效。  属性名称不能包含 \(\"\)、\(\'\)、\(\<\) 或 \(=\)。” |  
| HTML1410 | “未加引号的属性值无效。  未加引号的属性值不能包含 \(\"\)、\(\'\)、\(\<\)、\(=\) 或 \(\`\)。” |  
| HTML1411 | “文件意外结束。” |  
| HTML1412 | “注释格式不正确。  注释应以 \<\!-- \> 开头。” |  
| HTML1413 | “不符合要求的字符: U+003E 大于号 \(\>\)” |  
| HTML1414 | “不符合要求的字符: U+0021 感叹号 \(\!\)” |  
| HTML1415 | “不符合要求的字符: U+002D 连字符 - 负号 \(-\)” |  
| HTML1416 | “注释末尾出现不符合要求的字符。  应为 ‘-->’。” |  
| HTML1417 | “DOCTYPE 为空。  最短的有效 DOCTYPE 为 \<\!DOCTYPE html\>”。 |  
| HTML1418 | “DOCTYPE 中出现不符合要求的字符。” |  
| HTML1419 | “DOCTYPE 中出现不符合要求的关键字。  应为‘PUBLIC’或‘SYSTEM’。” |  
| HTML1420 | “‘PUBLIC’或‘SYSTEM’关键字后出现不符合要求的引号。  应为空格。” |  
| HTML1421 | “结束标记的格式不正确。  结束标记不能包含属性。” |  
| HTML1422 | “开始标记的格式不正确。  自结束斜线后应跟随 U+003E 大于号 \(\>\)。” |  
| HTML1423 | “开始标记的格式不正确。  属性应使用空格分隔。” |  
| HTML1424 | “无效字符   ” |  
| HTML1500 | “标记无法自结束。  请使用显式结束标记。” |  
| HTML1501 | “文件意外结束。” |  
| HTML1502 | “DOCTYPE 不符合要求。  只允许一个 DOCTYPE，并且它必须出现在所有元素之前。” |  
| HTML1503 | “开始标记不符合要求。” |  
| HTML1504 | “结束标记不符合要求。” |  
| HTML1505 | “字符令牌不符合要求。” |  
| HTML1506 | “令牌不符合要求。” |  
| HTML1507 | “不符合要求的字符: U+0000 NULL。  不应使用 Null 字符。” |  
| HTML1508 | “结束标记不匹配。” |  
| HTML1509 | “结束标记不匹配。” |  
| HTML1510 | “所需节点不在范围内。” |  
| HTML1511 | “在 \<head\> 之外出现不符合要求的头级元素。” |  
| HTML1512 | “结束标记不匹配。” |  
| HTML1513 | “发现多余的 \<html\> 标记。  每个文档中只应存在一个 \<html\> 标记。” |  
| HTML1514 | “发现多余的 \<body\> 标记。  每个文档中只应存在一个 \<body\> 标记。” |  
| HTML1515 | “在文档中找到的 \<frameset\> 太远。  此标记应在 \<body\> 创建之前出现。” |  
| HTML1516 | “嵌套无效。  头标记（如 \<h1\> 或 \<h2\>）不应置于另一个头标记内。” |  
| HTML1517 | “嵌套无效。  \<form\> 标记不应置于另一个 \<form\> 内。” |  
| HTML1518 | “嵌套无效。  \<button\> 标记不应置于另一个 \<button\> 内。” |  
| HTML1519 | “嵌套无效。  \<a\> 标记不应置于另一个 \<a\> 内。” |  
| HTML1520 | “不符合要求的开始标记: \<isindex\> 元素已被弃用，因此不应使用。” |  
| HTML1521 | “\</body\> 或文件末尾不符合要求。  所有打开的元素应在文档结束前关闭。” |  
| HTML1522 | “结束标记: \</br\>无效。  请改用 \<br\> 或 \<br /\>。” |  
| HTML1523 | “重叠的结束标记。  标记的结构应为 \<b\>\<i\>\</i\>\</b\>，而不是 \<b\>\<i\>\</b\>\</i\>。” |  
| HTML1524 | “DOCTYPE 无效。  最短的有效 DOCTYPE 为 \<\!DOCTYPE html\>”。 |  
| HTML1525 | “在外部内容(MathML/SVG)中发现不符合要求的 HTML 标记。” |  
| HTML1526 | “嵌套无效。  \<nobr\> 标记不应置于另一个 \<nobr\> 内。” |  
| HTML1527 | “需要 DOCTYPE。  最短的有效 DOCTYPE 为 \<\!DOCTYPE html\>”。 |  
| HTML1528 | “HTML 内容中存在不符合要求的 \<image\>。  请改用 \<img\>。” |  
| HTML1529 | “xmlns:xlink 属性值无效。  值必须为‘\<https://w3.org/1999/xlink\>’。” |  
| HTML1530 | “在结构化表元素内发现文本。  表文本只能置于 \<caption\>、\<td\> 或 \<th\> 元素内。” |  
| HTML1531 | “xmlns 属性值无效。  对于 SVG 元素，值必须为‘\<https://w3.org/2000/svg/\>’。” |  
| HTML1532 | “xmlns 属性值无效。  对于 MathML 元素，值必须为‘\<https://w3.org/1998/Math/MathML/\>’。”  |  

## HTTP 代码  

从远程服务器返回的 HTTP 错误代码用于响应请求。  可能最常见的是 HTTP404，当服务器找不到统一资源标识符 \(URI\) 中指定的页面或文档时就会返回此代码。

| 代码 | 消息 | 描述 |  
| :--- |:--- |:--- |  
| HTTP400 | 错误请求 | 由于语法无效，服务器无法处理请求。  |  
| HTTP401 | 已拒绝 | 请求的资源需要用户身份验证。  |  
| HTTP402 | 需要付款 | 当前未在 HTTP 协议中实现。  |  
| HTTP403 | 已禁止 | 服务器读懂了此请求，但拒绝执行该请求。  |  
| HTTP404 | 未找到 | 服务器未找到与请求的 URI 匹配的任何内容。  |  
| HTTP405 | 错误的方法 | 不允许所使用的 Http 谓词。  |  
| HTTP406 | 无法接受 | 找不到客户端可接受的响应。  |  
| HTTP407 | 需要代理身份验证 | 需要代理身份验证。  |  
| HTTP408 | 请求超时 | 服务器等待请求时超时。  |  
| HTTP409 | 冲突 | 无法完成请求，因为与资源的当前状态有冲突。  |  
| HTTP410 | 不再存在 | 请求的资源在服务器中不再可用，并且转发地址未知。  |  
| HTTP411 | 需要长度 | 服务器拒绝接受未定义内容长度的请求。  |  
| HTTP412 | 不满足前提条件 | 在服务器上测试一个或多个请求标头字段中提供的前提条件时，该条件的计算结果为 false。  |  
| HTTP413 | 有效负载过大 | 由于请求实体超过了服务器愿意或能够处理的大小，服务器拒绝处理请求。  |  
| HTTP414 | URI 过长 | 服务器拒绝为此请求提供服务，因为请求 URI 的长度大于服务器愿意解释的 URI 长度。  |  
| HTTP415 | 不支持的媒体类型 | 服务器拒绝为此请求提供服务，因为请求的实体所使用的格式不受请求的方法的请求资源的支持。  |  
| HTTP416 | 无法满足请求的范围 | 服务器无法提供客户端已请求的文件部分。  该部分可能已超出文件结尾。  |  
| HTTP417 | 预期失败 | 服务器无法满足预期请求标头字段的要求。  |  
| HTTP418 | 我是茶壶 | 服务器是茶壶，不能煮咖啡。  |  
| HTTP419 | 身份验证超时 | 以前有效的身份验证已过期。  |  
| HTTP422 | 无法处理的实体 | 请求格式正确，但由于语义错误而无法处理。  |  
| HTTP423 | 已锁定。 | 正在访问的资源已锁定。  |  
| HTTP424 | 依赖关系失败 | 由于上次请求失败而导致请求失败。  |  
| HTTP426 | 需要升级 | 客户端必须切换到其他协议。  |  
| HTTP428 | 需要前提条件 | 源服务器需要请求具有条件。  |  
| HTTP429 | 请求太多 | 由于客户端提交的请求过多，服务器拒绝为请求提供服务。  |  
| HTTP431 | 请求标头字段太大 | 由于标头字段或所有标头字段的总大小大于服务器愿意或所能处理的大小，该服务器将拒绝为请求提供服务。  |  
| HTTP449 | 重试 | 应在执行相应操作后重试请求。  |  
| HTTP500 | 服务器错误 | 服务器遇到意外情况，无法完成请求。  |  
| HTTP501 | 不支持 | 服务器不支持完成请求所需的功能。  |  
| HTTP502 | 网关错误 | 服务器在充当网关或代理时收到了来自上游服务器的无效响应，在尝试完成请求时对该上游服务器进行了访问。  |  
| HTTP503 | 服务不可用 | 服务临时过载。  |  
| HTTP504 | 网关超时 | 等待网关时请求超时。  |  
| HTTP505 | 版本不受支持 | 服务器不支持，或拒绝支持请求消息中使用的 HTTP 协议版本。  |  
| HTTP506 | 变体即协商 | 请求的透明内容协商导致了循环引用。  |  
| HTTP507 | 存储空间不足 | 服务器无法存储完成请求所需的表示形式。  |  
| HTTP508 | 检测到循环 | 服务器在处理请求时检测到无限循环。  |  
| HTTP510 | 未扩展 | 需要进一步扩展该请求，以便服务器完成请求。  |  
| HTTP511 | 需要网络身份验证 | 客户端必须进行身份验证以获取网络访问权限。  |  

## JavaScript 语法错误  

当其中一个 JavaScript 语句的结构违反一个或多个语法规则时，将出现 JavaScript 语法错误。  

| 错误编号 | 描述 |  
| --- | --- |  
| 1019 | [循环之外不能有“break”](/scripting/javascript/misc/can-t-have-break-outside-of-loop) |  
| 1020 | [循环之外不能有“continue”](/scripting/javascript/misc/can-t-have-continue-outside-of-loop) |  
| 1030 | [条件编译已禁用](/scripting/javascript/misc/conditional-compilation-is-turned-off) |  
| 1027 | [“default”在“switch”语句中只能出现一次](/scripting/javascript/misc/default-can-only-appear-once-in-a-switch-statement) |  
| 1005 | [缺少“\(”](/scripting/javascript/misc/expected-left-parenthesis-javascript) |  
| 1006 | [缺少“\)”](/scripting/javascript/misc/expected-right-parenthesis-javascript) |  
| 1012 | [缺少“/”](/scripting/javascript/misc/expected-minus) |  
| 1003 | [缺少“:”](/scripting/javascript/misc/expected-colon) |  
| 1004 | [缺少“;”](/scripting/javascript/misc/expected-semicolon) |  
| 1032 | [缺少 "@"](/scripting/javascript/misc/expected-at) |  
| 1029 | [缺少“@end”](/scripting/javascript/misc/expected-at-end) |  
| 1007 | [缺少“\]”](/scripting/javascript/misc/expected-right-square-bracket) |  
| 1008 | [缺少“{”](/scripting/javascript/misc/expected-left-curly-brace) |  
| 1009 | [缺少“}”](/scripting/javascript/misc/expected-right-curly-brace) |  
| 1011 | [缺少“=”](/scripting/javascript/misc/expected-equal-javascript) |  
| 1033 | [缺少“catch”](/scripting/javascript/misc/expected-catch) |  
| 1031 | [缺少常量](/scripting/javascript/misc/expected-constant) |  
| 1023 | [缺少十六进制数字](/scripting/javascript/misc/expected-hexadecimal-digit) |  
| 1010 | [缺少标识符](/scripting/javascript/misc/expected-identifier-javascript) |  
| 1028 | [缺少标识符、字符串或数字](/scripting/javascript/misc/expected-identifier-string-or-number) |  
| 1024 | [缺少“while”](/scripting/javascript/misc/expected-while) |  
| 1014 | [无效字符](/scripting/javascript/misc/invalid-character-javascript) |  
| 1026 | [标签未找到](/scripting/javascript/misc/label-not-found) |  
| 1025 | [标签重复定义](/scripting/javascript/misc/label-redefined) |  
| 1018 | [“return”语句在函数之外](/scripting/javascript/misc/return-statement-outside-of-function) |  
| 1002 | [语法错误](/scripting/javascript/misc/syntax-error-javascript) |  
| 1035 | [throw 的后面必须在同一行跟有一个表达式](/scripting/javascript/misc/throw-must-be-followed-by-an-expression-on-the-same-source-line) |  
| 1016 | [注释未结束](/scripting/javascript/misc/unterminated-comment) |  
| 1015 | [未结束的字符串常量](/scripting/javascript/misc/unterminated-string-constant-javascript) |  
  
### 脚本宿主错误  

以下错误与脚本宿主相关，可能偶尔会出现：  
  
| 错误 | HRESULT | 描述 |  
| ---| --- | --- |  
| SCRIPT_E_RECORDED | 0x86664004 | 脚本引擎与宿主之间已记录并已传递错误。  宿主需要将错误代码传递到调用方。  |  
| SCRIPT_E_REPORTED | 0x80020101 | 脚本引擎通过 IActiveScriptSite::OnScriptError 向宿主报告了未经处理的异常。  宿主可以忽略此错误。  |  
| SCRIPT_E_PROPAGATE | 0x8002010 | 传播到调用方的脚本错误可能位于其他线程中。  宿主应将错误代码传递到调用方。  |  

## JavaScript 运行时错误

当脚本尝试执行系统无法执行的操作时，将出现 JavaScript 运行时错误。  在计算变量表达式或正在分配内存时，可能会出现运行时错误。

| 错误编号 | 描述 |  
| --- | --- |  
| 5 | [拒绝访问。](/scripting/javascript/misc/access-is-denied) |  
| 438 | [对象不支持此属性或方法](/scripting/javascript/misc/object-doesn-t-support-this-property-or-method) |  
| 1001 | 内存不足 |  

### Windows 运行时错误  

 如果你使用的是 Windows Runtime \(WinRT\) API，你可能会看到已从 Windows Runtime HRESULT 转换的 JavaScript 错误。  通过采用低位的十六进制值并将其转换为十进制值，可将超过 0x80070000 范围内的 Windows 运行时 HRESULT 转换为 JavaScript 错误。  例如，将 HRESULT 0x80070032 转换为十进制值 50，转换后的 JavaScript 错误为 SCRIPT50。  将 HRESULT 0x80074005 转换为十进制值 16389，转换后的 JavaScript 错误为 SCRIPT16389。

| 错误编号 | 描述 |  
| --- | --- |  
| 5029 | [数组长度必须为有限正整数](/scripting/javascript/misc/array-length-must-be-a-finite-positive-integer) |  
| 5030 | [必须为数组长度分配一个有限正数](/scripting/javascript/misc/array-length-must-be-assigned-a-finite-positive-number) |  
| 5028 | [缺少 Array 或 arguments 对象](/scripting/javascript/misc/array-or-arguments-object-expected) |  
| 5010 | [缺少布尔值](/scripting/javascript/misc/boolean-expected) |  
| 5003 | [不能为函数结果赋值](/scripting/javascript/misc/cannot-assign-to-a-function-result) |  
| 5000 | [不能为“this”赋值](/scripting/javascript/misc/cannot-assign-to-this) |  
| 5034 | [值参数中不支持循环引用](/scripting/javascript/misc/circular-reference-in-value-argument-not-supported) |  
| 5006 | [缺少日期对象](/scripting/javascript/misc/date-object-expected) |  
| 5015 | [缺少枚举器对象](/scripting/javascript/misc/enumerator-object-expected) |  
| 5022 | [引发了异常但未捕获](/scripting/javascript/misc/exception-thrown-and-not-caught) |  
| 5020 | [正则表达式中缺少“)”](/scripting/javascript/misc/expected-right-parenthesis-in-regular-expression-javascript) |  
| 5019 | [正则表达式中缺少“&#93;”](/scripting/javascript/misc/expected-right-square-bracket-in-regular-expression-javascript) |  
| 5023 | [函数没有有效的原型对象](/scripting/javascript/misc/function-does-not-have-a-valid-prototype-object) |  
| 5002 | [缺少函数](/scripting/javascript/misc/function-expected) |  
| 5008 | [非法赋值](/scripting/javascript/misc/illegal-assignment-javascript) |  
| 5021 | [字符集越界](/scripting/javascript/misc/invalid-range-in-character-set-javascript) |  
| 5035 | [无效的替换器参数](/scripting/javascript/misc/invalid-replacer-argument) |  
| 5014 | [缺少 JavaScript 对象](/scripting/javascript/misc/javascript-object-expected) |  
| 5001 | [缺少数字](/scripting/javascript/misc/number-expected) |  
| 5007 | [缺少对象](/scripting/javascript/misc/object-expected) |  
| 5012 | [缺少对象成员](/scripting/javascript/misc/object-member-expected) |  
| 5016 | [缺少正则表达式对象](/scripting/javascript/misc/regular-expression-object-expected) |  
| 5005 | [缺少字符串](/scripting/javascript/misc/string-expected) |  
| 5017 | [正则表达式中的语法错误](/scripting/javascript/misc/syntax-error-in-regular-expression-javascript) |  
| 5026 | [小数位数超出范围](/scripting/javascript/misc/the-number-of-fractional-digits-is-out-of-range) |  
| 5027 | [精度超出范围](/scripting/javascript/misc/the-precision-is-out-of-range) |  
| 5025 | [要解码的 URI 不是有效的编码](/scripting/javascript/misc/the-uri-to-be-decoded-is-not-a-valid-encoding) |  
| 5024 | [要编码的 URI 包含无效字符](/scripting/javascript/misc/the-uri-to-be-encoded-contains-an-invalid-character) |  
| 5009 | [未定义标识符](/scripting/javascript/misc/undefined-identifier) |  
| 5018 | [限定符不符合要求](/scripting/javascript/misc/unexpected-quantifier-javascript) |  
| 5013 | [缺少 VBArray](/scripting/javascript/misc/vbarray-expected) |  

## 安全代码

安全错误代码采用 `SEC7xxx` 格式，如 `SEC7113`。  以下错误反映 Microsoft Edge 强制执行的安全条件，例如混合内容和跟踪保护。

| 代码 | 消息 | 描述 | 建议的修补程序 |  
| :--- |:--- |:--- |:--- |  
| SEC7111 | “HTTPS 安全受到 [资源名称] 的威胁” | 安全超文本传输协议 \(HTTPS\) 页面包含来自不安全来源的内容。  | 请确保页面中的所有内容（包括脚本、样式表对象和图像）均来自 HTTPS 来源。  |  
| SEC7112 | “[URL] 的脚本因 MIME 类型不匹配而被阻止” | URL 指定的 JavaScript 文件的 HTTP 响应头具有“X-Content-Type-Options: nosniff”标头，并且没有已识别的内容类型声明。  | 更新服务器，以便在 HTTP 响应头中发送 JavaScript 文件的正确内容类型 \(例如，text/javascript、application/javascript\)。  有关内容类型的详细信息和完整列表，请参阅 [Internet Explorer 中的 MIME 处理更改](https://blogs.msdn.microsoft.com/ie/2010/10/26/mime-handling-changes-in-internet-explorer/)。  |  
| SEC7113 | “由于 MIME 类型不匹配，已忽略 CSS” | 未使用导入的样式表，因为 HTTP 头中的 MIME 类型错误。  | 确保使用正确的 HTTP 响应头（包括文本/CSS 内容类型）传递样式表文件。  有关详细信息，请参阅 [Internet Explorer 中的 MIME 处理更改](https://blogs.msdn.microsoft.com/ie/2010/10/26/mime-handling-changes-in-internet-explorer/)。  |  
| SEC7114 | “跟踪保护阻止了此页面的下载。[在此处提供 URL]” | 用户使用跟踪保护阻止了一个脚本或内容。  | 无 - 由用户发起。  |  
| SEC7115 | “:visited 和 :link 样式只能在颜色上有区别。  有些样式未应用于 :visited。” | 使用 visited 和 link 样式更改了多个属性（如字体或大小）。  | 仅更改颜色属性。  |  
| SEC7116 | “拒绝访问。  无法撤销跨源 URL: [URL]。” | 具有与 blob 不同的源站点的脚本尝试撤销 blob URL。  由于 blob 源策略，尝试失败。  | 确保使用与创建 blob URL 的文档相同的源站点中的脚本撤销所有 blob URL。  |  
| SEC7120 | “在 Access-Control-Allow-Origin 标头中找不到源 [域]”。 | 在对你的 XMLHttpRequest 的响应中，返回了 Access-Control-Allow-Origin 标头，其值不包含或不匹配网站的原始值。  | 该资源返回正确类型的标头代码，但不允许用于你的站点。  联系负责资源的开发人员更新 Access-Control-Allow-Origin 标头，以便允许用于你的站点。  可以让他们参考 [IE10 中的 CORS for XHR](https://blogs.msdn.microsoft.com/ie/2012/02/09/cors-for-xhr-in-ie10/)，详细了解响应头中的 CORS。  |  
| SEC7121 | “凭据标记设置为 true 时，不允许在 Access-Control-Allow-Origin 中使用通配符”。 | 服务器在标头中返回“Access-Control-Allow-Origin: *”，但如果在 XMLHttpRequest 中将 `withCredentials` 标记设置为 **true**，则不允许这样做。  | 必须修改服务器端处理程序，以返回专门允许此类型请求上的原点的 Access-Control-Allow-Origin 标头。  如果不控制服务器端处理程序，则必须联系相关开发人员。  |  
| SEC7122 | “凭据标记已设置为 true，但 Access-Control-Allow-Credentials 不存在，或者未设置为‘true’。” | 使用 `withCredentials` 标记发出了 XMLHttpRequest。  未返回 Access-Control-Allow-Credentials 标头，或返回了标头，但值不是 **true**。  | 凭据或服务器的响应可能存在问题。  有关已提供凭据的请求的信息，请参阅 [XMLHttpRequest 级别 2 规范](https://w3.org/TR/XMLHttpRequest2/)。  |  
| SEC7123 | “Access-Control-Allow-Headers 列表中不存在请求标头 [标头]。” | 自定义标头类型已包含在请求中，但响应的 Access-Control-Allow-Headers 列表中未包含它。  | 确保服务器允许自定义标头，具体来说就是在请求中发送的那个标头。  |  
| SEC7124 | “Access-Control-Allow-Methods 列表中不存在请求方法 [方法]。” | XMLHttpRequest 中使用了某种请求方法（如 POST），但响应返回的 Access-Control-Allow-Methods 标头中未包含该方法。  | 确保服务器允许此类型的请求方法，并且如果该方法的访问权限受限制，你仍可正确使用 `withCredentials`。  |  
| SEC7125 | “[URL] 的 XMLHttpRequest 导致了响应头分析失败。” | 无法分析服务器的响应头，因此请求失败。  | 使用[网络工具](https://msdn.microsoft.com/library/dn255004.aspx)捕获并检查响应头，确保它们符合 [CORS 规范](https://w3.org/TR/cors/)。  |  
| SEC7126 | “CORS 预检请求不允许重定向。” | 已在源标头中检测到重定向，并且在预检过程中用户代理未跟踪重定向。  | 使用[网络工具](https://msdn.microsoft.com/library/dn255004.aspx)捕获并检查请求标头，确保有一个直接原点。  |  
| SEC7127 | “已阻止针对 CORS 请求的重定向。” | 指向 CORS 资源的路径包含已违反安全规则的重定向。  | 确保 XMLHttpRequest 中 CORS 资源的路径是最直接的。  |  
| SEC7128 | “CORS 响应不允许多个 Access-Control-Allow-Origin 标头。” | 响应头包含多个 Access-Control-Allow-Origin 标头。  | 这是服务器端错误。  服务器应返回一个 Access-Control-Allow-Origin 标头。  向负责服务器端资源的开发人员报告此错误。
| SEC7129 | “CORS 响应不允许多个 Access-Control-Allow-Credentials 标头。” | 响应头包含多个 Access-Control-Allow-Credentials 标头。  | 这是服务器端错误。  服务器应返回一个 Access-Control-Allow-Credentials 标头。  向负责服务器端资源的开发人员报告此错误。  |  
| SEC7130 | “[URL] 中检测到可能的跨站点脚本操作。  内容已被 XSS 筛选器修改。” | [XSS 筛选器](https://msdn.microsoft.com/library/dd565647.aspx)检测到来自资源的响应中可能存在恶意内容并删除了恶意内容。  | 详细了解 [XSS 筛选器](https://msdn.microsoft.com/library/dd565647.aspx)。  |  
| SEC7131 | “如果允许脚本和同源访问，沙盒 iframe 的安全可能会受到威胁。” | 如果沙盒 iframe 中的内容来自不受信任或不安全的源，则在同时允许脚本和同源访问时，将转义沙盒。  | 这是一条通知性警告消息，不会影响功能。  建议避免合并这些权限，除非你确定将在 iframe 中运行的内容。  |  
| SEC7132 | “用于保护此网站的证书使用了较弱的加密技术" | 此网站使用的 TLS 安全证书使用的加密技术较弱 | 更新服务器的 TLS 证书 |  

> [!NOTE]
> 对于用户受信任的安全区域中的网站，Microsoft Edge 不检查样式表的 MIME 类型。

## SVG 代码  

DevTools 目前不支持广泛可扩展矢量图形 \(SVG\) 调试，但某些控制台消息旨在帮助调试。

| 代码 | 消息 | 描述 | 建议的修补程序 |  
| :--- |:--- |:--- |:--- |  
| SVG5601 | “SVG 路径数据的格式不正确，未能进行完全分析。” | SVG [路径](https://msdn.microsoft.com/library/ff972086.aspx)字符串格式不正确，或者包含无法识别的命令。  | 检查命令的格式。  |  
| SVG5602 | “SVG 点列表的格式不正确，未能进行完全分析。" | 用于元素的点列表（如[折线](https://msdn.microsoft.com/library/ff972113.aspx)）的格式不正确。  | 确保点的完整性，并正确设置用户坐标系统的格式。  |  

## XML 代码  

XML 代码采用 XML5xxx 的形式，如 XML5603。  

| 代码 | 消息 |  
|:--- |:--- |  
| XML5001 | “应用集成的 XSLT 处理。” |  
| XML5601 | “MX_E_MX” |  
| XML5602 | “输入意外结束。” |  
| XML5603 | “无法识别的编码”。 |  
| XML5604 | “无法切换编码。” |  
| XML5605 | “无法识别的输入编码签名。” |  
| XML5606 | “WC_E_WC” |  
| XML5607 | “缺少空格。” |  
| XML5608 | “缺少分号。” |  
| XML5609 | “缺少‘>’。” |  
| XML5610 | “缺少引号字符。” |  
| XML5611 | “缺少‘=’。” |  
| XML5612 | “属性值中不允许使用 < 字符。” |  
| XML5613 | “缺少十六进制数字。” |  
| XML5614 | “缺少十进制数字。” |  
| XML5615 | “缺少‘[’。” |  
| XML5616 | “缺少‘(’。” |  
| XML5617 | “非法 XML 字符。” |  
| XML5618 | “非法名称字符。” |  
| XML5619 | “文档语法不正确。” |  
| XML5620 | “CDATA 节语法不正确。” |  
| XML5621 | “注释语法不正确。” |  
| XML5622 | “条件节语法不正确。” |  
| XML5623 | “ATTLIST 声明语法不正确。” |  
| XML5624 | “DOCTYPE 声明语法不正确。” |  
| XML5625 | “ELEMENT 声明语法不正确。” |  
| XML5626 | “ENTITY 声明语法不正确。” |  
| XML5627 | “NOTATION 声明语法不正确。” |  
| XML5628 | “缺少‘NDATA’。” |  
| XML5629 | “缺少‘PUBLIC"’。” |  
| XML5630 | “缺少‘SYSTEM’。” |  
| XML5631 | “名称无效。” |  
| XML5632 | “仅允许一个根元素。” |  
| XML5633 | “结束标记名称与对应的开始标记名称不匹配。” |  
| XML5634 | “此元素上已存在同名属性。” |  
| XML5635 | “仅文件开头允许 XML 声明。” |  
| XML5636 | “先导‘xml’。” |  
| XML5637 | “文本声明语法不正确。” |  
| XML5638 | “XML 声明语法不正确。” |  
| XML5639 | “编码名称语法不正确。” |  
| XML5640 | “公共标识符语法不正确。” |  
| XML5641 | “内部 DTD 子集中的标记声明内不允许使用参数实体引用。” |  
| XML5642 | “各标记声明之间使用的参数实体引用的替换文本自身必须包含一系列完整的标记声明。” |  
| XML5643 | “分析的实体不得包含对自身的直接或间接引用。” |  
| XML5644 | “指定实体的内容格式不正确。” |  
| XML5645 | “尚未声明指定的实体。” |  
| XML5646 | “实体引用不能包含未分析实体的名称。” |  
| XML5647 | “属性值不得包含对外部实体的直接或间接引用。” |  
| XML5648 | “处理指令语法不正确。” |  
| XML5649 | “系统标识符语法不正确。” |  
| XML5650 | “缺少问号 \(\?\)。” |  
| XML5651 | “在元素内容中不得使用 CDATA-section-close 分隔符‘]]>’。” |  
| XML5652 | “尚未读取所有数据块。” |  
| XML5653 | “已找到 DTD，但被禁止。” |  
| XML5654 | “已找到 xml:space 属性，但值无效。  有效值为‘preserve’或‘default’。” |  
| XML5655 | “NC_E_NC” |  
| XML5656 | “非法的限定名称字符。” |  
| XML5657 | “一个限定名称中不得出现多个冒号‘:’。” |  
| XML5658 | “名称中不得出现冒号‘:’。” |  
| XML5659 | “已声明前缀。” |  
| XML5660 | “尚未声明指定的前缀。” |  
| XML5661 | “非默认命名空间声明不得有空的 URI。” |  
| XML5662 | “‘xml’是保留前缀，必须具有 URI‘<https://w3.org/XML/1998/namespace/>’。” |  
| XML5663 | “‘xmlns’是供 XML 使用的保留前缀。” |  
| XML5664 | “不得将 xml 命名空间 URI \(\<https://w3.org/XML/1998/namespace/\>\) 分配给前缀‘xml’。” |  
| XML5665 | “xmlns 命名空间 URI \(\<https://w3.org/2000/xmlns/\>\) 是保留的，不能使用。” |  
| XML5666 | “SC_E_SC” |  
| XML5667 | “超出了嵌套元素的最大深度。” |  
| XML5668 | “超出了最大的实体扩展数。” |  
| XML5669 | “WR_E_WR” |  
| XML5670 | “WR_E_NONWHITESPACE: 编写器: 指定的字符串不是空格。” |  
| XML5671 | “WR_E_NSPREFIXDECLARED: 编写器: 已使用其他命名空间声明了命名空间前缀。” |  
| XML5672 | “WR_E_NSPREFIXWITHEMPTYNSURI: 编写器: 无法将前缀与空命名空间 URI 一起使用。” |  
| XML5673 | “WR_E_DUPLICATEATTRIBUTE: 编写器: 重复的属性。” |  
| XML5674 | “WR_E_XMLNSPREFIXDECLARATION: 编写器: 无法重新定义 xmlns 前缀。” |  
| XML5675 | “WR_E_XMLPREFIXDECLARATION: 编写器: xml 前缀必须包含 \<https://w3.org/XML/1998/namespace/\> URI。” |  
| XML5676 | “WR_E_XMLURIDECLARATION: 编写器: 只能将 xml 命名空间 URI \(\<https://w3.org/XML/1998/namespace/\>\) 分配给前缀‘xml’。” |  
| XML5677 | “WR_E_XMLNSURIDECLARATION: 编写器: xmlns 命名空间 URI \(\<https://w3.org/2000/xmlns/\>\) 是保留的，不能使用。” |  
| XML5678 | “WR_E_NAMESPACEUNDECLARED: 编写器: 未检测到命名空间。” |  
| XML5679 | “WR_E_INVALIDXMLSPACE: 编写器: xml:space 属性的值无效 \(允许的值为‘default’和‘preserve’\)。” |  
| XML5680 | “WR_E_INVALIDACTION: 编写器: 执行所请求的操作将导致 XML 文档无效。” |  
| XML5681 | “WR_E_INVALIDSURROGATEPAIR: 编写器: 输入包含的代理项对无效或不完整。” |  
| XML5682 | “字符实体中出现不符合要求的字符。  应为十进制数字。” |  
| XML5683 | “字符实体中出现不符合要求的字符。  应为十六进制数字。” |  
| XML5684 | “指定的字符实体的 Unicode 值无效。” |  
| XML5685 | “编码无效。” |  
| XML5686 | “未指定的 XML 错误。” |  

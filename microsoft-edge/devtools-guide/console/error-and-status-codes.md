---
ms.assetid: 961ca575-6b93-4367-a72b-f3f02e5b9568
description: 对常见的控制台代码和建议的修补程序的参考
title: DevTools-控制台错误和状态代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、控制台代码
ms.custom: seodec18
localization_priority: Priority
ms.openlocfilehash: aa667941f619dcc0eac2411a087dbdfcf2fda613
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564310"
---
# 控制台错误和状态代码  

此参考可帮助你从 DevTools[控制台](../console.md)解释错误和状态消息。  使用下表按前缀 \ （其中，"x" 表示 0&ndash;9 位数字 \）查找代码：

| 代码前缀 | 区域 | 描述 |  
|:--- | :--- |:--- |  
| [CSP143xx](#csp-codes) | 内容安全策略 | 使用`Content-Security-Policy` HTTP 标头时被阻止的资源。  |  
| [CSS31xx](#css-codes) | 单 | 与*Web 打开字体格式*\ （WOFF \）和嵌入的*OpenType* \ （EOT \）字体源和主机服务器问题相关的错误。  |  
| [HTML1112-1300](#html-codes) | HTML | 其中大多数是特定于 Microsoft Internet Explorer 概念（如*文档模式*和*兼容性视图*）的旧版代码。  |  
| [HTML1400-1532](#html5-parser-warnings) | HTML5 分析 | HTML5 分析程序引发的验证警告。  |  
| [HTTP](#http-codes) | 服务器错误和状态 | 从远程服务器返回的代码，用于响应 HTTP 请求。  |  
| [SCRIPT10xx](#javascript-syntax-errors) | JavaScript 语法错误 | 当其中一个 JavaScript 语句的结构违反一个或多个语法规则时发生。  |  
| [SCRIPT50xx](#javascript-run-time-errors) | JavaScript 运行时错误 | 在脚本尝试执行系统无法执行的操作时发生。  |  
| [SEC71xx](#security-codes) | 安全性 | 反映 Microsoft Edge 强制实施的安全条件，如*混合内容*和*跟踪保护*。  |  
| [SVG560x](#svg-codes) | 可伸缩矢量图形 |  目前不支持广泛的 SVG 调试，但某些控制台消息是出于调试目的而提供的。  |  
| WebGL11_xxx | WebGL | 来自 WebGL 上下文的错误消息。  另请参阅[GLSL 错误](https://msdn.microsoft.com/library/dn611835.aspx)。  |  
| [XML5xxx](#xml-codes) | XML | XML 分析和验证中的错误。  |  

## CSP 代码  

通过使用`Content-Security-Policy` HTTP 标头被阻止的资源通过 DevTools 控制台进行报告，还可以按报表返回到服务器。

| 代码 | 消息 | 描述 | 建议的修复 |
|:--- |:--- |:--- |:--- |
| CSP14301 | "无法解析 \ [policy type \]，因为 \ <取消操作 \ > 的原因 \" 将被忽略。 " | 指定的安全策略类型 \ （例如，脚本-src，base uri \）因确定的原因而失败，将被忽略。  | 请确保在单个指令中列出特定类型的所有所需资源。  例如，在中`script-src https://host1.com; script-src https://host2.com`，第二个指令将被忽略。  以下内容正确地将这两个来源`script-src https://host1.com https://host2.com`指定为有效：。  |
| CSP14302 | "无法分析 \ [policy type \] 的" \ [源 URL \] "的源，将忽略源 URL \] 的源。"                                                         | 大多数 CSP 指令都需要一个或多个内容源 \ （指示可从 \ 加载内容的 URL）。  此错误指向一个策略，其中包含在分析尝试时失败的源 URL 的指令。  | 检查在指定的指令类型中可以找到的在指定指令中定义的内容源 \ （最常是 URL \）。  更正或替换源 URL 或删除指令。  <br /> *\ * 你的策略应包括默认的 src 策略指令，当其他资源类型没有自己的策略时，该指令将回退该指令。* |
| CSP14303 | "[Policy type] 策略为空。" | 策略类型 \ （例如，HTTP 标头中的内容安全策略 \）为空。  | 可以在上[http://content-security-policy.com](http://content-security-policy.com)找到有关设置内容安全策略的快速参考。  |
| CSP14304 | \ [策略类型 \] 中的指令 \ [指令类型 \] 的 "未知源 \ [源 URL \] 源将被忽略。" | 标识的指令中批准的 \ （safe \）内容的来源未知，将被忽略。  | 检查标识为 \ （通常是 URL \）的内容源，确保它是正确的。  |
| CSP14305 | "\ [Policy type \] 源中的指令 [指令类型] 的" 不支持源 \ [源 URL \] 源将被忽略。 " | 此指令中列出的源 \ （URL、关键字或数据）不受支持，将被忽略。  | 来源站点的地址可能包含可选的前导通配符 \ （星号字符`*`\）。  例如，http://`*`、foo.com 或 mail.foo.com： *。  主机由空格分隔。  源还可能是关键字 \ （none、self、不安全内联和不安全-eval 均受支持 \）或数据 \ （数据： Uri，mediastream： Uri \）。  |
| CSP14306 | "对于 \ [策略类型 \]，没有为指令提供的源 [指令类型 \]-这等效于使用" none "，并且将阻止下载此类型的所有资源。" | 为安全内容提供指令和不列出任何源以供访问，这与不允许下载指令中指定类型的任何资源相同。  | 源可以是一个或多个 internet 主机名或 IP 地址，以及可选的 URL 方案和/或端口号。  |
| CSP14307 | "源 [源 URL] 已为指令 \ [策略类型 \] 的指令类型 \] 提供。" | 此指令中列出了一个重复源 \ （URL、关键字或数据 \），将被忽略。  | 删除标识的重复源。  |
| CSP14308 | "在 [指令名称] 处的 \ [policy type \] 中解析指令失败。" | 指令标识失败。  有关如何编写支持的指令的指导，请[http://content-security-policy.com](http://content-security-policy.com/)参阅。  | 指令必须用分号分隔。  例如，如果你有一个应用程序从内容传递网络（例如`https://cdn.example.net`\）加载其所有资源，并且你知道你不需要带框架的内容或任何插件，则你的策略可能如下所示： `Content-Security-Policy: default-src https://cdn.example.net; child-src 'none'; object-src 'none'.` *\ * 当指令使用分号分隔时，指令中的源应仅使用空格分隔。* |
| CSP14309 | "\ [Policy type \] 中的 \ [指令名称 \] 的" 未知指令 "-指令将被忽略。" | CSP 策略中设置的指令未知，将被忽略。  | 有关支持的指令的列表，请[http://content-security-policy.com](http://content-security-policy.com/)参阅。  |
| CSP14310 | "\ [Policy type] 中的" 不支持的指令 [指令名称]-指令将被忽略。 " | 在对不受支持的策略类型 \ （例如， `Content-Security-policy-Report-Only`标头字段 \）进行分析时发现了一个指令，将被忽略。  有关支持的指令， [http://content-security-policy.com](http://content-security-policy.com/)请参阅。  | 删除不受支持的指令。  **注意**：在 \ <meta \ > 元素或 "标题" `Content-Security-policy-Report-Only`字段中不支持某些指令。  |
| CSP14311 | "指令 \ [指令名称 \] 已在 \ [策略类型 \] 中提供-重复指令将被忽略。" | 分析期间发现重复的指令，将忽略第二条指令及其源表达式。  | 删除重复的脚本。  |
| CSP14312 | "在 [policy type]： [target uri] 中的资源违反指令 [指令名称]。  将阻止资源。 " | 在此示例中： "资源违反指令" 脚本-源 ms-appx：数据：主机定义的策略中的 "unsafe-eval"：内联脚本。  将阻止资源。 " | 由于 "主机定义" 策略中的指令`'script-src ms-appx: data: 'unsafe-eval'` ，内联脚本 \ （目标 uri \）被阻止。  <br /> 作者需要将所有内联脚本和样式移出行，因为用户代理无法确定攻击者是否注入了内联脚本。  删除内联脚本并将其放在外部文件中。  |
| CSP14313 | "在 [policy type]： [target uri] 中的资源违反指令 [指令名称]。  由于策略为 "仅报告"，资源将不会被阻止。 " | 标识了违反`Content-Security-policy-Report-Only`标题字段中指定的指令的资源。  由于它属于`Report-Only`策略类型，因此不会阻止该资源。  | 如果应阻止此资源以保护您的网站，请将该指令移动到 "内容安全策略" 标题字段中。  |
| CSP14314 | "无法将策略冲突报告发送到 [目标位置 uri]，因为 [取消操作的原因]。" | 报告违反策略的问题、指定要发送报告的目标目的地和未发送报告的原因均应标识。  | 该`report-uri`指令指定当违反内容安全策略时，浏览器将发送报告的 URL。  *\ * 不能在 \ <meta \ > 标记中使用它。* |
| CSP14315 | "未能强制执行 [策略类型] 中的沙盒指令，因为 [取消操作的原因]。" | 由于指定的原因，沙盒指令失败。  此指令对页面可以执行的操作（而不是页面可以加载的资源）施加限制。  如果存在沙盒指令，则会将页面视为在 iframe 内加载。  它可以阻止弹出窗口和插件并阻止脚本执行。  | 将沙盒值保留为空以保持所有限制位置，或添加值： `allow-forms`、 `allow-same-origin`、 `allow-scripts`和`allow-top-navigation`。  *\ * 在 \ <元 > 元素或 "标题" `Content-Security-policy-Report-Only`字段中不支持沙盒指令。* |
| CSP14316 | "由于主机替代，允许脚本评估。" | 如果包含 " `script-src`或`default-src` " 指令，则内联脚本`eval()`将被禁用，除非您`unsafe-inline`分别`unsafe-eval`指定 and。  | `'unsafe-eval'` 允许使用`eval()`和类似的方法从字符串创建代码。  必须包含单引号。  ***注意**：这是不安全的，可打开您的网站以查看跨网站脚本漏洞。 * |
| CSP14317 | 由于主机替代而允许 "帧 [源名称]"。 | 由于主机 CSP 策略中设置了替代，因此已允许进行标识的源帧。  | 策略可能包含 nonce-源表达式，这意味着源只能在一次使用时使用，并且服务器每次传输策略时都必须为该指令生成一个新值。  Nonces 替代它们所处的指令中的限制。  |

> [!NOTE]
> 对于用户的受信任安全区域中的网站，Microsoft Edge 不检查样式表的 MIME 类型。  

## CSS 代码  

这些错误采用 CSS31xx 格式，与*Web 打开字体格式*\ （WOFF \）和*嵌入式 OpenType* \ （EOT \）字体源和主机服务器问题相关。  

| 代码 | 消息 | 描述 | 建议的修复 |
|:--- |:--- |:--- |:--- |
| CSS3111 | "@font 遇到未知错误" | 遇到了 "Web 打开字体格式 \ （WOFF \）" 和 "嵌入式 OpenType 字体 \ （EOT \）" 等级联样式表的 "嵌入式 OpenType 字体 \ （\）" 的情况下遇到的未知问题。  | 检查 WOFF 字体的来源。  尝试其他字体或源，看看是否可以再现该问题。  |
| CSS3112 | "@font WOFF 失败的完整性检查" | Web 打开字体格式 \ （WOFF \）字体可能已损坏、不完整或不是正确的格式。  | 检查字体来源。  尝试一种已知正常的字体或来源，看看是否可以再现该问题。  |
| CSS3113 | "@font 文档原点与 EOT 根字符串之间的人脸不匹配" | 无法使用该字体，因为嵌入的 OpenType \ （EOT \）字体中的 URL \ （rootstring \）与使用该字体的文档的域不匹配。  | EOT rootstring 中的 URL 校验和可能不正确，指示字体的损坏或更改的 URL。  请确保字体已获得许可或对使用该字体的网站具有权限。  |
| CSS3114 | "@font-遇到失败的 OpenType 嵌入权限检查。  权限必须是可安装的。 " | 字体正面没有安装当前网页所需的权限。  | 获取用于嵌入字体的正确权限或许可证。  |
| CSS3115 | "@font 面无法加载无效的 OpenType 字体。" | 字体正面对于此用途无效。  | 获取当前和有效字体的权限或许可证。  |
| CSS3116 | "@font-遇到失败的跨起源请求。  没有访问控制-原创标题。 " | 可能没有为跨域访问配置字体。  | 该字体并非从与文档相同的原点提供。  请确保为该字体提供服务的主机允许使用 "访问控制-原创" HTTP 标头来使用此字体。                        |
| CSS3117 | "@font-遇到失败的跨起源请求。  资源访问受限。 " | "访问控制-允许-原创" 标题可能未正确配置，或者字体主机可能不允许您的页面使用此字体。  | 请确保资源具有正确的权限和正确配置的 HTTP 响应标题，该标题在为字体提供服务的主机上具有跨域访问权限。  |
| CSS3118 | "无法创建新的样式表。  文档中包含多个 "最大值" 样式表。 " | Microsoft Edge 在呈现页面的过程中创建了超过4095的样式表对象。  | 这可能是控制不足的 JavaScript 进程或生成系统错误。  减少生成的样式表对象数。  |
| CSS3119 | "媒体查询-ms-视图状态已被弃用。  -在 Windows 8.1 之后，ms-视图状态媒体查询可能会更改或不可用。  而是使用最大宽度和最小宽度的查询。 " | 您的 CSS 包含`-ms-view-state`一个媒体查询。  | 使用最大宽度和最小宽度。  |

## HTML 代码

这些代码采用 HTML1xxx 格式，如 HTML1115。  其中许多特定于 Internet Explorer 概念（如*文档模式*和*兼容性视图*）的旧版代码  

| 代码 | 消息 | 描述 | 建议的修复 |  
| :--- |:--- |:--- |:--- |  
| HTML1112 | "从 \ [encoding \] 重启到 \ [编码 \]" | 指定的代码页与服务器的代码页不同。  | 使用与服务器相同的代码页来避免此错误。  |  
| HTML1113 | "文档模式从 \ [mode \] 重新启动到 \ [mode \]" | 该网页需要不同于浏览器当前设置为的文档模式。  | 当用户从其他页面浏览时，使其退出开发人员的控件时，可能会出现此消息。  |  
| HTML1114 | 来自 \ [domain \] 的 "代码页 \ [encoding \] 替代冲突的代码页 \ [encoding \] 来自 \ [域 \]" | 在 HTTP \ （来自服务器 \）和 HTML \ （页面 \）标题中指定的 codepages 彼此不同。  | 更改一个，使其匹配。  |  
| HTML1115 | "X-UA-兼容的 META 标记 \`[META tag]`" 已忽略，因为文档模式已完成 | 通常，META 标记位于 "Script" 或 "Style" 声明之后，该声明修复了页面的文档模式。  | 将 X-UA 兼容的 META 标记尽可能早地移动到标题中。  最好将其放在紧随 \ <title \ > 和字符集值之后。  |  
| HTML1116 | "X-UA-兼容的 META 标记 \`[META tag]`" 已忽略，因为有较早的 X-ua 兼容的 meta`[META tag]`标记 \ （\） " | 源代码的 \ <head \ > 部分中有多个 "X UA 兼容的" "META" 标记。  | 删除除一个 "X-UA 兼容的 META" 标记之外的所有标记，确保它在标题中尽可能早。  一个好的做法是将其放在紧随 \ <title \ > 和字符集值之后。  |  
| HTML1121 | 不允许使用 "代码页 \ [encoding \]"，仅允许使用代码页 \ [encoding \]。 " | 网页中的内容调用了在此上下文中不允许使用的字符编码。  | 请确保所有内容都使用邮件中指定的允许编码。  |  
| HTML1122 | "Internet Explorer 正在模拟 IE8" 的企业模式下运行 " | 页面当前在企业模式下呈现，这是 Windows Internet Explorer 8 的模拟。  | 此模式由 IT 管理层针对特定网站进行配置。  如果单个用户需要将其关闭到网页上，请清除 "工具" 菜单上的 "企业模式" 选项。  有关企业模式管理的详细信息，请参阅[IT 文档](https://technet.microsoft.com/library/dn640687.aspx)。  |  
| HTML1201 | "`[domain]`是你已添加到兼容性视图的网站。" | 用户已选择当前网站的 "**兼容性视图**" 按钮或通过 "**兼容性视图" 设置**添加。  | 用户启动。  |  
| HTML1202 | "`[domain]`正在兼容性视图中运行，因为已选中" 在兼容性视图中显示 intranet 网站 "。" | 用户已选中**兼容性视图设置**中的 "**在兼容性视图中显示 intranet 网站**" 复选框。  | 用户需要按 Alt + T，选择 "**兼容性视图设置**"，然后清除 "**在兼容性视图中显示 intranet 网站**" 复选框。  |  
| HTML1203 | "`[domain]`已配置为通过组策略在兼容性视图中运行。" | 网络管理员已指定网页将在兼容性视图中运行。  | 您需要与网络管理员联系。  |  
| HTML1204 | "`[domain]`正在兼容性视图中运行，因为已选中" 在兼容性视图中显示所有网站 "。" | 用户已选中 "**兼容性视图设置**" 中的 "**在兼容性视图中显示所有网站**" 复选框。  | 用户需要按 Alt + T，选择 "**兼容性视图设置**"，然后清除 "**在兼容性视图中显示所有网站**" 复选框。  |  
| HTML1300 | "导航发生" | 已导航到新页面，或者刷新了当前页面。  | 这是一条信息性消息，而不是错误。  |  

## HTML5 分析器警告  

在 HTML 分析期间执行的验证过程中，可能会出现以下警告。  这些警告不一定意味着页面损坏，但所提供的 HTML 对于每个 HTML5 标准无效。  与较早版本的 HTML 或 XHTML 规范创建的内容在 HTML5 中可能无效，尤其是在使用 DOCTYPEs 时。

这些警告通常表示缺少或其他字符以及不匹配的标记。  解决这些警告时，与较旧的浏览器兼容性以及网页符合 HTML5 标准的合规性将会提高。  为了帮助识别警告的来源，它包括行和字符偏移信息，以及指向发现问题所在位置的链接。

| 代码     | 消息 |  
| :--- |:--- |  
| HTML1400 | "数字字符引用的开头出现意外字符。  预期 [0-9]。 " |  
| HTML1401 | "十六进制数字字符引用开头的意外字符。  预期 ed [0-9]、[a-f] 或 [A-f]。 " |  
| HTML1402 | "字符引用缺少结束分号"; "。" |  
| HTML1403 | "数字字符引用未解析为有效字符。" |  
| HTML1404 | "无法识别的命名字符引用。" |  
| HTML1405 | "无效字符： U + 0000 NULL。  不应使用 Null 字符。 " |  
| HTML1406 | "无效的标记开始： \ < \？"。  问号不应为 "开始标记"。 |  
| HTML1407 | "标记名称无效。  第一个字符应匹配 [a-zA-Z]。 " |  
| HTML1408 | "无效的结束标记 \ </\ >。  结束标记不应为空。 " |  
| HTML1409 | "无效的属性名称字符。  属性名称不应包含 \ （\ "\）、\ （\ ' \）、\ （\ < \）或 \ （= \）。" |  
| HTML1410 | "未加引号的属性值无效。  未加引号的属性值不应包含 \ （\ "\" \）、\ （\）、\ （\ < \）、\ （= \）或 \ （\）。 " |  
| HTML1411 | "意外的文件结尾。" |  
| HTML1412 | "注释格式不正确。  批注应以 \ < \!--\ > 开头。 " |  
| HTML1413 | "意外字符： U + 003E 大于符号 \ （\ > \）" |  
| HTML1414 | "意外的字符： U + 0021 感叹号 \ （\！ \）" |  
| HTML1415 | "意外字符： U + 002D 连字符-减号 \ （-\）" |  
| HTML1416 | "注释结尾的" 意外字符 "。  应输入 "--\ >"。 " |  
| HTML1417 | "空 DOCTYPE。  最短有效的 doctype 为 \ < \！DOCTYPE html \ >。 " |  
| HTML1418 | "DOCTYPE 中出现意外字符。" |  
| HTML1419 | "DOCTYPE 中出现意外的关键字。  应输入 "PUBLIC" 或 "SYSTEM"。 " |  
| HTML1420 | "PUBLIC" 或 "SYSTEM" 关键字后出现意外的引号。  应输入空格。 " |  
| HTML1421 | "结束标记的格式不正确。  结束标记不应包含属性。 " |  
| HTML1422 | "开始标记的格式不正确。  一个自结束斜杠后面应跟一个 U + 003E 大于号 \ （\ > \）。 " |  
| HTML1423 | "开始标记的格式不正确。  属性应使用空格分隔。 " |  
| HTML1424 | "无效字符" |  
| HTML1500 | "标记不能是自结束标记。  使用显式结束标记。 " |  
| HTML1501 | "意外的文件结尾。" |  
| HTML1502 | "意外的 DOCTYPE。  仅允许一个 DOCTYPE，并且必须在任何元素之前出现。 " |  
| HTML1503 | "意外的开始标记。" |  
| HTML1504 | "意外的结束标记。" |  
| HTML1505 | "意外的字符标记。" |  
| HTML1506 | "意外的标记。" |  
| HTML1507 | "意外字符： U + 0000 NULL。  不应使用 Null 字符。 " |  
| HTML1508 | "不匹配的结束标记"。 |  
| HTML1509 | "不匹配的结束标记"。 |  
| HTML1510 | "必需节点不在作用域内。" |  
| HTML1511 | "在 \ <head \ > 外遇到意外的 head 级元素。" |  
| HTML1512 | "不匹配的结束标记"。 |  
| HTML1513 | "额外 <html \ > 标记 fond。  每个文档仅应存在一个 \ <html \ > 标记。 " |  
| HTML1514 | 找到 "特大" <正文 \ > 标记。  每个文档仅应存在一个 <正文 \ > 标记。 " |  
| HTML1515 | "发现 \ <的框架集 \ > 在文档中太远。  此标记应在创建 <body > 之前出现。 " |  
| HTML1516 | "无效的嵌套。  页眉标记（如 \ <h1 \ > 或 \ <h2 \ > 不应放置在另一个页眉标记中。 " |  
| HTML1517 | "无效的嵌套。  \ <形式 \ > 标记不应放置在另一个 \ <窗体 \ > 中。 " |  
| HTML1518 | "无效的嵌套。  \ <按钮 \ > 标记不应放置在另一个 \ <按钮 \ > 中。 " |  
| HTML1519 | "无效的嵌套。  \ <的 \ > 标记不应放置在另一个 \ <a \ > 中。 " |  
| HTML1520 | "意外的开始标记： \ <isindex \ > 元素已被否决，不应使用。" |  
| HTML1521 | "意外 \ </body\ > 或文件末尾。  所有打开的元素都应在文档结束之前关闭。 " |  
| HTML1522 | "无效的结束标记： \ </br\ >。  改用 \ <br \ > 或 \ <br/\ >。 " |  
| HTML1523 | "重叠结束标记。  标记的结构应为 \ <b \ > \ <i \ > \ </i\ > \ </b\ > 而不是 \ <b > <\ > </b\ > \ </i\ >。 " |  
| HTML1524 | "DOCTYPE 无效。  最短有效的 doctype 为 \ < \！DOCTYPE html \ >。 " |  
| HTML1525 | "在外来内容中发现意外的 HTML 标记 \ （MathML/SVG \）。" |  
| HTML1526 | "无效的嵌套。  \ <nobr \ > 标记不应放置在另一个 \ <nobr \ > 中。 " |  
| HTML1527 | "期望的" DOCTYPE "。  最短有效的 doctype 为 \ < \！DOCTYPE html \ >。 " |  
| HTML1528 | HTML 内容中 > "意外的 \ <图像 \"。  改用 \ <img \ >。 " |  
| HTML1529 | "无效的 xmlns： xlink 属性值。  值必须为 "\ <https://w3.org/1999/xlink\>"。 " |  
| HTML1530 | "在结构表元素内找到的文本。  表格文本只能放在 <标题为 \ >、\ <td \ > 或 \ <> 元素中。 " |  
| HTML1531 | "Xmlns 属性值无效。  对于 SVG 元素，值必须为 "\ <https://w3.org/2000/svg/\>"。 " |  
| HTML1532 | "Xmlns 属性值无效。  对于 MathML 元素，值必须为 "\ <https://w3.org/1998/Math/MathML/\>"。  |  

## HTTP 代码  

从远程服务器返回 HTTP 错误代码，以响应请求。  可能最熟悉的是 HTTP404，只要服务器找不到 "统一资源标识符 \ （URI \）" 中指定的页面或文档，就会返回该页面。

| 代码 | 消息 | 描述 |  
| :--- |:--- |:--- |  
| HTTP400 | 错误请求 | 由于语法无效，服务器无法处理请求。  |  
| HTTP401 | 遭 | 请求的资源需要用户身份验证。  |  
| HTTP402 | 需要支付 | 当前未在 HTTP 协议中实现。  |  
| HTTP403 | 被 | 服务器已理解该请求，但拒绝完成它。  |  
| HTTP404 | 找不到 | 服务器找不到与请求的 URI 匹配的任何内容。  |  
| HTTP405 | 错误方法 | 不允许使用的 HTTP 谓词。  |  
| HTTP406 | 无人接受 | 找不到客户端可接受的答复。  |  
| HTTP407 | 需要代理身份验证 | 需要代理身份验证。  |  
| HTTP408 | 请求超时 | 服务器等待请求时超时。  |  
| HTTP409 | 协调 | 由于与资源的当前状态发生冲突，无法完成请求。  |  
| HTTP410 | 熄灭 | 所请求的资源在服务器上不再可用，并且不知道转发地址。  |  
| HTTP411 | 需要长度 | 服务器拒绝接受未定义内容长度的请求。  |  
| HTTP412 | 前置条件失败 | 在服务器上测试一个或多个请求标头字段时，该条件的计算结果为 false。  |  
| HTTP413 | 负载太大 | 服务器拒绝处理请求，因为请求实体大于服务器愿意或能够处理的大小。  |  
| HTTP414 | URI 太长 | 服务器拒绝为请求服务，因为请求 URI 的长度超过服务器愿意解释的长度。  |  
| HTTP415 | 不支持的媒体类型 | 服务器拒绝为请求提供服务，因为请求的实体的格式不受请求方法的请求资源的支持。  |  
| HTTP416 | 请求的范围未 SATISFIABLE | 服务器无法提供客户端请求的文件部分。  该部分可能会超出文件末尾。  |  
| HTTP417 | 预期失败 | 服务器无法满足预期请求标头字段的要求。  |  
| HTTP418 | 向 TEAPOT 发送即时消息 | 服务器是 teapot;brew 咖啡。  |  
| HTTP419 | 身份验证超时 | 以前有效的身份验证已过期。  |  
| HTTP422 | UNPROCESSABLE 实体 | 请求格式良好，但无法处理，因为出现语义错误。  |  
| HTTP423 | 锁 | 正在访问的资源已被锁定。  |  
| HTTP424 | 失败的依赖关系 | 请求失败，因为以前的请求失败。  |  
| HTTP426 | 需要升级 | 客户端必须切换到其他协议。  |  
| HTTP428 | 需要前提条件 | 原始服务器要求请求具有条件。  |  
| HTTP429 | 请求太多 | 服务器拒绝为请求提供服务，因为客户端提交的请求过多。  |  
| HTTP431 | 请求标头字段太大 | 服务器拒绝为请求提供服务，因为标头字段或所有标头字段的大小大于服务器愿意或能够处理的大小。  |  
| HTTP449 | 重试 | 请求应在采取相应操作后重试。  |  
| HTTP500 | 服务器错误 | 服务器遇到意外情况，无法完成请求。  |  
| HTTP501 | 不支持 | 服务器不支持完成请求所需的功能。  |  
| HTTP502 | 网关错误 | 在作为网关或代理的情况下，服务器收到来自它在尝试完成请求时访问的上游服务器的无效响应。  |  
| HTTP503 | 服务不可用 | 服务暂时过载。  |  
| HTTP504 | 网关超时 | 请求在等待网关时超时。  |  
| HTTP505 | 版本不受支持 | 服务器不支持或拒绝支持请求消息中使用的 HTTP 协议版本。  |  
| HTTP506 | 变体还协商 | 请求的透明内容协商导致循环引用。  |  
| HTTP507 | 存储空间不足 | 服务器无法存储完成请求所需的表示形式。  |  
| HTTP508 | 检测到循环 | 服务器在处理请求时检测到无限循环。  |  
| HTTP510 | 不扩展 | 需要进一步扩展该请求，以便服务器完成它。  |  
| HTTP511 | 需要网络身份验证 | 客户端必须进行身份验证才能获得网络访问权限。  |  

## JavaScript 语法错误  

当其中一个语句的结构违反一个或多个语法规则时，将出现 JavaScript 语法错误。  

| 错误编号 | 描述 |  
| --- | --- |  
| 1019 | [循环外不能有 "break"](/scripting/javascript/misc/can-t-have-break-outside-of-loop) |  
| 1020 | [循环外不能有 "continue"](/scripting/javascript/misc/can-t-have-continue-outside-of-loop) |  
| 1030 | [条件编译处于关闭状态](/scripting/javascript/misc/conditional-compilation-is-turned-off) |  
| 1027 | ["default" 只能在 "switch" 语句中出现一次](/scripting/javascript/misc/default-can-only-appear-once-in-a-switch-statement) |  
| 1005 | [应输入 "\ （"](/scripting/javascript/misc/expected-left-parenthesis-javascript) |  
| 1006 | [应输入 "\）"](/scripting/javascript/misc/expected-right-parenthesis-javascript) |  
| 1012 | [应输入 "/"](/scripting/javascript/misc/expected-minus) |  
| 1003 | [应输入 "："](/scripting/javascript/misc/expected-colon) |  
| 1004 | [应输入 ";"](/scripting/javascript/misc/expected-semicolon) |  
| 1032 | [应输入 "@"](/scripting/javascript/misc/expected-at) |  
| 1029 | [应输入 "@end"](/scripting/javascript/misc/expected-at-end) |  
| 1007 | [应输入 "\]"](/scripting/javascript/misc/expected-right-square-bracket) |  
| 1008 | [应输入 "{"](/scripting/javascript/misc/expected-left-curly-brace) |  
| 1009 | [应输入 "}"](/scripting/javascript/misc/expected-right-curly-brace) |  
| 1011 | [应输入 "="](/scripting/javascript/misc/expected-equal-javascript) |  
| 1033 | [应输入 "catch"](/scripting/javascript/misc/expected-catch) |  
| 1031 | [应输入常量](/scripting/javascript/misc/expected-constant) |  
| 1023 | [应输入十六进制数字](/scripting/javascript/misc/expected-hexadecimal-digit) |  
| 1010 | [应输入标识符](/scripting/javascript/misc/expected-identifier-javascript) |  
| 1028 | [应输入标识符、字符串或数字](/scripting/javascript/misc/expected-identifier-string-or-number) |  
| 1024 | [应输入 "while"](/scripting/javascript/misc/expected-while) |  
| 1014 | [无效字符](/scripting/javascript/misc/invalid-character-javascript) |  
| 1026 | [找不到标签](/scripting/javascript/misc/label-not-found) |  
| 1025 | [标签重定义](/scripting/javascript/misc/label-redefined) |  
| 1018 | [函数外的 "return" 语句](/scripting/javascript/misc/return-statement-outside-of-function) |  
| 1002 | [语法错误](/scripting/javascript/misc/syntax-error-javascript) |  
| 1035 | [Throw 必须后跟在同一源行上的表达式](/scripting/javascript/misc/throw-must-be-followed-by-an-expression-on-the-same-source-line) |  
| 1016 | [注释未结束](/scripting/javascript/misc/unterminated-comment) |  
| 1015 | [未终止的字符串常量](/scripting/javascript/misc/unterminated-string-constant-javascript) |  
  
### 脚本主机错误  

以下错误属于脚本宿主，但你可能偶尔会看到这些错误：  
  
| 错误 | HRESULT | 描述 |  
| ---| --- | --- |  
| SCRIPT_E_RECORDED | 0x86664004 | 在脚本引擎和主机之间记录和传递错误。  主机需要将错误代码传递给呼叫方。  |  
| SCRIPT_E_REPORTED | 0x80020101 | 脚本引擎通过 IActiveScriptSite：： OnScriptError 向主机报告了未处理的异常。  主机可以忽略此错误。  |  
| SCRIPT_E_PROPAGATE | 0x8002010 | 传播到调用方的脚本错误可能位于其他线程中。  主机应将错误代码传递给呼叫方。  |  

## JavaScript 运行时错误

当脚本尝试执行系统无法执行的操作时，将发生 JavaScript 运行时错误。  在计算变量表达式或分配内存时，你可能会看到运行时错误。

| 错误号 | 描述 |  
| --- | --- |  
| 级 | [拒绝访问](/scripting/javascript/misc/access-is-denied) |  
| 438 | [对象不支持此属性或方法](/scripting/javascript/misc/object-doesn-t-support-this-property-or-method) |  
| 1001 | 内存不足 |  

### Windows 运行时错误  

 如果你使用的是 Windows 运行时 \ （WinRT） Api，你可能会看到已从 Windows 运行时 Hresult 转换的 JavaScript 错误。  通过获取低位的十六进制值并将其转换为十进制数，可将 over 0x80070000 范围内的 Windows 运行时 Hresult 转换为 JavaScript 错误。  例如，HRESULT 0x80070032 转换为十进制值50，并且 JavaScript 错误为 SCRIPT50。  HRESULT 0x80074005 转换为十进制值16389，并且 JavaScript 错误为 SCRIPT16389。

| 错误编号 | 描述 |  
| --- | --- |  
| 5029 | [数组长度必须为有限正整数](/scripting/javascript/misc/array-length-must-be-a-finite-positive-integer) |  
| 5030 | [必须为数组长度分配一个有限的正数](/scripting/javascript/misc/array-length-must-be-assigned-a-finite-positive-number) |  
| 5028 | [缺少 Array 或 arguments 对象](/scripting/javascript/misc/array-or-arguments-object-expected) |  
| 5010 | [缺少布尔值](/scripting/javascript/misc/boolean-expected) |  
| 5003 | [无法分配给函数结果](/scripting/javascript/misc/cannot-assign-to-a-function-result) |  
| 5000 | [无法分配给 "this"](/scripting/javascript/misc/cannot-assign-to-this) |  
| 5034 | [不支持值参数中的循环引用](/scripting/javascript/misc/circular-reference-in-value-argument-not-supported) |  
| 5006 | [缺少日期对象](/scripting/javascript/misc/date-object-expected) |  
| 5015 | [应输入枚举器对象](/scripting/javascript/misc/enumerator-object-expected) |  
| 5022 | [引发了异常，未捕获](/scripting/javascript/misc/exception-thrown-and-not-caught) |  
| 5020 | [正则表达式中缺少 "）"](/scripting/javascript/misc/expected-right-parenthesis-in-regular-expression-javascript) |  
| 5019 | [正则表达式中缺少 "&#93;"](/scripting/javascript/misc/expected-right-square-bracket-in-regular-expression-javascript) |  
| 5023 | [函数没有有效的原型对象](/scripting/javascript/misc/function-does-not-have-a-valid-prototype-object) |  
| 5002 | [预期函数](/scripting/javascript/misc/function-expected) |  
| 5008 | [非法作业](/scripting/javascript/misc/illegal-assignment-javascript) |  
| 5021 | [字符集中的范围无效](/scripting/javascript/misc/invalid-range-in-character-set-javascript) |  
| 5035 | [无效的 replacer 参数](/scripting/javascript/misc/invalid-replacer-argument) |  
| 5014 | [缺少 JavaScript 对象](/scripting/javascript/misc/javascript-object-expected) |  
| 5001 | [应输入数字](/scripting/javascript/misc/number-expected) |  
| 5007 | [缺少对象](/scripting/javascript/misc/object-expected) |  
| 5012 | [需要对象成员](/scripting/javascript/misc/object-member-expected) |  
| 5016 | [应输入正则表达式对象](/scripting/javascript/misc/regular-expression-object-expected) |  
| 5005 | [应输入字符串](/scripting/javascript/misc/string-expected) |  
| 5017 | [正则表达式中的语法错误](/scripting/javascript/misc/syntax-error-in-regular-expression-javascript) |  
| 5026 | [小数位数字超出范围](/scripting/javascript/misc/the-number-of-fractional-digits-is-out-of-range) |  
| 5027 | [精度超出范围](/scripting/javascript/misc/the-precision-is-out-of-range) |  
| 5025 | [要解码的 URI 不是有效的编码](/scripting/javascript/misc/the-uri-to-be-decoded-is-not-a-valid-encoding) |  
| 5024 | [要编码的 URI 包含无效字符](/scripting/javascript/misc/the-uri-to-be-encoded-contains-an-invalid-character) |  
| 5009 | [未定义的标识符](/scripting/javascript/misc/undefined-identifier) |  
| 5018 | [意外限定符](/scripting/javascript/misc/unexpected-quantifier-javascript) |  
| 5013 | [需要 VBArray](/scripting/javascript/misc/vbarray-expected) |  

## 安全代码

安全错误代码的格式如下`SEC7xxx`所示`SEC7113`。  这些错误反映 Microsoft Edge 强制实施的安全条件，如混合内容和跟踪保护。

| 代码 | 消息 | 描述 | 建议的修复 |  
| :--- |:--- |:--- |:--- |  
| SEC7111 | "HTTPS 安全性受 [资源的名称] 影响" | 安全超文本传输协议 \ （HTTPS \）页面包含不安全源中的内容。  | 请确保页面中的所有内容（包括脚本、样式表对象和图像）都来自 HTTPS 源。  |  
| SEC7112 | "来自 [URL] 的脚本因 mime 类型不匹配而被阻止" | URL 指定的 JavaScript 文件的 HTTP 响应标头具有 "X-Content-Type： nosniff" 标头，并且没有可识别的内容类型声明。  | 更新服务器以在 HTTP 响应标题中发送 JavaScript 文件的正确内容类型 \ （如文本/javascript、应用程序/javascript）。  有关详细信息和内容类型的完整列表，请参阅[Internet Explorer 中的 MIME 处理更改](https://blogs.msdn.microsoft.com/ie/2010/10/26/mime-handling-changes-in-internet-explorer/)。  |  
| SEC7113 | "由于 mime 类型不匹配，已忽略 CSS" | 由于 HTTP 头中有错误的 MIME 类型，因此未使用导入的样式表。  | 确保使用正确的 HTTP 响应标题（包括文本/css 的内容类型）传递样式表文件。  有关详细信息，请参阅[Internet Explorer 中的 MIME 处理更改](https://blogs.msdn.microsoft.com/ie/2010/10/26/mime-handling-changes-in-internet-explorer/)。  |  
| SEC7114 | "跟踪保护阻止了此页面中的下载。[此处提供的 URL] " | 用户使用跟踪保护阻止了一个脚本或内容。  | 无-用户启动。  |  
| SEC7115 | "：已访问和：链接样式只能通过颜色不同。  某些样式未应用于：已访问。 " | 已使用 "已访问" 和 "链接" 样式更改了多个属性（如字体或大小）。  | 仅更改颜色属性。  |  
| SEC7116 | "访问被拒绝。  无法撤销跨源 URL： [URL]。 " | 具有不同于 blob 的站点的脚本尝试撤消 blob URL。  由于有 blob 原始策略，尝试失败。  | 使用创建 blob URL 的文档，确保所有 blob Url 都已使用来自原始站点的脚本吊销。  |  
| SEC7120 | 在访问控制-原创标题中找不到 "原始 [域]"。 | 在对你的 XMLHttpRequest 的响应中，返回了访问控制允许源标头，其值不包含或不匹配你的网站的原始值。  | 资源正在返回正确类型的标题代码，但不允许您的网站。  请与该资源的开发人员联系，让他们更新其访问控制支持源标题，以便允许您的网站。  你可以将它们指向[XHR 在 IE10 中的 cors](https://blogs.msdn.microsoft.com/ie/2012/02/09/cors-for-xhr-in-ie10/) ，以了解有关响应标题中的 CORS 的详细信息。  |  
| SEC7121 | "当凭据标志设置为 true 时，无法在访问控制-允许源中使用通配符"。 " | 服务器在标题中返回 "访问控制-允许-原创： *"，但在 XMLHttpRequest 中将`withCredentials`标志设置为**true**时，不允许执行此操作。  | 必须修改服务器端处理程序，以返回特定于此类型请求上的原点的访问控制允许源标头。  如果您不控制服务器端处理程序，则必须与执行的开发人员交谈。  |  
| SEC7122 | "凭据标志已设置为 true，但访问控制-允许-凭据不存在或未设置为" true "。 | 使用该`withCredentials`标志进行了 XMLHttpRequest。  未返回访问控制允许的凭据标头，或者返回的值不是**true**。  | 您的凭据或服务器的响应可能存在问题。  有关 credentialed 请求的信息，请参阅[XMLHttpRequest 级别2规范](https://w3.org/TR/XMLHttpRequest2/)。  |  
| SEC7123 | "请求标头 [header] 未出现在访问控制-允许标题列表中。" | 请求中包含自定义标头类型，但响应的访问控制-允许标题列表未包含它。  | 请确保服务器允许自定义标头，并明确允许在请求中发送一个。  |  
| SEC7124 | "请求方法 [方法] 在访问控制-允许的方法列表中不存在。" | 请求方法（如 POST）已在 XMLHttpRequest 中使用，但响应返回了不包含它的访问控制允许标头。  | 请确保服务器允许此类型的请求方法，并且如果该方法具有受限`withCredentials`访问权限，则你可以正确使用。  |  
| SEC7125 | "用于 [URL] 的 XMLHttpRequest 导致响应标题分析失败。" | 无法分析服务器的响应标头，因此请求失败。  | 使用 "[网络" 工具](https://msdn.microsoft.com/library/dn255004.aspx)捕获和检查响应标题，确保它们符合[CORS 规范](https://w3.org/TR/cors/)。  |  
| SEC7126 | "CORS 预检请求不允许重定向。" | 在原始标头中检测到重定向，并且用户代理在预检期间不关注重定向。  | 使用 "[网络" 工具](https://msdn.microsoft.com/library/dn255004.aspx)捕获和检查请求标头，并确保有单个直接原点。  |  
| SEC7127 | "已阻止针对 CORS 请求的重定向。" | CORS 资源的路径包含违反安全规则的重定向。  | 请确保你的 XMLHttpRequest 中的 CORS 资源的路径最直接。  |  
| SEC7128 | "CORS 响应不允许有多个访问控制-允许源标题。" | 响应标头包含多个访问控制-允许源标题。  | 这是服务器端错误。  服务器应返回单个访问控制允许源标头。  将此错误报告给开发人员，负责服务器端资源。
| SEC7129 | "CORS 响应不允许有多个访问控制-允许凭据标头。" | 响应标头包含多个访问控制-允许凭据标头。  | 这是服务器端错误。  服务器应返回单个访问控制-允许凭据标头。  将此错误报告给开发人员，负责服务器端资源。  |  
| SEC7130 | "在 [URL] 中检测到潜在的跨网站脚本。  内容已被 XSS 筛选器修改。 " | [XSS 筛选器](https://msdn.microsoft.com/library/dd565647.aspx)检测到来自资源的响应中的潜在恶意内容，并删除了令人讨厌的内容。  | 了解有关[XSS 筛选器](https://msdn.microsoft.com/library/dd565647.aspx)的详细信息。  |  
| SEC7131 | "通过允许脚本和原始访问，已获得沙盒的 iframe 的安全可能受到威胁。" | 如果沙盒 iframe 中的内容来自不受信任或不安全的源，则它可能会在脚本和相同的原始访问都允许时转义沙盒。  | 这是一条信息性警告消息，不会影响功能。  我们建议你避免将这些权限组合在一起，除非你确定将在 iframe 中运行的内容。  |  
| SEC7132 | "保护此网站的证书使用弱密码加密" | 此网站使用的 TLS 安全证书使用弱加密 | 更新服务器的 TLS 证书 |  

> [!NOTE]
> 对于用户的受信任安全区域中的网站，Microsoft Edge 不检查样式表的 MIME 类型。

## SVG 代码  

DevTools 目前不支持广泛的可缩放矢量图形 \ （SVG \）调试，但某些控制台消息会提供给调试的帮助。

| 代码 | 消息 | 描述 | 建议的修复 |  
| :--- |:--- |:--- |:--- |  
| SVG5601 | "SVG 路径数据的格式不正确，无法完全分析。" | SVG[路径](https://msdn.microsoft.com/library/ff972086.aspx)字符串的格式不正确，或包含无法识别的命令。  | 检查命令的格式。  |  
| SVG5602 | "SVG 点列表的格式不正确，无法完全分析。" | 用于元素的点列表（如[折线](https://msdn.microsoft.com/library/ff972113.aspx)）的格式不正确。  | 确保指向 "用户" 坐标系统的点已完成且设置正确格式。  |  

## XML 代码  

XML 代码采用 XML5xxx 的形式，如 XML5603。  

| 代码 | 消息 |  
|:--- |:--- |  
| XML5001 | "应用集成的 XSLT 处理。" |  
| XML5601 | "MX_E_MX" |  
| XML5602 | "输入意外结束。" |  
| XML5603 | "无法识别的编码"。 |  
| XML5604 | "无法切换编码。" |  
| XML5605 | "无法识别的输入编码签名。" |  
| XML5606 | "WC_E_WC" |  
| XML5607 | "需要空白。" |  
| XML5608 | "需要分号"。 |  
| XML5609 | "预期的" > "。" |  
| XML5610 | "应输入引号字符"。 |  
| XML5611 | "预期" = "。" |  
| XML5612 | "属性值中不允许使用 < 字符。" |  
| XML5613 | "需要十六进制数字。" |  
| XML5614 | "需要十进制数字"。 |  
| XML5615 | "预期" ["。" |  
| XML5616 | "预期" （"." |  
| XML5617 | "XML 字符非法。" |  
| XML5618 | "非法名称字符"。 |  
| XML5619 | "文档语法不正确。" |  
| XML5620 | "CDATA 节语法不正确。" |  
| XML5621 | "注释语法不正确。" |  
| XML5622 | "条件节语法不正确。" |  
| XML5623 | "不正确的 ATTLIST 声明语法。" |  
| XML5624 | "不正确的 DOCTYPE 声明语法。" |  
| XML5625 | "ELEMENT 声明语法不正确。" |  
| XML5626 | "不正确的实体声明语法。" |  
| XML5627 | "NOTATION 声明语法不正确。" |  
| XML5628 | "应输入" n "。" |  
| XML5629 | "需要" PUBLIC "。" |  
| XML5630 | "预期" 系统 "。" |  
| XML5631 | "无效名称。" |  
| XML5632 | "仅允许一个根元素。" |  
| XML5633 | "结束标记名称与相应的开始标记名称不匹配。" |  
| XML5634 | "此元素上已存在具有相同名称的属性。" |  
| XML5635 | "只有在文件开头才允许 XML 声明。" |  
| XML5636 | "前导" xml "。" |  
| XML5637 | "文本声明语法不正确。" |  
| XML5638 | "XML 声明语法不正确。" |  
| XML5639 | "编码名称语法不正确。" |  
| XML5640 | "不正确的公共标识符语法。" |  
| XML5641 | "内部 DTD 子集内的标记声明中不允许使用参数实体引用。" |  
| XML5642 | "用于标记声明的参数实体引用的替换文本本身必须包含一系列完整的标记声明。" |  
| XML5643 | "分析的实体不能包含对自身的直接或间接引用。" |  
| XML5644 | "指定实体的内容的格式不正确。" |  
| XML5645 | "尚未声明指定的实体。" |  
| XML5646 | "Entity reference 不能包含未分析实体的名称。" |  
| XML5647 | "属性值不能包含对外部实体的直接或间接引用。" |  
| XML5648 | "处理指令语法不正确。" |  
| XML5649 | "系统标识符语法不正确。" |  
| XML5650 | "预期问号 \ （\？ \）"。 |  
| XML5651 | "CDATA-section close 分隔符"]] > "不得用于元素内容。" |  
| XML5652 | "未读取所有数据块。" |  
| XML5653 | "已找到 DTD，但被禁止。" |  
| XML5654 | "已找到的 xml： space 属性的值无效。  有效值为 "保留" 或 "默认值"。 " |  
| XML5655 | "NC_E_NC" |  
| XML5656 | "非法的限定名字符"。 |  
| XML5657 | "多个冒号"： "不能出现在限定名称中。" |  
| XML5658 | "名称中不得出现" 冒号 "："。 |  
| XML5659 | "已声明前缀"。 |  
| XML5660 | "尚未声明指定的前缀。" |  
| XML5661 | "非默认命名空间声明不得具有空 URI。" |  
| XML5662 | "Xml" 前缀已保留，并且必须具有 URI "<https://w3.org/XML/1998/namespace/>"。 " |  
| XML5663 | "Xmlns" 前缀已保留供 XML 使用。 " |  
| XML5664 | "Xml 命名空间 URI \ （\ <https://w3.org/XML/1998/namespace/\>\)必须仅分配给前缀" xml "。" |  
| XML5665 | "Xmlns 命名空间 URI \ （\ <https://w3.org/2000/xmlns/\>\)已保留，不得使用。" |  
| XML5666 | "SC_E_SC" |  
| XML5667 | "已超过最大嵌套元素深度。" |  
| XML5668 | "已超过最大实体扩展数。" |  
| XML5669 | "WR_E_WR" |  
| XML5670 | "WR_E_NONWHITESPACE：编写器：指定的字符串不是空白。" |  
| XML5671 | "WR_E_NSPREFIXDECLARED：编写器：命名空间前缀已使用不同的命名空间声明。" |  
| XML5672 | "WR_E_NSPREFIXWITHEMPTYNSURI： writer：不能对空命名空间 URI 使用前缀。" |  
| XML5673 | "WR_E_DUPLICATEATTRIBUTE：编写器：重复属性。" |  
| XML5674 | "WR_E_XMLNSPREFIXDECLARATION： writer：无法重新定义 xmlns 前缀。" |  
| XML5675 | "WR_E_XMLPREFIXDECLARATION：编写器： xml 前缀必须具有 \ <https://w3.org/XML/1998/namespace/\> URI。" |  
| XML5676 | "WR_E_XMLURIDECLARATION：编写器： xml 命名空间 URI \ （ https://w3.org/XML/1998/namespace/\>\) \ <必须仅分配给前缀" xml "。" |  
| XML5677 | "WR_E_XMLNSURIDECLARATION：编写器： xmlns 命名空间 URI \ （ https://w3.org/2000/xmlns/\>\) \ <已保留，不得使用。" |  
| XML5678 | "WR_E_NAMESPACEUNDECLARED：编写器：命名空间未声明。" |  
| XML5679 | "WR_E_INVALIDXMLSPACE：编写器： xml： space 属性 \ 的值无效 \ （允许的值为" default "和" preserve "\）。" |  
| XML5680 | "WR_E_INVALIDACTION：编写器：执行所请求的操作将导致 XML 文档无效。" |  
| XML5681 | "WR_E_INVALIDSURROGATEPAIR：编写器：输入包含无效或不完整的代理项对。" |  
| XML5682 | "字符实体中出现意外字符。  应输入十进制数字。 " |  
| XML5683 | "字符实体中出现意外字符。  应输入十六进制数字。 " |  
| XML5684 | "指定字符实体的 Unicode 值无效。" |  
| XML5685 | "编码无效。" |  
| XML5686 | "未指定的 XML 错误。" |  

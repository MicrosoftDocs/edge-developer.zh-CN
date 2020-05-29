# Microsoft Edge 文档

## Microsoft 开放源代码行为准则

此项目采用了[Microsoft 开放源代码行为准则](https://opensource.microsoft.com/codeofconduct/)。
有关详细信息，请参阅[行为准则常见问题解答](https://opensource.microsoft.com/codeofconduct/faq/)或联系[opencode@microsoft.com](mailto:opencode@microsoft.com) ，了解任何其他问题或意见。

## 法律声明
Microsoft 及任何创作人按照[创作共用署名 4.0 国际公共许可](https://creativecommons.org/licenses/by/4.0/legalcode)授予你此存储中的 Microsoft 文档和其他内容的许可，请参阅[许可证](LICENSE)文件，并按照 [MIT 许可](https://opensource.org/licenses/MIT)授予你存储库中任何代码的许可，请参阅[许可证代码](LICENSE-CODE)文件。

本文档中引用的 Microsoft、Windows、Microsoft Azure 和/或其他 Microsoft 产品和服务是 Microsoft 在美国和/或其他国际/地区的商标或注册商标。
此项目的许可证并未授予你使用任何 Microsoft 名称、徽标或商标的权利。
可以在上找到 Microsoft 的一般商标指南 https://go.microsoft.com/fwlink/?LinkID=254653 。

您可以在上找到隐私信息https://privacy.microsoft.com

Microsoft 及任何创作人保留所有其他权利（无论是其各自的版权、专利或商标），无论是通过默示、禁止否认的方式还是以其他方式。

## 所在

这是托管于的 Microsoft Edge**文档**的存储库 [https://docs.microsoft.com/microsoft-edge/](https://docs.microsoft.com/microsoft-edge/) 。

如果您想要查看新的覆盖范围或有反馈，请考虑[**参与**](/CONTRIBUTING.md)。  你可以编辑现有内容、添加新内容或仅创建新[问题](https://github.com/MicrosoftDocs/edge-developer/issues)。 我们将查看你的建议，并协同工作以将它们合并到文档中。

[`Status`](https://dev.windows.com/microsoft-edge/platform/status/)在以下位置查找页面的数据： https://github.com/MicrosoftEdge/Status 。 此 `Status` 页面提供 Microsoft Edge 中 web 平台功能的最新实现状态和未来计划。

### 约定

- 添加页面时，必须在[toc.md](microsoft-edge/toc.md)中为其添加一个条目以使其显示。
- 文件夹可包含更多文件夹或 `readme.md` s
- 文件夹/目录名称以短划线（如 `f12-tools` ）和小写字母分隔。 它们用于 docs.microsoft.com 网站上的 Url。 不要使用下划线或 PascalCase/camelCase。

### 其他文本元素

这些其他文本元素的样式设置可用：

* 排序列表
* 具有常规项目符号
   * 您也可以嵌套项目符号。
   * 项目符号列表应具有多个条目。
* 非常标准

1. 排序列表。
2. 使用常规 ol 的西方样式编号。
3. 仅当列表确实有订单时才应使用。

_________________________

水平标尺可用。 我们建议谨慎使用它们以减少混乱。
不将水平标尺与标题标记合并;某些已使用的视觉层次结构线条样式。

### 显示代码

你可以使用内联 `code` 标记语法（使用 backticks）。

或者，你可以显示如下所示的代码块：

```css
body {
    background: #fff;
}
```

### 表

| 你可以     | 使用页眉 | 在表上    |
|-------------|-------------|-------------:|
| 左对齐| 除非#  | 456          |
| 文本值  | 更多文本   | $0.00        |

### 注释

谨慎使用笔记。 它们是用来突出显示 "不错过-it" 信息的块。

当前有四种不同版本的笔记的样式：
- 注意
- 条
- 提示
- 重要提示

它们分别如下所示：

![笔记模式](./media/notes.png)

```
> [!WARNING]
> Hello. Yes. I am a warning note that has been automagically created. My text may wrap to more than one line when the Markdown is parsed, but I must include all my information within a single (sometimes very long line) in the Markdown itself.```

For multi-line blockquote notes, use a > in front of each line of the notes as seen in the example below.

```


### Images

图像应存储在文件夹中 `media` ，并使用相对路径进行引用：

`![Note patterns](media/notes.png)`

# <a name="microsoft-edge-documentation"></a>Microsoft Edge 文档  

## <a name="microsoft-open-source-code-of-conduct"></a>Microsoft 开放源代码行为准则  

此项目已采用 [Microsoft 开放源代码行为准则](https://opensource.microsoft.com/codeofconduct)。  
有关详细信息，请参阅行为准则 [常见问题解答](https://opensource.microsoft.com/codeofconduct/faq) 或 [opencode@microsoft.com任何其他问题](mailto:opencode@microsoft.com) 或意见。  

## <a name="legal-notices"></a>法律声明  

Microsoft 和任何参与者在 Creative [Commons Attribution 4.0 国际](https://creativecommons.org/licenses/by/4.0/legalcode)公共许可证下授予你 Microsoft 文档和此存储库中其他内容的许可证，[](./LICENSE)导航到许可证文件，并授予你 MIT 许可证下存储库中任何代码的[](https://opensource.org/licenses/MIT)许可证，导航到[LICENSE-CODE](./LICENSE-CODE)文件。  

本文档中引用的 Microsoft、Windows、Microsoft Azure 和/或其他 Microsoft 产品和服务是 Microsoft 在美国和/或其他国际/地区的商标或注册商标。  
此项目的许可证并未授予你使用任何 Microsoft 名称、徽标或商标的权利。  
可以在以下网站找到 Microsoft 一般商标指南 [https://go.microsoft.com/fwlink/?LinkID=254653](https://go.microsoft.com/fwlink/?LinkID=254653) 。  

隐私信息位于 [https://privacy.microsoft.com](https://privacy.microsoft.com) 。  

Microsoft 及任何创作人保留所有其他权利（无论是其各自的版权、专利或商标），无论是通过默示、禁止否认的方式还是以其他方式。  

## <a name="contributing"></a>参与  

这是托管在 的 Microsoft **Edge** 文档的存储库 [https://docs.microsoft.com/microsoft-edge/](https://docs.microsoft.com/microsoft-edge/index) 。  

如果你想要包含新的覆盖范围或提供反馈，请考虑 [提供](./CONTRIBUTING.md)。  您可以编辑现有内容、添加新内容或创建新 [问题](https://github.com/MicrosoftDocs/edge-developer/issues)。  Microsoft Edge 团队查看您的建议，并努力将建议纳入文档。  

查找" [状态"页](https://developer.microsoft.com/microsoft-edge/status) 的数据，  [https://github.com/MicrosoftEdge/Status](https://github.com/MicrosoftEdge/Status) 位置为：  该页面提供了 Microsoft Edge 中 Web 平台功能的最新实现状态 `Status` 和未来计划。

### <a name="conventions"></a>约定  

*   添加页面时，您必须在页面中添加一个 [toc.md项，](./microsoft-edge/toc.yml) 这样它就会出现。
*   目录可能包含 `readme.md` 更多目录
*   文件夹/目录名称是短划线分隔的 \ (例如 `f12-tools` ，\) 和小写。  目录用于网站的 `docs.microsoft.com` URL。  避免使用下划线、PascalCase 或 camelCase。  

### <a name="other-text-elements"></a>其他文本元素  

这些其他文本元素具有可用的样式：  

*   未排序列表  
*   具有常规项目符号  
    *   您还可以嵌套项目符号。  
    *   项目符号列表应具有多个条目。  
*   标准排列 

1.  已排序列表。  
1.  使用常规的西文样式编号。  
1.  应仅在列表确实具有顺序时使用。  

---  

水平规则可用。  请慎用水平规则来减少混乱。  
避免将水平规则与标题标记一同使用;一些标题已使用线条样式作为视觉层次结构。  

### <a name="displaying-code"></a>显示代码  

可以使用内联 `code` Markdown 语法 \ (backticks\) 。  

或者，你可以显示代码块。  以下代码段是 css 示例。  

```css
body {
    background: #fff;
}
```  

### <a name="tables"></a>表  

| 可以 | 使用标头 | 表上 |  
|:--- |:--- |:--- |  
| 左对齐 | 除非# | 456 |  
| 文本值 | 更多文本 | $0.00 |  

### <a name="notes"></a>注释  

请谨慎使用备注。  这些块旨在突出显示"请勿错过"信息。  

目前已设置四个不同版本的注释样式。  

*   注意  
*   警告  
*   提示  
*   重要提示  

这些注释分别与以下代码段类似。  

```md
> [!NOTE]
> This is a NOTE  
```  

```md
> [!WARNING]
> This is a WARNING  
```  

```md
> [!TIP]
> This is a TIP  
```  

```md
> [!IMPORTANT]
> This is IMPORTANT  
```  

![笔记模式](./media/notes.png)

对于多行块注释，在每个注释行的前面使用大于 \ (\) 的字符，如以下示例 `>` 所示。  

```md
> This is a line in a blockquote.  
> My text may wrap to more than one line when the Markdown is parsed, but I must include all my information within a single \(sometimes very long line\) in the Markdown.  
> This is another line in a blockquote.  
```

### <a name="images"></a>Images  

图像应存储在目录中，并且使用图像脚本 `media` 的相对路径进行引用。  

<!--  `![Note patterns](media/notes.png)`  -->  

```md
:::image type="complex" source="./media/notes.png" alt-text="Note patterns" lightbox="./media/notes.png":::
   Note patterns  
:::image-end:::  
```  

# <a name="microsoft-edge-documentation"></a>Microsoft Edge 文档  

## <a name="microsoft-open-source-code-of-conduct"></a>Microsoft 开放源代码行为准则  

有关 Microsoft 开放源代码行为准则的信息，请导航到["Microsoft 开放源代码行为准则"。](CODE_OF_CONDUCT.md)  

## <a name="legal-notices"></a>法律声明  

Microsoft 和任何参与者在[Creative Commons Attribution 4.0 国际](https://creativecommons.org/licenses/by/4.0/legalcode)公共许可证下授予你 Microsoft 文档和此存储库中其他内容的许可证，导航到[许可证](./LICENSE)文件，并授予你 MIT 许可证下存储库中任何代码的[](https://opensource.org/licenses/MIT)许可证，导航到[LICENSE-CODE](./LICENSE-CODE)文件。  

本文档中引用的 Microsoft、Windows、Microsoft Azure 和/或其他 Microsoft 产品和服务是 Microsoft 在美国和/或其他国际/地区的商标或注册商标。  
此项目的许可证并未授予你使用任何 Microsoft 名称、徽标或商标的权利。  
可以在 上找到 Microsoft 一般商标准则 [https://go.microsoft.com/fwlink/?LinkID=254653](https://go.microsoft.com/fwlink/?LinkID=254653) 。  

隐私信息位于 [https://privacy.microsoft.com](https://privacy.microsoft.com) 。  

Microsoft 及任何创作人保留所有其他权利（无论是其各自的版权、专利或商标），无论是通过默示、禁止否认的方式还是以其他方式。  

## <a name="contributing"></a>参与  

这是托管在 的Microsoft Edge**文档**存储库 [https://docs.microsoft.com/microsoft-edge](https://docs.microsoft.com/microsoft-edge/index) 。  

如果你想要包含新的覆盖范围或提供反馈，请考虑 [提供](./CONTRIBUTING.md)。  您可以编辑现有内容、添加新内容或创建新 [问题](https://github.com/MicrosoftDocs/edge-developer/issues)。  工作组Microsoft Edge查看您的建议，并努力将这些建议纳入文档。  

查找"状态"网页 [的数据](https://developer.microsoft.com/microsoft-edge/status) ，位置为  [https://github.com/MicrosoftEdge/Status](https://github.com/MicrosoftEdge/Status) ：。  网页 `Status` 提供了 Web 平台功能的最新实现状态和Microsoft Edge。

### <a name="conventions"></a>约定  

*   在添加网页时，必须在网页中添加一个 [toc.md，这样](./microsoft-edge/toc.yml) 它就会出现。
*   目录可能包含更多目录或 `readme.md` s
*   文件夹/目录名称是短划线分隔的 \ (例如 `f12-tools` ，\) 小写。  目录用于网站的 `docs.microsoft.com` URL。  避免使用下划线、PascalCase 或 camelCase。  

### <a name="other-text-elements"></a>其他文本元素  

这些其他文本元素具有可用的样式：  

*   无序列表  
*   具有常规项目符号  
    *   您还可以嵌套项目符号。  
    *   项目符号列表应具有多个条目。  
*   标准排列 
    
1.  已排序列表。  
1.  使用常规的西文编号。  
1.  应仅在列表确实具有顺序时使用。  
    
---  

水平规则可用。  请慎用水平规则来减少混乱。  
避免将水平规则与标题标记一同使用;一些标题已对可视化层次结构使用线条样式。  

### <a name="displaying-code"></a>显示代码  

可以使用内联 `code` markdown 语法 \ (backticks\) 。  

或者，你可以显示代码块。  以下代码段是 css 示例。  

```css
body {
    background: #fff;
}
```  

### <a name="tables"></a>表  

| 可以 | 使用标头 | 表上的 |  
|:--- |:--- |:--- |  
| 左对齐 | 除非# | 456 |  
| 文本值 | 更多文本 | $0.00 |  

### <a name="notes"></a>注释  

请慎用笔记。  这些块旨在突出显示"不要错过"信息。  

四个不同的笔记版本当前已设置样式。  

*   注意  
*   WARNING  
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

对于多行块注释，在每个注释行前面使用大于 `>` \ (\) 字符，如以下示例所示。  

```md
> This is a line in a blockquote.  
> My text may wrap to more than one line when the markdown is parsed, but I must include all my information within a single \(sometimes very long line\) in the markdown.  
> This is another line in a blockquote.  
```  

### <a name="images"></a>Images  

图像应存储在目录中，并且使用图像脚本 `media` 通过相对路径引用。  

<!--  `![Note patterns](media/notes.png)`  -->  

```md
:::image type="complex" source="./media/notes.png" alt-text="Note patterns" lightbox="./media/notes.png":::
   Note patterns  
:::image-end:::  
```  

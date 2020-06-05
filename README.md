### 简介
本模板参照自<https://github.com/Aetf/xjtuthesis.git>，根据<http://www.lib.xjtu.edu.cn/info/1102/1217.htm>提供的论文模板调整而来。
该模板在原有xjtuthesis的基础上，至少（基本）修复了以下问题：

1. 一二三级标题的前后间距。
2. 参考文献采用2015的样式而非2005的样式， xjtuthesis所采用的样式中，有诸如冒号后面缺少空格，姓氏应该是首字母大写等比较细节的问题。
3. 调整英文封面页与模板一致（模板中首页专业部分没有括号，以及顺序不对）。
4. 调整目录的标题前后间距，并且在目录中添加了摘要的目录项。
5. 摘要的字体，字号均有问题。
6. 摘要的关键字字号有问题。
7. 致谢需要在参考文献前。
8. 关键词后应该有空行。
9. 三级标题(\subsubsection)应该是中文括号。
10. 公式应该居中。
11. 摘要页中不需要论文题目等信息。
12. 其它一些比较细节的问题。

### 关于字体
强烈建议在本地安装texlive2020进行编译，这种编译方法可以避免字体的问题。如果需要在overleaf等环境中编译，需要查询该环境所支持的字体列表，例如Overleaf支持的字体列表为：
<https://www.overleaf.com/learn/latex/Questions/Which%20OTF%20or%20TTF%20fonts%20are%20supported%20via%20fontspec%3F>，若需要在Overleaf上编译，请去掉master.tex中的truefont选项，并使用xelatex和texlive2019进行编译。

其它环境（例如ubuntu）需要自行更改xjtuthesis.cls中的字体。


### 安装使用
本模板需要texlive2020以上版本，文献管理使用biber后端，若使用vscode编译，配置文件如下：
```json
{
    "latex-workshop.latex.tools": [
        {
            "name": "xelatex",
            "command": "xelatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOC%"
            ]
        },
        {
            "name": "biber",
            "command": "biber",
            "args": [
                "%DOCFILE%"
            ]
        }
    ],
    "latex-workshop.latex.recipes": [
        {
            "name": "xelatex",
            "tools": [
                "xelatex"
            ]
        },
        {
            "name": "xelatex -> biber -> xelatex*2",
            "tools": [
                "xelatex",
                "biber",
                "xelatex",
                "xelatex"
            ]
        }
    ],
}
```

# 现代计算机图形学导论

本项目由北京大学可视计算与学习实验室筹划。

在线阅读地址：<https://cg-textbook.readthedocs.io>

## 快速入门

### 手动配置

1. 安装 Python 3.6 以上版本并配置环境变量；

2. 在项目根目录下依次运行下列命令：

   ``` shell
   pip install -r requirements.txt
   make html
   ```

   在使用 Powershell 时，若运行错误可使用 `.\make` 替代；

3. 使用浏览器打开 `build\html\index.html`；

4. 当修改本地文件后，在根目录下运行下列命令刷新网站：

   ``` shell
   make clean
   make html
   ```

### 自动配置（可选）

使用 `sphinx-autobuild` 可避免频繁调用 `make`。

首先调用 `pip` 安装：

```shell
pip install sphinx-autobuild
```

随后在根目录下调用下列命令以启动服务器：

```shell
sphinx-autobuild -a source build/html
```

在浏览器中打开 <http://127.0.0.1:8000> 以查看。网站将在发生本地修改后自动配置。

## 编写指南

本项目使用 `sphinx` 默认加载了 `mst-parser` 等插件，从而支持 reStructuredText 和 Markdown 两种标记语言及多项特殊语法。接下来将以 Markdown 为例简要介绍，reStructuredText 可参阅文档自行转换。

所用插件文档链接：

- [MyST](https://myst-parser.readthedocs.io)
- [sphinx-proof](https://sphinx-proof.readthedocs.io)
- [sphinxcontrib-bibtex](https://sphinxcontrib-bibtex.readthedocs.io)

### 插入公式

使用 LaTeX 风格的行内及行间公式语法：

```markdown
$行内公式$

$$
行间公式
$$
```

### 插入图片

MyST 插件使 Markdown 支持插入带编号的图片：

````markdown
```{figure-md}
<img src="图片地址" alt="替代文字" width="宽度（如500px）">

这里填写图片标题
```
````

### 插入特殊块

特殊块指用方框包含的、经过特殊美化的段落。MyST 支持下列特殊块：

- note （注解）
- warning（警告）

插入方法为：

````markdown
```{块类型}
内容
```
````

这里的块类型可代入前文列表中的类型英文名。MyST 支持的特殊块均可嵌套。

### 插入数学块

数学块也是一种特殊块，它不可嵌套，但能在每一个文档内自动编号，并进行交叉引用。sphinx-proof 支持下列数学块：

- proof（证明）
- theorem（定理）
- axiom（公理）
- lemma（引理）
- definition（定义）
- criteria（准则）
- remark（评注）
- conjecture（猜想）
- corollary（推论）
- algorithm（算法）
- example（示例）
- property（原理、定律）
- observation（观察）
- proposition（命题）

插入方法为：

````markdown
```{prf:块类型} 标题（可省略）
:label: 标签名（不重复的标识符，用来交叉引用；可省略）
:nonumber:（使当前块不参与标号；省略则正常）

内容
```
````

这里的块类型可填入前述的各数学块的英文名；标题填入该块显示的标题，如“牛顿第二定律”等。

注意 proof 块不支持自定义标题。使用 `` {prf:ref}`标签名` `` 进行交叉引用。

### 插入参考文献

`sphinxcontrib-bibtex` 插件使 sphinx 支持 bibliography 风格的文献引用。

首先在 `source/refs.bib` 中维护参考文献，随后在文档中使用 `` {cite}`文献标签` ``进行引用。

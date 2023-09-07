# $\LaTeX$

## 如何自定义命令

`\newcommand{新命令}[参数数量][默认值]{定义内容}`

`\def\{新命令字符串}{原命令}`

比如：

```latex
\newcommand{\me}{\mathrm{e}}
%% 或 %%
\def\Var{\mathrm{Var}}
```

实例：

$$
\newcommand{\me}{\mathrm{e}}
\newcommand{\mi}{\mathrm{i}}
\newcommand{\md}{\mathrm{d}}
\def\Var{\mathrm{Var}}

\Var
\\
\me
\\
\mi
\\
\md
\\
$$

## 排版

### 对齐

`&`是对齐锚点

```latex
\begin{align}
  (a + b)^3  &= (a + b) (a + b)^2        \\
             &= (a + b)(a^2 + 2ab + b^2) \\
             &= a^3 + 3a^2b + 3ab^2 + b^3
\end{align}
```

$$
\begin{align}
  (a + b)^3  &= (a + b) (a + b)^2        \\
             &= (a + b)(a^2 + 2ab + b^2) \\
             &= a^3 + 3a^2b + 3ab^2 + b^3
\end{align}
$$

### 空隙间隔

$\LaTeX$ 默认是两个字母之间是有一定空隙的，然而我们可以用某些命令来增大，或者缩小这些空隙，以下命令使用之后，就会取代这个默认的空隙。

下面依次越来越小，分别是双 quad 空格，quad 空格，大空格，中空格，小空格，没空格（也就是默认什么都不写），紧贴。

```latex
\qquad
\quad
\ <!-- 注意这里反斜杠后有个空格 -->
\;
\,
<!-- 目测默认的空隙大小在上下这两个之间 -->
\!
```

实例：

​	在上标中取消左星号和字母 x 的间隔：${}^*\!x^*$，不使用空隙函数：${}^*x^*$

## 文本模式

如果想要在公式中编排普通的文字（非斜体），必须把文本放在`\textrm{...}`命令中

实例：
$$f_{\textrm{pre}}(x)$$

在数学模式中，TEX 根据上下文选择字体大小。例如，上标会排版成较小的字体。

如果你想要把等式的一部分排版成罗马字体，不要用`\textrm` 命令，只因`\textrm` 会暂时切换到文本模式， 而此时字体大小切换机制将不起作用。使用`\mathrm` 来保持字体大小切换机制的正常。

```latex
$$\int_a^b f(x)\mathrm{d}x$$
```

$$\int_a^b f(x)\mathrm{d}x$$

## 数学模式

有两种，一种是行内，一种是段落，行内公式的**高度会受到文本排版中的行高限制**

行内公式一般放在 `\begin{math}` 和 `\end{math}` 之间，或者`\(\)`，段落公式一般放在 `\begin{displaymath}` 和 `\end{displaymath}` 之间，或者`\[\]`

## 常用量

无穷大：`\infty` $\infty$

音标：

![Latex常用数学符号输入方法](https://exp-picture.cdn.bcebos.com/430174fec314f1c54e6c5f743c27ac5307889ddb.jpg?x-bce-process=image%2Fresize%2Cm_lfit%2Cw_500%2Climit_1%2Fformat%2Cf_jpg%2Fquality%2Cq_80)

小写希腊字母：

![Latex常用数学符号输入方法](https://exp-picture.cdn.bcebos.com/a48bc2e8904800fc927586bbd42043715edb93db.jpg?x-bce-process=image%2Fresize%2Cm_lfit%2Cw_500%2Climit_1%2Fformat%2Cf_jpg%2Fquality%2Cq_80)

## 方程组

联立方程：

```latex
\begin{cases}
\sqrt{\frac{1}{N}}, N\geq 1, \\
\sqrt{\frac{1}{2N}}, N<1,
\end{cases}
```

效果：
$$
\begin{cases}
\sqrt{\frac{1}{N}}, N\geq 1, \\
\sqrt{\frac{1}{2N}}, N<1,
\end{cases}
$$

方程组（以麦克斯韦方程为例）：

```latex
\begin{align}
\nabla\cdot\mathbf{E}  &= \cfrac{\rho}{\varepsilon_0} \\
\nabla\cdot\mathbf{B}  &= 0 \\
\nabla\times\mathbf{E} &= -\cfrac{\partial\mathbf{B}}{\partial t} \\
\nabla\times\mathbf{B} &= \mu_0\mathbf{J}+\mu_0\varepsilon_0\cfrac{\partial\mathbf{E}}{\partial t}
\end{align}
```

效果：
$$
\begin{align}
\nabla\cdot\mathbf{E}  &= \cfrac{\rho}{\varepsilon_0} \\
\nabla\cdot\mathbf{B}  &= 0 \\
\nabla\times\mathbf{E} &= -\cfrac{\partial\mathbf{B}}{\partial t} \\
\nabla\times\mathbf{B} &= \mu_0\mathbf{J}+\mu_0\varepsilon_0\cfrac{\partial\mathbf{E}}{\partial t}
\end{align}
$$

方程组要注意 & 的用法（参见排版中的对齐），这个的用处是：以某个位置为依据对齐方程组，比如上面就是以“=”为依据。

## 集合

| 语法      |    效果     | 语法        | 效果          | 语法      | 效果        | 语法      | 效果        | 语法        | 效果          |
| --------- | :---------: | ----------- | ------------- | --------- | ----------- | --------- | ----------- | ----------- | ------------- |
| \forall   |  $\forall$  | \exists     | $\exists$     | \empty    | $\empty$    | \emptyset | $\emptyset$ | \varnothing | $\varnothing$ |
| \in       |    $\in$    | \ni         | $\ni$         | \not\in   | $\not\in$   | \notin    | $\notin$    | \subset     | $\subset$     |
| \subseteq | $\subseteq$ | \supset     | $\supset$     | \supseteq | $\supseteq$ | \cap      | $\cap$      | \bigcap     | $\bigcap$     |
| \cup      |   $\cup$    | \bigcup     | $\bigcup$     | \biguplus | $\biguplus$ | \sqsubset | $\sqsubset$ | \sqsubseteq | $\sqsubseteq$ |
| \sqsupset | $\sqsupset$ | \sqsupseteq | $\sqsupseteq$ | \sqcap    | $\sqcap$    | \sqcup    | $\sqcup$    | \bigsqcup   | $\bigsqcup$   |

## 关系符号

| 语法                         | 效果                         |
| ---------------------------- | ---------------------------- |
| `\sim`                       | $\sim$                       |
| `\approx`                    | $\approx$                    |
| `\simeq`                     | $\simeq$                     |
| `\cong`                      | $\cong$                      |
| `\dot=`                      | $\dot=$                      |
| `\ggg`                       | $\ggg$                       |
| `\gg`                        | $\gg$                        |
| `>`                          | $>$                          |
| `\ge`                        | $\ge$                        |
| `\geqq`                      | $\geqq$                      |
| `=`                          | $=$                          |
| `\leq`                       | $\leq$                       |
| `\leqq`                      | $\leqq$                      |
| `<`                          | $<$                          |
| `\ll`                        | $\ll$                        |
| `\lll`                       | $\lll$                       |
| `\equiv`                     | $\equiv$                     |
| `\because \qquad \therefore` | $\because \qquad \therefore$ |
| `\not\equiv`                 | $\not\equiv$                 |
| `\ne`                        | $\ne$                        |
| `\neq`                       | $\neq$                       |
| `\propto`                    | $\propto$                   |
| `\pm`                        | $\pm$                        |
| `\mp`                        | $\mp$                        |

## 上标下标

这个太简单了就不说了

## 分式

输入较短分式和带分号的分式：

```latex
(x+y)/2 \\ % 较短分式

\frac{x+y}{2} \\
\frac{1}{1+\frac{1}{2}}
```

效果：
$$
(x+y)/2 \\ % 较短分式

\frac{x+y}{2} \\
\frac{1}{1+\frac{1}{2}}
$$

## 根式

```latex
$$\sqrt{2}<\sqrt[3]{3}$$
$$\sqrt{1+\sqrt[p]{1+a^2}}$$
$$\sqrt{1+\sqrt[^p\!]{1+a^2}}$$
```

效果：

$$\sqrt{2}<\sqrt[3]{3}$$
$$\sqrt{1+\sqrt[p]{1+a^2}}$$
$$\sqrt{1+\sqrt[^p\!]{1+a^2}}$$

## 求和与积分

```latex
$$
\sum_{k=1}^{n}\frac{1}{k}
$$

$\sum_{k=1}^n\frac{1}{k}$

$$
\int_a^b f(x)dx
$$

$\int_a^b f(x)dx$
微分符直体：$$\int_a^b f(x)\mathrm{d}x$$
```

效果：

$$
\sum_{k=1}^{n}\frac{1}{k}
$$

$\sum_{k=1}^n\frac{1}{k}$

$$
\int_a^b f(x)dx
$$

$\int_a^b f(x)dx$
微分符直体：$$\int_a^b f(x)\mathrm{d}x$$

很容易就能看出行内公式的高度受制于行高，变小了（数学模式的两种）。

## 定界符

```latex
$($    %(
$)$    %)
$[$    %[
$]$    %]
$\{$    %{
$\}$    %}
$|$    %|
$\|$    %||
```

实例：

```latex
$$\left(\sum_{k=\frac{1}{2}}^{N^2}\frac{1}{k}\right)$$
```

$$
\left\|\sum_{k=\frac{1}{2}}^{N^2+2*\left(N+1\right)}\frac{1}{k}\right\|
$$

## 矩阵

对于少于 10 列的矩阵，可使用 matrix，pmatrix，bmatrix，Bmatrix，vmatrix 和 Vmatrix 等环境。

```latex
$$\begin{matrix}1 & 2\\3 &4\end{matrix}$$
$$\begin{pmatrix}1 & 2\\3 &4\end{pmatrix}$$
$$\begin{bmatrix}1 & 2\\3 &4\end{bmatrix}$$
$$\begin{Bmatrix}1 & 2\\3 &4\end{Bmatrix}$$
$$\begin{vmatrix}1 & 2\\3 &4\end{vmatrix}$$
$$\begin{Vmatrix}1 & 2\\3 &4\end{Vmatrix}$$
```

$$
\begin{matrix}
1 & 2 \\
3 & 4
\end{matrix}
$$
$$
\begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix}
$$
$$
\begin{bmatrix}
1 & 2 \\
3 & 4
\end{bmatrix}
$$
$$
\begin{Bmatrix}
1 & 2 \\
3 & 4
\end{Bmatrix}
$$
$$
\begin{vmatrix}
1 & 2 \\
3 & 4
\end{vmatrix}
$$
$$
\begin{Vmatrix}
1 & 2 \\
3 & 4
\end{Vmatrix}
$$

### 排版矩阵

```latex
$$
\mathbf{X} =
\left(
\begin{array}{ccc}
x_{11} & x_{12} & \ldots \\
x_{21} & x_{22} & \ldots \\
\vdots & \vdots & \ddots
\end{array}
\right)
$$
```

效果：

$$
\mathbf{X} =
\left(
\begin{array}{ccc}
x_{11} & x_{12} & \ldots \\
x_{21} & x_{22} & \ldots \\
\vdots & \vdots & \ddots
\end{array}
\right)
$$

由此看出，`vdots` 是垂直的点，`ldots` 是水平的点，`ddots` 是斜的点

也可以在矩阵中划线：

```
$$
\left(
\begin{array}{c|c}
1 & 2 \\
\hline
3 & 4
\end{array}
\right)
$$
```

效果：

$$
\left(
\begin{array}{c|c}
1 & 2 \\
\hline
3 & 4
\end{array}
\right)
$$

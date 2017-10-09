## Latex 数学公式入门

[TOC]

### 1. 基础

#### 行内公式
latex的行内公式可以在一行中显示，用两个`$`包括起来，前后可以是正常的文字。
> 这是一个行间公式 $ a + b > c $ , 它的代码是:`$ a + b > c $`

#### 行间公式
与行内公式不同的是行间公式必须单独一行显示，用`$$`包括起来。
> $$
> a + b > c
> $$
> 代码为：
> ```latex
> $$
> a + b > c
> $$
> ```
#### 公式编号

在公式的末尾用`\tag{编号}`可以对公式进行手动编号，但是需要注意的是编号只对行间公式有效，如果对行内公式使用了编号，该行内公式会自动转换成未行间公式。
> $$
> a + b > c \tag{3}
> $$
> 代码为：
> ```latex
> $$
> a + b > c \tag{3}
> $$
> ```

### 2. 常用符号
#### 运算符号

| 名称    | 语法                          | 示例                                       | 效果                                       |
| ----- | --------------------------- | ---------------------------------------- | ---------------------------------------- |
| 乘号与除号 | `\times与\div`               | `$a \times b \div c$`                    | $a \times b \div c$                      |
| 点乘    | `\cdot`                     | `$a \cdot b$`                            | $a \cdot b$                              |
| 并集与交集 | `\cup与\cap`                 | `$A \cup B \cap C$`                      | $A \cup B \cap C$                        |
| 上标或指数 | `^`                         | `$a^b$`                                  | $a^b$                                    |
| 下标    | `_`                         | `$a_b$`                                  | $a_b$                                    |
| 分数    | `\frac{分子}{分母}`             | `$\frac{a+b}{b}$`                        | $\frac{a+b}{b}$                          |
| 开方    | `\sqrt[次数]{被开方数}`           | `$\sqrt[3]{5}$`                          | $\sqrt[3]{5}$                            |
| 求和    | `\sum_{下界}^{上界}{内容}`        | `$\sum_{i=1}^{n}{p_i}$ or  $$\sum_{i=1}^{n}{p_i}$$` | $\sum_{i=1}^{n}{p_i}$ or  $$\sum_{i=1}^{n}{p_i}$$ |
| 连乘    | `\prod_{下界}^{上界}`           | `$\prod_{i=0}^{n}a_i$ or $$\prod_{i=0}^{n}a_i$$` | $\prod_{i=0}^{n}a_i$ or  $$\prod_{i=0}^{n}a_i$$ |
| 积分    | `\int_{下界}^{上界}{被积函数}\,dx}` | `$\int_{a}^{b}{f(x)\,dx}+\iint g(x)\,dx$` | $\int_{a}^{b}{f(x)\,dx}+\iint g(x)\,dx$  |
| 曲线积分  | `\oint`                     | `$\oint f(x)$`                           | $\oint f(x)$                             |

#### 关系符号

| 名称        | 语法                    | 示例                            | 效果                          |
| --------- | --------------------- | ----------------------------- | --------------------------- |
| 大于等于、小于等于 | `\leq、\geq`           | `$a\leq b\geq c$`             | $a\leq b\geq c$             |
| 恒等于       | `\equiv`              | `$a \equiv b$`                | $a \equiv b$                |
| 不等号       | `\neq`                | `$a \neq b$`                  | $a \neq b$                  |
| 约等于       | `\approx`             | `$a \approx b$`               | $a \approx b$               |
| 全等        | `\cong`               | `$\cong$`                     | $\cong$                     |
| 相似        | `\simeq`              | `$\simeq$`                    | $\simeq$                    |
| 属于与不属于    | `\in与\notin`          | `$a \in b 和 a \notin c$`      | $a \in b 和 a \notin c$      |
| 包含于       | `\subseteq和\supseteq` | `$\subseteq、\supseteq$`       | $\subseteq、\supseteq$       |
| 平行与垂直     | `\parallel与\perp`     | `$a \parallel n、 a \perp c $` | $a \parallel n、 a \perp c $ |

#### 常用希腊字母

| 字母        | 语法        | 字母            | 语法            |
| --------- | --------- | ------------- | ------------- |
| $\alpha$  | `\alpha`  | $\beta$       | `\beta`       |
| $\gamma$  | `\gamma`  | $\varepsilon$ | `\varepsilon` |
| $\lambda$ | `\lambda` | $\theta$      | `\theta`      |
| $\eta$    | `\eta`    | $\rho$        | `\rho`        |
| $\omega$  | `\omega`  | $\sigma$      | `\sigma`      |
| $\mu$     | `\mu`     | $\varphi$     | `\varphi`     |

#### 其他符号

| 名称   | 语法               | 示例                                       | 效果                                       |
| ---- | ---------------- | ---------------------------------------- | ---------------------------------------- |
| 无穷符号 | `\infty`         | `$\infty$`                               | $\infty$                                 |
| 圆周率  | `\pi`            | `$\pi$`                                  | $\pi$                                    |
| 三角形  | `\bigtriangleup` | `$\bigtriangleup ABC \cong \bigtriangleup CDE$` | $\bigtriangleup ABC \cong \bigtriangleup CDE$ |
| 极限   | `\lim_{下标}{函数}`  | `$$\lim_{x\to 0}$$`                      | $$\lim_{x\to 0}$$                        |
| 三角函数 | `\三角函数名 变量`      | `$\sin x、\cos x$`                        | $\sin x、\cos x$                          |

### 3. 矩阵

#### 普通矩阵

普通的矩阵由`\begin{matrix}`开始，由`\end{matrix}`结束，每一行内的元素用`&`隔开，行间用`\\`作为分隔符：
> $$
> \begin{matrix}
>    1 & 2 & 3 \\
>    4 & 5 & 6 \\
>    7 & 8 & 9
>   \end{matrix}
> $$
>
> 生成上面矩阵的代码如下：
>
> ```latex
> $$
>  \begin{matrix}
>    1 & 2 & 3 \\
>    4 & 5 & 6 \\
>    7 & 8 & 9
>   \end{matrix}
> $$
> ```

#### 带括号的矩阵

但就几个数字还不像常见到的数学矩阵，一般来说矩阵在两端用括号括起来，括号有圆括号、方括号、花括号之分，为矩阵添加括号就需要在上面的代码前后添加一段就可以了：
> $$
> \left\{
> \begin{matrix}
>   1 & 2 & 3 \\
>   4 & 5 & 6 \\
>   7 & 8 & 9
> \end{matrix}
> \right\}
> $$
> 代码为：
>
> ```latex
> $$
> \left\{
> \begin{matrix}
>   1 & 2 & 3 \\
>   4 & 5 & 6 \\
>   7 & 8 & 9
> \end{matrix}
> \right\}
> $$
> ```

生成的矩阵如下： 


用`(`和`[`代替上面代码中的`\{`就可以换成圆括号或方括号。

#### 带省略号的矩阵

上面的是元素有限的矩阵，但有时候在矩阵中需要用到省略号，在Latex的省略号如下：

| 省略号类型    | 代码       |
| -------- | -------- |
| $\cdots$ | `\cdots` |
| $\ddots$ | `\ddots` |
| $\vdots$ | `\vdots` |

带省略号的矩阵示例如下： 

> $$
> \left[
> \begin{matrix}
> 1      & 2      & \cdots & n_1      \\
> 7      & 6      & \cdots & n_2      \\
> \vdots & \vdots & \ddots & \vdots   \\
> m      & 9      & \cdots & n_m      \\
> \end{matrix}
> \right]
> $$
>
> 代码为：
>
> ```latex
> $$
> \left[
> \begin{matrix}
> 1      & 2      & \cdots & n_1      \\
> 7      & 6      & \cdots & n_2      \\
> \vdots & \vdots & \ddots & \vdots   \\
> m      & 9      & \cdots & n_m      \\
> \end{matrix}
> \right]
> $$
> ```

#### 增广矩阵

增广矩阵中的最右边一列需要单独考虑，它与左边的部分用一条竖线分割开。使用`\begin{array}{cc|c}`来代替原来的`\begin{matrix}`来指定显示模式：

> ```latex
> $$
> \left[
> \begin{array}{cc|c}
>   1 & 2 & 3 \\
>   4 & 5 & 6 \\
>   7 & 8 & 9
> \end{array}
> \right]
> $$
> ```
>
> 代码中的`{cc|c}`中的`c`的总数等于矩阵的总列数，`|`的位置就是矩阵中分割线的位置，效果： 
> $$
> \left[
> \begin{array}{cc|c}
>   1 & 2 & 3 \\
>   4 & 5 & 6 \\
>   7 & 8 & 9
> \end{array}
> \right]
> $$
>

### 4. 例子

$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix} 
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
$$

代码：
```latex
$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix} 
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
$$
```


### 5. 参考 

[维基百科](https://zh.wikibooks.org/wiki/LaTeX/%E6%95%B0%E5%AD%A6%E5%85%AC%E5%BC%8F#.E6.95.B8.E5.AD.B8.E7.AC.A6.E8.99.9F.E5.88.97.E8.A1.A8) 
[MATHEMATICSmeta](http://meta.math.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)

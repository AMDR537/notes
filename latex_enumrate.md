# Latex 列表(enumerate)格式调整

主要包含调整编号格式，调整段首缩进和调整交叉引用格式。

## 1、调整编号格式

### 1.1 使用enumerate宏包

文首加入如下代码：

```latex
\usepackage{enumerate}
```

直接在中括号中输入目标格式即可。示例如下：

```latex
\begin{enumerate}[(1)]
    \item
\end{enumerate}
```

编号将改为（1）（2）（3）格式。

```latex
\begin{enumerate}[a.]
    \item
\end{enumerate}
```

编号将改为a. b. c.格式

```latex
\begin{enumerate}[(i)]
    \item
\end{enumerate}
```

编号将改为(i)，(ii)，(iii)格式

### 1.2 使用enumitem宏包

文首加入如下代码：

```latex
\usepackage{enumitem}
```

在中括号中加入 `label`选项及对应格式即可。示例如下：

```latex
\begin{enumerate}[label=(\arabic*)]
    \item
\end{enumerate}
```

- `\arabic`：阿拉伯数字1，2，3······
- `\alph`：字母a，b，c······
- `\Roman`:大写罗马字母：I， II， III······
  ······

## 2、调整段首缩进

### 2.1 使用enumitem宏包

引入 `enumitem`宏包后，可以通过在中括号添加 `left`选项进行修改：

```latex
\begin{enumerate}[left=2em]
    \item
\end{enumerate}
```

代码起到所有 `item`对象向右缩进两个字符大小。

### 2.2 手动调节

在不使用任何包的情况下，可以通过 `\setlength`命令调节：

```latex
\begin{enumerate}
    \setlength{\itemindent}{2em}
    \item
\end{enumerate}
```

## 3、调整交叉引用格式

引入 `enumitem`宏包，可以通过在中括号中添加 `ref`选项进行修改：

```latex
\begin{enumerate}[ref=\Roman*]
    \item 111 \label{first_item}
\end{enumerate}
```

在二级列表中，还可以通过 `\theenumi`引用第一级标题的序号，起到类似1.1， 1.2的效果。

```latex
\begin{enumrate}[ref=\Roman*]
    \item
    \begin{enumerate}[ref=\theenumi.\alph*]
        \item
    \end{enumerate}
\end{enumerate}
```

### 小结

想要调整列表格式，可以通过`enumerate`,`enumitem`宏包在中括号中改变对应参数实现。

本人随笔，如有错误，请多多包涵(*/ω＼*)

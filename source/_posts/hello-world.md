---
title: Markdown常用语法大全
tags: markdown 
categories: 教程
---
## 1.标题（这是一级标题）

格式如下：

``` Copy
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题	
```

效果如下：

## 一级标题

## 二级标题

### 三级标题

#### 四级标题

##### 五级标题

###### 六级标题

`提示：使用#在一行的最前面，并且#后面需要跟一个空格。`

## 2.代码块

**方法1**  
格式如下：

``` Copy
`一行代码块`(用一个反引号包起来）
```

效果如下：

```Copy
一行代码块
```

**方法2**  
格式如下：

```Copy
```
	一行代码块（用三个反引号包起来）
	二行代码块
```
```

效果如下：

```Copy
	一行代码块
	二行代码块
```

## 3.字体

格式如下：

``` markdown
*这是倾斜的文字*（一个星号包围）
**这是加粗的文字**（两个星号包围）
***这是斜体加粗的文字***（三个个星号包围）
~~这是加删除线的文字~~（两个波浪线包围）
H~2~O is是液体。
2^10^ 运算结果是 1024.
```

**效果如下：**

*这是倾斜的文字*  
**这是加粗的文字**  
***这是斜体加粗的文字***  
这是加删除线的文字  
H2O is是液体。  
2^10^ 运算结果是 1024.

## 4.文字上带链接

格式如下：

```copy
[百度](http://baidu.com)
```

效果如下：  
[百度](http://baidu.com/ "http://baidu.com")

## 5.表格

格式如下：

```markdown
项目     | Value
-------- | -----（表示上方的是表头）
电脑  | 1600
手机  | 12
导管  | 1
```

效果如下：

| 项目 | Value |
| --- | --- |
| 电脑 | 1600 |
| 手机 | 12 |
| 导管 | 1 |

## 6.列表

#### 6.1无序列表

格式如下：（用‘-’放前面）

```markdown
- 银河
  - 地球
    - 中国
```

效果如下：

+   银河
    +   地球
        +   中国

#### 6.1有序列表

格式如下：

```markdown
1. 苹果
2. 香蕉
3. 菠萝
```

效果如下：

1.  苹果
2.  香蕉
3.  菠萝

## 7.分割线

三个或三个以上的 ‘-’ 或 ‘\*’ 都可以 格式如下：

```copy
***
---
```

效果如下：

* * *

---
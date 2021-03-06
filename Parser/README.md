# Custom Markdown - Accelerating Contributions

In order to accelerate the process of building documentation/lesson webpages, whereever the text might have been drafted -- Google Docs or Word -- please do the following:

1.

## Headers

In order to indicate headers, in before the header title, write `#` for the largest available header. For a smaller sub-header, use `##` and `###` for sub-sub-headers. The code will go through the text document line-by-line until it hits any one of these symbols. This annotation is very similar to traditional markdown. After encountering any one of these pounds, the parser will preserve/match the string immmediately after this up until a newline. Here is the equivalent Regex.

```{regex}
/(#){1, 3}.*$
```

## Inline Code

To correctly display inline code, surround any code that you wish to preserve enclosed in single backticks. The parser will wait until the first encounter for this string and immediately stop the formatting as soon as the second backtick is detected. In order to ensure the syntax is highlighted according to your specified programming language, immediately after the backtick, please write either `{cpp}` or `{bash}` or `{python}`. Here is the equivalent Regex.

```{regex}
/`(\{( | (python) | (cpp) | (bash) )\})?.*`
```

## Space-Preserved Code

Similar to traditional markdown, we would indicate wanting space-preserved code by enclosing our code within three backticks. Moreover, immediately after the initial three backticks, please specify the programming language used. Here is the equivalent Regex.

````{regex}
/```(\{( | (python) | (cpp) | (bash) )\})?.*```
````

## Numerical / Alphabetical Lists (Ordered)

No special annotations are needed to the document in order to change lists. However, for nested lists, the default precedence is the outer list will be numerical and the inner sublist will be alphabetical. In order to change this precedence, please include `~~swap_precedence~~` somewhere in the document before the list. Here is the equivalent Regex to detect whether or not the list priority will be swapped.

```{regex}
/(~~swap_precedence~~)?
```

## Bullet Point Lists (Unordered)

In order to indicate we want bullet points, enclose.

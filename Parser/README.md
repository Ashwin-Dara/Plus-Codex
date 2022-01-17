# Custom Markdown - Accelerating Contributions

In order to accelerate the process of building documentation/lesson webpages, whereever the text might have been drafted -- Google Docs or Word -- please do the following:

1.

## Indicating Headers

In order to indicate headers, in before the header title, write `#` for the largest available header. For a smaller sub-header, use `##` and `###` for sub-sub-headers. The code will go through the text document line-by-line until it hits any one of these symbols. After encountering any one of these pounds, the parser will preserve/match the string immmediately after this up until a newline. Here is the equivalent Regex.

```{regex}
/ (#){1, 3}.*$
```

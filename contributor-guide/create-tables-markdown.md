<properties title="" pageTitle="在 markdown 中建立資料表" description="說明如何在 Markdown 中撰寫表格的程式碼。" metaKeywords="" services="" solutions="" documentationCenter="" authors="mblythe" videoId="" scriptId="" manager="dongill" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="09/01/2015" ms.author="mblythe" />

#在 markdown 中建立資料表

Markdown 中建立資料表最簡單的方法是使用管道和線條。

 ![][1]

您可以利用冒號，讓欄左右對齊︰

  	|-----:| - this is right aligned
  	|:-----| -  this is left aligned
  	|:-----:| - this is centered

如果您使用 HTML 表格，而且您 markdown 不會呈現兩個資料表之間，您需要關閉 TABLE 標記後面加入 BR 結尾標記。

![2]

如需如何在 markdown 中建立資料表的詳細資訊，請參閱︰
- Markdown 資料表產生器︰ http://www.tablesgenerator.com/markdown_tables
- https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables
- http://michelf.ca/projects/php-markdown/extra/#table

###著作指南的連結

- [概觀文章](./../README.md)
- [指引文章的索引](./contributor-guide-index.md)

<!--image references-->
[1]: ./media/create-tables-markdown/table-markdown.png
[2]: ./media/create-tables-markdown/break-tables.png

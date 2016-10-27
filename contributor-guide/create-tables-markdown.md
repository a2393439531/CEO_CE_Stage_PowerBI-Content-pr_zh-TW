<properties title="" pageTitle="Create tables in markdown" description="說明如何在 Markdown 中撰寫表格的程式碼。" metaKeywords="" services="" solutions="" documentationCenter="" authors="mblythe" videoId="" scriptId="" manager="dongill" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="09/01/2015" ms.author="mblythe" />

#Create tables in markdown

The simplest way to create a table in markdown is to use pipes and lines.

 ![][1]

您可以利用冒號，讓欄左右對齊︰

  	|-----:| - this is right aligned
  	|:-----| -  this is left aligned
  	|:-----:| - this is centered

If you use HTML tables and your markdown is not rendering between the two tables, you need to add a closing BR tag after the closing TABLE tag.

![2]

For more information about how to create tables in markdown, see:
- Markdown tables generator: http://www.tablesgenerator.com/markdown_tables
- https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables
- http://michelf.ca/projects/php-markdown/extra/#table

###Contributors' Guide Links

- [概觀文章](./../README.md)
- [指引文章的索引](./contributor-guide-index.md)

<!--image references-->
[1]: ./media/create-tables-markdown/table-markdown.png
[2]: ./media/create-tables-markdown/break-tables.png

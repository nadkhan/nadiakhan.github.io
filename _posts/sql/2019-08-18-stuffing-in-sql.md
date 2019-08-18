---
layout: post
title:  "Stuffing in SQL!"
date:   2019-08-18 10:22:41 +0500
categories: posts sql
---
I've written this code .. Hit like if you really like

```sql
SELECT STUFF(
(
	SELECT ',' + [ContactName] FROM [Northwind].[dbo].[Customers] ORDER BY [CustomerID] FOR XML PATH('')
),
1, 1, ''
) AS Employees
```

To understand the working of this expression, lets split understand it line by line. Initially, we have to look into the main query which represents a simple SELECT statement except the last part which uses keywords XML and PATH. Here, results of the select statement is convereted to XML and the tag is represented

```sql
SELECT ',' + [ContactName] FROM [Northwind].[dbo].[Customers] ORDER BY [CustomerID] FOR XML PATH('Name')
```

```sql
-- We had the output from the SELECT statement as
-- ,firstname,secondname,thirdname
-- There's a preceeding comma at the start
-- So we use STUFF to replace the contents of string a defined position

SELECT STUFF(',firstname,secondname,thirdname', 1, 1, '')
```

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/

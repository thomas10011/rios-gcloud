## Query Delta Data

网址：https://console.cloud.google.com/bigquery?project=patent-download-392805&ws=!1m4!1m3!3m2!1spatents-public-data!2spatents

> (GoogleSQL 是一种 ANSI 兼容的结构化查询语言 (SQL)，它支持多种类型的语句，包括查询语句、过程语言语句、数据定义语言 (DDL) 语句、数据操作语言 (DML) 语句、数据控制语言 (DCL) 语句和事务控制语言 (TCL) 语句)

使用 BigQuery 的 GoogleSQL 对数据集筛选，筛选出最近更新的专利号：

```sql
SELECT NEWTABLE.* FROM
`patents-public-data.patents.publications_202304` as OLDTABLE RIGHT JOIN
`patents-public-data.patents.publications_202310` as NEWTABLE ON
OLDTABLE.publication_number = NEWTABLE.publication_number
WHERE OLDTABLE.publication_number IS NULL

```

1. 在查询编辑器中，粘贴上述 SQL 查询语句。
2. 点击运行按钮来执行查询。查询结果将显示在下方的结果窗格中。
3. 在结果窗格中，点击保存结果按钮，并选择将结果保存到表格。
4. 在弹出的对话框中，选择您想要保存结果的项目、数据集和表格名称，然后点击保存按钮。
5. 在左侧导航栏中，找到您刚才保存的表格，并右键单击它。
6. 在弹出的菜单中，选择导出并选择您想要导出的文件格式。然后按照提示操作，将表格数据导出并下载到计算机。




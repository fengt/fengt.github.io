---
layout: post
title: excel匹配及计算
---

### 1. 设置日期每5分钟递增填充：

```
=TEXT(TIME(HOUR(D1),MINUTE(D1)+5,0),"h:MM")

DATE(YEAR(D1),MONTH(D1),DAY(TIME(HOUR(D1),MINUTE(D1)+5,0)))

=YEAR(D1)&"-"&MONTH(D1)&"-"&DAY(D1)&" "&HOUR(D1)&":"&MINUTE(D1)+5&":"&SECOND(D1)

=TEXT(YEAR(D1)&"/"&MONTH(D1)&"/"&DAY(D1)&" "&HOUR(D1)&":"&MINUTE(D1)+5,"yyyy/m/d h:mm")
```

### 2. 将excel中的重复数据取出（也可以直接使用“插入-->数据透视表”）：

* a、筛选出重复值![an image alt text]({{ site.baseurl }}/images/technology/excel001.jpg "001")；

+ b、筛选出有颜色的重复值![an image alt text]({{ site.baseurl }}/images/technology/excel002.jpg "002")；

- c、删除重复值，即剩余的重复唯一值![an image alt text]({{ site.baseurl }}/images/technology/excel003.jpg "003")；

### 3. 将excel中的多个工作表追加合成一个工作表：

```
Sub Merge()
For j = 1 To Sheets.Count
If Sheets(j).Name <> ActiveSheet.Name Then
X = Range("A65536").End(xlUp).Row
Sheets(j).UsedRange.Copy Cells(X, 1)
End If
Next
End Sub
```

### 4. 从地址中抓取区名称：

```
= IFERROR (
     MID (
          N2,
          FIND ("市", N2, 1) + 1,
          IFERROR (
               FIND ("区", N2, FIND("市", N2, 1)) - FIND ("市", N2, 1),
               FIND ("县", N2, FIND("市", N2, 1)) - FIND ("市", N2, 1)
          )
     ),
     ""
)
```

### 5. 根据一列(A)值和某个sheet表中一列(B)值匹配，并将B列对应的其他列值返回给A列与之对应：

```
=IF(ISERROR(VLOOKUP(A1,Sheet2!A$1:C$905,2,FALSE)),"",VLOOKUP(A1,Sheet2!A$1:C$905,2,FALSE))
```

### 6. 合并计算：

- _合并计算一列中重复值在不同列的行值相加：_
数据-->合并计算-->引用位置（Sheet2!A$1:C$10）-->最左列，确定。

- SUMIF函数的语法是这样的：=SUMIF(条件区域，条件，求和数据区域)举例来说=SUMIF(A$2:A$7,C2,B$2:B$7)，就是求A$2:A$7区域里等于C2单元格的值对应B$2:B$7数据的合计。

>  `=SUMIF(A$1:A$40,H1,B$1:B$40)`



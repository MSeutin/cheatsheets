# Html Cheatsheet

## Table of Contents
- [Tables](#Tables)
- [Forms](#Forms)


## Tables

#### Example 
<table border = "1">
    <tr>
        <th>Name</th>
        <th>Salary</th>
    </tr>
    <tr>
        <td>Ramesh Raman</td>
        <td>5000</td>
    </tr>
    <tr>
        <td>Shabbir Hussein</td>
        <td>7000</td>
    </tr>
</table>

#### Table Elements
```html
<table> <!-- wrapper element for all tables -->
<thead> <!-- defines column headers -->
<tbody> <!-- defines body -->
<tfoot> <!-- defines footer -->
<tr> <!-- sets up a row -->
<th> <!-- cell w bold centered text -->
<td> <!-- cell -->
```

#### Table Attributes
```html
<border> <!-- specify border around table & cells -->
<align> <!-- set the alignment of table horizontally -->
<colspan> <!-- number of columns a td element should span -->
<rowspan> <!-- number of rows a td elment should span -->
<!-- Examples -->
<table border="1"> ... </table>
<table align="center"> ... </table>
<td colspan="2"> Text will span horizontally </td> <!-- cell will span 2 columns -->
<td rowspan="2"> Text will span vertically </td> <!-- cell sill span 2 rows -->
```

## Forms

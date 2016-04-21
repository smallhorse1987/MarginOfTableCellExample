# 【技巧】随心所欲设置表格分割线水平间距

##纠结的表格分割线
纠结1：单元格没有填完一整屏时，出现了填充的分割线，影响美观。

纠结2：不管如何设置，分割线总是不能靠做对齐。

纠结3：表格里，有的单元格分割线要靠左对齐，有的要空10个point，有的不需要分割线。

##与分割线相关的设置
1. UITableView  
[UITableView setSeparatorInset:UIEdgeInsetsMake(0,leftMargin,0,0)];  
[UITableView setLayoutMargins:UIEdgeInsetsMake(0,0,0,0)];  

2. UITableViewCell  
[UITableViewCell setSeparatorInset:UIEdgeInsetsMake(0,leftMargin,0,0)];  
[UITableViewCell setLayoutMargins:UIEdgeInsetsMake(0,0,0,0)];  

**注意：**
setSeparatorInset 是iOS7.0开始提供的接口  
setLayoutMargins  是iOS8.0开始的提供的接口

##解决方案
第一，经过多次尝试，首先tableview和tableviewcell的margin都必须设置为0。  
第二，UITableView的SeparatorInset可以设置可以影响到所有的tableviewcell。  
第三，UITableViewCell的SeparatorInset可以单独设置特定单元的分割线缩进。  

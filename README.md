# 【技巧】随心所欲设置表格分割线水平间距

##纠结的表格分割线
问题1：单元格没有填完一整屏时，出现了填充的分割线，影响美观。

问题2：不管如何设置，分割线总是不能靠左对齐。

问题3：表格里，有的单元格分割线要靠左对齐，有的要空10个point，有的不需要分割线。

很多人不得不自己来绘制分割线。其实完全不必要，以下就是完全解决方案。

##与分割线相关的设置
首先要了解所有会影响分割线相关的设置
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
第一，要精准的控制分割线的左右间距，必须将tableview和tableviewcell的margin都必须设置为0。不要问我为什么，这是尝试了各种组合实践得出的结果。非常关键，也是很多人无法理解如何解决问题2）的根源。  
第二，UITableView的SeparatorInset可以设置可以影响到所有的tableviewcell。  
第三，UITableViewCell的SeparatorInset可以单独设置特定单元的分割线缩进。  

##见效果


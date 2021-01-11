# day03

### DML语言——数据操作语言（重点）

插入：insert

修改：update

删除：delete

### 一、插入语句

#### 语法一

~~~mysql
insert into 表名(字段名1,...) values(值1,...);
~~~

**要求：**

1、要求值的类型和字段的类型要一致或兼容
2、字段的个数和顺序不一定与原始表中的字段个数和顺序一致
	  但必须保证值和字段一一对应
3、假如表中有可以为null的字段，注意可以通过以下两种方式插入null值
	  ①字段和值都省略
  	②字段写上，值使用null
4、字段和值的个数必须一致
5、字段名可以省略，默认所有列

#### 规则与例子

![image-20210110203401001](day03.assets/image-20210110203401001.png)

![image-20210110203507233](day03.assets/image-20210110203507233.png)

![image-20210110203636786](day03.assets/image-20210110203636786.png)

![image-20210110203731489](day03.assets/image-20210110203731489.png)

![image-20210110203837635](day03.assets/image-20210110203837635.png)

![image-20210110203959779](day03.assets/image-20210110203959779.png)

#### 语法二

~~~mysql
insert into 表名 set(字段1=值1,...);
~~~

![image-20210110204301163](day03.assets/image-20210110204301163.png)

#### 两种语法比较

![image-20210110204427811](day03.assets/image-20210110204427811.png)

![image-20210110204627628](day03.assets/image-20210110204627628.png)

![image-20210110204747136](day03.assets/image-20210110204747136.png)

### 二、修改语句

#### 语法

![image-20210110204959626](day03.assets/image-20210110204959626.png)

![image-20210110205202866](day03.assets/image-20210110205202866.png)

![image-20210110205350643](day03.assets/image-20210110205350643.png)

修改多表又称为级联更新。

![image-20210110205519307](day03.assets/image-20210110205519307.png)

![image-20210110205646059](day03.assets/image-20210110205646059.png)

### 三、删除语句

#### 方式一：delete

![image-20210110205757194](day03.assets/image-20210110205757194.png)

![image-20210110210104027](day03.assets/image-20210110210104027.png)

![image-20210110210127506](day03.assets/image-20210110210127506.png)

**注意delete后面可以跟表1,或表2或表1和表2，这与需要删除的内容所在表有关。**



单表删除中可以通过添加LIMIT关键字来实现删除指定行：

~~~mysql
delete from 表名 【where 筛选条件】【limit 条目数】
~~~

#### 案例

![image-20210110205926436](day03.assets/image-20210110205926436.png)

![image-20210110210238404](day03.assets/image-20210110210238404.png)

![image-20210110210347714](day03.assets/image-20210110210347714.png)

#### 方式二：truncate

![image-20210110205811322](day03.assets/image-20210110205811322.png)

#### 案例

![image-20210110210733707](day03.assets/image-20210110210733707.png)

#### 两种方式的区别（面试题）

![image-20210110210856038](day03.assets/image-20210110210856038.png)

![image-20210110211320732](day03.assets/image-20210110211320732.png)

truncate和delete之间的第三点区别：

![image-20210110211048483](day03.assets/image-20210110211048483.png)

![image-20210110211154603](day03.assets/image-20210110211154603.png)

![image-20210110211202546](day03.assets/image-20210110211202546.png)

![image-20210110211209009](day03.assets/image-20210110211209009.png)

### 案例讲解——增删改

![image-20210110211527828](day03.assets/image-20210110211527828.png)

![image-20210110211536410](day03.assets/image-20210110211536410.png)

![image-20210110211729976](day03.assets/image-20210110211729976.png)

![image-20210110211750011](day03.assets/image-20210110211750011.png)

![image-20210110211849426](day03.assets/image-20210110211849426.png)

![image-20210110211904692](day03.assets/image-20210110211904692.png)

![image-20210110211920183](day03.assets/image-20210110211920183.png)

![image-20210110211944308](day03.assets/image-20210110211944308.png)

![image-20210110212010386](day03.assets/image-20210110212010386.png)

![image-20210110212126821](day03.assets/image-20210110212126821.png)

![image-20210110212149738](day03.assets/image-20210110212149738.png)

![image-20210110212218346](day03.assets/image-20210110212218346.png)

![image-20210110212222924](day03.assets/image-20210110212222924.png)





### DDL语言——数据定义语言

库和表的管理

#### 一、库的管理

![image-20210110220706788](day03.assets/image-20210110220706788.png)

##### 1.库的创建

![image-20210110220339605](day03.assets/image-20210110220339605.png)

![image-20210110220256836](day03.assets/image-20210110220256836.png)

~~~mysql
create database 【if not exists】 库名【 character set 字符集名】;
~~~



![image-20210110220350309](day03.assets/image-20210110220350309.png)

##### 2.库的修改

一般通过直接重命名文件夹实现库名修改（但是一般不要随意修改库名）

![image-20210110220545355](day03.assets/image-20210110220545355.png)

##### 3.库的删除

![image-20210110220628675](day03.assets/image-20210110220628675.png)

#### 二、表的管理



##### 1.表的创建

![image-20210110220907773](day03.assets/image-20210110220907773.png)

![image-20210110221138004](day03.assets/image-20210110221138004.png)

![image-20210110221227747](day03.assets/image-20210110221227747.png)

或

![image-20210110222052877](day03.assets/image-20210110222052877.png)

##### 2.表的修改

![image-20210110221815781](day03.assets/image-20210110221815781.png)

![image-20210110221435125](day03.assets/image-20210110221435125.png)

![image-20210110221523125](day03.assets/image-20210110221523125.png)

![image-20210110221602436](day03.assets/image-20210110221602436.png)

![image-20210110221627741](day03.assets/image-20210110221627741.png)

![image-20210110221844917](day03.assets/image-20210110221844917.png)

关于第三条，默认添加在最后，可以写为如下形式来指定插入的位置：

~~~mysql
alter table 表名 add column 列名 类型 【first|after 字段名】;
~~~



##### 3.表的删除

![image-20210110221933513](day03.assets/image-20210110221933513.png)

或

![image-20210110222108692](day03.assets/image-20210110222108692.png)

![image-20210110222216932](day03.assets/image-20210110222216932.png)

##### 4.表的复制

先给author表添加一些数据：

![image-20210110222413477](day03.assets/image-20210110222413477.png)

![image-20210110222512302](day03.assets/image-20210110222512302.png)

![image-20210110222709221](day03.assets/image-20210110222709221.png)

![image-20210110222833397](day03.assets/image-20210110222833397.png)

##### 案例讲解

![image-20210110223021644](day03.assets/image-20210110223021644.png)

![image-20210110223231773](day03.assets/image-20210110223231773.png)

![image-20210110223326804](day03.assets/image-20210110223326804.png)

![image-20210110223411557](day03.assets/image-20210110223411557.png)

![image-20210110223429788](day03.assets/image-20210110223429788.png)

![image-20210110223444876](day03.assets/image-20210110223444876.png)

![image-20210110223456532](day03.assets/image-20210110223456532.png)

![image-20210110223533772](day03.assets/image-20210110223533772.png)



#### 常见的数据类型

![image-20210110223944942](day03.assets/image-20210110223944942.png)

##### 一、整型

![image-20210110224459166](day03.assets/image-20210110224459166.png)

![image-20210110231716609](day03.assets/image-20210110231716609.png)

![image-20210110231120405](day03.assets/image-20210110231120405.png)

##### 二、小数

![image-20210110231856708](day03.assets/image-20210110231856708.png)

![image-20210110232211694](day03.assets/image-20210110232211694.png)

![image-20210110232400391](day03.assets/image-20210110232400391.png)

![image-20210110232439527](day03.assets/image-20210110232439527.png)



##### 选择原则

![image-20210110232540726](day03.assets/image-20210110232540726.png)



##### 三、字符型

![image-20210110232846126](day03.assets/image-20210110232846126.png)

补充：ENUM类型

![image-20210110233142104](day03.assets/image-20210110233142104.png)

注意不区分大小写

补充：SET类型

![image-20210110233334622](day03.assets/image-20210110233334622.png)

注意不区分大小写

补充：其他

![image-20210110233411318](day03.assets/image-20210110233411318.png)



![image-20210110233018512](day03.assets/image-20210110233018512.png)



##### 四、日期型

![image-20210110233850127](day03.assets/image-20210110233850127.png)

![image-20210110233928415](day03.assets/image-20210110233928415.png)



#### 常见约束

##### 含义

![image-20210111095638527](day03.assets/image-20210111095638527.png)

##### 分类：六大约束

![image-20210111100603465](day03.assets/image-20210111100603465.png)

##### 添加约束的时机

![image-20210111100704182](day03.assets/image-20210111100704182.png)

##### 约束的添加分类

![image-20210111100823015](day03.assets/image-20210111100823015.png)

![image-20210111100834239](day03.assets/image-20210111100834239.png)

##### 主键与唯一的比较：

![image-20210111103056810](day03.assets/image-20210111103056810.png)



注意，唯一允许非空的列中只允许存在唯一的null值，即如下语句执行会报错：

![image-20210111102600672](day03.assets/image-20210111102600672.png)

![image-20210111102612558](day03.assets/image-20210111102612558.png)



关于是否允许组合：

执行以下语句

![image-20210111103220463](day03.assets/image-20210111103220463.png)

查看stuinfo的结构为：

![image-20210111103243559](day03.assets/image-20210111103243559.png)

从中可以发现，表面上虽然有两个列名为主键，但实际只有一个，这可以从如下语句判断：

向表中插入数据：

![image-20210111103406696](day03.assets/image-20210111103406696.png)

发现能正确执行。

为不影响接下来的数据插入，先删除表中的数据，然后执行插入数据语句：

![image-20210111103544247](day03.assets/image-20210111103544247.png)

发现也能正确执行。

但是，执行如下语句则会报错：

![image-20210111103516951](day03.assets/image-20210111103516951.png)

所以，从这两个例子可以体会组合主键的意思。



##### 外键的说明

![image-20210111104158479](day03.assets/image-20210111104158479.png)









##### 一、创建表时添加约束

###### 1.添加列级约束

![image-20210111101529926](day03.assets/image-20210111101529926.png)





![image-20210111101226360](day03.assets/image-20210111101226360.png)

###### 2.添加表级约束

![image-20210111102035897](day03.assets/image-20210111102035897.png)

![image-20210111101835969](day03.assets/image-20210111101835969.png)

###### 通用的写法

![image-20210111102226312](day03.assets/image-20210111102226312.png)



##### 二、修改表时添加约束

![image-20210111104655879](day03.assets/image-20210111104655879.png)

###### 1.添加非空约束

![image-20210111104503032](day03.assets/image-20210111104503032.png)

![image-20210111104710939](day03.assets/image-20210111104710939.png)

##### 三、修改表时删除约束

![image-20210111104949681](day03.assets/image-20210111104949681.png)

##### 案例讲解

![image-20210111105323605](day03.assets/image-20210111105323605.png)

##### 列级约束和表级约束的对比

![image-20210111105315017](day03.assets/image-20210111105315017.png)





#### 标识列

又称为自增长列。

##### 含义

![image-20210111105438904](day03.assets/image-20210111105438904.png)

##### 特点

![image-20210111110501306](day03.assets/image-20210111110501306.png)

##### 一、创建表时设置标识列

![image-20210111105634239](day03.assets/image-20210111105634239.png)

![image-20210111105737001](day03.assets/image-20210111105737001.png)



注意可以通过语句：

![image-20210111105900648](day03.assets/image-20210111105900648.png)

查询自增长的列/列名：

![image-20210111110020393](day03.assets/image-20210111110020393.png)

然后通过语句：

![image-20210111105954724](day03.assets/image-20210111105954724.png)

将步长设置为3：

![image-20210111110035128](day03.assets/image-20210111110035128.png)



##### 二、修改表时设置标识列

![image-20210111110608865](day03.assets/image-20210111110608865.png)

##### 三、修改表时删除标识列

![image-20210111110644954](day03.assets/image-20210111110644954.png)



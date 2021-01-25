# day04

## TCL语言——事务控制语言

Transaction Control Language

### 事务

![image-20210111111301591](day04.assets/image-20210111111301591.png)

![image-20210111111708858](day04.assets/image-20210111111708858.png)

![image-20210111111739219](day04.assets/image-20210111111739219.png)

#### 存储引擎

![image-20210111111825810](day04.assets/image-20210111111825810.png)

#### ==事务的ACID属性（经典面试题）==

![image-20210111112309594](day04.assets/image-20210111112309594.png)

概括版：

![image-20210111112500720](day04.assets/image-20210111112500720.png)

#### 事务的创建

##### 隐式事务

![image-20210111112654472](day04.assets/image-20210111112654472.png)

![image-20210111112659338](day04.assets/image-20210111112659338.png)

##### 显示事务

![image-20210111112712537](day04.assets/image-20210111112712537.png)

![image-20210111112726945](day04.assets/image-20210111112726945.png)

设置自动提交功能为禁用的语句：![image-20210111112802609](day04.assets/image-20210111112802609.png)

###### 步骤：

![image-20210111113021752](day04.assets/image-20210111113021752.png)

###### 演示事务使用步骤

![image-20210111113259498](day04.assets/image-20210111113259498.png)

![image-20210111140512567](day04.assets/image-20210111140512567.png)

###### 演示savepoint的使用

![image-20210111140630476](day04.assets/image-20210111140630476.png)



#### ==事务并发问题==

![image-20210111113506841](day04.assets/image-20210111113506841.png)

![image-20210111113823330](day04.assets/image-20210111113823330.png)

#### ==数据库事务的隔离性==

数据库系统必须具有隔离并发运行各个事务的能力，使它们不会相互影响，避免各种并发问题。

![image-20210111113934154](day04.assets/image-20210111113934154.png)

<img src="day04.assets/image-20210111113949618.png" alt="image-20210111113949618" style="zoom:80%;" />

<img src="day04.assets/image-20210111114015780.png" alt="image-20210111114015780" style="zoom:80%;" />

#### 在MySQL中设置隔离级别

![image-20210111140125093](day04.assets/image-20210111140125093.png)

### 视图

#### 含义

虚拟表，和普通表一样使用

mysql5.1版本出现的特性，是通过表动态生成的数据。

<img src="day04.assets/image-20210111141020453.png" alt="image-20210111141020453" style="zoom:80%;" />

#### 应用场景

![image-20210111141125876](day04.assets/image-20210111141125876.png)

#### 示例

![image-20210111141156493](day04.assets/image-20210111141156493.png)

![image-20210111141309397](day04.assets/image-20210111141309397.png)

通过视图将其封装，以便多次使用

![image-20210111141347406](day04.assets/image-20210111141347406.png)

#### 视图的创建

![image-20210111141500317](day04.assets/image-20210111141500317.png)

#### 案例解析

![image-20210111141658938](day04.assets/image-20210111141658938.png)

![image-20210111141713671](day04.assets/image-20210111141713671.png)

![image-20210111141947444](day04.assets/image-20210111141947444.png)

![image-20210111142047044](day04.assets/image-20210111142047044.png)

![image-20210111142235060](day04.assets/image-20210111142235060.png)

#### 视图的好处

- 重用sql语句；
- 简化复杂的sql操作，不必一一知道它的查询细节；
- 保护数据，提高安全性。



#### 视图的修改

- 方式一

![image-20210111142604581](day04.assets/image-20210111142604581.png)

![image-20210111142639100](day04.assets/image-20210111142639100.png)

- 方式二

![image-20210111142701046](day04.assets/image-20210111142701046.png)

#### 视图的删除

![image-20210111142756238](day04.assets/image-20210111142756238.png)

![image-20210111142831606](day04.assets/image-20210111142831606.png)

#### 视图的查看（结构）

![image-20210111142946622](day04.assets/image-20210111142946622.png)

#### 案例讲解

![image-20210111143135533](day04.assets/image-20210111143135533.png)

![image-20210111143320725](day04.assets/image-20210111143320725.png)

![image-20210111143357102](day04.assets/image-20210111143357102.png)

#### 视图的更新

![image-20210111144026951](day04.assets/image-20210111144026951.png)

![image-20210111144035406](day04.assets/image-20210111144035406.png)

注意原始表中也会插入这行数据。

![image-20210111144202847](day04.assets/image-20210111144202847.png)

注意原始表中也会修改相应的数据。

![image-20210111144229830](day04.assets/image-20210111144229830.png)

注意原始表中也会删除相应的数据。



![image-20210111144308664](day04.assets/image-20210111144308664.png)

例如，以下语句会报错：

![image-20210111144525519](day04.assets/image-20210111144525519.png)

![image-20210111144543046](day04.assets/image-20210111144543046.png)



![image-20210111144629014](day04.assets/image-20210111144629014.png)

报错：![image-20210111144639535](day04.assets/image-20210111144639535.png)



![image-20210111144724333](day04.assets/image-20210111144724333.png)

![image-20210111144749574](day04.assets/image-20210111144749574.png)

报错：![image-20210111144809807](day04.assets/image-20210111144809807.png)



![image-20210111144939366](day04.assets/image-20210111144939366.png)

执行语句![image-20210111145058230](day04.assets/image-20210111145058230.png)

会报错![image-20210111145107293](day04.assets/image-20210111145107293.png)



![image-20210111145253222](day04.assets/image-20210111145253222.png)

执行![image-20210111145321671](day04.assets/image-20210111145321671.png)

会报错：![image-20210111145331373](day04.assets/image-20210111145331373.png)



![image-20210111145513270](day04.assets/image-20210111145513270.png)



执行![image-20210111145556823](day04.assets/image-20210111145556823.png)

会报错：![image-20210111145612593](day04.assets/image-20210111145612593.png)



#### ==视图与表的对比==

|      | 创建语法的关键字 | 是否实际占用物理空间 |             使用             |
| :--: | :--------------: | :------------------: | :--------------------------: |
| 视图 |   create view    |  只是保存了sql逻辑   | 增删改查，只是一般不能增删改 |
|  表  |   create table   |      保存了数据      |           增删改查           |

#### 测试题

![image-20210111150505544](day04.assets/image-20210111150505544.png)

![image-20210111150611560](day04.assets/image-20210111150611560.png)

![image-20210111150642079](day04.assets/image-20210111150642079.png)

![image-20210111150707480](day04.assets/image-20210111150707480.png)

![image-20210111150714518](day04.assets/image-20210111150714518.png)





### 变量

![image-20210111151245000](day04.assets/image-20210111151245000.png)

#### 系统变量

##### 说明

![image-20210111151436768](day04.assets/image-20210111151436768.png)

##### 使用的语法

![image-20210111151744814](day04.assets/image-20210111151744814.png)

##### 操作演示

![image-20210111152224959](day04.assets/image-20210111152224959.png)



![image-20210111152856072](day04.assets/image-20210111152856072.png)

![image-20210111152805814](day04.assets/image-20210111152805814.png)

![image-20210111152833383](day04.assets/image-20210111152833383.png)

#### 自定义变量

##### 说明

![image-20210111154955687](day04.assets/image-20210111154955687.png)

##### 使用步骤

![image-20210111155043280](day04.assets/image-20210111155043280.png)

![image-20210111155718712](day04.assets/image-20210111155718712.png)

![image-20210111155413303](day04.assets/image-20210111155413303.png)

![image-20210111155536240](day04.assets/image-20210111155536240.png)

![image-20210111155632527](day04.assets/image-20210111155632527.png)

![image-20210111160009641](day04.assets/image-20210111160009641.png)

![image-20210111160020201](day04.assets/image-20210111160020201.png)

##### 用户变量与局部变量的比较

![image-20210111160139376](day04.assets/image-20210111160139376.png)

![image-20210111160345448](day04.assets/image-20210111160345448.png)



## 存储过程和函数

类似于java中的方法

好处：

![image-20210111160726992](day04.assets/image-20210111160726992.png)

### 存储过程

#### 含义

![image-20210111160618537](day04.assets/image-20210111160618537.png)

#### 语法

##### 一、创建语法

![image-20210111161042065](day04.assets/image-20210111161042065.png)



**注意事项**：

![image-20210111161311177](day04.assets/image-20210111161311177.png)

![image-20210111161510927](day04.assets/image-20210111161510927.png)

##### 二、调用语法

![image-20210111161547856](day04.assets/image-20210111161547856.png)



##### 案例解析

![image-20210111161718192](day04.assets/image-20210111161718192.png)

![image-20210111161839753](day04.assets/image-20210111161839753.png)

![image-20210111161918873](day04.assets/image-20210111161918873.png)





![image-20210111162212780](day04.assets/image-20210111162212780.png)

![image-20210111162427888](day04.assets/image-20210111162427888.png)



![image-20210111162945898](day04.assets/image-20210111162945898.png)



![image-20210111163355397](day04.assets/image-20210111163355397.png)

![image-20210111163423978](day04.assets/image-20210111163423978.png)

![image-20210111163635193](day04.assets/image-20210111163635193.png)

![image-20210111165216826](day04.assets/image-20210111165216826.png)

![image-20210111165531585](day04.assets/image-20210111165531585.png)



#### 案例讲解

![image-20210111165744387](day04.assets/image-20210111165744387.png)

![image-20210111165919018](day04.assets/image-20210111165919018.png)

![image-20210111170200378](day04.assets/image-20210111170200378.png)

#### 二、删除存储过程

##### 语法

![image-20210111170322520](day04.assets/image-20210111170322520.png)

![image-20210111170357409](day04.assets/image-20210111170357409.png)

#### 三、查看存储过程的信息

![image-20210111170529995](day04.assets/image-20210111170529995.png)

#### 案例讲解（接上一个）

![image-20210111170803106](day04.assets/image-20210111170803106.png)

![image-20210111171055474](day04.assets/image-20210111171055474.png)

![image-20210111171400219](day04.assets/image-20210111171400219.png)





### 函数

#### 含义

![image-20210111160618537](day04.assets/image-20210111160618537.png)

好处：

![image-20210111160726992](day04.assets/image-20210111160726992.png)

#### 与存储过程的区别

![image-20210111172443163](day04.assets/image-20210111172443163.png)

#### 语法

##### 一、创建语法

![image-20210111172631026](day04.assets/image-20210111172631026.png)

**注意**

![image-20210111172823291](day04.assets/image-20210111172823291.png)

##### 二、调用语法

![image-20210111172940817](day04.assets/image-20210111172940817.png)

##### 案例演示

![image-20210111190639742](day04.assets/image-20210111190639742.png)

![image-20210111190945950](day04.assets/image-20210111190945950.png)

![image-20210111191303973](day04.assets/image-20210111191303973.png)



##### 三、查看函数

![image-20210111191442605](day04.assets/image-20210111191442605.png)

##### 四、删除函数

![image-20210111191500797](day04.assets/image-20210111191500797.png)



##### 案例

![image-20210111191639559](day04.assets/image-20210111191639559.png)





### 流程控制结构

![image-20210111191849205](day04.assets/image-20210111191849205.png)

#### 一、分支结构

##### 1.if函数

![image-20210111192052645](day04.assets/image-20210111192052645.png)

##### 2.case结构

![image-20210111192427037](day04.assets/image-20210111192427037.png)

![image-20210111192800638](day04.assets/image-20210111192800638.png)

![image-20210111193050855](day04.assets/image-20210111193050855.png)

##### 3.if结构

![image-20210111193228629](day04.assets/image-20210111193228629.png)



![image-20210111193452726](day04.assets/image-20210111193452726.png)



#### 二、循环结构

##### 分类

while、loop、repeat

##### 循环控制

![image-20210111193658542](day04.assets/image-20210111193658542.png)

##### 1.while

**语法**：

![image-20210111193823709](day04.assets/image-20210111193823709.png)

##### 2.loop

![image-20210111193910037](day04.assets/image-20210111193910037.png)



##### 3.repeat

![image-20210111194000342](day04.assets/image-20210111194000342.png)





##### 案例

![image-20210111194624413](day04.assets/image-20210111194624413.png)

![image-20210111194903832](day04.assets/image-20210111194903832.png)

![image-20210111195333298](day04.assets/image-20210111195333298.png)



##### 总结

![image-20210111200441193](day04.assets/image-20210111200441193.png)



#### 经典案例

![image-20210111201751372](day04.assets/image-20210111201751372.png)

![image-20210111202534328](day04.assets/image-20210111202534328.png)





# 实验3：图书管理系统领域对象建模
|学号|班级|姓名|
|:-------:|:-------------: | :----------:|
|201710414324|软件(本)17-3|余涛
## 1. 图书管理系统的类图

### 1.1 类图PlantUML源码如下：

```class
@startuml
title  图书管理系统类图
读者 "1" -- "*" 预定记录
读者 -- 借书记录
读者 : 姓名
读者 : 身份证号
读者 : 借书卡号
读者 : 已借图书数
预定记录 "*" -- "1" 现有图书资源 : 被预定
预定记录 : 预定日期
借书记录 "*" -- "1" 图书管理员 :登记
借书记录 "1" -- "0..1" 逾期记录
借书记录 "0..1" -- "1" 资源项
借书记录 : 归还日期
借书记录 : 借书日期
图书管理员 : 职工号
图书管理员 : 姓名
逾期记录 : 逾期天数
逾期记录 "*" -- "0..1" 罚款细则 : 使用
资源项 "*" --* "1" 现有图书资源
资源项 : 馆藏流水号
资源项 : 状态
现有图书资源 "1..*" -- "1" 馆藏目录
现有图书资源 <-- 图书品种
现有图书资源 : 资源名称
现有图书资源 : 国际出版号
现有图书资源 : 价格
现有图书资源 : 简介
现有图书资源 : 馆藏数量
现有图书资源 : 可借数量

图书品种 : 作者
图书品种 : 出版社
图书品种 : 出版日期
@enduml
```

### 1.2. 类图如下：


![在这里插入图片描述](https://img-blog.csdnimg.cn/2020050610384252.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3l1dGFvOTk2,size_16,color_FFFFFF,t_70)

### 1.3. 类图说明：
该系统共有读者丶预定记录丶借书记录丶图书管理员丶现有图书资源丶图书品种等主要的类，其中类的关系和多重性如图所示。

## 2. 图书管理系统的对象图
### 2.1 类读者的对象图
#### 源码如下：
```class
@startuml
object 读者 {
姓名=鸽子
身份证号=123
借书卡号=123
借书限额=12
可用限额=8
}
@enduml
```
#### 对象图如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200506103902845.PNG)

### 2.2 类图书品种的对象图
#### 源码如下：
```class
@startuml
object 图书品种 {
书名=《系统分析》
作者= 余涛
出版社 = 三班
出版日期 = 2020 
}
@enduml
```
#### 对象图如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200506104930987.png)



### 2.3 类图书管理员的对象图
#### 源码如下：
```class
@startuml
object 图书管理员 {
职工号=666
姓名=鳄鱼倒立
}
@enduml
```
#### 对象图如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200506104027322.PNG)


### 2.4 类现有图书资源的对象图
#### 源码如下：
```class
@startuml
object 现有图书资源 {
借书日期=2011-12-3
应还日期=2011-1-20
归还日期=2012-1-1
}
@enduml
```
#### 对象图如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200506104042341.PNG)


### 2.5 类借书记录的对象图
#### 源码如下：
```class
@startuml
object 现有图书资源 {
资源名称=sfdf
国际出版号=123451
价格=26
简介=dfsfdsfds
馆藏数量=5
可借数量=3
}
@enduml
```
#### 对象图如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200506104054733.PNG)

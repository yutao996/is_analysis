# 实验4：图书管理系统顺序图绘制
|学号|班级|姓名|
|:-------:|:-------------: | :----------:|
|201710414324|软件(本)17-3|余涛|

## 图书管理系统的顺序图

## 1. 借书用例
## 1.1. 借书用例PlantUML源码

```mermaid
sequenceDiagram
@startuml
actor 图书管理员
图书管理员 ->>读者:验证读者
图书管理员 ->>读者:取读者限额
loop
图书管理员 ->>资源项:获取资源项
资源项 ->>馆藏资源品种:查找图书资源
图书管理员 ->>借书记录:创建借书记录
图书管理员 ->>资源项:借出资源
资源项 ->> 馆藏资源品种:减少可借数量
end
图书管理员 ->> 借书记录:打印借书清单
@enduml
```

## 1.2. 借书用例顺序图
![](https://img-blog.csdnimg.cn/20200506105928138.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3l1dGFvOTk2,size_16,color_FFFFFF,t_70)



***

## 2. 还书用例
## 2.1. 还书用例PlantUML源码

```mermaid
sequenceDiagram
@startuml
actor 图书管理员
图书管理员 ->>资源项:读取资源信息
资源项 ->> 借书记录:取借书记录
资源项 ->>馆藏资源品种:取资源的品种
图书管理员 ->>读者:取借阅者信息
图书管理员 ->>资源项:归还资源
资源项 ->>馆藏资源品种:增加可借数量
图书管理员 ->>借书记录:登记归还日期
opt 逾期
图书管理员 ->>逾期记录:登记逾期日期
end
@enduml
```

## 2.2. 还书用例顺序图
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200506105946863.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3l1dGFvOTk2,size_16,color_FFFFFF,t_70)



***

## 3. 维护图书
## 3.1. 维护图书PlantUML源码

```mermaid
sequenceDiagram
@startuml
actor 图书管理员
loop
图书管理员 ->>资源项:读取资源信息
资源项 ->>馆藏资源品种:维护资源
end
@enduml
```

## 3.2. 维护图书顺序图
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200506110000370.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3l1dGFvOTk2,size_16,color_FFFFFF,t_70)



## 4. 查询图书
## 4.1. 查询图书PlantUML源码

```mermaid
sequenceDiagram
@startuml 查询书目
actor 读者
loop
读者 ->>资源项:获取资源项
资源项 ->>馆藏资源品种:查找图书资源
馆藏资源品种 ->>读者:返回图书信息
end
@enduml
```

## 4.2. 查询图书顺序图
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200506110011266.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3l1dGFvOTk2,size_16,color_FFFFFF,t_70)


***

## 5. 预定图书
## 5.1. 预定图书PlantUML源码

```mermaid
sequenceDiagram
@startuml 预定图书
actor 读者
loop
读者 ->>资源项:获取资源项
资源项 ->>馆藏资源品种:查找图书资源
馆藏资源品种 ->>读者:返回图书信息
读者 ->>图书 : 预定
图书 ->>预定记录:数目增加
end
@enduml
```

## 5.2. 预定图书顺序图
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200506110022334.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3l1dGFvOTk2,size_16,color_FFFFFF,t_70)


***

## 6. 取消预定图书
## 6.1. 取消预定图书PlantUML源码

```mermaid
sequenceDiagram
@startuml 取消预定
actor 读者
loop
读者 ->>资源项:获取资源项
资源项 ->>馆藏资源品种:查找图书资源
馆藏资源品种 ->>读者:返回图书信息
读者 ->>图书 : 取消预定
图书 ->>预定记录:数目减少
end
@enduml
```

## 6.2. 取消预定图书顺序图
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200506110033116.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3l1dGFvOTk2,size_16,color_FFFFFF,t_70)


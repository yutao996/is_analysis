
# 实验5：图书管理系统数据库设计与界面设计
|学号|班级|姓名|
|:-------:|:-------------: | :----------:|
|201710414324|软件(本)17-3|余涛|

## 1.数据库表设计

## 1.1. 图书表
|字段|类型|主键，外键|可以为空|默认值|约束|说明|
|:-------:|:-------------:|:------:|:----:|:---:|:----:|:-----|
|ISBN|varchar2(100)|主键|否||||
|Name|varchar2(100)| |否|||书名|
|Writer|varchar2(100)| |否|||作者|
|Pub|varchar2(100)| |否|||出版社|
|Pub_time|varchar2(100)| |否|||出版日期|

## 1.2. 馆藏资源品种表
|字段|类型|主键，外键|可以为空|默认值|约束|说明|
|:-------:|:-------------:|:------:|:----:|:---:|:----:|:-----|
|ISBN|varchar2(100)|主键|否||||
|Name|varchar2(100)|外键 |否|||书名|
|Price|float(3,1)| |否|||价格|
|Intro|varchar2(100)| |是|||简介|
|Collect_Num|int(3)| |否|||馆藏数量|
|Borrow_Num|int(3)| |否||值在0-馆藏数量之间|可借数量|

## 1.3. 预定记录表
|字段|类型|主键，外键|可以为空|默认值|约束|说明|
|:-------:|:-------------:|:------:|:----:|:---:|:----:|:-----|
|Name|varchar2(100)|主键|否||||
|ISBN|varchar2(100)|外键|否||||
|Pre_time|datetime()| |否|||预定日期|

## 1.4. 资源项表
|字段|类型|主键，外键|可以为空|默认值|约束|说明|
|:-------:|:-------------:|:------:|:----:|:---:|:----:|:-----|
|Name|varchar2(100)|主键|否|||书名|
|Collect_Num_status|varchar2(20)| |否|||馆藏流水号状态|

## 1.5. 逾期记录表
|字段|类型|主键，外键|可以为空|默认值|约束|说明|
|:-------:|:-------------:|:------:|:----:|:---:|:----:|:-----|
|Name|varchar2(100)|主键|否||||
|Over_time|datetime(20)| |否|||逾期天数|

## 1.6. 图书管理员表
|字段|类型|主键，外键|可以为空|默认值|约束|说明|
|:-------:|:-------------:|:------:|:----:|:---:|:----:|:-----|
|Emp_id|int(12)|主键|否||||
|Name|varchar2(100)| |否||||

## 1.7. 借书记录表
|字段|类型|主键，外键|可以为空|默认值|约束|说明|
|:-------:|:-------------:|:------:|:----:|:---:|:----:|:-----|
|ISBN|varchar2(100)|主键|否|||借书号|
|Return_time|datetime()| |否|||归还日期|
|Borrow_time|datetime()| |否|||借书日期|

## 1.8. 读者表
|字段|类型|主键，外键|可以为空|默认值|约束|说明|
|:-------:|:-------------:|:------:|:----:|:---:|:----:|:-----|
|Borrow_id|int(12)|主键|否||||
|id|int(17)| |否| ||身份证号|
|Name|varchar2(100)| |否||||
|ISBN|varchar2(100)|外键|否|||借书号|
|Return_num|int(1)| |否||小于10|已借图书数|

***

## 2. 界面设计
## 2.1. 借书界面设计
[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-jlCxqQzZ-1590458949545)(pic1.png)]
- 用例图参见：用户登录
- 类图参见：用户类，管理员类
- 顺序图参见：用户登录顺序图
- API接口如下：

1. 账户API

- 功能：用于用户账户的登录
- 请求地址： https://zhaobinglin.github.io/is_analysis_pages/page1.html
- 请求方法：POST
- 请求参数：

|参数名称|必填|说明|
|:-------:|:-------------: | :----------:|
|<username>|是|用户名或邮箱或手机号码 |
|<password>|是|密码|
|<access_token>|是|用于验证请求合法性的认证信息|
|<method>|是|固定为"POST"|
|<password>|是|密码|

- 返回实例：
```
{
    "info": "欢迎登录。",
    "data": {
        "username": "admin",
        "uid": "14361",
        "role_id": "1",
        "audit":"1",
    },
    "code": 200,
    "data_1":{...}
}
```
- 返回参数说明：
    
|参数名称|说明|
|:-------:|:-------------: |
|Info|返回的提示信息|
|data|用户的个人信息|
|code|返回码|
|data_1|登录用户的信息|

2. 用户API
- 功能：获取用户信息
- 请求地址： https://zhaobinglin.github.io/is_analysis_pages/index.html
- 请求方法：GET
- 请求参数：

|参数名称|必填|说明|
|:-------:|:-------------: | :----------:|
|id|是|用户的uid|
|access_roken|是|用于验证请求合法性的认证信息|
|method|是|固定为 “GET”。|

- 返回实例：
```
{
    "info": "返回成功",
    "data": {
        "nickname": "O记_Mega可达鸭",
        "uid": "14361",
        "sex": "0",
        "birthday": "0000-00-00",
        "status": "1",
        
    },
    "code": 200
}
```
- 返回参数说明：
    
|参数名称|说明|
|:-------:|:-------------: |
|Info|返回信息|
|data|用户的个人信息|
|dodo|返回码|

<!-- markdownlint-disable MD033-->
<!-- 禁止MD033类型的警告 https://www.npmjs.com/package/markdownlint -->

# 基于GitHub的实验管理平台的分析与设计

### 成都大学信息科学与工程学院

<table>
    <tr>
        <td>学号</td>
        <td>班级</td>
        <td>姓名</td>
        <td>照片</td>
    </tr>
    <tr>
        <td>201710414324</td>
        <td>三班</td>
        <td>余涛</td>
        <td></td>
    </tr>
</table>

## 1. 概述
<ul>
    <li>基于GitHub的实验管理平台的作用是在线管理实验成绩的Web应用系统，学生和教师的实验内容均存放在GitHUB 页面上；</li>
    <li>
        用户的功能主要有五点：
        <ol>
            <li>登录；</li>
            <li>登出；</li>
            <li>修改自己的密码；</li>
        </ol>
    </li>
    <li>
        学生的功能主要有两点：
        <ol>
            <li>设置用户名；</li>
            <li>查询自己的成绩；</li>
        </ol>
    </li>
    <li>
        教师的功能主要有两点：
        <ol>
            <li>批改每个学生的实验成绩；</li>
            <li>查看每个学生的成绩；</li>
        </ol>
    </li>
    <li>老师和学生都能通过本系统的链接方便地跳转到学生的每个GitHUB实验目录，以便批改实验或者查看实验情况。</li>
    <li>实验成绩按数字分数计算，每项实验的满分为100分，最低为0分。</li>
    <li>系统自动计算每个学生的所有实验的平均分。</li>
    <li>系统自动计算每个学生的所有课程的平均分。</li>
</ul>
    

## 2. 系统总体结构

界面设计参见：https://yutao996.github.io/is_analysis/test6/ui/index.html
    
## 3. 用例图设计 [源码](src/UseCase.puml)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200526213541665.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3l1dGFvOTk2,size_16,color_FFFFFF,t_70)
## 4. 类图设计 [源码](src/class.puml)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200526215330284.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3l1dGFvOTk2,size_16,color_FFFFFF,t_70)

## 5. 数据库设计
- ### [参见数据库设计](./数据库设计.md)

## 6. 用例及界面详细设计
- ### [“学生列表”用例](./用例/学生列表.md),[界面](https://yutao996.github.io/is_analysis/test6/ui/index.html)
- ### [“评定成绩”用例](./用例/评定成绩.md),[界面](https://yutao996.github.io/is_analysis/test6/ui/评定成绩.html)
- ### [“查看成绩”用例](./用例/查看成绩.md),[界面](https://yutao996.github.io/is_analysis/test6/ui/查看成绩.html)
- ### [“修改密码”用例](./用例/修改密码.md),[界面](https://yutao996.github.io/is_analysis/test6/ui/顶部菜单.html)
- ### [“修改用户信息”用例](./用例/修改用户信息.md),[界面](https://yutao996.github.io/is_analysis/test6/ui/顶部菜单.html)
- ### [“查看用户信息”用例](./用例/查看用户信息.md),[界面](https://yutao996.github.io/is_analysis/test6/ui/顶部菜单.html)
- ### [“登出”用例](./用例/登出.md),[界面](https://yutao996.github.io/is_analysis/test6/ui/顶部菜单.html)
- ### [“登录”用例](./用例/登录.md),[界面](https://yutao996.github.io/is_analysis/test6/ui/登录.html)
    

# 实验一：业务流程建模
学号     |班级     | 姓名     |
-------- | ----- | ----- 
201710414324 |三班 | 余涛
## 流程图1：考试及成绩管理流程
### PlantUML源码如下：
<pre>
@startuml
|教务处|
start
    :安排考试;
    :考试安排表<
|教师|
    :出卷;
    fork
    :A、B试卷<
    fork again
    :打印审批表<
    |系主任|
    :审批签字;
    :打印审批表<
    end fork
   |教务处|
    :打印试卷;
    :试卷<
    |学生|
    :参加考试;
    :答卷<
    |教师|
    :阅卷出成绩;
    fork
    :成绩单<
    |教务处|
    if(有不及格？) then (yes)
        :安排补考;
        fork
        :补考安排表<
        end
        fork again

        end fork
    endif
    |教师|
    fork again
    :答卷<
    :装订存档;
    end fork  
stop
@enduml
</pre>

### 业务流程图如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200316111907952.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3l1dGFvOTk2,size_16,color_FFFFFF,t_70)
### 流程说明
* 采用泳道实现该业务流程图。用泳道的|角色|将四个角色所进行活动和拥有资料区分开。
* 使用圆边矩形表示活动。
* 使用if语句进行选择，fork语句进行并行。
## 流程图2： 客户维修服务流程
### PlantUML源码如下：
<pre>
@startuml
|客户|
    start
    title 客户维修服务流程
    :申请服务;

|业务经理|
    if (是新客户吗?) then (yes)
        :登记客户信息;
    else (no)
    endif 
    :上门勘察;
    :制定方案;

|客户|
    if (满意吗?) then  (yes)
    :签订服务合同;
    |业务经理|
        fork
	    :安排工人;
        fork again
	    :安排材料;
        end fork
        :派写工单;
        |工人|
        :领取材料;
        :上门服务;
        |客户|
        :验收并填写反馈意见;
        |业务经理|
        :交回派工单;
        |财务人员|
        :结算收款;
        stop
    else (不满意)
        |客户|
        end
    endif
@enduml
</pre>
### 业务流程图如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200316112142478.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3l1dGFvOTk2,size_16,color_FFFFFF,t_70)
### 流程说明
* 采用泳道实现该业务流程图。用泳道的|角色|将客户，业务经理，财务，维修人员四个角色所进行活动和拥有资料区分开。
* 使用圆边矩形表示活动。
* 使用if语句进行选择，fork语句进行并行。

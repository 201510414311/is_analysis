<<<<<<< HEAD
# is_analysis
信息系统分析与设计
=======
<<<<<<< HEAD
# is_analysis
信息系统分析与设计
=======
﻿#实验一：业务流程建模
学号  | 班级 | 姓名  
:-:|:-:|:-:
    201510414311    |     软工三班      |   彭启瑞
###流程图1：考试及成绩管理流程
####PlantUMl源代码如下：

```
@startuml
|教务处|
start
:安排考试;
:考试安排表<
|#AntiqueWhite|教师|
:出卷;
split
:A,B试卷;
split again
:打印审批表<
|系主任|
:审批签字;
:打印审批表<
end split
|教务处|
:打印试卷;
:试卷<
|#AntiqueWhite|学生|
:参加考试;
:答卷;
|教师|
:阅卷出成绩;
split
:答卷<
:装订成档;
split again
:成绩单<
|教务处|
if (有不及格？) then (有)
  :安排补考;
:补考安排表<
endif
end split
|教师|

:期末流程结束;
stop
@enduml
```
####业务流程图如下：
![](./1.png '描述')
####流程说明：
从教务处安排考试，形成考试安排表。然后教师出卷，形成a,b两套试卷并打印审批表，审批表交由系主任签字，然后再打印审批表，此时教务处再打印试卷，发放试卷。学生参加考试，答卷。然后阅卷出成绩，形成成绩单和答卷。如果成绩单有不及格的，安排补考，形成补考安排表。答卷装订成册，最后期末流程结束。

###流程图2：客户维修服务流程
####PlantUMl源代码如下

```
@startuml
|客户|
start
:申请服务;

|#AntiqueWhite|业务经理|
if (是新客户吗？) then (是)
  :登记客户信息;
else(不是)
endif
:上门勘察;
:制定方案;

|客户|
if (满意吗) then (否)
stop
else (是)
:签订服务合同;

|业务经理|
fork
:安排工人;
fork again
:安排材料;
endfork
:填写派工单;

|工人|
:领取材料;
:上门服务;

|客户|
:验收并填写反馈意见;

|业务经理|
:交回派工单;

|#AntiqueWhite|账务人员|
:结算收款;
stop
@enduml
```
####业务流程图如下：
![](./2.png '描述')
####流程说明：

首先由客户申请服务，业务经理判断其是否为新客户，如果是，先登记客户信息，不是，直接上门勘察。然后制定方案，询问客户是否满意，否的话，就结束业务，是的话，和客户签订服务合同。然后业务经理安排工人和材料，填写派工单。然后工人领取材料，进行上门服务。客户验收并填写反馈意见，在业务经理这交回派工单，最后财务人员结算收款。



>>>>>>> 提交文件
>>>>>>> 提交文件
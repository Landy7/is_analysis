# flow1:Page107图6.1---考试及成绩管理流程:
### 1.UML语句:
```
@startuml
title 期末考试流程
|教务处|
start
:安排考试;
:考试安排表]
|教师|
:出卷;
note left
用fork并行代替箭头
end note
fork
: A,B试卷]
fork again
:打印审批表]
|系主任|
:审批签字;
:打印审批表]
endfork
|教务处|
:打印试卷;
:试卷]
|学生|
:参加考试;
:答卷]
|教师|
:阅卷出成绩;
fork
|教务处|
:成绩单]
if( 有不及格？) then( 有 )
:安排补考;
split
:补考安排表]
detach
split again
end split
endif
fork again
|教师|
:答卷]
:装订存档;
fork end
:期末流程;
stop
@enduml
```
### 2.说明：
教务处安排考试，发出考试安排表给教师，教师进行出卷，打印A，B试卷和审批表（这一部分使用fork并行来代替split）
审批表交给系主任签字，再次打印审批表，然后教务处打印试卷，试卷发放给学生进行考试，学生答完后由教师阅卷出成绩(用并行语句实现)成绩单交给教务处，若有不合格学生则安排补考(这一部分由split语句完成)发放补考安排表，合格的学生直接装订存档，结束期末流程。
### 3.显示结果：
![image](https://github.com/Landy7/is_analysis/blob/master/test1/flow1.jpg)
# flow2:Page108图6.2---客户维修服务流程:
### 1.UML语句:
```
@startuml
|客户|
start
:申请服务;
|业务经理|
if(是新客户吗？)then(是)
note left
if条件语句
end note
:登记客户信息;
else(不是)
endif
:上门勘察;
:制定方案;
|客户|
if(满意吗？)then(是)
else
end
endif
:签订服务合同;
|业务经理|
fork
:安排工人;
fork again 
:安排材料;
fork end
:填写派工单;
|工人|
:领取材料;
:上门服务;
|客户|
:验收并填写反馈意见;
|业务经理|
:交给派工单;
|财务人员|
:结算收款;
stop
```
### 2.说明：
客户申请维修服务，然后业务经理查看是否是新客户(用if语句编写)，是新客户则登记客户信息，进行上门勘察，制定方针，若客户满意则签订服务合同，然后业务经理安排工人和材料并填写派工单(使用fork)，工人领取材料然后上门服务，客户进行验收和提交反馈意见，并交给业务经理，最后业务经理把派工单交给财务人员，流程结束
### 3.显示结果
![image](https://github.com/Landy7/is_analysis/blob/master/test1/flow2.jpg)


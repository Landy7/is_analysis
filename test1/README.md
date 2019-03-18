# flow1:Page107图6.1---考试及成绩管理流程:
## 1.UML语句:
```
@startuml
title 期末考试流程
|教务处|
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
:成绩单;
|教务处|
if(有不及格？)then(有)
else
  end
endif
:安排补考;
note right
用split来并行
end note
split
:补考安排表]
detach
split again
split end
fork again
|教师|
:答卷]
:装订存档;
fork end
:期末流程;
stop
@enduml
```
### 说明：
教务处安排考试，发出考试安排表给教师，教师进行出卷，打印A，B试卷和审批表（这一部分使用fork并行来代替split）
审批表交给系主任签字，再次打印审批表，然后教务处打印试卷，试卷发放给学生进行考试，学生答完

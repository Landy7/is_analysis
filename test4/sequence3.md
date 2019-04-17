@startuml
title
 借出图书
 <u>说明：图中的“/”均表示“或者”</u>
end title
skinparam sequenceArrowThickness 2
skinparam maxmessagesize 60
skinparam sequenceParticipant underline
actor "图书管理员/超级管理员" as U
boundary "借书办理窗口   " as A
database "数据库" as B
collections "借书记录" as C
-> U:查阅将借阅的读书内容
activate U
activate A
U ->U:检查图书是否满足借阅条件
U ->A:输入读者信息
A ->B:查询读者信息
activate B
B -->A:返回读者信息
U ->A:确认借书
A ->B:修改图书库存
B ->C:生成借书记录
activate C
C -->B:增加借阅信息
B -->A:返回操作结果
A -->U:返回借出结果

@enduml
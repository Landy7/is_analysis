@startuml
title
 维护图书管理员信息
 <u>说明：图中的“/”均表示“或者”</u>
end title
skinparam sequenceArrowThickness 2
skinparam maxmessagesize 60
skinparam sequenceParticipant underline
actor "超级管理员" as U
boundary "图书管理员信息管理窗口" as A
database "数据库" as B
activate U
U ->A:输入要查询/添加/修改/删除的图书管理员信息
activate A
A ->B:查询/添加/修改/删除相应图书管理员
activate B
B -->A:返回相应操作结果
A -->U:返回相应操作结果
@enduml
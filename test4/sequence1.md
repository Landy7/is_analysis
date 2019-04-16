@startuml
title
 图书查询
 <u>说明：图中的“/”均表示“或者”</u>
end title
skinparam sequenceArrowThickness 2
skinparam maxmessagesize 60
skinparam sequenceParticipant underline
actor "游客/读者/图书管理员/超级管理员" as U
boundary "查询图书窗口" as A
database "数据库" as B
activate U
U ->A:输入图书信息
activate A
A ->B:获取对应图书信息
deactivate A
activate B
B ->U:返回图书信息
deactivate B
@enduml
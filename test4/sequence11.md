@startuml
title
 查询借阅情况
 <u>说明：图中的“/”均表示“或者”</u>
end title
skinparam sequenceArrowThickness 2
skinparam maxmessagesize 60
skinparam sequenceParticipant underline
actor "读者" as U
boundary "查询借阅窗口   " as A
database "数据库" as B
collections "借书记录" as C
activate U
activate A
U ->A:查询借阅信息
A ->B:查询借书记录
activate B
B ->C:获取借书记录
activate C
C -->B:返回操作结果
B -->A:返回查询结果
A -->U:返回借阅信息

@enduml
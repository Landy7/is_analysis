@startuml
title
 预定图书
 <u>说明：图中的“/”均表示“或者”</u>
end title
skinparam sequenceArrowThickness 2
skinparam maxmessagesize 60
skinparam sequenceParticipant underline
actor "读者" as U
boundary "预定图书办理窗口   " as A
collections "预定记录" as B
database "数据库" as C
activate U
activate A
U ->A:输入图书信息
A ->C:查询该图书信息
activate C
C -->A:返回图书信息
U ->A:确认预定
A ->B:添加预定记录
activate B
B ->C:添加对应预定记录
C -->B:返回操作结果
B -->A:返回操作结果
A -->U:返回预定结果

@enduml
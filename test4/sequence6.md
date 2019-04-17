@startuml
title
 取消预定
 <u>说明：图中的“/”均表示“或者”</u>
end title
skinparam sequenceArrowThickness 2
skinparam maxmessagesize 60
skinparam sequenceParticipant underline
actor "读者" as U
boundary "取消预定办理窗口   " as A
collections "预定记录" as B
database "数据库" as C
activate U
activate A
U ->A:查询预定图书信息
A ->B:查询预定记录
activate B
B -->A:返回预定记录
activate C
U ->A:确认取消预定
A ->B:删除对应书籍预定记录
B ->C:删除对应预定记录
C -->B:返回操作结果
B -->A:返回操作结果
deactivate B
A ->C:修改库存
C -->A:返回操作结果
A -->U:返回取消预定结果

@enduml
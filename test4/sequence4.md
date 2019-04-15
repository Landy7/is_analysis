@startuml
title
 归还图书
 <u>说明：图中的“/”均表示“或者”</u>
end title
skinparam sequenceArrowThickness 2
skinparam maxmessagesize 60
skinparam sequenceParticipant underline
actor "图书管理员/超级管理员" as U
boundary "还书办理窗口   " as A
collections "借书记录" as B
database "数据库" as C
-> U:检查书籍完整性
activate U
<-- U:登记赔偿
activate A
U ->A:输入读者信息
A ->B:查询借书记录
activate B
B -->A:返回借书记录
U ->U:查找对应借书记录，检查是否逾期
U ->A:确认还书
deactivate B
A ->C:修改图书库存
activate C
C -->A:返回操作结果
A ->B:修改借书记录
activate B
B ->C:删除对应借书记录
C -->B:返回操作结果
B -->A:返回操作结果
A -->U:返回归还结果

@enduml
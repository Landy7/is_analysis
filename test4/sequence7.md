@startuml
title
 登记赔偿
 <u>说明：图中的“/”均表示“或者”</u>
end title
skinparam sequenceArrowThickness 2
skinparam maxmessagesize 60
skinparam sequenceParticipant underline
actor "图书管理员/超级管理员" as U
boundary "登记赔偿窗口   " as A
collections "罚款细则" as B
activate U
activate A
-> U:登记赔偿信息
U ->A:输入决策处理方法
A ->B:生成罚款细则
activate B
B -->A:返回操作结果
A -->U:返回赔偿结果
<-- U:归还图书
@enduml
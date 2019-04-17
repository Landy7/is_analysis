@startuml
title
 登记赔偿
 <u>说明：图中的“/”均表示“或者”</u>
end title
skinparam sequenceArrowThickness 2
skinparam maxmessagesize 60
skinparam sequenceParticipant underline
actor "图书管理员/超级管理员" as U
participant "罚款细则" as A
activate U
activate A
-> U:登记赔偿信息
U ->U:决策处理方法
U ->A:生成罚款细则
A -->U:返回赔偿结果
<-- U:归还图书
@enduml
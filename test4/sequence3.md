@startuml
title
 借出图书
 <u>说明：图中的“/”均表示“或者”</u>
end title
skinparam sequenceArrowThickness 2
skinparam maxmessagesize 60
skinparam sequenceParticipant underline
actor "图书管理员/超级管理员" as U
participant "读者" as A
participant "资源项" as B
participant "馆藏资源品种" as C
participant "借书记录" as D
U ->A:验证读者
activate A
U ->B:获取资源项
deactivate A
activate B
B ->C:查找资源品种
activate C
deactivate B
A ->D:创建借书记录
deactivate C
activate D
U ->B:借出资源
activate B
activate C
B ->C:减少库存数量

@enduml
@startuml
title
 维护书目
 <u>说明：图中的“/”均表示“或者”</u>
end title
skinparam sequenceArrowThickness 2
skinparam maxmessagesize 60
skinparam sequenceParticipant underline
actor "图书管理员/超级管理员" as U
participant "馆藏资源品种" as A
participant "图书" as B
U ->A:输入所要查询/添加/修改/删除的书目信息
activate A
A ->A:查询/添加/修改/删除书目
A -->U:提示“查询/添加/修改/删除成功”
deactivate A
U ->B:对应查询/添加/修改/删除图书
activate B
B -->U:提示“查询/添加/修改/删除成功”
deactivate B
@enduml
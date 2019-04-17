@startuml
title
 维护读者信息
 <u>说明：图中的“/”均表示“或者”</u>
end title

skinparam sequenceArrowThickness 2
skinparam maxmessagesize 60
skinparam sequenceParticipant underline

actor "图书管理员/超级管理员" as U
participant "读者" as A

activate U


U ->A:输入所要查询/添加/修改/删除的读者信息
activate A

A ->A:查询/添加/修改/删除读者


A -->U:提示“查询/添加/修改/删除成功”
deactivate A
@enduml
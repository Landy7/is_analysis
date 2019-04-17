@startuml
title
 维护图书管理员信息
 <u>说明：图中的“/”均表示“或者”</u>
end title

skinparam sequenceArrowThickness 2
skinparam maxmessagesize 60
skinparam sequenceParticipant underline

actor "超级管理员" as U
participant "图书管理员" as A

activate U


U ->A:输入所要查询/添加/修改/删除的图书管理员信息
activate A

A ->A:查询/添加/修改/删除图书管理员


A -->U:提示“查询/添加/修改/删除成功”
deactivate A
@enduml
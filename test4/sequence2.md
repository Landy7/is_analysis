@startuml
title
 账户设置
 <u>说明：图中的“/”均表示“或者”</u>
end title
skinparam sequenceArrowThickness 2
skinparam maxmessagesize 60
skinparam sequenceParticipant underline
actor "读者/图书管理员/超级管理员" as U
participant "用户" as A
U ->A:点击个人信息栏目
activate A
A -->U:显示个人信息
U ->A:点击并修改个人信息
A ->A:验证提交信息合法性
A -->U:返回修改信息结果
@enduml
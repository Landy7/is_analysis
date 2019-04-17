@startuml
title
 归还图书
 <u>说明：图中的“/”均表示“或者”</u>
end title
skinparam sequenceArrowThickness 2
skinparam maxmessagesize 60
skinparam sequenceParticipant underline
actor "图书管理员/超级管理员" as U
participant "资源项" as A
participant "借书记录" as B
participant "馆藏资源品种" as C
participant "读者" as D
participant "逾期记录" as E
activate U

-> U:检查书籍完整性
<-- U:登记赔偿

U ->A:获取资源信息
activate A
A ->B:取借书记录

activate B
A ->C:获取资源品种
deactivate A
deactivate B

activate C
U ->D:获取读者信息
deactivate C
activate D

U ->A:归还资源项
activate A

A ->C:增加图书库存
deactivate A

activate C
U ->B:登记归还日期和数量
activate B
deactivate C
deactivate D
opt 逾期
   U ->E:登记逾期记录
   deactivate B
   activate E
end
@enduml
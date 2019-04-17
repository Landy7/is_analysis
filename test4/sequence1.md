@startuml
title
 图书查询
 <u>说明：图中的“/”均表示“或者”</u>
end title
skinparam sequenceArrowThickness 2
skinparam maxmessagesize 60
skinparam sequenceParticipant underline
actor "用户" as U
participant "图书" as A
activate U
U ->A:输入图书信息
activate A
A -->U:返回图书信息
@enduml
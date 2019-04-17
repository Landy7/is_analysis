@startuml
title
 取消预定
 <u>说明：图中的“/”均表示“或者”</u>
end title
skinparam sequenceArrowThickness 2
skinparam maxmessagesize 60
skinparam sequenceParticipant underline
actor 读者
participant "预定记录" as B
activate 读者 
读者 ->B:取预定记录
activate B
B -->读者:返回该读者所有预定信息
deactivate B
读者 ->B:取消预定（删除预定记录）
activate B
B -->读者:返回操作结果
deactivate B
@enduml
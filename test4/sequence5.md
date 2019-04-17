@startuml
title
 预定图书
 <u>说明：图中的“/”均表示“或者”</u>
end title
skinparam sequenceArrowThickness 2
skinparam maxmessagesize 60
skinparam sequenceParticipant underline

actor 读者
participant "馆藏资源品种" as A
participant "预定记录" as B

activate 读者
读者 ->A:输入预定图书信息
activate A

A -->读者:返回操作结果
deactivate A

读者 ->A:选择预定图书
activate A

A ->B:生成预定记录
deactivate A
activate B

B -->读者:输出预定结果
deactivate B

@enduml
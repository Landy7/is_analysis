@startuml
title
 查询借阅情况
 <u>说明：图中的“/”均表示“或者”</u>
end title
skinparam sequenceArrowThickness 2
skinparam maxmessagesize 60
skinparam sequenceParticipant underline

actor 读者
participant "借书记录" as B

activate 读者

读者 ->B:获取借书记录
activate B

B -->读者:返回该读者所有借书记录
deactivate B
@enduml
@startuml
title:图书查询流程图
|游客/读者|
start
	:输入查询条件;
	|系统|
if(图书信息不存在?) then (存在)
	:返回图书信息;
else 
	:返回图书不存在;
endif
:返回信息;
|游客/读者|
:查看返回结果;
stop
@enduml
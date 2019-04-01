@startuml
title:查询借阅用例流程图
|读者|
start
:输入账号;
	|系统|
    :判断账号合法性;
if(账号合法?) then (是)
:返回借阅信息;
|读者|
:查看借阅信息;
stop
else(否)
|系统|
:账号错误;
:返回登录界面;
end
@enduml
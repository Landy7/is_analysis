@startuml
title:预定图书用例流程图
|读者|
start
:输入账号;
	|系统|
    :判断账号合法性;
if(账号合法?) then (否)
|系统|
:账号错误;
:返回登录界面;
end
else(是)
if(库存不足?) then (不足)
	:库存不足，中止预订;
	detach
else (充足)
	:库存减一;
:返回预订信息;
|读者|
:预订成功;
stop
@enduml
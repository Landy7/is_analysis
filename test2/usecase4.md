@startuml 
title:借书用例流程图
|超级管理员/图书管理员|
start
:输入账号;
	|系统|
    :判断账号正确性;
if(账号正确?) then (否)
|系统|
:账号错误;
:返回登录界面;
end
else(是)
:查询图书;
|系统|
if (书籍库存>=1?) then(否)
:库存不足;
|超级管理员/图书管理员|
:返回上级菜单;
end
else(是)
endif
|系统|
:相关书籍库存-1;
|超级管理员/图书管理员|
:显示借阅信息;
stop
@enduml
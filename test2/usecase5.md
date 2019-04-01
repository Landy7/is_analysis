@startuml
title:还书用例流程图
|超级管理员/图书管理员|
start
:输入账号;
	|系统|
    :判断账号合法性;
if(账号合法?) then (是)
|超级管理员/图书管理员|
repeat
	:输入归还账号;
	|系统|
	:判断账号合法性;
repeat while (输入合法?)
    |系统|
    if (账号是否借阅该书) then (是)
	    if(书籍是否破损或丢失) then (是)
	      :[登记赔偿];
		  detach
		  else(否)
		  :归还图书;
        endif
	        if(书籍是否逾期归还) then (是)
	          :[登记赔偿];
			  detach
	          else(否)
	          :归还图书;
			  :修改库存;
              |超级管理员/图书管理员|
              :查看结果;
              stop
		    endif
    else (未借阅)
	 |系统|
     :返回用户未借，中止还书;
	 detach
     endif
else(否)
|系统|
:账号错误;
:返回登录界面;
end
endif
@enduml

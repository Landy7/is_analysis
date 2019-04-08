@startuml
left to right direction
class 管理员 {
    ID
    管理员名
    密码
    角色
    电话
    邮箱
    照片
    电话
    --set 和 get--
    ...
    --
    End of class
}

class 图书管理员 {
    角色
    --
    End of class
}
class 超级管理员{
    角色
    --
    End of class
}

class 读者 {
    ID
    姓名
    密码
    性别
    出生日期
    角色
    所属学院
    专业
    借书数量
    照片
    邮箱
    电话
    --set 和 get--
    ...
    --
    End of class
}

class 图书品种{
    ID
    ISBN
    书名
    语言
    种类
    出版日期
    --get 和 set--
    ...
    --
    End of class
}
class 图书{
    ID
    ISBN
    书名
    出版社
    作者
    价格
    馆藏数量
    可借数量
    借出总次数
    内容简介
    照片
    --set和get--
    ...
    --
    End of class
}

class 借书记录{
    ID
    ISBN
    图书ID
    读者ID
    书名
    借书日期
    归还日期
    借书时长
    是否归还
    是否逾期
    --set和get--
    ...
    --
    End of class
}

class 预定记录{
    ID
    ISBN
    图书ID
    读者ID
    书名
    预定日期
    取书日期
    是否超期未取
    是否取消预定
    --set和get--
    ...
    --
    End of class
}

class 逾期记录{
    ID
    ISBN
    图书ID
    读者ID
    书名
    逾期日期
    归还日期
    逾期时长
    备注
    --set和get--
    ...
    --
    End of class
}

class 罚款细则{
    ID
    读者ID
    图书ID
    书名
    罚款原因
    罚款金额
    处理人ID
    罚款时间
    --set和get--
    ...
    --
    End of class
}


管理员 <- 超级管理员
管理员 <- 图书管理员

超级管理员 "1"-- "1..10"图书管理员:管理
超级管理员 "1"-- "n"读者 :管理
图书管理员 "1"-- "n"读者 :管理
图书管理员 "1"-- "n"图书 :管理
图书管理员 "1"-"n"借书记录:登记
图书品种 "1"*-- "n"图书:馆藏
图书 "1"--  "n"预定记录
图书 "1"-- "n"借书记录
读者 "1"--"n"预定记录:查询
读者 "1"-- "n"借书记录:查询
读者 "1"-- "0..1"逾期记录:查询
读者 "1"-- "n"图书:借阅

逾期记录 "0..1"--"0..1"罚款细则:使用
@endum
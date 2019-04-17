@startuml
left to right direction
class 游客{
    ID
}
class 用户{
    ID
    姓名
    性别
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
    所属部门
    --set 和 get--
    ...
    --
    End of class
}
class 超级管理员{
    所属部门
    --set 和 get--
    ...
    --
    End of class
}

class 读者 {
    出生日期
    所属学院
    专业
    借书数量
    --set 和 get--
    ...
    --
    End of class
}

class 馆藏资源品种{
    资源名称
    国际出版号
    价格
    简介
    馆藏数量
    可借数量
    借出总次数
    作者
    出版社
    出版日期
    --get 和 set--
    ...
    --
    End of class
}
class 资源项{
    馆藏流水号
    状态
}
class 图书{
    ID
    ISBN
    书名
    出版社
    作者
    价格
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
    馆藏流水号
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
    预定记录号
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

用户 <|-left- 读者
用户 <|-down- 图书管理员
用户 <|-left- 超级管理员

图书管理员 "1..10"-up-"1" 超级管理员:维护
超级管理员 "1"-up- "n"读者 :维护
图书管理员 "1"-right-"n"借书记录:登记
图书管理员 "1"-down-"n"逾期记录:登记
图书管理员 "1"-down-"n"罚款细则:登记
读者 "1"-right-"n"预定记录:查询
读者 "1"-down- "n"借书记录:查询
读者 "1"-left- "0..1"逾期记录:查询
读者 "1"-right- "n"图书:查询
游客 "1"-left- "n"图书:查询
馆藏资源品种 "1"*-right- "n"图书:馆藏
馆藏资源品种 "1" *- "n" 资源项 : 拥有
馆藏资源品种 "1"-down- "n"预定记录
馆藏资源品种 "1"-right- "n"借书记录
逾期记录 "0..1"-down-"0..1"罚款细则:使用
@enduml
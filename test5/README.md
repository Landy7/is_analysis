## 实验五（test5）：图书管理系统数据库设计与界面设计
|学号|班级|姓名|
|:---------------:|:------------:|:------------:|
|201610414105|软件16-1|兰迪|
###1.数据库表设计
#### 1.1 管理员信息（Manager）表(包括超级管理员和图书管理员)：
|项目|字段名|类型与宽度|主键、外键|是否允许为空值|约束|说明|
|:------:|:-------:|:-------:|:-------:|:-------:|:-------:|:-------:|
|ID|managerId|int(12)|主键|×|||
|姓名|managerName|varchar(20)||×|||
|性别|gender|varchar(20)||√|||
|密码|password|varchar(20)||×|||
|角色|role|bit||×||1:超级管理员，0:图书管理员，2:读者|
|邮箱|mail|varchar(30)||×|||
|照片|photo|varbinary(MAX)||√|||
|电话|tel|int(11)||×||联系电话|
|所属部门|department|varchar(30)||×|||

### 1.2 读者信息（Reader）表：
|项目|字段名|类型与宽度|主键、外键|是否允许为空值|约束|说明|
|:------:|:-------:|:-------:|:-------:|:-------:|:-------:|:-------:|
|ID|readerId|int(12)|主键|×|||
|姓名|readerName|varchar(20)||×|||
|性别|gender|varchar(20)||×|||
|密码|password|varchar(20)||×|||
|角色|role|bit||×||1:超级管理员，0:图书管理员，2:读者|
|邮箱|mail|varchar(30)||×|||
|照片|photo|varbinary(MAX)||√|||
|电话|tel|int(11)||×||联系电话|
|出生日期|born|int(8)||×|||
|专业|major|varchar(20)||×|||
|所属学院|institute|varchar(20)||×|||
|借书数量|num|int(10)||×||初始默认为0|

### 1.3 图书信息(Book)表：
|项目|字段名|类型与宽度|主键、外键|是否允许为空值|约束|说明|
|:------:|:-------:|:-------:|:-------:|:-------:|:-------:|:-------:|
|ID|bookId|int(12)|主键|×|||
|书名|bookName|varchar(20)||×|||
|ISBN|ISBN|varchar(20)||×|||
|作者|author|varchar(20)||×|||
|出版社|publish|varchar(20)||×|||
|价格|price|varchar(30)||×|||
|内容简介|summary|varchar(50)||√|||
|照片|photo|varbinary(MAX)||√|||

### 1.4 馆藏资源品种信息(Resource)表：
|项目|字段名|类型与宽度|主键、外键|是否允许为空值|约束|说明|
|:------:|:-------:|:-------:|:-------:|:-------:|:-------:|:-------:|
|馆藏流水号|serId|int(20)|主键|×|||
|预定记录号|reserveId|int(20)|外键|√||为空说明还没有预定|
|ISBN|ISBN|int(20)||×|||
|作者|author|varchar(20)||×|||
|出版社|publish|varchar(20)||×|||
|价格|price|varchar(30)||×|||
|简介|summary|varchar(50)||√|||
|馆藏数量|sum|int(10)||×||初始默认值为0|
|可借数量|borrNum|int(10)||×||初始默认值为0|
|借出总次数|borSum|int(15)||×||初始默认值为0|
|出版日期|pubTime|int(8)||×|||
|状态|state|varchar(20)||×|||


### 1.5 借书记录信息(borrow)表：
|项目|字段名|类型与宽度|主键、外键|是否允许为空值|约束|说明|
|:------:|:-------:|:-------:|:-------:|:-------:|:-------:|:-------:|
|ID|borrowId|int(20)|主键|×|||
|ISBN|ISBN|int(20)||×|||
|馆藏流水号|serId|int(40)|外键|×||参照馆藏资源信息表|
|读者ID|readerId|int(20)|外键|×||参照读者信息表|
|书名|bookName|varchar(20)||×|||
|借书日期|borrowTime|datetime||×|||
|归还日期|returnTime|datetime||×||没有会显示"暂无"|
|借书期限|borrowLenth|int(10)||×|||
|是否归还|isReturn|varchar(5)||×|||
|是否逾期|isOverdue|varchar(5)||×|||

### 1.6 预定记录信息(order)表：
|项目|字段名|类型与宽度|主键、外键|是否允许为空值|约束|说明|
|:------:|:-------:|:-------:|:-------:|:-------:|:-------:|:-------:|
|ID|orderId|int(20)|主键|×|||
|ISBN|ISBN|int(20)||×|||
|预定记录号|reserveId|int(20)|外键|×|||
|读者ID|readerId|int(20)|外键|×||参照读者信息表|
|书名|bookName|varchar(20)||×|||
|预定日期|orderTime|datetime||×|||
|取书日期|takeTime|datetime||√|||
|是否超期未取|isOverDue|varchar(10)||×|||
|是否取消预定|isCancelOrder|varchar(10)||×|||

### 1.7 逾期记录信息(overdue)表：
|项目|字段名|类型与宽度|主键、外键|是否允许为空值|约束|说明|
|:------:|:-------:|:-------:|:-------:|:-------:|:-------:|:-------:|
|ID|overdueId|int(20)|主键|×|||
|ISBN|ISBN|int(20)||×|||
|馆藏流水号|serId|int(20)|外键|×||参照馆藏资源信息表|
|读者ID|readerId|int(20)|外键|×||参照读者信息表|
|书名|bookName|varchar(20)||×|||
|逾期日期|overTime|datetime||×|||
|归还日期|returnTime|datetime||×|||
|逾期时长|overLenth|int(10)||×|||
|备注|detail|varchar(30)||×|||

### 1.8 罚款细则信息(punish)表：
|项目|字段名|类型与宽度|主键、外键|是否允许为空值|约束|说明|
|:------:|:-------:|:-------:|:-------:|:-------:|:-------:|:-------:|
|ID|punishId|int(20)|主键|×|||
|ISBN|ISBN|int(20)||×|||
|馆藏流水号|serId|int(20)|外键|×||参照馆藏资源信息表|
|读者ID|readerId|int(20)|外键|×||参照读者信息表|
|书名|bookName|varchar(20)||×|||
|罚款原因|punishReason|varchar(20)||×|||
|罚款金额|punishMoney|varchar(10)||×|||
|处理人ID|managerId|int(10)||×|||
|罚款时间|punishTime|datetime||×|||

###2.界面设计

###3.API接口设置
#### 3.1 查询借书记录
- 功能：查询借书记录，可以获取全部的借书记录信息<br>
- 请求地址：http://api.library.com/v1/api/borrow<br>
- 请求方式：GET<br>
- 请求参数：
|参数名称|必填|说明|
|:-------:|:-------------: | :----------:|
|ID|是|用户登录状态凭证 |
|access_token|是|用于验证请求合法性的认证信息 |
|method|是|固定为 “GET”|
- 返回实例：
```
{
    "info": "所有的借书记录",
    "total": 1024,
    "data": [
        {
        "ID": "1",
        "ISBN":"978-7-302-32982-4",
        "readerId":"201610414105"
        "bookName": "数据库原理",
        "borrowTime": "2018-01-23 17:34",
        "returnTime": "2018-01-23 17:34",
        "borrowLenth": "2018-01-23至2018-06-23",
        "isReturn": "是",
        "isOverdue": "否",
        "botton":"删除",
        "path": "http://api.library.com/v1/api/borrow/ID/borrowList",
        },
        {
        ...其他还书单
        }
    ]
    "code": 200
}

```
- 返回参数说明:
|参数名称|说明|
|:-------:|:------------- |
|Info|返回的提示信息|
|total|返回借书记录的数量|
|data|返回借书记录列表内容数据主体<br>"ID":借书记录单号<br>"ISBN":国际版本号<br>"bookName": "书名"<br>"borrowTime": "借书日期"<br>"returnTime": "还书处理日期"<br>"borrowLenth": "还书期限"<br>"isReturn": "是否还书"<br>"isOverdue": "是否逾期"<br>"botton": "删除:删除已还书的借书记录"<br>"path": 借书记录详情链接地址"|
|code|返回码|


#### 3.2 删除借书记录（只能删除已还书的借书记录）
- 功能：用于图书管理员删除已还书的借书记录
- 请求地址： http://api.library.com/v1/api/borrow/delete
- 请求方法：DELETE
- 请求参数：

|参数名称|必填|说明|
|:-------:|:-------------: | :----------:|
|ID|是|用户登录状态凭证 |
|access_token|是|用于验证请求合法性的认证信息 |
|method|是|固定为 “DELETE”|

- 返回实例：
```
{
    "info": "删除成功",
    "code": 200
}
```
- 返回参数说明：
    
|参数名称|说明|
|:-------:|:-------------: |
|Info|返回的提示信息|
|code|返回码|

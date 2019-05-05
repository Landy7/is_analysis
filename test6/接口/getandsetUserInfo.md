# 接口：getUserInfo/setUserInfo  [返回](../../README.md)
用例： [查看用户信息](../用例/查看用户信息.md),[修改用户信息](../用例/修改用户信息.md)

- 功能：
    查看用户的所有信息。
    
- 权限：
    学生/老师：查看自己的信息，必须先登录，不能查看其他用户的信息。    
    
- API请求地址： 
    接口基本地址/v1/api/getUserInfo/<user_id>

- 请求方式 ：
    GET
      
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |user_id|用户的ID号。对应表USERS.USER_ID的值|
  
- 返回实例1：

        {         
            "status": true,
            "info": null,
            "data": {
                "user_id":"201610414105",    
                "name":"兰迪",
                "github_username":"landy7",
                "role":"学生",
                "tel":"18183371221"
                "website":"https://github.com/Landy7/is_analysis/"
                "student": {
                    "major": "软件工程",
                    "garde":"95"
                    "class": 1,
                    "institute":"信息科学与工程学院"
                    "enrollment_year": 2016,
                }  
            }          
        }
        
 - 返回实例2：

        {         
            "status": true,
            "info": null,
            "data": {
                "user_id":"35677656",    
                "name":"张三",
                "github_username":"landy76",
                "role":"老师",
                "teacher": {
                    "department": "学工办"
                }  
            }          
        }
 
- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |data|返回主体信息JSON串|
  |user_id|学号或者工号|
  |name|用户的真实姓名|
  |website|Github网址|  
  |github_username|gitHub用户名|
  |tel|电话|
  |student|学生信息|
  |major|学生所在专业|
  |grade|学生成绩|
  |class|学生所在班级|
  |enrollment_year|学生入学年份|
  |institute|学生所在学院|
  |teacher|老师信息|
  |department|老师所在部门|
  * 注：系统根据所查询的user_id对应的role值，传回学生或老师的信息
# 接口：getStudents  [返回](../../README.md)
用例： [学生列表](../用例/学生列表.md)

- 功能：
   根据课程编号显示本课程学生列表。
    
- 权限：
    老师。    
    
- API请求地址： 
    接口基本地址/v1/api/getStudents

- 请求方式：
    GET

- 请求实例：

        {
            "course_id": "044787865"
        }
        
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |course_id|课程编号|
  
- 返回实例：

        { 
            "status": true,
            "info": null,
            "data": {
                "students": [{
                    "student_id": "201610414105",
                    "institute":"信息科学与工程学院"
                    "major": "软件工程",
                    "class": "一班",
                    "grade": 95,
                    "user": {
                        "user_id": "201610414105",
                        "name": "兰迪",
                        "github_username": "Landy7",
                        "tel":18183371221,

                    }
                },{
                    ...
                }]   
            }    
        }

- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |data|返回主体信息JSON串|
  |students|返回本课程学生集合，若空则返回[]|
  |student_id|学号|
  |institute|学院| 
  |major|专业|  
  |class|班级|
  |grade|95|
  |user|学生关联的用户信息|
  |user_id|用户编号|
  |name|用户姓名|
  |github_username|GitHub用户名|
  |tel|电话|
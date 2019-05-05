# 接口：setCourses  [返回](../../README.md)
用例：[增加课程](../用例/增加课程.md) [修改课程](../用例/修改课程.md) 

- 功能：
    创建（修改）指定课程的课程信息。
    
- 权限：
    老师。    
    
- API请求地址： 
    接口基本地址/v1/api/setCourses

- 请求方式 ：
    POST

- 请求实例：

        {
            "course_id": "03241176",
            "course_name": " JAVA高级开发",
            "course_content": "JAVA高级开发与应用",
            "course_term": "2018-2019学年第二学期",
            "course_major": "软件工程",
            "course_class": "2016级1，2班",
            "techer_id": "21228767"
        }    
    
        
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |course_id|课程编号|
  |course_name|课程名称|  
  |course_content|课程简介|
  |course_term|开课学期|
  |course_major|开课专业|
  |course_class|开课班级|
  |teacher_id|老师编号|
  * 注：新建课程无需传入course_id,course_id为数据库主键，创建后无法更改，
  teacher_id由系统关联，同样无法更改。
  
- 返回实例：

        {         
            "status": true,
            "info": null,    

        }
 
- 返回参数说明： 
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|


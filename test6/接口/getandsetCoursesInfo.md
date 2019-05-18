# 接口：get/setCourseInfo  [返回](../README.md)
用例： [查看课程](../用例/查看课程.md),[修改课程](../用例/修改课程.md)

- 功能：
    查看指定课程的信息。
    
- 权限：
    学生/老师：查看所修/所任教课程信息，不能查看其他课程的信息。    
    
- API请求地址： 
    接口基本地址/v1/api/getCourseInfo/<course_id>

- 请求方式 ：
    GET
      
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |course_id|课程的ID号。对应表courses.courses_id的值|
  
- 返回实例：

        {         
            "status": true,
            "info": null,
            "data": {
                "course_id": "04478976"
                "course_name": "形式与政策（6）"
                "course_teacher": "安鸿"
                "course_content": "介绍当前国内外经济政治形势、国际关系以及国内外热点事件的基础上，阐明了我国政府的基本原则、基本立场与应对政策。"
                "course_term": "2018-2019学年第二学期"
                "course_major": "软件工程，自动化"
                "course_class": "全体班级"
                "course_time":"第12-14周，周四7-9节课"
            }          
        }
 
- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |data|返回主体信息JSON串|
  |course_id|课程编号|
  |course_name|课程名称|  
  |course_teacher|任教老师|
  |course_content|课程简介|
  |course_term|开课学期|
  |course_major|开课专业|
  |course_class|开课班级|
  |course_time|上课时间|
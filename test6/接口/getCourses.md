# 接口：getCourses  [返回](../../README.md)
用例： [课程列表](../用例/课程列表.md)

- 功能：
   显示学生/老师的课程列表。
    
- 权限：
    学生/老师。    
    
- API请求地址： 
    接口基本地址/v1/api/getCourses

- 请求方式：
    GET

- 请求实例：

        {
            "student_id": "201610144106",
            "term": "2015-2016学年第1学期"
        }
        {
            "teacher_id": "77865498",
            
        }
        
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |student_id|学生学号|
  |term|学生所修的学期，格式必须固定|
  |teacher_id|老师工号|
  
- 返回实例：
学生课程列表：
        { 
            "status": true,
            "info": null,
            "data": {
                "courses": [{
                    "course_id": "03367565",
                    "course_name": "形式与政策(6)",
                    "techer": {
                        "techer_id": "78656790",
                        "name": "兰迪"
                    }
                },{
                    "course_id": "03367565",
                    "course_name": "数据库原理",
                    "teacher": {
                        "teacher_id": "22223982",
                        "name": "黄荣兵"
                    }
                }]   
            }    
        }
老师课程列表：
        { 
            "status": true,
            "info": null,
            "data": {
                "courses": [{
                    "course_id": "03367565",
                    "course_name": "形式与政策(6)",
                    "student": {
                        course_major:"软件工程"
                    }
                },{
                    "course_id": "03367565",
                    "course_name": "数据库原理",
                    "student": {
                        course_major:"软件工程"
                    }
                }]   
            }    
        }

- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |data|返回主体信息JSON串|
  |courses|返回符合条件的所有课程集合，若空则返回[]|
  |course_id|课程编号|
  |course_name|课程名称|
  |course_major|开课专业|  
  |teacher|老师信息|
  |teacher_id|老师工号|
  |teacher_name|老师姓名|

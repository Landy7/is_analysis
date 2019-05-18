# 接口：getChoice_Courses[返回](../README.md)
[选课](../用例/选课.md)

- 功能：
    - 用于系统自动设置一门教师已发布的的课程的选课学生学号、姓名和选课时间
    
- 权限：
    - 学生：系统识别用户角色，设置一门教师教师已发布的的课程的选课学生学号、姓名和选课时间
    
- API请求地址： 
    接口基本地址/v1/api/getChoice_courses

- 请求方式 ：
    POST
    
- 请求实例：

        {
            "courses_id": "879768897",
            "course_name": "形式与政策",
            "name": "安鸿",
            "course_term": "2018-2019第二学期",
            "course_major": "全体专业",
            "course_class": "全体班级",
            "choice_date": "2019-02-04 16:32:24",
            "choice_state": "1",
        }
 
- 请求参数说明：
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|
  |courses_id|选课编号|
  |course_name|课程名称|
  |name|用户真实姓名|
  |course_term|开课学期|
  |course_major|开课专业|
  |course_class|开课班级|
  |choice_date|选课时间|
  |choice_state|选课状态|

- 返回实例：

        {
            "status": true,
            "info": null
        }

- 返回参数说明：

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|


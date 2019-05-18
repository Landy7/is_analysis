# 接口：getScores  [返回](../README.md)
用例： [查看成绩以及评价](../用例/查看成绩以及评价.md)

- 功能：
   根据课程编号及学号返回成绩列表。
    
- 权限：
    学生/老师。    
    
- API请求地址： 
    接口基本地址/v1/api/getScores

- 请求方式：
    POST

- 请求实例：

        {
            "course_id": "04470470",
            "student_id": "201610414105"
        }
        
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |course_id|课程编号，对应唯一课程|
  |student_id|学号，对应唯一学生|
  
  
- 返回实例：

        { 
            "status": true,
            "info": null,
            "data": {
                "course_id": "04470470"
                "student_id": "201610414105"
                "course_score": 90,
                "course_comment": 完成的非常不错，
                注意细节问题。
                "course_update_date": null
                "experiment_scores": [{
                    "experiment_id": 1
                    "experiment_score": 90,
                    "experiment_comment": "完成度非常高，有些小错误，比如界面还可以更加优化。
                    继续加油"。
                    "experiment_update_date": "2019-04-12 14:32:44"
                    "assess_scores": [{
                        "assess_score": 95,
                        "assess_comment": "完成的相当不错！",
                        "assess_update_date": "2019-04-11 13:32:44"
                    },{
                        "assess_score": 85,
                        "assess_comment": "有些小错误",
                        "assess_update_date": "2019-04-12 13:32:44"
                    }]
                }
            }    
        }

- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |data|返回主体信息JSON串|
  |experiments|返回课程对应的所有实验集合，若空则返回[]|
  |course_id|课程编号|
  |student_id|学号|
  |course_score|课程成绩|
  |course_comment|课程评价|
  |course_web_sum|学生课程GitHub地址是否正确，1正确，0错误|
  |course_update_date|课程成绩批改时间|
  |experiment_scores|实验成绩集合|
  |experiment_id|实验编号|
  |experiment_score|某个实验成绩|
  |experiment_comment|某个实验评价|
  |experiment_web_sum|某个实验GitHub地址是否正确，1正确，0错误|
  |experiment_update_date|某个实验批改时间|
  |assess_scores|评分点成绩集合|
  |assess_score|评分点成绩|
  |assess_comment|评分点评价|  
  |assess_update_date|评分点批改时间|
 
  同时在其子表下的内容将无需查询，并无需返回。<br>

# 接口：setScores  [返回](../README.md)
用例： [评定成绩](../用例/评定成绩.md)

- 功能：
    评定（修改）学生的成绩和评价。
    
- 权限：
    老师。    
    
- API请求地址： 
    接口基本地址/v1/api/setScores

- 请求方式 ：
    POST

- 请求实例：

        {
            "course_id": "04476785"
            "student_id": "201610414105"
            "experiment_scores": [{
                "experiment_id": 1
                "experiment_score": 90,
                "experiment_comment": ""完成度非常高，有些小错误，比如界面还可以更加优化。
                继续加油"。",
                "experiment_update_date": "2019-04-12 14:32:44"
                "assess_scores": [{
                    "assess_score": 95,
                    "detail_comment": "完成的相当不错！",
                    "experiment_update_date": "2019-04-11 13:32:44"
                },{
                    "assess_score": 85,
                    "assess_comment": "有些小错误",
                    "assess_update_date": "2019-04-12 13:32:44"
                }]
            }]
        }    
    
        
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |course_id|课程编号|
  |student_id|学号|
  |course_score|课程成绩|
  |course_comment|课程评价|
  |course_update_date|课程成绩批改时间|
  |experiment_scores|实验成绩集合|
  |experiment_id|实验编号|
  |experiment_score|某个实验成绩|
  |experiment_comment|某个实验评价|
  |experiment_update_date|某个实验批改时间|
  |assess_scores|评分点成绩集合|
  |assess_score|评分点成绩|
  |assess_comment|评分点评价|  
  |assess_update_date|评分点批改时间|
  * 注：未打成绩的项不计入参数列表，例子见请求实例。
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


# 接口：getExperiments  [返回](../README.md)
用例： [查看实验任务](../用例/查看实验任务.md)

- 功能：
   根据课程编号返回实验列表。
    
- 权限：
    学生/老师。    
    
- API请求地址： 
    接口基本地址/v1/api/getExperiments

- 请求方式：
    GET

- 请求实例：

        {
            "course_id": "04478976"
        }
        
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |course_id|课程编号，对应唯一课程|
  
  
- 返回实例：

        { 
            "status": true,
            "info": null,
            "data": {
                "experiments": [{
                    "experiment_id": 1，
                    "experiment_name": "实验一：图书管理系统用例建模"，
                    "experiment_content": "本实验的目的是理解用例(Use Case)的意义和作用，并能用PlantUML工具绘制用例图。
                    仔细阅读并理解第7章用例建模。"，
                    "experiment_last_time": "2019-04-11"

                },{
                    "experiment_id": 2，
                    "experiment_name": "实验二：图书管理系统领域对象建模"，
                    "experiment_content": "本实验的目的是掌握领域对象建模中类图的作用，并能用PlantUML工具绘制类图。
                    仔细阅读并理解第8章领域对象建模。"，
                    "experiment_last_time": "2019-04-18"
                }]   
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
  |experiment_id|实验编号|
  |experiment_name|实验名称|  
  |experiment_content|实验内容|
  |experiment_last_time|实验截至时间|

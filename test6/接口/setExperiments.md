# 接口：setExperiments  [返回](../README.md)
用例：[增加实验任务](../用例/增加实验任务.md) [修改实验任务](../用例/修改实验任务.md) 

- 功能：
    创建（修改）指定课程的实验信息。
    
- 权限：
    老师。    
    
- API请求地址： 
    接口基本地址/v1/api/setExperiments

- 请求方式 ：
    POST

- 请求实例：

        {
            "course_id": 04746786,
            "experiment_id": 1,
            "experiment_name": "AS练习1",
            "experiment_content": "熟练掌握AS语法练习",
            "experiment_last_time": "2015-11-29 11:46:27"
        }    
    
        
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |course_id|课程编号|
  |experiment_id|实验编号|  
  |experiment_name|实验名称|
  |experiment_content|实验内容|
  |experiment_last_time|实验截至时间|
  * 注：每个id为数据库主键，创建后无法更改。
  
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


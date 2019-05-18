# 接口：getAssess_details  [返回](../README.md)
用例： [查看评分点](../用例/查看评分点.md)

- 功能：
   根据实验编号和课程编号返回评分点列表。
    
- 权限：
    学生/老师。    
    
- API请求地址： 
    接口基本地址/v1/api/getAssess_details

- 请求方式：
    GET

- 请求实例：

        {
            "course_id": "03367565",
            "experiment_id": 1
        }
        
- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |course_id|课程编号，对应唯一课程|
  |experiment_id|实验编号，和课程编号同时对应唯一实验|
  
  
- 返回实例：

        { 
            "status": true,
            "info": null,
            "data": {
                "getAssess_details": [{
                    "assess_name": "代码设计"，
                    "assess_content": "代码截图全部给出，并且要有代码注释"
                    "assess_occupy": "占总实验的40%"

                },{
                    "assess_name": "界面设计"
                    "assess_content": "界面截图全部给出，并且要有说明你为什么这样设计"，
                    "assess_occupy": "占总实验的60%"
                }]   
            }    
        }

- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |data|返回主体信息JSON串|
  |details|返回实验对应的所有评分点集合，若空则返回[]|
  |assess_name|评分点名称|
  |assess_content|评分点内容|  
  |assess_occupy|评分点占比|

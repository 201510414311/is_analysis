# 接口：setOneStudentResults [返回](./REDEME.md)
- 功能：设置一个学生的部分实验成绩和评语。输入参数result_point不为空，自动设置update_date为当前日期，表示同时设置批改日期。
输入参数result_point为空，自动设置update_date为空，表示未批改。
- 权限：师：可以查看所有学生的成绩。
- API请求地址：http://202.115.82.8:1522/v1/api/setOneStudentResults
- 请求方式 ： POST
- 请求实例：
|参数名称|说明|
|:-:|:-:|
|stu_id|学生学号|
|total|本次批改的所有实验的总数，小于等于全部实验的总数|
|data|实验的成绩和评语|
|test_id|实验编号|
|sub_id|课程号|
|term_id|学期号|
|point_score|每一项得分|
|point_memo|每一项评语|
|result|实验分数|
```
  {
      "stu_id":"20204824",
      "total": 6,
      "data":[{
        "test_id":"1",
        "sub_id":"12124",
        "term_id":"21345",
        "point_score":{80,69,70,80
        },
        "point_memo":{""该分部做得好","该分部还行","……""
      },
        "result":75
        },
        {……其他实验}
      ]
  }
```
- 返回实例：
```
{ 
      "status": true,
      "info": null,    
  }
```
- 返回参数说明：
|参数名称|说明|
|:-:|:-:|
|status|bool类型，true表示正确的返回，false表示有错误|
|info|返回结果说明信息|





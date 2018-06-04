# 接口：getStudentGradeList [返回](./REDEME.md)
- 功能：查看学生实验成绩
- 权限：老师查看
- API请求地址：http://202.115.82.8:1522/v1/api/getStudentGradeList
- 请求方式 ： GET
- 请求参数说明:

|参数名称|说明|
|:-:|:-:|
|studentList|学生学号集合|


- 返回实例
```
 {         
      "status": true,
      "info": null
      "studentList":{
         "2021845",
         "2012445",
         "2323503",
         ……
      }
      "data":[
          {
          "test_id":"1",
          "sub_id":"210034",
          "term_id":"230124",
          "test_name":"C语言编程",
          "each_score":"78,76,89,68,56",
          "each_memo":""该步骤完成尚好","改步骤还行",……"
          "rusult_grade": 87, 
          "update_date": "2018-04-02 13:48:01"
          }, 
          {
          ...其他实验
          }
      ] 
      "data":[{
        "name":"张三",
        "class":"软件3班"
      },
      {
        ……其他学生
      }
      ]
  }
```
- 返回参数说明：

|参数名称|说明|
|:-:|:-:|
|status|bool类型，true表示正确的返回，false表示有错误|
|info|返回结果说明信息|
|studentList|学生学号集合|
|test_name|实验名|
|data|评分内容/学生信息|
|test_id|实验编号|
|sub_id|课程号|
|term_id|学期号|
|each_score|每项评分|
|each_memo|每项的评语|
|rusult_grade|该实验总分数|
|update_date|修改时间|
|name|姓名|
|class|班级|




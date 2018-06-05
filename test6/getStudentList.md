# 接口：getStudentList [返回](./REDEME.md)
- 功能：返回所有学生的列表。
- 权限：
- API请求地址：http://202.115.82.8:1522/v1/api/getStudentList
- 请求方式 ： GET
- 请求实例：
无


- 返回实例：
```
{ 
      "status": true,
      "info": null,
      "total": 121,
      "data": [
          {
          "GITHUB_USERNAME": "Chinajuedui",
          "STUDENT_ID": "201510315203",
          "CLASS": "软工3班",
          "NAME": "张三",
          "UPDATE_DATE": "2018-04-02 13:48:01"},
          {
          ...其他学生
          }
      ]
  }
```
- 返回参数说明：

|参数名称|说明|
|:-:|:-:|
|status|bool类型，true表示正确的返回，false表示有错误|
|info|返回结果说明信息|
|total|返回学生人数|
|data|所有学生的数组|
|GITHUB_USERNAME|GITHUB 用户名|
|STUDENT_ID|学号|
|CLASS|班级|
|NAME|姓名|
|UPDATE_DATE|GitHUB用户名修改日期|





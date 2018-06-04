# 接口：getUserSub [返回](./REDEME.md)
- 功能：返回用户当前学期课程。
- 权限：学生/老师：修改自己的信息，必须先选择课程。
- API请求地址：http://202.115.82.8:1522/v1/api/getUserSub/<term_id>
- 请求方式 ： GET
- 请求实例：
|参数名称|说明|
|:-:|:-:|
|term_id|用户选择的学期|


- 返回实例：
```
{ 
      "status": true,
      "info": null, 
      "sub":[{
        "sub_id":"24236"，
        "sub_name":"C语言教程",
      },
      {……其他课程}
      ]
  }
```
- 返回参数说明：
|参数名称|说明|
|:-:|:-:|
|status|bool类型，true表示正确的返回，false表示有错误|
|info|返回结果说明信息|
|sub|课程信息|
|sub_id|课程id号|
|sub_name|课程名字|





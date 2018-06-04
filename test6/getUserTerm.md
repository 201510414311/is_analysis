# 接口：getUserTerm [返回](./REDEME.md)
- 功能：返回用户当前学期列表。
- 权限：
- API请求地址：http://202.115.82.8:1522/v1/api/getUserTerm
- 请求方式 ： GET
- 请求实例：
|参数名称|说明|
|:-:|:-:|
|userId|用户id信息|


- 返回实例：
```
{ 
      "status": true,
      "info": null, 
      "term"：[{
          "term_id":"134356",
          "term_name":"2015-2016第一学期"
      },{……其他学期}
      ]
  }
```
- 返回参数说明：
|参数名称|说明|
|:-:|:-:|
|status|bool类型，true表示正确的返回，false表示有错误|
|info|返回结果说明信息|
|term|学期信息|
|term_id|学期id号|
|term_name|学期名字|





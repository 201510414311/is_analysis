# 接口：logout [返回](./README.md)
- 功能：已经登录的用户登出平台。
- 权限：学生/老师已经登录
- API请求地址：http://202.115.82.8:1522/v1/api/logout
- 请求方式 ： POST
- 请求实例：

|参数名称|说明|
|:-:|:-:|
|user_id|用户的ID号。对应表USERS.USER_ID的值|

```
{
      "user_id":291234
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





# 接口：setUserInfo [返回](./README.md)
- 功能：修改用户信息。
- 权限：学生/老师：修改自己的信息，必须先登录。
- API请求地址：http://202.115.82.8:1522/v1/api/setUserInfo
- 请求方式 ： POST
- 请求实例：

|参数名称|说明|
|:-:|:-:|
|id|用户的ID号。对应表USERS.USER_ID的值|
|github_username|用户GitHub用户名|
|password|用户密码|
|name|用户真实姓名|

```
 {
      "id":"2004124055",
      "github_username":"ABCDE", 
      "password":2435267,
      "name":"lisi"
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





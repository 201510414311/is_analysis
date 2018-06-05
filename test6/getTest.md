# 接口：getTest [返回](./README.md)
- 功能：返回实验的内容
- 权限：学生，老师都能用
- API请求地址：http://202.115.82.8:1522/v1/api/getTest
- 请求方式 ： GET
- 请求参数说明:

|参数名称|说明|
|:-:|:-:|
|test_id|实验的实验编号|


- 返回实例
```
{
"status": true,
"info": null,
"data": [
          {
          "test_id":1,
          "sub_id": 100012, 
          "term_id":100231,
          "test_name": "C语言教程"
          }, 
          {
          ...其他实验
          }
      ] 
}
```
- 返回参数说明：

|参数名称|说明|
|:-:|:-:|
|status|bool类型，true表示正确的返回，false表示有错误|
|info|返回结果说明信息|
|data|实验内容|
|test_id|实验编号|
|sub_id|课程编号|
|term_id|学期编号|
|test_name|实验名称|

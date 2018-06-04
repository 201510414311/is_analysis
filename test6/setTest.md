# 接口：setTest [返回](./REDEME.md)
- 功能：增加实验
- 权限：老师用
- API请求地址：http://202.115.82.8:1522/v1/api/setTest
- 请求方式 ： POST
- 请求实例：
```
{
"information":"本次实验为c语言，要完成以下几个方面……",
"data": {
        "test_name":"linux编程",
        "test_id":2,
        "sub_id": 100014,
        "term_id":100231,
    }
}
```
- 请求参数说明：
|参数名称|说明|
|:-:|:-:|
|information|实验描述|
|data|实验内容|
|test_id|实验编号|
|sub_id|课程编号|
|term_id|学期编号|
|test_name|实验名称|

- 返回实例
```
 {         
      "status": true,
      "info": null
  }
```
- 返回参数说明：
|参数名称|说明|
|:-:|:-:|
|status|bool类型，true表示正确的返回，false表示有错误|
|info|返回结果说明信息|


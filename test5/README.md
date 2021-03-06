﻿# 实验5：图书管理系统数据库设计与界面设计
学号  | 班级 | 姓名  
:-:|:-:|:-:
201510414311    |     软工三班      |   彭启瑞
## 1.数据库表设计
### 1.1馆藏资源品种表
字段 | 类型 | 主键（外键） | 可以为空 | 默认值 | 约束 | 说明
:-:|:-:|:-:|:-:|:-:|:-:|:-:
ziyuan_name|varchar2(100)|否|否|||资源的名称|
|ziyuan_id|long|是|否|||资源的id号，自动递增
|ISBN|varchar2(100)|否|否||||
|price|float(10)|否|否|||图书的价格
|information|varchar2(1024)|否|否|||资源信息介绍
|ziyuan_num|int|否|否|||馆藏数量
|canlend_num|int|否|否|||可借数目
|book_id|int|外键|否|||图书的id号
### 1.2资源项
字段 | 类型 | 主键（外键） | 可以为空 | 默认值 | 约束 | 说明
:-:|:-:|:-:|:-:|:-:|:-:|:-:
|waterNum|varchar2(100)|是|否|||馆藏流水号
|state|int|否|否|||图书的状态,0为未借出，1：已借出，2：预定

### 1.3图书管理员
字段 | 类型 | 主键（外键） | 可以为空 | 默认值 | 约束 | 说明
:-:|:-:|:-:|:-:|:-:|:-:|:-:
|lib_id|long|是|否|||图书管理员的id
|lib_name|varchar2(20)|否|否|||管理员的姓名

### 1.4图书种类
字段 | 类型 | 主键（外键） | 可以为空 | 默认值 | 约束 | 说明
:-:|:-:|:-:|:-:|:-:|:-:|:-:
|book_id|int|是|否|||图书的id号
|Press|varchar(100)|否|否|||出版社名字
|publishdata|data|否|否|||出版日期

### 1.5借书记录
字段 | 类型 | 主键（外键） | 可以为空 | 默认值 | 约束 | 说明
:-:|:-:|:-:|:-:|:-:|:-:|:-:
|lend_id|int|是|否|||借书订单号
|lend_data|data|否|否|||借书日期
|return_data|data|否|否|||应当归还书日期
|return_real_data|data|否|是|||实际归还日期
|reader_id|long|外键|否|||读者id
|book_id|int|外键|否|||图书的id

### 1.6读者
字段 | 类型 | 主键（外键） | 可以为空 | 默认值 | 约束 | 说明
:-:|:-:|:-:|:-:|:-:|:-:|:-:
|reader_id|long|是|否|||读者id号
|reader_name|varchar2(20)|否|否|||读者姓名
|reader_cId|long|否|否|||读者的身份证号
|lend_Mnum|int|否|否|||可借图书最大限额
|lend_ar|int|否|否|||已借图书数量

### 1.7逾期记录
字段 | 类型 | 主键（外键） | 可以为空 | 默认值 | 约束 | 说明
:-:|:-:|:-:|:-:|:-:|:-:|:-:
|overdue_id|long|是|否|||逾期记录id
|overdue_data|int|否|否|||逾期的天数
|lend_id|int|外键|否|||借书订单号
|fa_price|float|否|否|||应缴罚款
|is_fa_price|Boolean|否|否|||0：已交罚款；1：未交罚款

### 1.8预定记录
字段 | 类型 | 主键（外键） | 可以为空 | 默认值 | 约束 | 说明
:-:|:-:|:-:|:-:|:-:|:-:|:-:
|reserve_id|long|是|否|||预定记录流水号
|reserve_data|data|否|否|||预定日期
|book_id|int|外键|否|||预定图书id
|reader_id|long|外键|否|||预定读者id

##2.界面设计
### 2.1借书界面设计
![](./booklend.png '借书')

* 用例图参见：借书用例
* 类图参见：借书类
* 顺序图参见：借书顺序图
* API接口如下：
##### 1.获取读者信息：
* 功能：获取读者信息
* 请求地址：http://localhost:8080/bookManagetwo/selectBook.action
* 请求方法：POST
* 请求参数：

| 参数名称 | 必填 | 说明 |
|:-:|:-:|:-:|
|reader_id |是|读者的借书id号，验证读者
|method|是|固定为“POST”|


* 返回实例：
```
{
      "info": "查询成功",
      "data": {
          "图书ID":“1009”，
          "ISBN":“1009”，
          "书名":“数值分析”，
          "出版社":“数学出版社”，
          "价格":“45.0”，
          "借书时间":“2018-05-07”，
      },……
      "code": 200
  }
```

* 返回参数说明：

| 参数名称 |  说明 |
|:-:|:-:|
|info|查询成功|
|data|返回用户的借书数据|
|code|返回码|
##### 2.获取图书信息
* 功能：获取图书信息
* 请求地址：http://localhost:8080/bookManagetwo/lendBook.action
* 请求方法：POST
* 请求参数：

| 参数名称 | 必填 | 说明 |
|:-:|:-:|:-:|
|ISBN|是|图书的ISBN编码
|book_id|是|图书的id号
|method|是|固定为“POST”


* 返回实例：
```
{
      "info": "借书成功",
      "data": {
          "图书ID":“1009”，
          "ISBN":“1009”，
          "书名":“数值分析”，
          "出版社":“数学出版社”，
          "价格":“45.0”，
          "借书时间":“2018-05-07”，
      },……
      "code": 200
  }
```

* 返回参数说明：

| 参数名称 |  说明 |
|:-:|:-:|
|info|借书成功信息|
|data|返回用户的借书数据|
|code|返回码|
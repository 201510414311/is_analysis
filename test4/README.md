# 实验4：图书管理系统顺序图绘制
学号  | 班级 | 姓名  
:-:|:-:|:-:
201510414311    |     软工三班      |   彭启瑞
### 1.录入图书用例
#### 1.1PlantUMl源代码如下：

```
@startuml
actor librarian
participant "登录界面" as A
participant "校验信息" as B
participant "新书注册界面" as C
participant "扫描仪" as D
activate librarian
librarian ->A:登录系统
activate A
deactivate librarian

A->B:查找（用户名和密码）
activate B
deactivate A

B->B:校验信息
activate A
activate C
A->C:选择新书注册
deactivate B
deactivate A


activate librarian

librarian->D:扫描验证码
deactivate C
activate D


D->B:查找（图书验证码）
deactivate D
deactivate librarian

activate B
B->B:是否存在
activate C
B->C:传递信息（成功或失败）
deactivate B
deactivate C
@enduml
```
#### 1.2录入图书顺序图
![](./luru.png '描述')
#### 1.3录入图书说明
    管理员首先登录系统，登陆成功后，选择新书进行注册，扫描验证码，然后系统查找图书id，判断是否可以录入，返回信息。
### 2.查询书用例
#### 2.1PlantUMl源代码如下：
```
@startuml
actor user
participant "登录界面" as A
participant "校验信息" as B
participant "图书查询界面" as C
participant "数据库" as D
activate user
activate A
user->A:登录系统

deactivate user
activate B
A->B:查找（用户名和密码）

deactivate A

B->B:校验信息
deactivate B

activate A
activate C
A->C:进入
deactivate A

C->D:查询条件
activate D


D->C:返回查询结果
deactivate D
deactivate C
@enduml
```
#### 2.2查询书用例顺序图
![](./chaxunshu.png '描述')
#### 2.3查询书用例说明
    首先用户登录系统，登陆成功后，进入图书查询界面，输入查询的图书信息后，系统返回查询信息。
### 3.借书用例
#### 3.1借书用例PlantUMl源代码如下：
```
@startuml
actor librarian
participant "登录界面" as A
participant "借书记录" as B
participant "读者记录" as C
participant "读者" as D
activate librarian
activate A
librarian->A:登录系统
A->librarian:返回信息
deactivate A

activate D
D->librarian:发出借书请求
deactivate D
deactivate librarian

librarian->C:扫描读者ID
activate C
activate librarian
deactivate librarian
C->librarian:返回读者信息
deactivate C

activate librarian
librarian->B:扫描书籍ID
activate B
B->librarian:返回该书信息
deactivate B
deactivate librarian


B->B:记录借书记录
activate B
B->librarian:借阅成功
deactivate B

activate librarian
librarian->把书给读者
deactivate librarian
@enduml
```
#### 3.2借书用例时序图
![](./lend.png '描述')
#### 3.3借书用例说明
    图书管理员登录系统，读者向管理员发出借书请求，，图书管理员扫描读者的借书id，，然后扫描书籍的id，进行借书登记，然后管理员把书交给读者。
### 4.还书用例
#### 4.1还书用例PlantUMl源代码如下：
```
@startuml
actor librarian
participant "登录界面" as A
participant "还书记录" as B
participant "读者记录" as C
participant "读者" as D
activate librarian
activate A
librarian->A:登录系统
A->librarian:返回信息
deactivate A

activate D
D->librarian:发出还书请求
deactivate D
deactivate librarian

librarian->C:扫描读者ID
activate C
activate librarian
deactivate librarian
C->librarian:返回读者信息
deactivate C

activate librarian
librarian->B:扫描书籍ID
activate B
B->librarian:返回该书信息
deactivate B
deactivate librarian


B->B:记录还书记录
activate B
B->librarian:还书成功
deactivate B
@enduml
```
#### 4.2还书用例时序图
![](./return.png '描述')
#### 4.3还书用例说明
    图书管理员登录系统，读者向管理员发出还书请求，，图书管理员扫描读者的借书id，，然后扫描书籍的id，进行还书登记。
    
### 5.添加读者用例
#### 5.1添加读者PlantUMl源代码如下：
```
@startuml
actor librarian
participant "登录界面" as A
participant "读者记录" as B
participant "读者" as C
activate librarian
activate A
librarian->A:登录系统
A->librarian:返回信息
deactivate A

librarian->B:添加读者账户
deactivate librarian
activate B
B->B:检查账户

B->librarian:返回添加读者信息
deactivate B
activate librarian
librarian->C:将新开设的读者账户给读者
deactivate librarian
@enduml
```
#### 5.2添加读者时序图
![](./addR.png '描述')
#### 5.3添加读者用例说明
    图书管理员登录系统，开始添加读者账户，在读者记录中进行验证，返回添加的读者信息，把新开设的读者账户交给读者。

### 6.删除读者用例
#### 6.1Plantuml代码：
```
@startuml
actor librarian
participant "登录界面" as A
participant "查找读者界面" as B
participant "读者记录" as C
activate librarian
activate A
librarian->A:登录系统
A->librarian:返回信息
deactivate A

librarian->B:查找读者信息
deactivate librarian
activate B
B->C:查找信息（）
deactivate B

activate C
C->C:检查读者信息
C->B:返回读者信息
activate B
deactivate C
deactivate B

activate librarian
librarian->C:删除读者信息
activate C
C->librarian:返回删除成功信息
deactivate C
deactivate librarian
@enduml
```
#### 6.2删除读者时序图
![](./delectR.png '描述')
#### 6.3删除读者用例说明
    图书管理员登录系统，在查找读者界面中，输入查询信息，然后系统返回查询信息，管理员删除读者信息，系统返回删除读者成功的信息。

### 7.查询读者用例
#### 7.1plantUML代码：
```
@startuml
actor librarian
participant "登录界面" as A
participant "查找读者界面" as B
participant "读者记录" as C
activate librarian
activate A
librarian->A:登录系统
A->librarian:返回信息
deactivate A

librarian->B:查找读者信息
deactivate librarian
activate B
B->C:查找信息（）
deactivate B

activate C
C->C:检查读者信息
C->B:返回读者信息
activate B
deactivate C
deactivate B
@enduml
```
#### 7.2查询读者时序图：
![](./lookR.png '描述')
#### 7.3查询读者用例说明：
    用户登录系统，在查询读者界面，输入相关信息，系统验证返回信息。
    
### 8.删除图书用例
#### 8.1删除图书plantUml代码：
```
@startuml
actor librarian
participant "登录界面" as A
participant "数据库" as B
participant "图书记录" as C
activate librarian
activate A
librarian->A:登录系统
A->librarian:返回信息
deactivate A

librarian->B:删除数据库书目
deactivate librarian
activate B
B->C:删除馆藏书目（）
activate C
C->B:返回删除信息
deactivate C
deactivate B


B->B:更新数据库
activate B
B->librarian:删除成功
activate librarian
deactivate B
deactivate librarian
@enduml
```
#### 8.2相关时序图：
![](./delectB.png '描述')
#### 8.3删除图书说明：
    图书管理员登录系统后，对图书删除数据库书目，在图书列表中，删除管藏书目，返回删除信息，更新数据库，返回删除成功信息。
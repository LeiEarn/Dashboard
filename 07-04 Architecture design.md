## 架构设计

### 功能需求：

- 用户必须在授权登录并实名认证通过后才能进行其他操作，如任务的发布、接受等；
- 用户可以对自己在平台的个人信息进行修改如昵称、介绍等；
- 用户可以在平台注销账号；
- 用户可以发布任务，目前可以发布调查问卷、普通任务，在填完任务信息并确认无误后提交；
- 用户发布的任务可以限定接受的性别、年龄、信用等属性；
- 用户提交任务后，扣除任务所需要的赏金，由管理员确认后发布，若确认失败则返还赏金；
- 用户可以浏览推荐任务列表，全部任务列表；
- 用户点击任务可以浏览任务详情，根据需求接受任务，接受任务后可以根据实际情况线上或线下完成任务；
- 用户完成任务后，提交对应的证明，由发布者确认后即可获得赏金；
- 用户在发布任务后可以中止任务，接受任务后可以放弃任务，但会受到一定的信用度惩罚。
- 用户可以创建组织，以组织的身份进行任务的发布与接受。
- 管理人员需要内部的账号和密码才能进入管理系统。
- 管理员在管理系统中对用户的身份信息和任务信息的真实和合理程度进行审核。

### 性能需求：

- 本系统的主要应用为微信小程序，需要有较快的加载速度和页面渲染速度，所以页面上的逻辑处理不应该过于复杂，计算的内容不宜过度，以免造成界面卡顿。
- 页面内容呈现需要清晰、易读，具有能被普遍接受的色彩区分，操作的相应提示内容醒目。
- 语言表述尽可能不产生歧义，特殊名词特殊说明。



### 架构设计：

![Structure](/Users/guyunquan/Dashboard/images/Structure.png)

### 模块划分：

我们将后台分为**certificationServer**和**swaggerServer**两个部分，其中**certificationSever**用于与管理平台进行交互，为管理员提供用户管理、信息认证等功能接口；而**swaggerServer**用于与移动端的小程序进行交互，实现单独用户的创建、认证等一系列功能。

- ​	文件结构组织

```
.
├── server
│   ├── main.py
│   ├── c_server.py
│   ├── certificationServer
│   │   ├── routers
│   │   │   ├── prove.py
│   ├── swagger_server
│   │   ├── config.py
│   │   ├── constants.py
│   │   ├── encoder.py
│   │   ├── util.py
│   │   ├── model*
│   │   ├── moudules*
│   │   ├── controllers*
│   │   ├── routers
│   │   │   ├── auth.py
│   │   │   ├── img.py
│   │   │   ├── prove.py
│   │   ├── swagger
│   │   │   ├── swagger.yaml
│   │   ├── test
│   │   │   ├── ...
│   │   ├── utils
│   │   │   ├── ...
```

- `model`类代码文件结构

```
├── model
│   ├── Adminstrator.py
│   ├── Group.py
│   ├── Task.py
│   ├── User.py
```

- `module`包含各类管理系统以及登录持久化的实现:

```
├── moudules
│   ├── accessControlSystem.py
│   ├── AdminPlatform.py
│   ├── loginPersistent.py
│   ├── mailSystem.py
│   ├── taskManagementSystem.py
│   ├── userManagementSystem.py
```

- `controllers`包含各类路由所分发向的controller文件。真正的Controller模块实际上是controller文件以及modules文件夹下的同名模块共同结合发挥作用

```
├── controllers
│   ├── group_controller.py
│   ├── system_controller.py
│   ├── task_controller.py
│   ├── user_controller.py
```


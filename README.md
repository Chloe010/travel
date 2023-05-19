# travel-蛐蛐旅游网
### 一、实验目的和要求
#### 1、目的
######    蛐蛐旅游网是被作为一个项目的初始启动去书写的，为了巩固对于Java web该课程的学习基础和更好地展示页面以面对大二以后的学习要求和项目要求，提高综合运用能力，实践出真知，把一个项目或是一个实验完整的自己陈列一遍才能更加清晰的去了解和掌握它。
#### 2、要求
###### 1、运用Java web知识以及java后台语言
###### 2、个人独立完成
###### 3、代码条理清晰，实验效果良好

### 二、实验环境
##### 1、实验运行环境
######    Idea、 Maven快捷启动

##### 2、技术选型
######    Web层：
###### a)Servlet：前端控制器
###### b)html：视图
###### c)Filter：过滤器
###### d)BeanUtils：数据封装
###### e)Jackson：json序列化工具
######       Service层：
###### f)Javamail：java发送邮件工具
###### g)Redis：nosql内存数据库
###### h)Jedis：java的redis客户端
######       Dao层：
###### i)Mysql：数据库
###### j)Druid：数据库连接池
###### k)JdbcTemplate：jdbc的工具

### 三、实验环境
##### 1、创建数据库
###### 1.1 数据库汇总
![image](https://github.com/Chloe010/travel/assets/129756356/fd4638ad-189c-42dc-a760-1d620d66e628)
###### 1.2数据库_导航表
![image](https://github.com/Chloe010/travel/assets/129756356/3df859b2-1918-453c-ad6c-d0f78f3bdff4)
###### 1.3 数据库_收藏表
![image](https://github.com/Chloe010/travel/assets/129756356/73997ab5-a66a-4f7d-a813-cfd6f23a6aa2)
###### 1.4 数据库_详情页表
![image](https://github.com/Chloe010/travel/assets/129756356/d9e0f560-e02a-4e44-a1a5-d9c681dc5163)
###### 1.5 数据库_图片储存表
![image](https://github.com/Chloe010/travel/assets/129756356/76757b5c-0804-4879-8da5-306d1e000efe)
###### 1.6 客户信息表
![image](https://github.com/Chloe010/travel/assets/129756356/021319c1-0acf-41b8-819f-104fd06bbd29)
###### 1.7 显示信息表
![image](https://github.com/Chloe010/travel/assets/129756356/bb940450-2d02-4cbd-9462-a7be8311b835)

##### 2、代码框架构建
##### 2.1 连接数据库
###### 2.1.1 配置文件
######          druid.properties
######          jedis.properties
###### 2.1.2 创建工具类
######          JDBCUtils.java
![image](https://github.com/Chloe010/travel/assets/129756356/25f2fd75-3207-47b1-947c-1cd14b1a8c6f)
###### 2.1.3 创建实体类
![image](https://github.com/Chloe010/travel/assets/129756356/bb7c9f88-61ab-4485-adfb-55add4ecafea)
###### 2.1.4 使用dao用于对数据库进行操作
######          UserDao.java
######          UserDaoImpl.java
![image](https://github.com/Chloe010/travel/assets/129756356/c44f9b00-f7d0-4828-84c9-254dd5d0aa46)
###### 2.1.5 使用service用于连接dao与servlet
![image](https://github.com/Chloe010/travel/assets/129756356/95ac1365-c06e-49b7-862f-43330ad6fe17)
##### 2.2 前端页面书写
###### 2.2.1 前端页面
![image](https://github.com/Chloe010/travel/assets/129756356/7873c2a7-7183-4d12-8272-b60fd8c30344)

##### 2.3 bootstrap的导入
######       2.3.1 官网下载bootstrap资源
######       2.3.2 导入需要的css、js等
![image](https://github.com/Chloe010/travel/assets/129756356/f4341bea-debd-4e64-bc9b-a5cb1d52926d)

##### 2.4 前端页面显示与功能添加
###### 2.4.1 注册功能
![image](https://github.com/Chloe010/travel/assets/129756356/453ca826-7b63-4e95-9b88-5271a5274899)
###### a)静态页面代码的实现
###### b)表单校验（正则判断用户书写内容是否符合标准）
###### c)Html异步提交
###### d)编写servlet创建功能
######       验证码校验
######       注册校验
###### e)回到service和dao去数据库内进行校验

###### 2.4.2 用户点击邮件激活
![image](https://github.com/Chloe010/travel/assets/129756356/e5f91464-7a71-4ac9-b923-2e8ba6ab3f81)
###### 2.4.3 登录功能
![image](https://github.com/Chloe010/travel/assets/129756356/4902033f-b10b-49af-9302-8e5f2199236d)
###### 2.4.4 主页面显示用户姓名提示信息功能
![image](https://github.com/Chloe010/travel/assets/129756356/2a9084a9-2951-4218-a213-66acbc055db2)

![image](https://github.com/Chloe010/travel/assets/129756356/de6b4dd2-d803-4846-b3aa-6ff24679114c)

###### 2.4.5 退出
![image](https://github.com/Chloe010/travel/assets/129756356/20cc7f11-40d3-4ef1-97a2-4c64b3e49f46)

###### 2.4.6 导航栏展示
![image](https://github.com/Chloe010/travel/assets/129756356/f7824502-700e-4175-bf8d-1e6fd5cb1158)

###### 2.4.7 分类数据缓存
###### 分类的数据在每一次页面加载后都会重新请求数据库来加载，
###### 对数据库的压力比较大，而且分类的数据不会经常产生变化，
###### 所有可以使用redis来缓存这个数据。

###### 2.4.8 分页显示页面内容
###### 页面端：
######     在redis中查询cid，利用cid在页面传递与获取来实现分页功能
######     根据id查询不同类型的旅游路线数据进行展示
######     字符串拼接实现页码显示
###### 服务器端：
###### a)记录数等数据存储在数据库中
###### b)编写实体类装存页码、页数等数据
###### c)Servlet中去接受并处理参数
###### d)调用service查询实体类对象
###### e)将实体类对象序列化为json返回
###### f)Service、dao分别去设置方法和操作数据库

###### 2.4.9 旅游路线名称查询
![image](https://github.com/Chloe010/travel/assets/129756356/58dbbc9b-e7b2-4112-82d3-8933d7a1cba8)

###### a)静态页面代码实现
###### b)利用radis中的cid进行查询
###### c)字符串拼接实现页面跳转
###### d)Servlet对页面添加分页功能
###### e)Service、dao分别去设置方法和操作数据库

###### 2.4.10 详情页面
![image](https://github.com/Chloe010/travel/assets/129756356/69c2a7be-5b1a-472a-93ce-28cc3b5c973c)

###### 2.4.11 收藏功能页面显示
![image](https://github.com/Chloe010/travel/assets/129756356/d581cf19-68a4-486e-a2ee-b2bdd145f4e0)

###### a)访问数据库
###### b)判断用户是否登录
###### c)给出限制： 用户没有登录无法实现收藏功能
###### d)判断用户是否收藏
###### e)根据判断在页面给出不同显示
![image](https://github.com/Chloe010/travel/assets/129756356/c5ec8847-4003-40ad-a471-fd1e5abfa961)

###### 2.4.12 收藏次数的动态展示
![image](https://github.com/Chloe010/travel/assets/129756356/6e9f7755-e345-44ae-bcec-ba0d00a37fca)

###### 2.4.13 点击按钮收藏路线
![image](https://github.com/Chloe010/travel/assets/129756356/78753566-eaaa-47dd-809a-0c792ab87e3b)

##### 2.5 构建过滤器-WebFilter


### 备注：
####   1、启动项目前需要安装idea，下载并配置maven、bootstrap、radis等；
####   2、用户没登录前会受到一些限制：
####       比如收藏功能无法实现，详情页面只读等，可能控制台会报一些空指针错误，此时需要用户进行注册完登录（或直接登录数据库内的用户）即可解决报错问题，无需更改代码。
####   3、若在其他设备运行此项目，需要更改一些.properties的配置文件信息
####        比如数据库的连接等。



### 四、实验结果、分析、总结
#### 项目启动-数据库、Redis、Tomcat
#### 效果图（以下原创图片，侵权必究）
##### 首页
![image](https://github.com/Chloe010/travel/assets/129756356/2e89be39-fb19-4a00-8a33-b49e221d2ee3)
![image](https://github.com/Chloe010/travel/assets/129756356/6b8f5f6c-a60a-4b0d-a2fd-39013f5c0fa4)
![image](https://github.com/Chloe010/travel/assets/129756356/c0f1498e-4a18-44ac-8a0d-af4c7c221b1a)

##### 导航栏、搜索栏
![image](https://github.com/Chloe010/travel/assets/129756356/8e58bdcf-4dfe-4cfb-bcf8-28e3ae2229e9)
![image](https://github.com/Chloe010/travel/assets/129756356/9b5f42e6-831a-4c0e-9add-5dde6e50df18)

##### 注册页面
![image](https://github.com/Chloe010/travel/assets/129756356/7e0e2ad5-f4e2-4cbe-9cd6-e553678f93c1)
![image](https://github.com/Chloe010/travel/assets/129756356/c3c2baf5-6ba3-4eb4-92cc-cd745957520f)

##### 登录页面
![image](https://github.com/Chloe010/travel/assets/129756356/deeb71b2-6913-43e4-a4bd-80ffc41543bd)

##### 国内游
![image](https://github.com/Chloe010/travel/assets/129756356/ec89f1b7-8a14-4e2d-99f2-65ce9e59573d)
![image](https://github.com/Chloe010/travel/assets/129756356/e046a278-27e1-421e-9cd9-84656f24eb96)

##### 详情页面
![image](https://github.com/Chloe010/travel/assets/129756356/9f839661-1be9-47f8-8940-00383d400465)
![image](https://github.com/Chloe010/travel/assets/129756356/a996f689-9915-4db4-8d30-0212e5ddf81e)
![image](https://github.com/Chloe010/travel/assets/129756356/4a09aca5-912e-41f0-9e9d-0b44bcaac440)

##### 收藏排行榜
![image](https://github.com/Chloe010/travel/assets/129756356/fbd641c9-e422-4e23-88af-d2b294d4d3c1)















## 初始django
### 1.引入django
#### 应用程序
+ 控制台应用程序

  ![](C:\Users\Zhangpeng\Desktop\django\控制台.png)

+ 窗体应用程序

  ![](C:\Users\Zhangpeng\Desktop\django\窗体.png)

+ Web应用程序

  ![](C:\Users\Zhangpeng\Desktop\django\web.png)

#### 关于web应用程序
+ 接收request请求
+ url处理
+ 业务逻辑处理
+ 数据库的访问
+ 前端html页面加载
+ 填充页面的数据
+ 页面的response
#### 引入Web框架
对于Web开发复杂的工作，需要把工作模块化。实现相应工作运行独立性和层次性。这个就是Web框架作用
MVC全名是Model View Controller，是Web开发的通用标准，实现了业务逻辑、数据、界面的分离。目前所有的Web框架都遵循MVC标准
Django是Python平台最流行的Web框架

#### Python常见的Web框架
##### 1.Flask

![](C:\Users\Zhangpeng\Desktop\django\flask.jpg)

1：轻量级web框架，只有一个内核，默认依赖两个外部库：Jinja2 模板引擎和 Werkzeug WSGI 工具集，自由，灵活，可扩展性强，开发者可以根据需求自己造轮子
2：适用于做小型网站以及web服务的API，开发大型网站无压力，架构需自行设计
3：与关系型数据库结合不弱于Django，而与非关系型数据库的结合远远优于Django

##### 2.django

![](C:\Users\Zhangpeng\Desktop\django\django.jpg)

1：重量级web框架,功能齐全，提供一站式解决的思路，能让开发者不用在选择应用上花费大量时间
2：自带ORM(Object-Relational Mapping )和模板引擎，支持JinJa等非官方模板引擎，灵活度不高
3：自带ORM使Django和关系型数据库耦合度过高，如果要使用非关系型数据库，需要使用第三方库
4：自带数据库管理app
5：成熟、稳定、开发效率高、相对于Flask，Django的整体封闭性比较好，适合做企业级网站的开发
6：python web框架的先驱，第三方库丰富
7：上手容易，开发文档详细、完善、资料丰富

##### 3.tornado

![](C:\Users\Zhangpeng\Desktop\django\tornado.jpg)

1.基于非阻塞 I/O 的 Web 框架，它的设计理念是高并发、高性能
2.Tornado 采用了类似 Node.js 的事件循环机制，可以支持数万并发连接。
3.Tornado 的优点是性能高、适合高并发应用、易于扩展。
### 2.MVC和MVT
#### MVC

![](C:\Users\Zhangpeng\Desktop\django\mvc.png)

MVC : （Model-View-Controller）
 传统的Web开发的标准设计模型。

> C全拼为Controller: 用于接收请求，处理业务逻辑，与Model和View交互，返回结果。
> M全拼为Model: 主要封装对数据库层的访问，对数据库中的数据进行增、删、改、查操作。
> V全拼为View: 用于封装结果，生成页面展示的html内容。
#### MVT

![](C:\Users\Zhangpeng\Desktop\django\mvt.png)

MVT:  (Model-View-Template)
基于传统MVC的django的MVT框架

> M全拼为Model: 与MVC中的M功能相同，负责和数据库交互，进行数据处理。
> V全拼为View:与MVC中的C功能相同，接收请求，进行业务处理，返回应答。
> T全拼为Template:与MVC中的V功能相同，负责封装构造要返回的html。
#### Response三种场景
+ Response返回纯文本
+ Response返回一个静态页面
+ Response返回一个动态页面
### 3.Django环境部署
#### 查看版本
查看python版本
`print(sys.version)`
查看django版本
`print(django.__version__)`
#### pip工具
Python包管理工具，提供对Python查找、下载、安装、卸载的功能
+ 查找  `pip search django`  不支持
+ 安装  `pip install django`
+ 查看  `pip show django`
+ 卸载  `pip uninstall  django`
#### pip升级报错
+ 升级pip `pip install –upgrade pip`
+ 恢复pip `python –m ensurepip`
+ 修复模式升级 `python –m pip install –upgrade pip`
#### 安装django
+ 安装最新版本的django  `pip install django`
+ 安装指定版本的django  `pip install django==1.10.3`
+ 查看当前安装的Django   `pip show django`
+ 卸载django  `pip uninstall django`
### 4.Django虚拟环境部署
在一台计算机上可以通过虚拟环境实现多个版本Django的开发环境

![](C:\Users\Zhangpeng\Desktop\django\虚拟环境.png)

#### 1.虚拟环境安装步骤(windows平台)
安装虚拟环境
`pip install virtualenv virtualenvwrapper-win` 或 `pip install virtualenvwrapper-win`
设置存储环境的位置

![](C:\Users\Zhangpeng\Desktop\django\虚拟环境2.png)

创建虚拟环境
`mkvirtualenv 名称`
进入虚拟环境
`workon 名称`
退出虚拟环境
`deactivate 名称`
#### 2.git
1.创建虚拟环境
`python -m venv 名称`

#### 3.pycharm

### 5.Django结构介绍
项目 --- 一个容器
App --- 容器中的一个模块

#### 创建项目
`django-admin startproject project_name`

#### 创建App
`django-admin.py startapp app_name`
`python manage.py startapp app_name`
#### 项目相关配置
+ 注册App
```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'app01',
]
```
+ 配置数据库
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}
```
+ 配置语言及时区
```python
LANGUAGE_CODE = 'en-us'

TIME_ZONE = 'Asia/shanghai'
```
+ 配置静态文件路径
```python
STATICFILES_DIRS = [
    BASE_DIR / 'static'
]
```

## 用virtualenv创建一个独立的python环境

在cmd终端中安装virtualenv `pip install virtualenv`
	

cd到你需要创建的文件夹下使用 `virtualenv my_env` 创建环境，`my_env` 是文件名。

`virtualenv --no-site-packages my_env`是创建一个干净的python环境

激活 virtualenv使用命令 `my_env\Scripts\activate`,shell 提示将会附上激活的 virtualenv 名，被包含在括号中,其中 `my_env` 是你的创建的环境文件夹名

退出当前的`virtualenv`环境，`deactivate` 

### 安装Django
	在虚拟目录下 `pip install Django` 这个指令太卡了。
	用 `pip install -i https://pypi.douban.com/simple django` 非常的快
    
### 按照django by example的例子codeing...
先初始化项目文件结构 `django-admin startproject mysite`

我们需要为这些初始应用在数据库中创建表

	cd mysite
	python manage.py migrate

在终端中，在项目主目录下运行以下代码来开启开发服务器：
`python manage.py runserver`

然后在打开浏览器 [ http://127.0.0.1:8000/ ]( http://127.0.0.1:8000/ ), 就会看到一个告诉你项目成功运行的页面。

可以指定 **Django** 在定制的 **host** 和端口上运行开发服务，或者读取一个不同的配置文件。通过 **manage.py** 命令：
    
	python manage.py runserver 127.0.0.1:8001 \
	--settings=mysite.settings

## 创建第一个应用
`python manege.py startapp blog` 创建 **blog** 项目

**设计 blog 数据架构**

学习先到这里，还有工作任务需要完成，先切回去码代码了.....


















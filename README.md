## 用virtualenv创建一个独立的python环境

在cmd终端中安装virtualenv `pip install virtualenv`
	

cd到你需要创建的文件夹下使用 `virtualenv my_env` 创建环境，`my_env` 是文件名。

`virtualenv --no-site-packages my_env`是创建一个干净的python环境

激活 virtualenv使用命令 `my_env\Scripts\activate`,shell 提示将会附上激活的 virtualenv 名，被包含在括号中,其中 `my_env` 是你的创建的环境文件夹名

退出当前的`virtualenv`环境，`deactivate` 

### 安装Django
	在虚拟目录下 `pip install Django` 这个指令太卡了。
	用 `pip install -i https://pypi.douban.com/simple django` 非常的快
	最好注明django的版本 django==1.8.6
    
### 按照django by example的例子创建第一个项目
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
`python manage.py startapp blog` 创建 **blog** 项目

**设计 blog 数据架构**


## The Second Day...
安装文档中修改 `modle.py`, 需要在后面添加 `on_delete=models.CASCADE`， 否则会报错！
 
    author = models.ForeignKey(User, related_name='blog_posts', on_delete=models.CASCADE)

将后台修改为中文，将setting.py中的语言修改即可

    LANGUAGE_CODE = 'zh-Hans'

如何将models也显示为中文了？

将 `models.py` 中的字段都加上 `verbose_name="标题"` 类似的属性，并如下修改
	
	class Meta:
		verbose_name = '笔记'
		verbose_name_plural = '笔记'

而且我们可以通过终端来打开shell `python manage.py shell`

并且我们可以通过一下的形式来 创建一个记录

    >>> from django.contrib.auth.models import User
    >>> from blog.models import Post
    >>> user = User.objects.get(username='admin')
    >>> post = Post.objects.create(title='One more post',
    			slug='one-more-post',
    			body='Post body.',
    			author=user)
    >>> post.save()
#####
	那么我想，我们就可以通过一脚本的形式来管理后台拉！？


























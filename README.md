## 用virtualenv创建一个独立的python环境

在cmd终端中安装virtualenv `pip install virtualenv`
	

cd到你需要创建的文件夹下使用 `virtualenv my_env` 创建环境，`my_env` 是文件名。

`virtualenv --no-site-packages my_env`是创建一个干净的python环境

激活 virtualenv使用命令 `my_env\Scripts\activate`,shell 提示将会附上激活的 virtualenv 名，被包含在括号中,其中 `my_env` 是你的创建的环境文件夹名

退出当前的`virtualenv`环境，`deactivate` 

### 安装Django
在虚拟目录下 `pip install Django`









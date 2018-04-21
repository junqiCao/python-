# python环境管理方法

* 步骤一： 安装pip3  
`$ sudo apt-get install python-pip`

* 步骤二： 安装 virtualenv
`$ sudo apt-get install python-virtualenv`

* 步骤三： 安装virtualenvwrapper
`$ pip3 install virtualenvwrapper`

* 步骤四： 配置虚拟管理环境

搜索virtualenvwrapper.sh的位置，利用下面的指令可以获取文件位置。
`$ find / -name virtualenvwrapper | grep wrapper`
* 步骤五： 创建虚拟环境的母文件夹
例如主目录先创建一个文件夹`.virtualEnvs`，此处是隐藏文件夹，利用`Ctrl+h`可以将其显示
`$ mkdir -p ~/.virtualEnvs`

* 步骤六： 配置bashrc文件

打开bashrc
`$ gedit ~/.bashrc`

在该文件的最后加上这几句话，修改WORK_HOME的文件路径
```
# added by virtualenvwrapper
export WORKON_HOME=~/.virtualEnvs
export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
source ~/.local/bin/virtualenvwrapper.sh
```
保存并关闭，刷新bashrc文件
`$ source ~/.bashrc`
* 步骤七： virtualenvwrapper的使用

在虚拟环境目录下建立语言为python3的caffe环境，同时会在虚拟环境主目录下查看caffe文件夹：

`$ mkvirtualenv -p python3 caffe`

启动caffe环境
`$ workon caffe`

退出caffe环境
`(caffe) $ deactivate`

删除虚拟环境：

`$ rmvirtualenv caffe`


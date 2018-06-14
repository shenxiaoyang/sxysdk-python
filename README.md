sxysdk-python
=============
sxy python sdk

## 简介
此项目主要是制作python sxysdk包，然后上传到pypi上。
sxysdk包主要是封装了一些常用的操作，涉及到一些不同类型系统（Windows、Linux、VMware）远程命令调用、数据库操作、服务器电源管理等。

## 依赖说明
此项目基于Python 3.5

## 目录结构说明
|--sxysdk
|   |--Database                     //数据库相关
|   |   |--OracleDB.py              //Oracle数据相关操作
|   |--Examples
|   |   |--OracleDB_Test_Script.py  //Oracle数据库操作例子
|   |--FileCopy
|   |   |--FileCopy.py
|   |--IPMI
|   |   |--IPMI.py
|   |--PsExc
|   |   |--PsExc.py
|   |--SSH
|   |   |--SSH.py
|   |--Time
|   |   |--Time.py
|   |--Tools
|   |--vSphereCLI
|   |   |--vSphereCLI.py
|   |--WinCmd
|   |   |--WindowsCMD.py
|   |--__init__.py
|--.gitignore
|--__init__.py
|--LICENSE
|--MANIFEST.in
|--pip_upload_script.py
|--README.md
|--setup.py

## 打包说明
### 打包相关文件
setup.py、pip_upload_script.py、MANIFEST.in
setup.py 为主要的打包配置文件
pip_upload_script.py 包含了上传到pypi源的命令
MANIFEST.in 配置了包含需要上传的资源文件列表

### 打包流程
1、在https://pypi.org/ 上注册一个账号
2、编辑本地pip配置文件 %UserProfile%\\.pypirc，没有.pypirc文件则新建一个。（如何在Windows下新建.开头的文件自行百度）
3、编写.pypirc文件
```
[distutils]
index-servers =
  pypi
  pypitest

[pypi]
repository=https://pypi.python.org/pypi
username=你的pypi用户名
password=你的pypi密码

[pypitest]
repository=https://testpypi.python.org/pypi
username=你的pypi用户名
password=你的pypi密码
```
4、使用pip_upload_script.py脚本打包上传自定义包

## 安装说明
1、包上传到pypi仓库后，可以直接使用pip install sxysdk安装
2、如果是升级，则使用pip install -U sxysdk升级

## sxysdk 功能介绍
### sxysdk.PsExc.PsExc
doRemoteWinCmd() 远程执行Windows系统命令，调用PsExec.exe(PsExec64.exe)实现

### sxysdk.SSH.SSH
ssh() 远程执行Linux系统命令，调用paramiko模块实现


## 历史记录
0.0.18 初版，框架构建，支持doRemoteWinCmd、ssh
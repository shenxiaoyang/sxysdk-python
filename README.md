sxysdk-python
=============
sxy python sdk

## 简介
此项目主要是制作python sxysdk包，然后上传到pypi上.<br />
sxysdk包主要是封装了一些常用的操作，涉及到一些不同类型系统（Windows、Linux、VMware）远程命令调用、数据库操作、服务器电源管理等。<br />

## 依赖说明
此项目基于Python 3.5

## 目录结构说明
|--sxysdk <br />
|   |--Database                     //数据库相关 <br />
|   |   |--OracleDB.py              //Oracle数据相关操作 <br />
|   |--Examples <br />
|   |   |--OracleDB_Test_Script.py  //Oracle数据库操作例子 <br />
|   |--FileCopy <br />
|   |   |--FileCopy.py <br />
|   |--IPMI <br />
|   |   |--IPMI.py <br />
|   |--PsExc <br />
|   |   |--PsExc.py <br />
|   |--SSH <br />
|   |   |--SSH.py <br />
|   |--Time <br />
|   |   |--Time.py <br />
|   |--Tools <br />
|   |--vSphereCLI <br />
|   |   |--vSphereCLI.py <br />
|   |--WinCmd <br />
|   |   |--WindowsCMD.py <br />
|   |--__init__.py <br />
|--.gitignore <br />
|--__init__.py <br />
|--LICENSE <br />
|--MANIFEST.in <br />
|--pip_upload_script.py <br />
|--README.md <br />
|--setup.py <br />

## 打包说明
### 打包相关文件
setup.py、pip_upload_script.py、MANIFEST.in <br />
setup.py 为主要的打包配置文件 <br />
pip_upload_script.py 包含了上传到pypi源的命令 <br />
MANIFEST.in 配置了包含需要上传的资源文件列表 <br />

### 打包流程
1、在https://pypi.org/ 上注册一个账号 <br />
2、编辑本地pip配置文件 %UserProfile%\\.pypirc，没有.pypirc文件则新建一个。（如何在Windows下新建.开头的文件自行百度） <br />
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
1、包上传到pypi仓库后，可以直接使用pip install sxysdk安装 <br />
2、如果是升级，则使用pip install -U sxysdk升级 <br />

## sxysdk 功能介绍
### sxysdk.Database.OracleDB
OracleDB 类 提供了连接Oracle、查询、插入Oracle表空间方法 <br />

### sxysdk.FileCopy.FileCopy
download_file 使用paramiko模块下载远程计算机文件（支持Linux和Windows） <br />
upload_file 使用paramiko模块上传远程计算机文件（支持Linux和Windows） <br />
win_download_file 使用Windows管道命令下载远程计算机文件（仅支持Windows） <br />
win_download_dir 使用Windows管道命令下载远程计算机目录（仅支持Windows） <br />

### sxy.IPMI.IPMI
power_on 调用ipmitool.exe远程打开计算机电源 <br />
power_off 调用ipmitool.exe远程关闭计算机电源 <br />
power_status 调用ipmitool.exe查看远程计算机电源状态 <br />

### sxysdk.PsExc.PsExc
doRemoteWinCmd 远程执行Windows系统命令，调用PsExec.exe(PsExec64.exe)实现 <br />
winRebootRemoteMachine 使用PsExec工具重启远程Windows计算机 <br />
winShutdownRemoteMachine 使用PsExec工具关闭远程Windows计算机 <br />
winBangRemoteMachine 使用PsExec工具bang远程Windows计算机（手动蓝屏） <br />

### sxysdk.SSH.SSH
ssh 远程执行Linux系统命令，调用paramiko模块实现 <br />
linuxShutDownRemoteMachine 使用paramiko模块，实现关闭远程Linux计算机 <br />
linuxRebootRemoteMachine 使用paramiko模块，实现重启远程Linux计算机 <br />

### sxysdk.Time.Time
getCurrentDatetimeString 获取本计算机的当前时间字符串 <br />
get_beijin_time_str 获取北京时间字符串 <br />
get_local_time_str 获取本计算机当前时间字符串 <br />
get_linux_time_str 获取远程linux计算机时间字符串 <br />
get_windows_time_str 获取远程windows计算机时间字符串 <br />
time_minus 时间字符串比较 <br />
set_windows_time 设置远程windows计算机时间 <br />
set_linux_time 设置远程linux计算机时间 <br />

### sxysdk.vSphereCLI.vSphereCLI
startVirtualMachineSoft 使用vmware-cmd.pl命令行工具远程打开VM电源 <br />
startVirtualMachineHard 使用vmware-cmd.pl命令行工具远程打开VM电源 <br />
stopVirtualMachineSoft 使用vmware-cmd.pl命令行工具远程关闭VM电源 <br />
stopVirtualMachineHard 使用vmware-cmd.pl命令行工具远程关闭VM电源 <br />
getVirtualMachineList 使用vmware-cmd.pl命令行工具获取虚拟机主机的VM名字 <br />
callVirtualMachineCommadLine 封装vmware-cmd.pl命令行工具 <br />
getVmxByVirtualMachineName 通过VM名字获取vmx配置文件路径 <br />

### sxysdk.WinCmd.WindowsCMD
pingIP ping远程计算机，测试其是否网络通畅 <br />
queryPIDByProcess 根据远程计算机的进程名查询其PID <br />
queryProcess 查询远程计算机的进程名列表 <br />
killProcess 强制杀死某个远程计算机的进程名 <br />
copyfileTo 拷贝文件到远程计算机 <br />


## 历史记录
0.0.20 加入了Database子模块、FileCopy子模块、IPMI子模块、Time子模块、vShereCLI子模块、WinCmd子模块
0.0.18 初版，框架构建，支持doRemoteWinCmd、ssh
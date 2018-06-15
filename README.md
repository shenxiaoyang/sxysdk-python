sxysdk-python
=============
sxy python sdk

## ���
����Ŀ��Ҫ������python sxysdk����Ȼ���ϴ���pypi��.<br />
sxysdk����Ҫ�Ƿ�װ��һЩ���õĲ������漰��һЩ��ͬ����ϵͳ��Windows��Linux��VMware��Զ��������á����ݿ��������������Դ����ȡ�<br />

## ����˵��
����Ŀ����Python 3.5

## Ŀ¼�ṹ˵��
|--sxysdk <br />
|   |--Database                     //���ݿ���� <br />
|   |   |--OracleDB.py              //Oracle������ز��� <br />
|   |--Examples <br />
|   |   |--OracleDB_Test_Script.py  //Oracle���ݿ�������� <br />
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

## ���˵��
### �������ļ�
setup.py��pip_upload_script.py��MANIFEST.in <br />
setup.py Ϊ��Ҫ�Ĵ�������ļ� <br />
pip_upload_script.py �������ϴ���pypiԴ������ <br />
MANIFEST.in �����˰�����Ҫ�ϴ�����Դ�ļ��б� <br />

### �������
1����https://pypi.org/ ��ע��һ���˺� <br />
2���༭����pip�����ļ� %UserProfile%\\.pypirc��û��.pypirc�ļ����½�һ�����������Windows���½�.��ͷ���ļ����аٶȣ� <br />
3����д.pypirc�ļ�
```
[distutils]
index-servers =
  pypi
  pypitest

[pypi]
repository=https://pypi.python.org/pypi
username=���pypi�û���
password=���pypi����

[pypitest]
repository=https://testpypi.python.org/pypi
username=���pypi�û���
password=���pypi����
```
4��ʹ��pip_upload_script.py�ű�����ϴ��Զ����

## ��װ˵��
1�����ϴ���pypi�ֿ�󣬿���ֱ��ʹ��pip install sxysdk��װ <br />
2���������������ʹ��pip install -U sxysdk���� <br />

## sxysdk ���ܽ���
### sxysdk.Database.OracleDB
OracleDB �� �ṩ������Oracle����ѯ������Oracle��ռ䷽�� <br />

### sxysdk.FileCopy.FileCopy
download_file ʹ��paramikoģ������Զ�̼�����ļ���֧��Linux��Windows�� <br />
upload_file ʹ��paramikoģ���ϴ�Զ�̼�����ļ���֧��Linux��Windows�� <br />
win_download_file ʹ��Windows�ܵ���������Զ�̼�����ļ�����֧��Windows�� <br />
win_download_dir ʹ��Windows�ܵ���������Զ�̼����Ŀ¼����֧��Windows�� <br />

### sxy.IPMI.IPMI
power_on ����ipmitool.exeԶ�̴򿪼������Դ <br />
power_off ����ipmitool.exeԶ�̹رռ������Դ <br />
power_status ����ipmitool.exe�鿴Զ�̼������Դ״̬ <br />

### sxysdk.PsExc.PsExc
doRemoteWinCmd Զ��ִ��Windowsϵͳ�������PsExec.exe(PsExec64.exe)ʵ�� <br />
winRebootRemoteMachine ʹ��PsExec��������Զ��Windows����� <br />
winShutdownRemoteMachine ʹ��PsExec���߹ر�Զ��Windows����� <br />
winBangRemoteMachine ʹ��PsExec����bangԶ��Windows��������ֶ������� <br />

### sxysdk.SSH.SSH
ssh Զ��ִ��Linuxϵͳ�������paramikoģ��ʵ�� <br />
linuxShutDownRemoteMachine ʹ��paramikoģ�飬ʵ�ֹر�Զ��Linux����� <br />
linuxRebootRemoteMachine ʹ��paramikoģ�飬ʵ������Զ��Linux����� <br />

### sxysdk.Time.Time
getCurrentDatetimeString ��ȡ��������ĵ�ǰʱ���ַ��� <br />
get_beijin_time_str ��ȡ����ʱ���ַ��� <br />
get_local_time_str ��ȡ���������ǰʱ���ַ��� <br />
get_linux_time_str ��ȡԶ��linux�����ʱ���ַ��� <br />
get_windows_time_str ��ȡԶ��windows�����ʱ���ַ��� <br />
time_minus ʱ���ַ����Ƚ� <br />
set_windows_time ����Զ��windows�����ʱ�� <br />
set_linux_time ����Զ��linux�����ʱ�� <br />

### sxysdk.vSphereCLI.vSphereCLI
startVirtualMachineSoft ʹ��vmware-cmd.pl�����й���Զ�̴�VM��Դ <br />
startVirtualMachineHard ʹ��vmware-cmd.pl�����й���Զ�̴�VM��Դ <br />
stopVirtualMachineSoft ʹ��vmware-cmd.pl�����й���Զ�̹ر�VM��Դ <br />
stopVirtualMachineHard ʹ��vmware-cmd.pl�����й���Զ�̹ر�VM��Դ <br />
getVirtualMachineList ʹ��vmware-cmd.pl�����й��߻�ȡ�����������VM���� <br />
callVirtualMachineCommadLine ��װvmware-cmd.pl�����й��� <br />
getVmxByVirtualMachineName ͨ��VM���ֻ�ȡvmx�����ļ�·�� <br />

### sxysdk.WinCmd.WindowsCMD
pingIP pingԶ�̼�������������Ƿ�����ͨ�� <br />
queryPIDByProcess ����Զ�̼�����Ľ�������ѯ��PID <br />
queryProcess ��ѯԶ�̼�����Ľ������б� <br />
killProcess ǿ��ɱ��ĳ��Զ�̼�����Ľ����� <br />
copyfileTo �����ļ���Զ�̼���� <br />


## ��ʷ��¼
0.0.20 ������Database��ģ�顢FileCopy��ģ�顢IPMI��ģ�顢Time��ģ�顢vShereCLI��ģ�顢WinCmd��ģ��
0.0.18 ���棬��ܹ�����֧��doRemoteWinCmd��ssh
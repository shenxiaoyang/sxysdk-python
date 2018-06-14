sxysdk-python
=============
sxy python sdk

## ���
����Ŀ��Ҫ������python sxysdk����Ȼ���ϴ���pypi�ϡ�
sxysdk����Ҫ�Ƿ�װ��һЩ���õĲ������漰��һЩ��ͬ����ϵͳ��Windows��Linux��VMware��Զ��������á����ݿ��������������Դ����ȡ�

## ����˵��
����Ŀ����Python 3.5

## Ŀ¼�ṹ˵��
|--sxysdk
|   |--Database                     //���ݿ����
|   |   |--OracleDB.py              //Oracle������ز���
|   |--Examples
|   |   |--OracleDB_Test_Script.py  //Oracle���ݿ��������
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

## ���˵��
### �������ļ�
setup.py��pip_upload_script.py��MANIFEST.in
setup.py Ϊ��Ҫ�Ĵ�������ļ�
pip_upload_script.py �������ϴ���pypiԴ������
MANIFEST.in �����˰�����Ҫ�ϴ�����Դ�ļ��б�

### �������
1����https://pypi.org/ ��ע��һ���˺�
2���༭����pip�����ļ� %UserProfile%\\.pypirc��û��.pypirc�ļ����½�һ�����������Windows���½�.��ͷ���ļ����аٶȣ�
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
1�����ϴ���pypi�ֿ�󣬿���ֱ��ʹ��pip install sxysdk��װ
2���������������ʹ��pip install -U sxysdk����

## sxysdk ���ܽ���
### sxysdk.PsExc.PsExc
doRemoteWinCmd() Զ��ִ��Windowsϵͳ�������PsExec.exe(PsExec64.exe)ʵ��

### sxysdk.SSH.SSH
ssh() Զ��ִ��Linuxϵͳ�������paramikoģ��ʵ��


## ��ʷ��¼
0.0.18 ���棬��ܹ�����֧��doRemoteWinCmd��ssh
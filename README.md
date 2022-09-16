# anjuna-SGX

```
$ wget https://s3-us-west-1.amazonaws.com/anjuna-security.vault/anjuna-vault-0.22.0005.bin
$ chmod +x anjuna-vault-0.22.0005.bin 
$ sudo apt-get install linux-headers-$(uname -r)
$ ./anjuna-vault-0.22.0005.bin 

```

```
$ ./anjuna-vault-0.22.0005.bin 

 Anjuna SGX Runtime self-extracting installer

Archive extracted to anjuna-vault-0.22.0005

Checking for Operating System
Found Ubuntu 18.04.6 LTS

Checking for SGX Hardware support
This host is SGX capable (sgx_is_capable => 1)


Checking for OS packages

Checking for Intel SGX Driver
Intel Driver not installed => will be compiled

Checking for Anjuna SGX module
Anjuna SGX module not installed => will be compiled

Compiling Anjuna SGX module
Anjuna SGX module compilation succeeded

Installing Intel ISGX module

Installing Anjuna SGX module

Kernel module status:
anjuna                 16384  0
isgx                   53248  0

Checking for Python 3
Python 3 already installed

Checking for Python 3 packages
The following packages were automatically installed and are no longer required:
  amd64-microcode intel-microcode iucode-tool linux-image-generic-hwe-18.04 thermald
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  dh-python libexpat1-dev libpython3-dev libpython3.6-dev python-pip-whl python3-dev python3-distutils python3-lib2to3
  python3-setuptools python3-wheel python3.6-dev
Suggested packages:
  python-setuptools-doc
The following NEW packages will be installed:
  dh-python libexpat1-dev libpython3-dev libpython3.6-dev python-pip-whl python3-dev python3-distutils python3-lib2to3
  python3-pip python3-setuptools python3-wheel python3.6-dev
0 upgraded, 12 newly installed, 0 to remove and 0 not upgraded.
Need to get 47.9 MB of archives.
After this operation, 85.4 MB of additional disk space will be used.
Selecting previously unselected package python3-lib2to3.
(Reading database ... 183353 files and directories currently installed.)
Preparing to unpack .../00-python3-lib2to3_3.6.9-1~18.04_all.deb ...
Unpacking python3-lib2to3 (3.6.9-1~18.04) ...
Selecting previously unselected package python3-distutils.
Preparing to unpack .../01-python3-distutils_3.6.9-1~18.04_all.deb ...
Unpacking python3-distutils (3.6.9-1~18.04) ...
Selecting previously unselected package dh-python.
Preparing to unpack .../02-dh-python_3.20180325ubuntu2_all.deb ...
Unpacking dh-python (3.20180325ubuntu2) ...
Selecting previously unselected package libexpat1-dev:amd64.
Preparing to unpack .../03-libexpat1-dev_2.2.5-3ubuntu0.7_amd64.deb ...
Unpacking libexpat1-dev:amd64 (2.2.5-3ubuntu0.7) ...
Selecting previously unselected package libpython3.6-dev:amd64.
Preparing to unpack .../04-libpython3.6-dev_3.6.9-1~18.04ubuntu1.8_amd64.deb ...
Unpacking libpython3.6-dev:amd64 (3.6.9-1~18.04ubuntu1.8) ...
Selecting previously unselected package libpython3-dev:amd64.
Preparing to unpack .../05-libpython3-dev_3.6.7-1~18.04_amd64.deb ...
Unpacking libpython3-dev:amd64 (3.6.7-1~18.04) ...
Selecting previously unselected package python-pip-whl.
Preparing to unpack .../06-python-pip-whl_9.0.1-2.3~ubuntu1.18.04.5_all.deb ...
Unpacking python-pip-whl (9.0.1-2.3~ubuntu1.18.04.5) ...
Selecting previously unselected package python3.6-dev.
Preparing to unpack .../07-python3.6-dev_3.6.9-1~18.04ubuntu1.8_amd64.deb ...
Unpacking python3.6-dev (3.6.9-1~18.04ubuntu1.8) ...
Selecting previously unselected package python3-dev.
Preparing to unpack .../08-python3-dev_3.6.7-1~18.04_amd64.deb ...
Unpacking python3-dev (3.6.7-1~18.04) ...
Selecting previously unselected package python3-pip.
Preparing to unpack .../09-python3-pip_9.0.1-2.3~ubuntu1.18.04.5_all.deb ...
Unpacking python3-pip (9.0.1-2.3~ubuntu1.18.04.5) ...
Selecting previously unselected package python3-setuptools.
Preparing to unpack .../10-python3-setuptools_39.0.1-2_all.deb ...
Unpacking python3-setuptools (39.0.1-2) ...
Selecting previously unselected package python3-wheel.
Preparing to unpack .../11-python3-wheel_0.30.0-0.2_all.deb ...
Unpacking python3-wheel (0.30.0-0.2) ...
Setting up python-pip-whl (9.0.1-2.3~ubuntu1.18.04.5) ...
Setting up python3-wheel (0.30.0-0.2) ...
Setting up libexpat1-dev:amd64 (2.2.5-3ubuntu0.7) ...
Setting up python3-lib2to3 (3.6.9-1~18.04) ...
Setting up python3-distutils (3.6.9-1~18.04) ...
Setting up libpython3.6-dev:amd64 (3.6.9-1~18.04ubuntu1.8) ...
Setting up python3-pip (9.0.1-2.3~ubuntu1.18.04.5) ...
Setting up python3-setuptools (39.0.1-2) ...
Setting up python3.6-dev (3.6.9-1~18.04ubuntu1.8) ...
Setting up dh-python (3.20180325ubuntu2) ...
Setting up libpython3-dev:amd64 (3.6.7-1~18.04) ...
Setting up python3-dev (3.6.7-1~18.04) ...
Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
- Package [python3-pip]: installed
[ ok ] Restarting procps (via systemctl): procps.service.


Generating MRSIGNER certificate
MRSIGNER certificate generated: signing/enclave-key.pem

Summary:
Anjuna SGX Runtime fully installed

Execute the following commands to set up your environment

source /mnt/sgx/anjuna-vault-0.22.0005/env.sh
```

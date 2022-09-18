# anjuna-SGX

# 1. Install Ubuntu 16.04 LTS
```
$ uname -r
4.15.0-142-generic
```

# 2. Disable Hyper Threading in BIOS menu
If this entry says "1", it means only one thread is available per core. Hence Hyper-Threading is disabled. If it says "2", it means Hyper-Threading is enabled.
```
$ lscpu |grep Thread
Thread(s) per core:    1
```

# 3. Download and Install anjuna Runtime
```
$ wget https://s3-us-west-1.amazonaws.com/anjuna-security.vault/anjuna-vault-0.22.0005.bin
$ chmod +x anjuna-vault-0.22.0005.bin 
$ ./anjuna-vault-0.22.0005.bin 
```

```
$ ./anjuna-vault-0.22.0005.bin 

 Anjuna SGX Runtime self-extracting installer

Archive extracted to anjuna-vault-0.22.0005

... snip ...

Summary:
Anjuna SGX Runtime fully installed

Execute the following commands to set up your environment

source /mnt/sgx/anjuna-vault-0.22.0005/env.sh
```

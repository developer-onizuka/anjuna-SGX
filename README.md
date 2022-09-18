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

# 4. Tutorial
```
$ export ANJUNA_HOME=/mnt/sgx/anjuna-vault-0.22.0005
$ source $ANJUNA_HOME/env.sh
```
```
$ mkdir vault-tutorial
$ cd vault-tutorial
```
```
$ anjuna-tutorial-quick-vault-setup --port 9980
Launching Anjuna Tutorial Vault instance...
Initializing Vault...
Unsealing Vault...
Using unseal key #1...
Using unseal key #2...
Using unseal key #3...
Vault server unsealed
Connection to Vault...
Generating test wildcard certificate...
TLS certificates generated
Warning:
To use the Vault TLS certificate, the following entry should be added to /etc/hosts:
127.0.0.1 vault.local.test

Run the following command to add this entry to /etc/hosts
    $ echo '127.0.0.1 vault.local.test' | sudo tee -a /etc/hosts

Success: A test Vault configuration was created!
Vault Address          : https://vault.local.test:9980

... snip ...

```
```
$ echo '127.0.0.1 vault.local.test' | sudo tee -a /etc/hosts
```
```
$ Runtime/anjuna-runtime --provision vault
Anjuna Runtime version 0.22.0005, Copyright (C) Anjuna Security, Inc. All rights reserved.
Enclave initialized:
    Enclave base address:           0x0000000000000000
    Enclave size:                   2GB
    Maximum number of threads:      64
    Enclave attributes:             0x0000000000000007
    Enclave SSA frame size:         1
    
... snip ...

The provisioning for this enclave has been completed:
- provisioning secret key (SGX-encrypted) : vault.key.sealed
- provisioning public key                 : vault.provision.key
- SGX report created                      : vault.report.bin
- SGX quote created                       : vault.quote.bin

Secrets can be provisioned for this enclave by encrypting files using
the provisioning public key [vault.provision.key]:

    anjuna-prov-seal --public-key vault.provision.key FILE_TO_BE_SEALED


Before provisioning secrets for this enclave, make sure to run the Anjuna Attestation utility (anjuna-check-attestation)
to confirm that this enclave can be trusted:

    anjuna-check-attestation --quote-file vault.quote.bin --rsa-key-file vault.provision.key
```

```
$ anjuna-check-attestation --quote-file vault.quote.bin --rsa-key-file vault.provision.key
INFO SHA512 of RSA DER BYTES: 

... snip ...

DEBUG Attestation complete                         
INFO Quote status: OK
```
```
$ anjuna-prov-seal --public-key vault.provision.key config/vault_config.hcl
Sealed config/vault_config.hcl to config/vault_config.hcl.sealed

$ anjuna-prov-seal --public-key vault.provision.key config/vault_tls.key
Sealed config/vault_tls.key to config/vault_tls.key.sealed
```
```
$ export VAULT_API_ADDR='http://127.0.0.1:9980'
$ Runtime/anjuna-runtime vault 
```

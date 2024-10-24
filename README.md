Welcome to the ExpressPQDelivery Project
==============================
The epqd_client_lib is a library that implements ExpressPQDelivery handshake for client side based on OpenSSL.

## How to start(Linux Ubuntu)
### Set compile option
```bash
./Configure
```
### Make
```bash
make depend && make
```
### Install
```bash
sudo make install
```
### Build OQS-provider
```bash
cd epqd_client_lib
```
```bash
git clone https://github.com/open-quantum-safe/oqs-provider.git  
cd oqs-provider  
```

```bash
git reset --hard 49bb2d271ec64f35f5a3905577f2dbc2c1b8d07d  
```
```bash
sudo su  
cmake -DOQS_KEM_ENCODERS=ON -S . -B _build && cmake --build _build && cmake --install _build  
```
### Setting openssl.cnf file
In the case of `oqs-provider` add these lines to achieve this:

```
[provider_sect]
default = default_sect
oqsprovider = oqsprovider_sect
[oqsprovider_sect]
activate = 1
```


## TroubleShooting
```bash
OPENSSL_ROOT_DIR=~/epqd_client_lib/ OPENSSL_INSTALL=/usr/local/lib64 ./scripts/fullbuild.sh  
```

```bash
export OPENSSL_CONF=/etc/ssl/openssl.cnf
```


## Reference
https://www.lesstif.com/system-admin/openssl-compile-build-6291508.html
https://github.com/open-quantum-safe/oqs-provider/blob/main/USAGE.md?plain=1
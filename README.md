Welcome to the ExpressPQDelivery Project
==============================
The epqd_client_lib is a library that implements ExpressPQDelivery handshake for client side based on OpenSSL.

## How to start(Linux Ubuntu)
### Set compile option
./Configure

### Make
make depend && make

### Install
sudo make install

### Build OQS-provider
cd epqd_client_lib  
git clone https://github.com/open-quantum-safe/oqs-provider.git  
cd oqs-provider  
git reset --hard 49bb2d271ec64f35f5a3905577f2dbc2c1b8d07d  
sudo su  
cmake -DOQS_KEM_ENCODERS=ON -S . -B _build && cmake --build _build && cmake --install _build  

### Setting openssl.cnf file



## TroubleShooting


OPENSSL_ROOT_DIR=~/epqd_client_lib/ OPENSSL_INSTALL=/usr/local/lib64 ./scripts/fullbuild.sh  



## Reference
https://www.lesstif.com/system-admin/openssl-compile-build-6291508.html
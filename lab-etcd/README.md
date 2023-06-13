# Exemple de gestion de la base de donnees avec ETCD 

## A faire sur un noeud, pas sur le master 
```shell
sudo snap install go --classic
wget https://github.com/etcd-io/etcd/archive/refs/tags/v3.5.0.tar.gz
tar -zxvf v3.5.0.tar.gz
cd etcd-3.5.0
./build
cd bin
./etcd &
./etcdctl put key1 value1
./etcdctl get key1
```
## Copy etcdctl on the master
```shell
scp .ssh/id_rsa 10.128.15.222:/home/ubuntu/.ssh/id_rsa
scp 10.128.15.222:/home/ubuntu/etcd-3.5.0/bin/etcdctl .
```

## On the master, enter this line for getting ectd key name of kubernetes objects
```shell
sudo ETCDCTL_API=3 etcdctl --endpoints https://127.0.0.1:2379 --cert=/etc/ssl/etcd/ssl/node-master-1.pem --key=/etc/ssl/etcd/ssl/node-master-1-key.pem --cacert=/etc/ssl/etcd/ssl/ca.pem get / --prefix --keys-only
```

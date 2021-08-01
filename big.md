

## centos
 sudo yum install -y yum-utils
 sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo


 sudo yum install docker-ce docker-ce-cli containerd.io


 sudo systemctl start docker


 sudo docker run hello-world




## docker-compose

sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose


sudo chmod +x /usr/local/bin/docker-compose


docker-compose --version


## docker external network
docker network create es_network



## 环境配置
docker ps -a

docker-compose exec hive-server bash

docker cp mysql.jar sqoop.tar.gz id:/opt/

tar -zxvf sqoop.tar.gz

cp mysql.jar  sqoop/lib


./sqoop list-databases --connect jdbc:mysql://18.119.126.228:3306/ --username root --password zhangyang517


## 数据导入

hive

create database  


./sqoop import --connect jdbc:mysql://18.119.126.228:3306/i_member --username root --password zhangyang517  --table t_member --num-mappers 1 --hive-import --fields-terminated-by "\t" --hive-overwrite --hive-database i_member --hive-table t_member

./sqoop import --connect jdbc:mysql://18.119.126.228:3306/i_member --username root --password zhangyang517  --table t_member_addr --num-mappers 1 --hive-import --fields-terminated-by "\t" --hive-overwrite --hive-database i_member --hive-table t_member_addr


./sqoop import --connect jdbc:mysql://18.119.126.228:3306/i_commodity --username root --password zhangyang517  --table t_commodity --num-mappers 1 --hive-import --fields-terminated-by "\t" --hive-overwrite --hive-database i_commodity --hive-table t_commodity


./sqoop import --connect jdbc:mysql://18.119.126.228:3306/i_commodity --username root --password zhangyang517  --table t_commodity_cate --num-mappers 1 --hive-import --fields-terminated-by "\t" --hive-overwrite --hive-database i_commodity --hive-table t_commodity_cate


./sqoop import --connect jdbc:mysql://18.119.126.228:3306/i_marketing --username root --password zhangyang517  --table t_coupon --num-mappers 1 --hive-import --fields-terminated-by "\t" --hive-overwrite --hive-database i_marketing --hive-table t_coupon


./sqoop import --connect jdbc:mysql://18.119.126.228:3306/i_marketing --username root --password zhangyang517  --table t_coupon_member --num-mappers 1 --hive-import --fields-terminated-by "\t" --hive-overwrite --hive-database i_marketing --hive-table t_coupon_member


./sqoop import --connect jdbc:mysql://18.119.126.228:3306/i_marketing --username root --password zhangyang517  --table t_coupon_order --num-mappers 1 --hive-import --fields-terminated-by "\t" --hive-overwrite --hive-database i_marketing --hive-table t_coupon_order



./sqoop import --connect jdbc:mysql://18.119.126.228:3306/i_operation --username root --password zhangyang517  --table t_delivery --num-mappers 1 --hive-import --fields-terminated-by "\t" --hive-overwrite --hive-database i_operation --hive-table t_delivery



./sqoop import --connect jdbc:mysql://18.119.126.228:3306/i_operation --username root --password zhangyang517  --table t_feedback --num-mappers 1 --hive-import --fields-terminated-by "\t" --hive-overwrite --hive-database i_operation --hive-table t_feedback



./sqoop import --connect jdbc:mysql://18.119.126.228:3306/i_operation --username root --password zhangyang517  --table t_shop --num-mappers 1 --hive-import --fields-terminated-by "\t" --hive-overwrite --hive-database i_operation --hive-table t_shop



./sqoop import --connect jdbc:mysql://18.119.126.228:3306/i_operation --username root --password zhangyang517  --table t_shop_order --num-mappers 1 --hive-import --fields-terminated-by "\t" --hive-overwrite --hive-database i_operation --hive-table t_shop_order


./sqoop import --connect jdbc:mysql://18.119.126.228:3306/i_operation --username root --password zhangyang517  --table t_user --num-mappers 1 --hive-import --fields-terminated-by "\t" --hive-overwrite --hive-database i_operation --hive-table t_user



./sqoop import --connect jdbc:mysql://18.119.126.228:3306/i_order --username root --password zhangyang517  --table t_order --num-mappers 1 --hive-import --fields-terminated-by "\t" --hive-overwrite --hive-database i_order --hive-table t_order


./sqoop import --connect jdbc:mysql://18.119.126.228:3306/i_order --username root --password zhangyang517  --table t_order_commodity --num-mappers 1 --hive-import --fields-terminated-by "\t" --hive-overwrite --hive-database i_order --hive-table t_order_commodity











## mysql

CREATE DATABASE db_name;

## web页面
hadoop namenode 50070


## 删除

- You can delete the lock file with the following command:

sudo rm /var/lib/apt/lists/lock


- You may also need to delete the lock file in the cache directory

sudo rm /var/cache/apt/archives/lock
sudo rm /var/lib/dpkg/lock




```
sudo rm /var/lib/dpkg/lock-frontend


sudo rm /var/lib/apt/lists/lock
sudo rm /var/cache/apt/archives/lock
sudo rm /var/lib/dpkg/lock
```





## 进程
ps aux | grep [a]pt


pgrep -a apt


sudo kill -9 processnumber





## centos ssh
1. aws   sudo passwd 
2. vi /etc/ssh/sshd_config
3. PermitRootLogin yes
4. PasswordAuthentication yes
5. vi /root/.ssh/authorized_keys
6. systemctl restart sshd    /etc/init.d/sshd restart


ifconfig

netstat -anp | grep :22

service sshd start 
service iptables stop



## ubuntu 18.04

apt-get update
apt-get install docker.io

docker --version
docker pull hello-world
docker run hello-world

service docker restart

docker ps -a


docker compose


sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose



sudo chmod +x /usr/local/bin/docker-compose


apt-get install docker-compose

sudo ln -s  /usr/bin/docker-compose  /usr/local/bin/docker-compose

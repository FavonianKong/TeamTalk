# TeamTalk
IM system for net-programing-learning
Dependency:
-----------
Please install mysql, you can use the following version or other version `Ver 15.1 Distrib 5.5.60-MariaDB`.<br>
Attention: Please do not use yum installed mysql in systems below centos 6.

You should also install redis which can be downloaded in this [link](https://redis.io/download).<br>
```
tar zxvf redis-2.8.19.tar.gz
cd redis-2.8.19
make
cd src
make install PREFIX=/usr/local/redis
mv redis.conf /usr/local/redis/etc
```

Building:
---------
TeamTalk must be build using  a reasonable C++ compiler,Also it should support `c++11`.
Before building the server,excute the following `x.sh`
```
make_hiredis.sh
make_log4cxx.sh
make_mariadb.sh  #maybe u can ignore it if you have install the mariaDB
make_protobuf.sh
```
-----------------------------------------------------------------------
Then go to the `/server/src` and excute the `build.sh version 1`
Using:
------
After compiling, a `.gz` file will be generated in the parent directory.
```
tar zxvf im-server-1.tar.gz
cd im-server-1
bash sync_lib_for_zip.sh
./restart.sh db_proxy_server
./restart.sh file_server
...
...
```
You the better shoutdown the firewall like `systemctl stop firewalld`

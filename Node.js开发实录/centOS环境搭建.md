## 搭建nginx
```
# 查看centOS版本
cat /etc/redhat -release

# 下载nginx
wget http://nginx.org/download/nginx-1.1.10.tar.gz

# 解压
tar -zxf nginx-1.1.10.tar.gz

# 查看nginx版本
nginx -v
```

## 搭建 nodejs/npm
```

```

## 搭建 MongoDB 数据库

1. 安装 MongoDB

```
# 提前进入要安装的目录
cd /usr/local

# 执行下载指令
wget https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-rhel62-3.2.7.tgz

# 解压MongoDB的压缩包
tar -xvf mongodb-linux-x86_64-rhel62-3.2.7.tgz

# 移动到目录
mv mongodb-linux-x86_64-rhel62-3.2.7 mongodb
```

2. 配置 MongoDB 环境变量

```
# 修改环境变量的配置文件
vim /etc/profile

# 点击i进行编辑模式，添加以下内容
export MONGODB_HOME=/usr/local/mongodb
export PATH=$MONGODB_HOME/bin:$PATH
# 添加完毕后，点击Esc退出编辑模式，输入":wq"保存退出
```

3. MongoDB 安装检查

```
# 查看MongoDB版本信息（如果输出相关版本信息，则证明安装成功）
mongod -v
```

4. MongoDB 定义启动

```
# 先创建MongoDB的文件目录
mkdir -p /data/mongodb
mkdir -p /data/mongodb/log

# 创建MongoDB的日志文件
touch /data/mongodb/log/mongodb.log

# 新建MongoDB启动配置文件
vim /etc/mongodb.conf
# 添加如下内容
dbpath=/data/mongodb
logpath=/data/mongodb/log/mongodb.log
logappend=true
port=27017
fork=true
auth = true

# 指示系统通过配置文件启动MongoDB
mongod -f /etc/mongodb.conf
# 看执行结果，如果提示successfully则证明配置成功

# 添加MongoDB端口到防火墙白名单
vi /etc/sysconfig/iptables
# 输入如下内容
-A INPUT -m state --state NEW -m tcp -p tcp --dport 27017 -j ACCEPT
# 重启ip Tables
/etc/init.d/iptables reload
```

5. 创建数据库和授权用户

```
# 进入MongoDB目录
cd /usr/local/mongodb/bin
# 执行MongoDB命令
./mongo
# 创建数据库
use t_student

# 创建用户
db.createUser(
    {
        user: "testUser",
        pwd: "123456",
        roles: [ { role: "readWrite", db: "t_student" } ]
    }
)
```

- MongoDB重启
```
# 查询MongoDB的进程
ps -ef | grep mongo
# 找到并杀死以mongodb.conf结尾的进程
kill 22694
# 重新启动
mongod -f /etc/mongodb.conf
```
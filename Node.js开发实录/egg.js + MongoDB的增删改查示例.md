## 案例代码和演示
## 准备事项
- 检查并启动MongoDB
检查MongoDB的方式有两种：
1. 通过浏览器直接访问URL（ http://localhost:27017/），如果出现***，，则表示连接成功
2. 或者通过启动Robo3T连接本地数据库，如果能进入主界面，则表示连接成功

- 启动MongoDB数据库


> 注意：目录名有空格的情况，如Program Files文件夹，要通过双引号将参数包含起来
> 注意：如未安装MongoDB的参考《MongoDB安装指导手册》
## 实现步骤
### 搭建egg项目框架
1. `egg-init egg-mongoose --type=simple` egg-mongoose是项目名
2. `cnpm i`
### 引入mongose工具
`cnpm install egg-mongoose --save` 引入egg-mongoose工具类
### 构建mongo schedul
`/app/model/job.js` 创建数据模型
### 编写control和service
### 调用测试
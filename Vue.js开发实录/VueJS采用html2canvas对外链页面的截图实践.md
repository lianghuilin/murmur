业务背景
前端表单可以调整配置项，Python根据这些配置项，返回一个图表页面的URL地址（该图表页面通过canvas实现），前端将图表页面显示到Vue视图中，同时可以将配置项的表单截图下来，添加备注。

实现逻辑
axios通过URL请求图表页面的文本内容
将文本内容转换成jquery DOM对象，插入到目标区域
使用html2canvas实现截图

备注
关于装载页面到Vue视图爬过两个坑，一开始使用iframe，只要赋值src，马上见效，但是h2c截图工具无法抓取到iframe的内容
后来使用v-html，将异步请求得到的页面内容装载到目标区域，但是页面的script标签不执行

实现步骤
1. 安装jquery和html2cavas
https://blog.csdn.net/weixin_41432849/article/details/81988058

2. 配置jquery到d2的配置文件
3. 构建外链页面的容器组件，并在主页面调用
4. 通过html2canvas实现截图
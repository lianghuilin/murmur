1. npm下载gojs并引入
```
npm i gojs --save
```
2. 定义数据源
3. 参考gojs官网实现
4. 去除水印
`/node_modules/gojs/release/go.js`
搜索“7eba17a4ca3b1a8346”
将`a.hr=b.W[Za("7eba17a4ca3b1a8346")][Za("78a118b7")](b.W,Ak,4,4);`替换成`a.hr=function(){return true;};`
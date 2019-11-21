1. vue create zmp_restrant_report
2. 安装所需的模块`npm i postcss-loader postcss-px2rem --S`,`npm i lib-flexible --S`
3. `main.js`引入 lib-flexible`import 'lib-flexible/flexible.js'`
4. 项目根目录创建 vue.config.js，并填入如下配置

```
module.exports = {
  css: {
    loaderOptions: {
      css: {
        // options here will be passed to css-loader
      },
      postcss: {
        // options here will be passed to postcss-loader
        plugins: [require('postcss-px2rem')({
          remUnit: 384,
          remPrecision: 8
        })]
      }
    }
  }
}
```

5. `npm run serve`通过控制台检查 px 单位是否转换成 rem
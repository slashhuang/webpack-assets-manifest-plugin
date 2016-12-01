# webpack-assets-manifest-plugin

# 开发初衷
> 解决公司内部webpack打包文件上传的版本号控制
> 提供给后端及运维json文件读取资源列表，方便做缓存控制

## 基于如下项目二次开发
[webpack-assets-manifest](https://github.com/webdeveric/webpack-assets-manifest/blob/master/src/webpack-assets-manifest.js)

## 使用 example code
``` javascript
    var ManifestPlugin = require('webpack-assets-manifest');
    # in webpack config file, add the following plugin config to plugins property
    # 抽取CSS和JS文件
      plugins: [
            new ManifestPlugin({
                hashNum:7,
                extractJsCss:true
              }),
           ...otherPlugins]

    # 单页面应用异步加载,加载主程序入口，别的文件通过require.ensure异步加载
      plugins: [
            new ManifestPlugin({
                 versionFiles:[
                  'app.js',
                  'common.css',
                  'safe.js',
                  'safe.css',
                  'common.js'],
                hashNum:7,
              }),
           ...otherPlugins]
```
## 代码发布
> 等在业务场景下更成熟后，考虑发布npm
> welcome pull request
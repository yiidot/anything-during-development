1. npm 切换淘宝镜像
```
npm config set registry https://registry.npm.taobao.org
```
2. vue init 卡在chromedriver上问题解决办法
```
npm config set chromedriver_cdnurl https://npm.taobao.org/mirrors/chromedriver
```
3. 禁用https
```
npm config set strict-ssl false
```

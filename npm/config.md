1. npm 切换淘宝镜像
```bash
npm config set registry https://registry.npm.taobao.org
```
2. vue init 卡在chromedriver上问题解决办法
```bash
npm config set chromedriver_cdnurl https://npm.taobao.org/mirrors/chromedriver
```
3. 禁用https
```bash
npm config set strict-ssl false
```
4. 在使用淘宝镜像的情况下发布npm包
```bash
npm login --registry http://registry.npmjs.org
npm publish --registry http://registry.npmjs.org
```

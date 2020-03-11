1. 在nas上新增一个用户iis_user
2. 在Windows server上新增一个iis_user, 密码要与nas上设置的一致
![创建iis_user](https://github.com/yiidot/anything-useful-during-development/blob/master/Windows/iis%E8%AE%BF%E9%97%AEnas/%E5%88%9B%E5%BB%BA%E7%94%A8%E6%88%B7.png)
3. 将iis_user添加到Administrator组中
![添加到Administrator组](https://github.com/yiidot/anything-useful-during-development/blob/master/Windows/iis%E8%AE%BF%E9%97%AEnas/%E6%B7%BB%E5%8A%A0%E5%88%B0Administrator%E7%BB%84.png)
4. 设置iis应用程序池的标识
![设置iis应用程序池的标识](https://github.com/yiidot/anything-useful-during-development/blob/master/Windows/iis%E8%AE%BF%E9%97%AEnas/%E8%AE%BE%E7%BD%AEiis%E7%A8%8B%E5%BA%8F%E6%B1%A0%E4%B8%AD%E7%9A%84(%E8%BF%9B%E7%A8%8B%E6%A8%A1%E5%9E%8B(%E6%A0%87%E8%AF%86)).png)
5. 设置网站的连接身份
![设置网站的连接身份](https://github.com/yiidot/anything-useful-during-development/blob/master/Windows/iis%E8%AE%BF%E9%97%AEnas/%E7%BD%91%E7%AB%99%E4%BB%A5iis_user%E8%BA%AB%E4%BB%BD%E8%BF%9E%E6%8E%A5.png)
6. 设置虚拟路径的路径和凭据，路径为\\ip\\共享目录
![设置虚拟路径的路径和凭据](https://github.com/yiidot/anything-useful-during-development/blob/master/Windows/iis%E8%AE%BF%E9%97%AEnas/%E8%99%9A%E6%8B%9F%E8%B7%AF%E5%BE%84%E8%AE%BE%E7%BD%AEip%E5%8A%A0%E5%85%B1%E4%BA%AB%E7%9A%84%E6%96%87%E4%BB%B6%E5%A4%B9iis_user%E7%94%A8%E6%88%B7%E5%B9%B3%E5%87%AD%E6%8D%AE.png)

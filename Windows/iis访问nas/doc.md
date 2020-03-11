1. 在nas上新增一个用户iis_user
2. 在Windows server上新增一个iis_user, 密码要与nas上设置的一致
![创建iis_user](https://github.com/yiidot/anything-useful-during-development/blob/master/Windows/iis%E8%AE%BF%E9%97%AEnas/%E5%88%9B%E5%BB%BA%E7%94%A8%E6%88%B7.png)
3. 将iis_user添加到Administrator组中
4. 设置iis应用程序池的标识
5. 设置网站的连接身份
6. 设置虚拟路径的路径和凭据，路径为\\ip\\共享目录

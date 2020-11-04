1. 发布网站时提示错误

锁定是默认设置的 (overrideModeDefault="Deny")，或者是通过包含 overrideMode="Deny" 或旧有的 allowOverride="false" 的位置标记明确设置的。

解决方法

管理员方式打开命令行运行以下命令

```shell
%windir%\system32\inetsrv\appcmd unlock config -section:system.webServer/handlers
%windir%\system32\inetsrv\appcmd unlock config -section:system.webServer/modules
```

2. 处理程序“ExtensionlessUrlHandler-Integrated-4.0”在其模块列表中有一个错误模块“ManagedPipelineHandler”
```shell
# 利用dism工具依次执行下面命令
dism /online /enable-feature /featurename:IIS-ISAPIFilter
dism /online /enable-feature /featurename:IIS-ISAPIExtensions
dism /online /enable-feature /featurename:IIS-NetFxExtensibility45
dism /online /enable-feature /featurename:IIS-ASPNET45
```

3. IIS上部署MVC网站，打开后ExtensionlessUrlHandler-Integrated-4.0解决方法

```
启动或关闭windows功能
勾选：
1、ASP.NET 3.5
2、ASP.NET 4.6
3、ISAPI扩展
4、ISAPI筛选器
5、.NET Extensibility 3.5
6、.NET Extensibility 4.6
```

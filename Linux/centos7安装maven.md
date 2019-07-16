1. 创建一个maven文件夹
```shell
mkdir /usr/local/maven
```
2. 上传maven文件到 /usr/local/maven
3. 解压缩
```shell
tar -zxvf apache-maven-3.5.0-bin.tar.gz -C /usr/local/maven/
```
4. 设置环境变量
```shell
vim /etc/profile
# 在/etc/profile的文件末尾添加以下配置:
export M2_HOME=/usr/local/maven/apache-maven-3.3.9
export PATH=$JAVA_HOME/bin:$JAVA_HOME/jre/bin:$M2_HOME/bin:$PATH
# 执行source命令让新配置立即生效:
source /etc/profile
```
5. 测试
```
mvn -v
```

```shell
# 自定义工作空间
E:/0_Code
# svn
https://192.168.100.90/svn/Code/UPBIM/Branch/V1.1/UBShow/Web3D/examples/m_demo
# Local module directory
./Demo_m

Always check out a fresh copy

# 脚本构建
Demo_m

# poll scm
H/10 9-22 * * 1-5

# 构建
echo %SVN_REVISION%
cd /d E:\0_Jenkins\Demo_m\Builder
start.bat

# 构建后操作
E-mail notification
weihl@ai-eco.cn
```

# zerotier_moon
创建zerotier虚拟局域网moon节点一键脚本，包含SSH端口更改、计划任务设定等功能
# 用法：

curl -O https://raw.githubusercontent.com/dajiangfu/zerotier_moon/master/moon.sh && chmod +x moon.sh && ./moon.sh

# 1.配置客户端

Linux:

使用之前步骤中 moon.json 文件中的 id 值 (10 位的字符串，就是xxxxxx），不知道的话在服务器上执行如下命令可以得到id。

执行命令：grep id /var/lib/zerotier-one/moon.json | head -n 1

然后在客户端机器里执行命令：

执行命令：zerotier-cli orbit ed2c88f24 ed2c88f24

此处的ed2c88f24就是刚刚在服务器得到的ID值

Windows:

打开服务程序services.msc, 找到服务"ZeroTier One", 并且在属性内找到该服务可执行文件路径,并且在其下建立moons.d文件夹,然后将moon服务器下生成的000xxxx.moon文件,拷贝到此文件夹内..再重启该服务即可(计算机右键管理-找到服务双击打开-找到zerotier one右键重新启动即可)

路径一般是Windows: C:\ProgramData\ZeroTier\One

# 2.测试是否成功

客户端cmd执行命令：zerotier-cli listpeers 若有出现你的服务器IP地址,即可证明moon连接成功

# 完成客户端配置

# 使用VPS搭建SS

VPS：（Virtual Private Server, 虚拟专用服务器）

SS：（shadowsocks）

## 选择VPS商

- 搬瓦工
- Vultr
  - 关注优惠码及优惠活动
  - 充值（Billing）使用Paypal
  - 以下以Vultr为例

## 选择服务器

1. 充值完成后，点击“+”号，进行Deploy New Server
2. Server Location 服务器选择 东京/洛杉矶
3. Server Yype 操作系统选择 Debian 7 x64
4. Server Size 选择月付 2.5/5/10
5. 其他设置默认
6. 点击Deploy生成新的VPS
7. 点击生成的service面板，获取IP地址、用户名、密码

## SS安装

1. 下载Putty
2. 在Putty界面输入IP地址、端口（默认SSH端口为22）
3. 打开命令框后输入用户名root，密码（窗口不显示，但已经输入，直接从上述第7步中复制，右键粘贴）
4. 输入如下命令
5. `wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-libev-debian.sh && chmod +x shadowsocks-libev-debian.sh && ./shadowsocks-libev-debian.sh 2>&1 | tee shadowsocks-libev-debian.log`
6. 设置密码和端口（443或其他）
7. 把运行完毕后的SS帐号信息保存下来
8. 在SS客户端输入相关信息就可以了（选择开机启动）
9. 手机端可以使用（wingy免费、shadowrocket 、surge ）

## 锐速优化

1. Vultr 是KVM系统的VPS，所以可以使用锐速来优化SS连接速度
2. 使用如下命令安装锐速
3. `wget -N --no-check-certificate https://raw.githubusercontent.com/91yun/serverspeeder/master/serverspeeder-all.sh && bash serverspeeder-all.sh`
4. 加入自启动，可以使用winscp，在根目录的etc/rc.local文件中最后的exit 0前插入`service serverSpeeder start`并保存

##  Chrome等浏览器设置

- 下载安装roxy SwitchyOmega插件
- 选择开发者模式，并在Chrome的扩展程序界面直接拖入插件即可安装
- 下载配置文件
- 在SwitchyOmega中导入配置文件
- 选择相应的模式（自动切换）
- 即可完成代理


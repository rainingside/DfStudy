mosquitto
[toc]

# centos7中安装
- yum list installed | grep mosquitto     查看是否安装
- systemctl status mosquitto              检查是否运行
- yum install epel-release -y             安装epel-release
- yum install mosquitto -y                安装mosquitto
- mosquitto -v                            确认版本
- systemctl start mosquitto               启动服务
- systemctl enable mosquitto              设置开机启动
- firewall-cmd --add-port=1883/tcp --permanent 防火墙放行
- firewall-cmd --reload                        防火墙重启
- 测试
  - mosquitto_sub -h localhost -t test/topic   订阅（新开终端）
  - mosquitto_pub -h localhost -t test/topic -m "hello centos7" 发布
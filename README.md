地址: **192.168.6.1**<br>
用户名: **root**<br>
密码: **password**

**OpenClash 设置**
```
**插件设置**
✅ 使用 Meta 内核
✅ Redir-Host（兼容）模式
✅ UDP 流量转发

✅ 路由本机代理
✅ 禁用 QUIC

✅ 本地 DNS 劫持 使用 Dnsmasq 转发
✅ 禁止 Dnsmasq 缓存 DNS

**覆写设置**
Github 地址修改 https://testingcf.jsdelivr.net/

✅ 自定义上游 DNS 服务器

✅ Nameserver-Policy
"geosite:cn": [119.29.29.29, 223.5.5.5]

✅ NameServer
      8.8.8.8/dns-query#
      1.1.1.1/dns-query#
❌ FallBack

✅ Default-NameServer
      119.29.29.29
      223.5.5.5

✅ 启用 TCP 并发
TCP Keep-alive 间隔（s）1800

✅ 启用 GeoIP Dat 版数据库
✅ 启用流量（域名）探测

网络加速设置
全锥形 NAT → XT_FULLCONE_NAT（更佳的兼容性）

这是 Mihomo（Meta Core） v1.19.6引入的兼容性问题。
复制 UI 面板（必须先做）：
cp -pdr /usr/share/openclash/ui /etc/openclash/ui

修改 yml_change.sh 阻止插入 external-ui：
vi /usr/share/openclash/yml_change.sh

把整行注释掉（在前面加 #）或直接删除：
Value['external-ui']='ui';
```

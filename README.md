# FRP 安装

# 下载

下载地址：
https://github.com/fatedier/frp/releases

**注意系统不同**

# 服务器端安装


# 客户端安装

```bash
chomd +x install.sh && ./insall.sh
```

### 安装为 Windows 服务，自启动

下载 WinSW-x64.exe，跟 `frpc`、`frps` 等放在一起，运行时还需要，所以目录都不能动

> https://github.com/winsw/winsw/releases

修改配置文件 `WinSW-x64.xml`

```xml
<service>
  <id>frpc</id>
  <name>frpc</name>
  <description>This service runs frpc powered by WinSW.</description>
  <executable>D:\Programs\frp_0.54.0\frpc.exe</executable>
  <arguments>-c "D:\Programs\frp_0.54.0\frpc.toml"</arguments>
  <onfailure action="restart" delay="30 sec"/>
  <onfailure action="restart" delay="300 sec"/>
  <log mode="roll" />
</service>
```

安装服务，配置里是随系统启动的

```bash
./WinSW-x64.exe install WinSW-x64.xml
```

其他命令

```bash
./WinSW-x64.exe start WinSW-x64.xml
./WinSW-x64.exe stop WinSW-x64.xml
./WinSW-x64.exe status WinSW-x64.xml
./WinSW-x64.exe uninstall WinSW-x64.xml
```

vs
[toc]

# 主题

工具->主题->获取更多主题
- 安装主题包 VisualStudioThemePack
  选择主题：Solarized Light 

# 个性化 工具->选项->环境->字体和颜色
- 文本编辑器背景色选择： rgb(224, 242, 241)
- 突出显示当前行：选择背景色 黄色

# nuget包默认存储位置修改
修改 [Nuget.config]中修改存放路径, 所在位置 C:\Users\{用户}\AppData\Roaming\NuGet
修改如下：

<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <packageSources>
    <add key="nuget.org" value="https://api.nuget.org/v3/index.json" protocolVersion="3" />
  </packageSources>
  <config>
    <add key="globalPackagesFolder" value="D:\Program\.nuget\packages" />
  </config>
</configuration> 

[globalPackagesFolder] 指定存放路劲即可
已下载的包可直接剪切复制到新路径，后续下载的包会下载到此路径



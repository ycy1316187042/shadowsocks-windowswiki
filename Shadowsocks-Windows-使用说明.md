[![Build Status]][Appveyor]

#### 功能

1. 系统代理设置
2. PAC 模式和全局模式
3. [GFWList] 和用户规则
4. 支持 HTTP 代理
5. 支持多服务器切换
6. 支持 UDP 代理

#### 下载

下载 [最新版]。

从 2.5.8 开始你可以在 Releases 页面找到 exe 文件的 hash 值，你可以使用 [fciv](https://support.microsoft.com/en-us/kb/841290) 等工具 校验 `Shadowsocks.exe` 文件. 例如 `fciv.exe -both -add Shadowsocks.exe`

#### 基本使用

1. 在任务栏找到 Shadowsocks 图标
2. 在 服务器 菜单添加多个服务器
3. 选择 `启用系统代理` 来启用系统代理。请禁用浏览器里的代理插件，或把它们设置为使用系统代理。
4. 除了设为系统代理，你也可以直接自己配置浏览器代理。在 SwitchyOmega 中把代理设置为 SOCKS5 或 HTTP 的 127.0.0.1:1080。这个 1080 端口可以在服务器设置中设置。

#### PAC

1. 可以编辑 PAC 文件来修改 PAC 设置。Shadowsocks 会监听文件变化，修改后会自动生效。
2. 你也可以从 [GFWList] （由第三方维护）更新 PAC 文件。
3. 你也可以使用在线 PAC URL

#### 服务器自动切换

1. 负载均衡：随机选择服务器
2. 高可用：根据延迟和丢包率自动选择服务器
3. 累计丢包率：通过定时 ping 来测速和选择。如果要使用本功能，请打开菜单里的`统计可用性`。
4. 也可以实现 IStrategy 接口来自定义切换规则，然后给我们发一个 pull request。

#### UDP

对于 UDP，请使用 SocksCap 或 ProxyCap 强制你想使用的程序走代理。

#### 多实例

如果想使用其它工具如 SwitchyOmega 管理多个服务器，可以启动多个 Shadowsocks。
为了避免配置产生冲突，把 Shadowsocks 复制到一个新目录里，并给它设置一个新的本地端口。

#### 服务器配置

请访问 [服务器] 获取更多信息。

#### 绿色模式

如果你想把所有临时文件放在 shadowsocks/temp 目录而不是系统的 temp 目录，
可以在 shadowsocks 所在目录创建一个 `shadowsocks_portable_mode.txt` 文件。

#### 开发

Visual Studio 2015 is required.

#### 授权

GPLv3


[Appveyor]:       https://ci.appveyor.com/project/wongsyrone/shadowsocks-windows-0cn3i
[Build Status]:   https://ci.appveyor.com/api/projects/status/47784ryn365vw56w/branch/master?svg=true
[最新版]: https://github.com/shadowsocks/shadowsocks-windows/releases
[服务器]:        https://github.com/shadowsocks/shadowsocks/wiki/Ports-and-Clients#linux--server-side
[GFWList]:        https://github.com/gfwlist/gfwlist
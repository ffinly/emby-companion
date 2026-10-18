<p><img src="assets/images/app-icon.png" alt="Emby Companion" width="96" height="96"></p>

# Emby Companion

**简体中文** | [繁體中文](README.zh-TW.md) | [English](README.en.md)

---

**更优雅地探索、订阅与播放你的 Emby 媒体库**

Emby 观影助手是一款 macOS 观影工具。从榜单、厂牌和喜欢的演员、导演出发，找到下一部想看的电影或剧集；连接 Emby 后，直接核对入库与缺集，再用熟悉的播放器继续观看，进度自动同步回媒体库。

**没有 Emby 服务器也可以用。** 配置自己的 TMDB API Key，即可独立浏览榜单、探索 48 个厂牌与平台、搜索影视和人物，查看评分与简介。Emby 与订阅服务都可以按需连接。

[下载最新版](https://github.com/ffinly/emby-companion/releases/latest) · [版本记录](https://github.com/ffinly/emby-companion/releases) · [反馈问题](https://github.com/ffinly/emby-companion/issues)

本仓库提供安装包、使用说明与问题反馈；应用闭源，不提供影视资源、服务器账号或第三方服务凭证。

## 界面预览

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/images/home.zh-CN.dark.png">
  <source media="(prefers-color-scheme: light)" srcset="assets/images/home.zh-CN.png">
  <img src="assets/images/home.zh-CN.png" alt="Emby 观影助手：首页厂牌探索">
</picture>

*图为未配置 Emby 的首页。连接并同步 Emby 后会显示媒体库；有可续播记录时显示“继续观看”。*

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/images/poster-wall.zh-CN.dark.png">
  <source media="(prefers-color-scheme: light)" srcset="assets/images/poster-wall.zh-CN.png">
  <img src="assets/images/poster-wall.zh-CN.png" alt="Emby 观影助手：榜单筛选与海报墙">
</picture>

*浏览影视榜单，筛选作品并查看 Emby 入库状态。*

## 主要功能

### 发现影视

- **榜单发现**：浏览 IMDb、豆瓣、TMDB、影展与奖项等榜单，查看排名和入库状态；从作品详情查看收录它的榜单。预置榜单随 [emby-collection-sync](https://github.com/ffinly/emby-collection-sync/blob/main/README.md) 更新，也可通过“添加 TMDB 片单”导入在线片单。
- **厂牌探索**：按电影厂牌、动画厂牌、欧美剧集和亚洲剧集浏览 48 个厂牌与平台的作品，支持作品筛选，展示入库、观看和订阅状态。
- **搜索与人物作品**：按片名、人物、合集名称或编号搜索，支持 TMDB／IMDb 编号及作品链接；片名留空可浏览所选地区的热门影视。浏览简介、评分、演职人员与人物作品集，详情页可跳转豆瓣、IMDb 和 TMDB。
- **核心榜单入库率**：默认统计第一至第三梯队，支持按级别选择、单独勾选或排除榜单，保存后更新去重统计。首页的全部片单作品数与已入库数量仍按所有片单统计。另可设置首页默认打开的榜单。

### 媒体库与播放

- **首页与继续观看**：首页浏览 Emby 媒体库与继续观看，使用默认播放器和线路续播对应版本，支持查看全部。
- **媒体库与合集**：浏览 Emby 电影、剧集、合集、季度与分集，查看可播放版本，管理观看状态；可临时隐藏观看记录与进度。
- **入库与缺集核对**：根据已同步的 Emby 数据展示入库状态，并按季度对照 TMDB 集数与 Emby 实际集号。尚未核对或总集数未知时单独提示。缺集核对无需配置 MoviePilot，订阅时才需要配置。
- **多线路与外部播放**：同一 Emby 服务器可分别配置资料同步与播放线路，选择媒体版本后调用 SenPlayer、Infuse 或 VidHub，支持续播与观看进度回传。分段电影以 `PART 1`、`DISC 2` 等标签标识，同组文件按数字或字母顺序排列；分段文件进度各自独立，普通完整版本之间仍同步进度。

### 订阅、缓存与备份

- **MoviePilot 联动**：订阅未入库电影或缺集季度，自动跳过已入库、集数已齐及已有订阅的内容；支持搜索和批量管理订阅。MoviePilot 为可选服务，下载与入库由其处理。
- **资料与图片缓存**：完整同步媒体库后自动获取所选语言的 TMDB 影视、人物及整季分集资料，图片按需加载；可查看同步结果、重试失败项，并管理缓存或重建本地搜索索引。
- **备份与恢复**：按需选择配置、片单、缓存及使用偏好，导出加密备份并选择恢复范围。

## 语言与显示

在“连接与设置 → 语言”分别设置界面、预置片单、TMDB 元数据及海报语言。界面支持跟随系统、简体中文、繁体中文与英文；片单和元数据可跟随界面，也可独立选择三种语言。

榜单同步会读取并缓存上游的三语名称，切换已有名称无需重新下载。影视与人物资料、分集信息及同步历史中的作品名称跟随 **TMDB 元数据语言**，不同语言资料分别缓存；缺少对应资料时保留可用的 Emby 内容。资料刷新只更新本机，不改写服务器元数据。

海报可选原语言、中文或英文。已有图片可复用，未缓存图片仍需联网。媒体库名称支持预置中英映射与自定义显示名称，留空保留原名称，仅影响本应用。

## 下载与初次使用

需要 **macOS 14 或更高版本**，通用安装包支持 **Apple Silicon 与 Intel**。从 [最新 Release](https://github.com/ffinly/emby-companion/releases/latest) 下载 DMG，将 **Emby Companion.app** 拖入“应用程序”；替换旧版前先退出应用。

### 首次打开：macOS 安全提示

当前安装包使用本地签名，尚未经过 Apple Developer ID 签名和公证。确认来源为本仓库 Releases 后，先尝试打开一次；如被系统阻止，前往 **系统设置 → 隐私与安全性 → 仍要打开**，按提示确认。参见 [Apple 官方说明](https://support.apple.com/zh-cn/102445)。

<details>
<summary>备用方法：通过终端处理首次打开限制</summary>

仅在确认安装包来自本仓库 Releases，并已将应用拖入“应用程序”后使用：

```bash
xattr -rd com.apple.quarantine "/Applications/Emby Companion.app"
```

若提示权限不足，可在命令前加上 `sudo`。

此命令移除应用的下载隔离属性，不能修复真正损坏的文件。若系统明确提示检测到恶意软件，请停止打开并反馈具体提示。

</details>

后续安装包的签名状态以 Release 说明为准。

### 连接服务

1. 如需使用媒体库功能，在“连接与设置”填写 Emby 地址并登录。
2. 在 [TMDB API 设置](https://www.themoviedb.org/settings/api) 申请自己的 API Key，阅读 [API 使用条款](https://www.themoviedb.org/api-terms-of-use)，再填入应用；需要时可配置 HTTP／SOCKS 代理，用于 TMDB 资料、图片、榜单及软件更新（GitHub）；Emby 与 MoviePilot 直连。
3. 在首页同步榜单；连接 Emby 后，再执行“完整同步媒体库”。
4. 需要播放时安装外部播放器；需要订阅时，再填写 MoviePilot 服务地址与 API 令牌；令牌可从 MoviePilot“设定 → 系统 → 基础设置”复制。

TMDB 与 MoviePilot 支持独立“清除配置”；清除 TMDB API 配置时保留代理。退出 Emby 登录会清空地址、账号、令牌及全部线路配置。

<a id="zh-hans-emby-routes-and-players"></a>

## 线路与播放器

登录后，在“连接与设置 → Emby → 多线路管理”添加和管理线路。同一服务器与账号的多条线路共用媒体库缓存，可分别指定同步主线路与默认播放线路，也可通过 `ecplayer://importserver` 链接预览并导入配置。格式见应用内“Emby 线路 → 通过链接导入 Emby”。

| 外部播放器 | 支持关闭播放窗口后回传进度的版本 |
| --- | --- |
| SenPlayer | 6.1.1 及以上 |
| Infuse | 8.4.7 及以上 |
| VidHub | 2.3.5 及以上 |

播放进度自动同步，无需开启开关。**播放结束后，请先关闭播放窗口，待进度同步后再退出播放器。直接退出播放器无法同步播放进度。** 应用仅使用播放器回传的实际位置；未收到有效回调时不会推算进度，网络异常导致同步失败时可在首页重试。播放器需自行安装。

播放期间建议保持本程序运行，以维持 Emby 会话与播放历史。仅关闭本程序窗口不影响保活；完全退出本程序或检测到播放器退出后会停止保活，但仍可接收稍后到达的有效进度回调。

在“连接与设置 → 播放 → 播放日志”查看播放器调用、保活、回调与同步记录，支持筛选、搜索、按播放请求查看及导出 `.log`。记录与展开的 Ping 明细随滚动自动加载；成功 Ping 默认隐藏，在全部视图中合并显示。日志仅保存在本机，保留最近 7 天、最多 20,000 条，不记录播放链接与密钥。

## 软件更新

在“连接与设置 → 软件更新”手动检查更新，或启用自动检查与下载。校验通过后由更新窗口引导安装并重新启动；校验失败会停止安装。

支持多语言的升级日志随当前界面语言显示；旧版单语言日志保留原文。

## 缓存与备份

“连接与设置”提供缓存清理、本地搜索索引重建及加密备份。清理本地缓存不删除 Emby 服务器内容，连接与登录信息保留；之后可重新同步。“TMDB 缓存清理”可单独清除搜索结果缓存，保留片单、媒体库资料与图片。

| 备份内容 | 包含的数据 |
| --- | --- |
| TMDB API 配置 | API 地址与 API Key |
| MoviePilot API 配置 | 服务地址与 API 令牌 |
| TMDB 榜单 | 榜单内容、自定义 TMDB 片单、片单设置与核心榜单范围 |
| TMDB 缓存 | 影视与人物资料、海报和人物图片 |
| Emby 配置 | 服务器、线路、当前账号、登录令牌及观看记录 |
| Emby 缓存 | 媒体库、合集、分集及 Emby 图片 |
| 使用偏好 | 语言、名称映射、播放器与显示偏好 |

导出时选择内容，设置至少 **8 个字符**的密码，保存为 `.ecbackup`。恢复时可再次选择范围：配置、榜单与偏好替换对应内容，缓存合并。核心榜单配置随“TMDB 榜单”备份；观看记录随“Emby 配置”备份，仅包含当前账号，恢复时核对服务器与账号并保留较新的记录。

备份可能包含 API 密钥与登录信息，请妥善保管文件和密码。

## 隐私与反馈

连接信息与缓存保存在本机。应用根据功能向你配置的服务、TMDB 和 GitHub 请求数据；GitHub 榜单配置与更新请求不携带 TMDB API Key 或 Emby 登录凭证。

反馈时请提供应用版本、macOS 版本、操作步骤及错误提示，并隐藏截图或日志中的地址、账号、密钥等私人信息。

## 📈 Star History

<a href="https://www.star-history.com/?repos=ffinly%2Femby-companion&amp;type=date&amp;legend=top-left">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=ffinly/emby-companion&amp;type=date&amp;theme=dark&amp;legend=top-left" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=ffinly/emby-companion&amp;type=date&amp;legend=top-left" />
    <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=ffinly/emby-companion&amp;type=date&amp;legend=top-left" />
  </picture>
</a>

## 许可与第三方说明

软件使用条款见[使用许可](LICENSE.txt)。

影视内容、资料、图片、人物肖像及第三方标识的权利归各自权利人所有。应用使用的独立开源组件适用各自许可，详见 [第三方说明](THIRD_PARTY_NOTICES.md)。本软件的使用许可不替代相关服务的使用条款。

## TMDB 署名

<a href="https://www.themoviedb.org"><img src="assets/images/tmdb-logo.svg" alt="TMDB" width="120"></a>

本产品使用 TMDB API，但未经 TMDB 认可或认证。

This product uses the TMDB API but is not endorsed or certified by TMDB.

[The Movie Database](https://www.themoviedb.org) · [API 使用条款](https://www.themoviedb.org/api-terms-of-use)

Emby、MoviePilot、各播放器及 TMDB 的名称和标识归各自权利人所有。本应用与这些服务的运营方无隶属或认证关系。

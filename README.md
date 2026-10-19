# PaperOS 应用仓库

给 [PaperOS](https://github.com/ChrisPei/PaperOS) 的原生应用商店使用。
默认目录地址：`https://api.github.com/repos/ChrisPei/paperos-apps/contents/catalog.json`。
PaperOS 自动使用 raw 媒体类型；也可在仓库内查看 `catalog.json` 的原始文件。

在 Kindle 的「应用 → 发现」选择条目，下载后点「确认安装」。
「已安装」可以打开和卸载；「更新」按应用编号和版本检查更新。
安装不会覆盖应用自己的数据目录。下载与安装分开，下载成功不会自动执行程序。

首批目录包含闹钟、万年历、天气、米家只读面板、木鱼和 KOReader 插件商店。
前四个轻量包使用设备上已有的 PaperOS 原生功能；需要带应用商店的 PaperOS 版本。
KOReader 插件商店在已安装的 KOReader 中运行，使用社区源码 ZIP，保留上游 GPL-3.0 许可证。
KOReader 主程序暂时沿用现有独立移植；此目录不分发其二进制运行镜像。

## 完整性和版本

`catalog.json.sig` 是目录原始字节的 Ed25519 签名，`catalog.pub` 是 Base64 公钥。
客户端内置同一公钥。每个应用条目记录固定版本下载 URL、SHA-256、大小和平台。
发布流程先上传固定版本文件，再提交新目录和签名。请勿覆盖已有版本的文件。
签名私钥只留在维护者电脑，不进入 Git。

## 源码与许可证

PaperOS 和原生应用：GPL-3.0-or-later，源码在主项目，构建入口为 `scripts/build-muyu.sh`、
`scripts/build-app-catalog.py`。发布页同时提供木鱼二进制对应的完整 C／FBInk／stb 源码包。
Noto CJK 字体使用 SIL OFL；字体由设备系统提供。

社区插件源码来自 [omer-faruq/appstore.koplugin](https://github.com/omer-faruq/appstore.koplugin)，
固定到目录记录的提交，发布文件即完整插件源码 ZIP。详见发布页 `SOURCES.md`。

第三方下载格式与运行兼容边界见主项目 [STORE.md](https://github.com/ChrisPei/PaperOS/blob/main/STORE.md)。
不提供商业游戏本体、个人设备镜像、账户、密钥或家庭数据。

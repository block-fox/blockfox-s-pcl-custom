# blockfox 的 PCL2 自定义主页

个人自用的 [PCL2](https://github.com/Hex-Dragon/PCL2) 自定义主页，已适配 **PCL 2.13 / 2.14**。

> 当前版本：**2.1.0**（2026-10-18）

## 功能

- **回声洞**：点击文字换一条，带逐字擦除动画；右下角保留「投稿」入口
- **日历与提示**：日历 + 「你知道吗」
- **快速搜索**：11 个搜索引擎下拉选择，输入关键词后一键搜索
- **快捷启动**：显示当前版本、跳转版本选择页、启动当前版本 / 启动并加入服务器
- **常用应用**：QQ、微信、Edge、Chrome 一键启动
- **快捷工具**：今日人品、清理垃圾、检查更新、打开 PCL 目录 / 日志
- **服务器状态**：输入地址即可查看 MineBBS MOTD 状态图（在线状态、MOTD、玩家数、延迟、版本）
- **常用网页**：MCNav、MC 百科、MC Wiki、B 站、MineBBS、Modrinth 等
- **下载器**：调用 PCL 多线程下载引擎
- 统一的卡片间距、按钮高度与折叠逻辑

## 安装

### 方式一：本地文件

1. 下载 [`Custom.xaml`](https://github.com/block-fox/blockfox-s-pcl-custom/releases/latest/download/Custom.xaml)
2. 放到 PCL 根目录下的 `PCL\Custom.xaml`
3. 打开 PCL → 设置 → 个性化 → 主页 → 选择「本地文件」→ 刷新主页

### 方式二：联网加载

在 PCL 的「主页 → 联网」中填入：

```text
https://github.com/block-fox/blockfox-s-pcl-custom/releases/latest/download/Custom.xaml
```

或使用 main 分支的 raw 地址：

```text
https://raw.githubusercontent.com/block-fox/blockfox-s-pcl-custom/main/Custom.xaml
```

## 说明与已知限制

- **需要 PCL 2.13 及以上**：`EventType` / `EventData` 已改为 `CustomEventService` 的附加属性写法。
- **版本列表不是下拉框**：自定义主页的 XAML 无法读取 PCL 的已安装版本集合，所以采用「显示当前版本 + 跳转版本选择页 + 启动当前版本」的流程。真正的版本下拉列表需要改 PCL 源码或由官方提供接口。
- **常用应用首次启动要确认**：QQ / 微信通过 `tencent://` / `weixin://` 协议打开，Edge / Chrome 通过系统 App Paths 打开；首次点击会弹出 PCL 的安全确认，选择「继续且今后不再要求确认」即可。
- **服务器状态需要联网**：使用 [MineBBS MOTD](https://motd.minebbs.com/) 的 `status_img` 接口；地址只填域名，端口可留空自动识别。
- 日历、回声洞、`{version}` 等均使用 PCL 内置控件与变量。

## 更新日志

### 2.1.0（2026-10-18）

- 修复 PCL 2.13 / 2.14 下 `<local:MyButton.EventData>` 报「无法设置未知成员」的问题，改为 `local:CustomEventService.EventData`
- 搜索改为「搜索引擎下拉 + 输入框 + 搜索按钮」，去掉原来的 11 个搜索按钮
- 回声洞独立成卡片，点击文字刷新，加入逐字擦除动画，恢复「投稿」按钮
- 日历移到「你知道吗」上方
- 快捷启动改为「当前版本 + 选择版本 + 启动」流程，新增 QQ / 微信 / Edge / Chrome
- 快捷工具新增 MineBBS 服务器状态图
- 清理冗余文本，统一卡片间距与按钮高度

### 2.0.0（2025-06-27）

- 初版主页

## 致谢

- **Letter_blackfox**：主页作者
- **Ad-closeNN / PCL2-home-page**：布局与 `MyComboBox` 用法参考
- **MineBBS MOTD**：服务器状态接口
- **PCL2 / OpenPCL**：启动器与源码

## 使用说明

个人自用主页，欢迎参考和二次修改；转载请注明出处。

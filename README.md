# Wallos-APP

> 🏠 **Wallos 的专属 Android 伴侣应用** —— 基于 Flutter 构建，专为自托管 Wallos 实例打造。
> Wallos Android APP Client. A private Flutter companion app for self-hosted Wallos instances.



## 📖 项目简介

Wallos-APP 是一款基于 [Wallos](https://github.com/ellite/Wallos) 官方 API 开发的Android 客户端。Wallos 是一款开源、可自托管的个人订阅追踪器，帮助你轻松管理周期性支出、掌握预算并节省开支。

本项目将 Wallos 的核心功能带到了移动端，让你随时随地管理订阅，并在订阅即将到期时收到本地推送提醒。

## ✨ 功能特性

### 📋 订阅管理
- **浏览订阅列表** —— 查看所有订阅的详细信息（名称、价格、周期、下次付款日等）
- **添加订阅** —— 通过表单快速添加新订阅，支持自定义分类、货币、支付方式
- **编辑订阅** —— 修改已有订阅的各项信息
- **删除订阅** —— 移除不再需要的订阅

### 🔔 到期提醒
- **本地推送通知** —— 在 Wallos 设置的提醒时间自动触发 Android 本地通知
- **前台与手动同步** —— 前台与手动1同步 Wallos 数据，确保提醒准确无误
- **自定义提醒设置** —— 支持配置提醒提前天数和通知行为

### 📊 数据统计
- **月度/年度支出概览** —— 直观展示总支出趋势
- **分类统计** —— 按类别查看支出分布
- **货币转换** —— 支持多币种，自动按主货币汇总
- **图表可视化** —— 将 Wallos 的统计图表功能搬到移动端

### 🌙 深色模式
- **自动跟随系统** —— 根据系统主题自动切换深浅色
- **独立开关** —— 也可在应用内手动切换
- **全界面适配** —— 所有页面均已完成深色模式适配

### 📅 日历视图
- **月度日历** —— 以日历形式查看每月订阅到期日
- **到期高亮** —— 到期日自动标注，一目了然
- **快速跳转** —— 支持切换月份，查看历史与未来的订阅安排

### 🔐 安全与隐私
- **API Key 认证** —— 通过 Wallos API Key 安全连接你的实例
- **数据不经过第三方** —— 所有请求直连你的 Wallos 服务器，数据完全由你掌控
- **本地数据缓存** —— 离线状态下仍可查看已同步的订阅信息

## 🛠️ 技术栈

| 技术 | 说明 |
|------|------|
| **Flutter** | 跨平台 UI 框架 |
| **Dart** | 开发语言 |
| **Wallos API** | 后端数据源（需自建 Wallos 实例） |
| **本地通知** | Android 原生推送提醒 |
| **SharedPreferences** | 本地配置存储 |

## 📥 安装与使用

### 前置要求

1. **已部署 Wallos 实例**
   - 可通过 Docker 快速部署：
   ```bash
   docker run -d --name wallos \
     -v ./db:/var/www/html/db \
     -v ./logos:/var/www/html/images/uploads/logos \
     -e TZ=Asia/Shanghai \
     -p 8282:80 \
     --restart unless-stopped \
     bellamy/wallos:latest
   ```
   - 详细部署文档请参考 [Wallos 官方仓库](https://github.com/ellite/Wallos)

2. **获取 API Key**
   - 登录你的 Wallos 实例
   - 进入「设置」→「API」页面
   - 生成并复制你的 API Key

### 安装 APK

1. 从 [Releases](https://github.com/dstansice/Wallos-APP/releases) 页面下载最新版 APK
2. 在 Android 设备上安装（可能需要开启「允许安装未知来源应用」）
3. 首次打开应用，输入你的 Wallos 实例地址和 API Key

### 配置提醒

1. 确保 Wallos 网页端已为订阅设置了提醒时间
2. 确保 Wallos 网页端已开启了始终汇率转换


## 📡 API 说明

本项目基于 [Wallos 官方 API](https://api.wallosapp.com/) 开发，**主要调用**以下接口：

| 接口 | 功能 |
|------|------|
| `GET /api/subscriptions/get_subscriptions.php` | 获取订阅列表 |
| `POST /api/subscriptions/add_subscription.php` | 添加订阅 |
| `POST /api/subscriptions/update_subscription.php` | 更新订阅 |
| `POST /api/subscriptions/delete_subscription.php` | 删除订阅 |
| `GET /api/stats/` | 获取统计数据 |

> ⚠️ **注意**：请确保你的 Wallos 实例版本支持 API 功能。API 文档详见 [api.wallosapp.com](https://api.wallosapp.com/)。

## 🗺️ 功能路线图

- [x] 订阅增删改查
- [x] 本地到期提醒
- [x] 基础数据统计
- [x] 深色模式支持
- [x] 日历视图
- [ ] 桌面小部件（Widget）

## 📄 许可证

本项目采用 [MIT License](LICENSE) 开源协议。

> Wallos 本身采用 [GPLv3](https://github.com/ellite/Wallos/blob/main/LICENSE.md) 协议。本项目为 Wallos 的第三方客户端，与 Wallos 官方无直接关联。

## 🙏 致谢

- [ellite/Wallos](https://github.com/ellite/Wallos) —— 优秀的开源订阅追踪器
- [Flutter Team](https://flutter.dev) —— 出色的跨平台开发框架

## 📮 联系方式

如有问题或建议，欢迎通过以下方式联系：

- 提交 [GitHub Issue](https://github.com/dstansice/Wallos-APP/issues)
- 发送邮件至：jiujiu@010085.xyz

---

<p align="center">
  Made with ❤️ for the Wallos community
</p>

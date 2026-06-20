# 医疗服务预约小程序

> 基于 uni-app + Vue 3 开发的跨端医疗服务预约平台，支持微信小程序、H5、App 等多端运行。

## 项目简介

本项目是一个面向医疗服务场景的预约小程序，为用户提供便捷的医院信息查询、服务预约、订单管理、在线支付等一站式服务。项目采用 uni-app 跨端框架开发，一套代码可同时发布到微信小程序、H5、App、支付宝小程序、百度小程序、头条小程序等多个平台，有效降低开发成本，提升迭代效率。

## 技术栈

- **前端框架**: uni-app (Vue 3 + Composition API)
- **构建工具**: uni-app CLI
- **状态管理**: Vue 3 ref/reactive + uni-app globalData（轻量全局状态共享）
- **样式方案**: SCSS + rpx 适配 + WeUI 设计规范
- **UI 组件**: uni-ui（官方组件库）+ 自定义业务组件
- **地图服务**: 腾讯地图（地址定位与导航）
- **二维码**: UQRCode（支付二维码生成）
- **版本控制**: Git

## 效果演示

> 📸 以下为功能演示 GIF，点击可查看完整效果

### 地图导航

<!-- 在此插入医院定位、地图导航等演示 GIF -->
<p align="center">
  <img src="./screenshots/navigation.gif" alt="地图导航" width="300" />
</p>![Uploading 动画 (8).gif…]()


### 二维码支付

<!-- 在此插入支付二维码生成、扫码支付等演示 GIF -->
<p align="center">
  <img src="./screenshots/qrcode-payment.gif" alt="二维码支付" width="300" />
</p>

### 验证码校验

<!-- 在此插入手机号验证码发送、倒计时、校验等演示 GIF -->
<p align="center">
  <img src="./screenshots/verify-code.gif" alt="验证码校验" width="300" />
</p>

### 分享转发

<!-- 在此插入分享弹窗、微信好友分享等演示 GIF -->
<p align="center">
  <img src="./screenshots/share.gif" alt="分享转发" width="300" />
</p>

## 功能特点

### 核心功能

- **医院信息展示**: 支持医院列表浏览、分类筛选、详情查看，集成地图定位与导航功能
- **服务预约系统**: 提供多种医疗服务预约，支持日期时间选择、服务数量配置
- **订单全流程管理**: 覆盖订单创建、待支付、待服务、已完成、已取消等完整状态流转
- **在线支付**: 集成微信支付，支持二维码扫码支付，实时同步支付状态
- **验证码安全机制**: 手机号验证码发送与校验，包含倒计时防重发、格式校验等安全措施

### 技术亮点

- **跨端开发**: 基于 uni-app 实现一套代码多端运行，覆盖微信小程序、H5、App、支付宝/百度/头条小程序
- **组件化封装**: 自定义封装导航栏、分享弹窗、日期选择器、计数器、格式化等 5+ 个业务组件，支持灵活配置与复用
- **分包加载优化**: 采用分包策略（服务页、医院页独立分包），将主包体积控制在 2MB 以内，提升首屏加载速度
- **响应式适配**: 使用 rpx 单位实现多尺寸屏幕适配，兼容不同分辨率设备，确保 100% 视觉一致性
- **状态安全处理**: 异步数据加载前进行空值检查与默认值兜底，避免 `undefined` 访问错误，提升应用稳定性
- **API 统一封装**: 二次封装 `uni.request` 统一处理请求头、响应拦截与错误处理，支持 Promise 链式调用

### 交互体验

- **沉浸式导航栏**: 自定义 navbar 组件动态获取状态栏高度，实现沉浸式导航效果
- **分享转发**: 支持微信好友分享与海报生成，组件化封装实现双向状态同步
- **条件编译**: 针对平台特定功能（如微信小程序分享、地图导航）使用条件编译，确保多端兼容性

## 项目结构

```
project/
├── common/
│   ├── js/
│   │   └── utils.js          # 请求封装与工具函数
│   └── style/
│       ├── weui.css          # WeUI 样式库
│       └── app.css           # 全局公共样式
├── components/
│   ├── navbar/               # 自定义导航栏
│   ├── share/                # 分享弹窗
│   ├── dtPicker/             # 日期时间选择器
│   ├── counter/              # 计数器
│   └── formater/             # 格式化组件
├── pages/
│   ├── index/                # 首页
│   ├── hospital/             # 医院详情
│   ├── service/              # 服务预约
│   ├── order/                # 订单管理
│   ├── search/               # 搜索页面
│   ├── user/                 # 用户中心
│   └── clients/              # 客户列表
├── static/                   # 静态资源
├── manifest.json             # 应用配置
├── pages.json                # 页面路由与分包配置
└── main.js                   # 入口文件
```

## 快速开始

### 环境要求

- [Node.js](https://nodejs.org/) >= 16
- [HBuilderX](https://www.dcloud.io/hbuilderx.html) 或 VS Code + uni-app 插件
- [微信开发者工具](https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html)（微信小程序开发）

### 安装依赖

```bash
npm install
```

### 运行项目

**HBuilderX 方式**:
1. 导入项目到 HBuilderX
2. 点击菜单栏「运行」→「运行到小程序模拟器」→「微信开发者工具」

**CLI 方式**:

```bash
# 微信小程序
npm run dev:mp-weixin

# H5
npm run dev:h5

# App
npm run dev:app
```

### 构建发布

```bash
# 微信小程序发布
npm run build:mp-weixin

# H5 发布
npm run build:h5

# App 发布
npm run build:app
```

## 发布说明

### 微信小程序发布流程

1. 使用 HBuilderX 或 CLI 构建微信小程序代码
2. 打开微信开发者工具，导入构建后的 `dist/build/mp-weixin` 目录
3. 点击右上角「上传」按钮，填写版本号与项目备注
4. 登录 [微信公众平台](https://mp.weixin.qq.com/)，进入「版本管理」
5. 提交审核，填写功能描述与截图
6. 审核通过后点击「发布」即可上线

## 相关链接

- [uni-app 官方文档](https://uniapp.dcloud.net.cn/)
- [Vue 3 文档](https://cn.vuejs.org/)
- [微信小程序开发文档](https://developers.weixin.qq.com/miniprogram/dev/framework/)
- [uni-ui 组件库](https://uniapp.dcloud.net.cn/component/uniui/uni-ui.html)

## 许可证

[MIT](LICENSE)
<img width="545" height="886" alt="动画 (8)" src="https://github.com/user-attachments/assets/68b1bdef-d39b-4567-9b2c-d10f251253fa" />

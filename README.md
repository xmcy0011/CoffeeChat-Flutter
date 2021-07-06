# CoffeeChat-Flutter

opensource im with server(go) and client(flutter+swift), this a simple flutter client, server see [Server](https://github.com/xmcy0011/CoffeeChat)

> PS：目前flutter技术栈暂停维护，仅供参考。
主要是因为实力有限，实现的效果没有原生好，不流畅，另外精力也是有限，顾不过来。如果有flutter大佬愿意贡献代码，欢迎给我发邮件😊。

## Getting Started

- for Android: 使用Android Studio打开android文件夹
- for iOS: 使用xcode打开ios文件夹，选择xcworkspace

## 目录结构说明

- Flutter SDK
    - /model：实体类
    - /proto：protobuf3协议文件
    - im_client.dart：登录、和服务器通信（其他业务模块调用send发送请求，收到结果后回调）
    - im_message.dart：发送消息、获取历史消息
    - im_session.dart：获取会话列表
- gui
    - /model：实体类
    - /widget：各种组件
    - page_chat.dart：消息tab
    - page_home.dart：主页
    - page_me.dart：我
    - page_message.dart：聊天界面

## Dependencies

```bash
cupertino_icons: ^0.1.2 # package 包含了一些 Cupertino widget 用到的图标资源
protobuf: ^1.0.1     # protobuf dart 支持
intl: ^0.15.7         # 提供了国际化和本地化的能力
provider: ^2.0.0+1    # 提供了一个用来跨界面管理 state 的简单办法
shrine_images: ^1.0.0 # 有一些需要用到的产品和商店的元素
toast: ^0.1.4         # 类似安卓的不阻塞提示
uuid: 2.0.1           # msgID生成(使用uuid，确保消息唯一)
shared_preferences: ^0.5.2 # 保存键值对信息
sqflite: ^1.1.7+1     # SQLite plugin for Flutter. Supports both iOS and Android
dio: ^3.0.7
agora_rtc_engine: 1.0.3     # 声网SDK
permission_handler: ^3.0.0  # 权限
```

PS：音视频通话功能依赖声网SDK，需要自行注册账号，1个月免费10000分钟，全局搜索agoraAppId，然后替换成自己的即可。

## 实现的功能

- [x] 闪屏页
- [x] 登录
    - [x] 记住密码
    - [x] 自动重连（可能有BUG）
    - [ ] 自动登录
    - [ ] 网络连接状态提示
- [x] 会话列表
    - [x] 最新消息
    - [x] 圆角头像
    - [x] 未读计数小红点
- [x] 聊天
    - [x] 收发文本
    - [x] 失败重发
    - [x] 下拉查询加载历史消息
- [ ] SDK
    - [x] SQFilte缓存会话列表

- [x] 闪屏全屏
- [ ] 搜索
- [x] 聊天框我-对方颜色区分显示
- [ ] 昵称
- [ ] 头像
- [ ] 联系人功能
- [ ] 自动登录
- [ ] 会话自动刷新（第一次、新会话）
- [x] 清除未读计数
- [x] tab不好点击
- [x] 消息时间
- [x] emotion存储乱码问题解决
- [ ] 消息标题栏显示未读总数

## 预览
具体见 demo 文件夹下的图片

## 运行

公网：106.14.172.35  
im_gate:8000/tcp，登录、消息处理等  
im_http:18080/http，用户注册  

测试账号：1007、1008  
密码：12345  

## 常见问题

### Building for iOS Simulator, but the linked and embedded framework 'App.framework' was built for iOS. (in target 'Runner' from project 'Runner')
1. 删除ios/flutter/app.framework
2. 重新编译

### ios图标替换
1. mac电脑下载安装icon maker(链接:https://pan.baidu.com/s/1j2WZSJ83RYu6hLnK4ICSYw  密码:1t9p)
2. 打开后，选择一张png图标，然后勾选Rounded Corner，点击IOS。
3. 把生成的目录IOS/Assets.xcassets/AppIcon.appiconset复制替换到ios/Runner/Assets.xcassets/AppIcon.appiconset
4. 重新编译即可

### pb报错

1. 查找protobuf最新的可用版本。[https://github.com/dart-lang/protobuf](https://github.com/dart-lang/protobuf)
2. 打开pubspec.yaml，更改protobuf插件的版本为最新的即可。

## 联系我
email：xmcy0011@sina.com
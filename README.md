# 中台建设方案实现定制化直播平台

#### 介绍

- 市面上的直播系统要么是SaaS的，拿来直接用，但功能总是有不满足业务需求的地方，提给厂商开发，等到猴年马月。要么是云厂商的各种资源的调用，要组装成自己的业务，要投入大量的研发。有没有一种方式，基本的直播功能已经有了，针对业务需要的特定功能，做一些简单的定制开发就能快速上线？
- 尝试用中台的方案，将定制的业务抽离出来单独做，通用的直播功能使用单点跳转的方式，用户进入SaaS环境使用
- 基于以上思路，需要实现定制业务抽离的端包括：管理后台端、直播观看端、定制API，需要厂商的直播平台架构支持这几个端的定制和直播基础功能的分离
- 目前找到可用并且走通的直播平台，[保利威](https://www.polyv.net?src=wh)可以支持，详细方案可以+V:wjc24680525，备注“中台”

#### 方案架构图
![Image](https://github.com/user-attachments/assets/b8fcf9f8-33bf-4a0e-92c7-49500cef929b)
#### 方案部署图
![Image](https://github.com/user-attachments/assets/69d9d347-d533-4863-b06e-3e297fab1fc2)
#### 观看页定制
- 基于官方提供的[webSDK](https://gitee.com/polyv_ef/polyv-web-live-watch-sdk/tree/master)，UI层的代码已经开源
- 官方[webSDK](https://gitee.com/polyv_ef/polyv-web-live-watch-sdk/tree/master)底层已支持：直播/回放播放、连麦、聊天互动、邀请、抽奖、红包、观看上报、自定义userid传参等
- 在界面UI层增加业务功能的定制，如界面UI的修改、增加自定义的抽奖功能等
#### 管理后台定制
- 基础直播功能可基于官方提供的[单点登录能力](https://help.polyv.net/#/live/api/account/sso_manager)开发
- 定制功能都做到一个系统内，调用厂商提供的[API](https://help.polyv.net/#/live/api/v4/channel/create)实现比如直播创建时传入组织通讯录中的用户，增加直播审批环节，成员特定功能权限等等
- API可基于厂商提供的能力封装，基础的数据存在厂商，改造的功能数据存在定制系统内
#### 方案对比
![Image](https://github.com/user-attachments/assets/ff52b23d-1bb4-40d3-886a-c68505f976d0)

---
title: 目录结构
---
<!--
 * @Description: 目录结构介绍
 * @Version: Beta1.0
 * @Author: 【B站&公众号】Rong姐姐好可爱
 * @Date: 2021-01-13 23:27:36
 * @LastEditors: 【B站&公众号】Rong姐姐好可爱
 * @LastEditTime: 2021-01-17 17:10:54
-->

# 目录结构介绍

利用官方提供的指令`npm init egg --type=simple`可以得到egg项目模板，而实际的项目会比模板复杂一些、层次分明一点


## 基础结构
```bash
egg-project
├── package.json
├── app.js (可选)
├── agent.js (可选)
├── app
|   ├── router.js
│   ├── controller
│   |   └── home.js
│   ├── service (可选)
│   |   └── user.js
│   ├── middleware (可选)
│   |   └── response_time.js
│   ├── schedule (可选)
│   |   └── my_task.js
│   ├── public (可选)
│   |   └── reset.css
│   ├── view (可选)
│   |   └── home.tpl
│   └── extend (可选)
│       ├── helper.js (可选)
│       ├── request.js (可选)
│       ├── response.js (可选)
│       ├── context.js (可选)
│       ├── application.js (可选)
│       └── agent.js (可选)
├── config
|   ├── plugin.js
|   ├── config.default.js
│   ├── config.prod.js
|   ├── config.test.js (可选)
|   ├── config.local.js (可选)
|   └── config.unittest.js (可选)
└── test
    ├── middleware
    |   └── response_time.test.js
    └── controller
        └── home.test.js

```

## 相关说明


- `app/router.js` 用于配置 URL 路由规则，具体参见 Router。
- `app/controller/**` 用于解析用户的输入，处理后返回相应的结果，具体参见 Controller。
- `app/service/**` 用于编写业务逻辑层，可选，建议使用，具体参见 Service。
- `app/middleware/**` 用于编写中间件，可选，具体参见 Middleware。
- `app/public/**` 用于放置静态资源，可选，具体参见内置插件 egg-static。
- `app/extend/**` 用于框架的扩展，可选，具体参见框架扩展。
- config/config.{env}.js` 用于编写配置文件，具体参见配置。
- config/plugin.js` 用于配置需要加载的插件，具体参见插件。
- test/** 用于单元测试，具体参见单元测试。
- `app.js 和 agent.js` 用于自定义启动时的初始化工作，可选，具体参见启动自定义。关于agent.js的作用参见Agent机制。


由内置插件约定的目录：

- `app/public/**` 用于放置静态资源，可选，具体参见内置插件 egg-static。
- `app/schedule/**` 用于定时任务，可选，具体参见定时任务。


若需自定义自己的目录规范，参见 Loader API

- `app/view/**` 用于放置模板文件，可选，由模板插件约定，具体参见模板渲染。
- `app/model/**` 用于放置领域模型，可选，由领域类相关插件约定，如 egg-sequelize或者egg-sequelize-plus（是在egg-sequelize基础上开发的模块，目前我仍在维护）
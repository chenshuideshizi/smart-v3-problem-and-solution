# Smart V3 Problem

#### 问题一

初始化 websocket 长连接失败导致后面的的代码不执行

websocket 连接失败后，重连机制的时间间隔太短


#### 问题二

**这个问题属于一个误会，是因为开启了 Slow 3G 模式**

在开启 Disable cache 的情况下， 页面打开总时长 1.8min

在关闭 Disable cache 的情况下，页面打开总时长 12s

**vue.js 和 main.js 加载时间太长**

initiator: parser 的过程太长

- main.js 4.4MB transferred over network, resource size 23MB

![avatar](./picture/main_load_pic.png)

- vue.js  415kB transferred over network, resource size 1.6MB

![avatar](./picture/vue_load_pic.png)

- page_default_bg 图片加载时间太长， 图片大小1.6M

![avatar](./picture/page_default_bg_load_pic.png)


#### 3. webpack 配置的问题

- 启动成功后，控制台打印了来的内容太多
- webpack-dev-server 热更新后，没有打印服务启动的地址。打印的内容应该和第一次启动后的内容相同

#### 4. 刚打开页面的时候只有loader，没有显示背景

解决方法骨架屏，应该选进行路由跳转然后再请求接口，

进入路由页面后，显示骨架屏

### 当获取网站信息的接口报错后， title 为 undefined

当接口报错后，应该不做任何操作，只显示报错信息
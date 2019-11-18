## Demo
[演示](https://www.readingblog.cn/#/tutorials/circle-select) (https://www.readingblog.cn/#/tutorials/circle-select)
## 开发调试
安装相关依赖，执行
```
npm run start
```
浏览器打开examples文件夹下test.html即可调试
## 构建
```
npm run build
```
## 配置
```js
import getPlatform from '../../utils/getPlatform';

const platform = getPlatform();

export default {
  appID: '',
  // 是否自动收集点击事件
  autoClick: true,
  debug: false,
  logUrl: '',
  sdk: {
    // 类型
    type: 'js',
    // 版本
    version: SDK_VERSION,
  },
  // 平台参数
  platform,
  optParams: {},
  postMsgOpts: [],
};
```
1. appID 你可以在初始化时注册一个appID，所以相关的埋点都会带上这个标记，相当于对埋点数据做了一层app维度上的管理。
2. autoClick 默认为true，开启会自动收集点击事件(即点击无埋点)。当然你可以实现页面登录、登出、浏览时间的埋点功能，同时可以在配置中加开关控制，让用户可以有选择地启用这些功能。
3. debug 默认不开启，开启会将埋点数据打印到控制台，便于调试。
4. logUrl 接收日志的后端地址
5. sdk sdk自身信息一些说明
6. platform 默认会自动获取一些平台参数，你也可以通过配置这个字段覆盖它
7. optParams 自定义数据
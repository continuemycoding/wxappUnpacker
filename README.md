
# 说明
- 本项目无法适用于 2018 年前开发的小程序(如最后更新时间为 2017.7.12), 请过早的小程序不用再尝试了
- 本项目完全基于 [wxappUnpacker](https://github.com/qwerty472123/wxappUnpacker "wxappUnpacker") 改进的。


# 分包功能

当检测到 wxapkg 为子包时, 添加-s 参数指定主包源码路径即可自动将子包的 wxss,wxml,js 解析到主包的对应位置下. 完整流程大致如下: 
1. 获取主包和若干子包
2. 解包主包 `node wuWxapkg.js "C:/workspace/decrypt/__APP__.wxapkg"`
3. 解包子包 `node wuWxapkg.js -s="C:/workspace/decrypt/__APP__.wxapkg" "C:/workspace/decrypt/_subpackages_Main_.wxapkg`

TIP
> -s 参数可为相对路径或绝对路径, 推荐使用绝对路径, 因为相对路径的起点不是当前目录 而是子包解包后的目录

```
├── testpkg
│   ├── sub-1-xxx.wxapkg #被解析子包
│   └── sub-1-xxx               #相对路径的起点
│       ├── app-service.js
│   ├── master-xxx.wxapkg
│   └── master-xxx             # ../master-xxx 就是这个目录
│       ├── app.json
```

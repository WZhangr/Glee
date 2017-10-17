# Glee
Built by Electron, Vanilla JS, Plain CSS
> 主要是感觉 "目前最好的网易云音乐客户端 [trazyn/ieaseMusic](https://github.com/trazyn/ieaseMusic)" 不太和我审美

## Description
- 基于 Electron, Windows 专属
- 原生 JS, 手写 CSS
- 界面抄袭巨硬家的 Groove Music (还直接偷了 iconfont 用)
- 数据来自网易云音乐API, 搬了[Binaryify/NeteaseCloudMusicApi](https://github.com/Binaryify/NeteaseCloudMusicApi/blob/master/util/crypto.js), [sqaiyan/netmusic-node](https://github.com/sqaiyan/netmusic-node/blob/master/crypto.js)的加密源码
- 不能登录的, 主要是不会写, 还有邮箱登录 API 被封了对吧 ?
- 因为不能登录所以就只算个播放器吧, 像 [listen1/listen1](https://github.com/listen1/listen1) 这样
- API里不登录能用的大概都用上了
- 等有空再加上搜索吧

## Feature
- 好看
- 播放条随专辑封面变色
- 启动时还原上次播放状态
- 解锁网页端大部分变灰歌曲 (奇特姿势来自[JixunMoe/netease-cloud-music-api](https://github.com/JixunMoe/netease-cloud-music-api))
- 下载歌曲写入ID3 Tag (需要灵感来自[codezjx/netease-cloud-music-dl](https://github.com/codezjx/netease-cloud-music-dl))

## Keyboard shortcuts

Description            | Keys
-----------------------| -----------------------
暂停/播放              | <kbd>Space</kbd>
上一曲                 | <kbd>Ctrl</kbd> <kbd>Left</kbd>
下一曲                 | <kbd>Ctrl</kbd> <kbd>Left</kbd>

## References
- ~~[jariz/vibrant.js](https://github.com/jariz/vibrant.js)~~  
感觉很有名, 描述里写的是"a javascript port of the awesome Palette class in the Android support library", 但是对比安卓上Phonograph的取色效果，用着总觉得不太理想, 翻issue发现作者说是基于color-thief的,就很无语了, 作者有提到可以看看material-palette, 试用感觉确实比这个好
- ~~[chengyin/albumcolors](https://github.com/chengyin/albumcolors)~~ 
本来展开详情想实现旧版iTunes的样式, 找了个这个库, 然而写完发现太难看了(是我的问题), 于是临摹新版iTunes的展开样式
还有作者没有控制canvas的大小, 图片太大会卡, 一开始还不知道是什么阻塞了......
- ~~[briangonzalez/rgbaster.js](https://github.com/briangonzalez/rgbaster.js)~~
百度搜到的, 试了跟vibrant.js差不多效果, (emmm其实是从它的issue里知道vibrant.js的), 取多色palette时颜色非常相近, 感觉比较废, 后来找到material-palette
- [marijnvdwerf/material-palette](https://github.com/marijnvdwerf/material-palette)
描述是"colour extraction library, based on the Palette support library", 作者说用js翻译了绝大部分palette库的java代码, 感觉就非常有诚意了, 虽然有时还是蜜汁取色, 不过相比之下效果还算好, 也有可能是心里作用吧
- [lokesh/color-thief](https://github.com/lokesh/color-thief/)
emmm还用这个主要是取主色比较方便, 虽然主色有可读性问题, 不过用到地方不是特别重要, 忽略忽略
- [Binaryify/NeteaseCloudMusicApi](https://github.com/Binaryify/NeteaseCloudMusicApi) , [sqaiyan/netmusic-node](https://github.com/sqaiyan/netmusic-node)
能扒到网易云API真是太牛逼了, 自己试着在source里跟踪调试, 直接原地爆炸, 也可能是我太菜的缘故......实话说有些接口没给type参数取哪些啊, 好吧我不该要求这么高的
- [Zazama/node-id3](https://github.com/Zazama/node-id3)
写ID3 tag用, 好像最近是才出的包, 看到npm上相关的好多好多, 反正是google搜到第一个, 也懒着挑了...最开始用的时候还只有同步的, 我想怎么放歌的时候会卡一下 ~ 现在更新后有异步调用了
- [electron-userland/electron-json-storage](https://github.com/electron-userland/electron-json-storage)
用来保存场景了, 感觉这个有同步的才好啊, 现在为了退出前保存设了一个flag, 然而一刷新就退出...调试麻烦了好多, 写代码的时候还是注释掉了

## Preview
![1](./screenshot/1.png)
![2](./screenshot/2.png)
![3](./screenshot/3.png)
![4](./screenshot/4.png)
![5](./screenshot/5.png)
![6](./screenshot/6.png)
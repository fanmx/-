# jsmpeg-ws-web
>jsmpeg + ws + ffmpeg  纯js实现多路视频直播浏览器播放，无插件限制

> 简单描述下原理， 客户端页面连接websocket将需要查看的直播地址传递过来，websocket服务端通过[FFMPEG](https://ffmpeg.org/download.html)将直播视频转码为mpegts 格式发送给客户端， 客户端通过[**jsmpeg**](https://github.com/phoboslab/jsmpeg) 解码数据 通过canvas 将直播画面绘制在页面上;

### First
First of all, it's a fork of [**node-rtsp-stream-es6**](https://github.com/Wifsimster/node-rtsp-stream-es6)
### depends
[**jsmpeg**](https://github.com/phoboslab/jsmpeg), [FFMPEG](https://ffmpeg.org/download.html)

### DEMO
 test目录下提供了个demo， 启动server.js， 将view-stream.html部署在服务器上 打开即可查看效果
 server.js 提供 ws服务和自动运行本地计算机上的ffmpeg 程序 解析web端传送过来的直播地址，并推送mpegts 程序到客户端， 客户端通过jsMpeg 解析数据绘制在canvas上,不依赖flash 和h5的video标签，所以也不受他们的限制，什么自动播放啥的轻松实现；
 经测试，停留时间过久，会出现延迟现象，并且同个端口目前浏览器限制为最多6路，本次测试1个端口下分配2路，多路需自行指定相应端口；

### 执行命令
`npm install -g ws`
`npm install ws`
`npm install http-server -g`
`http-server`
`node ./test/server.js`
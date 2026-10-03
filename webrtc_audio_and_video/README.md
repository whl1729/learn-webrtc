# 学习《WebRTC 音视频实时互动技术》

学习《WebRTC 音视频实时互动技术》书中的源代码。

## 启动信令服务器

服务器使用 HTTPS，首次运行前请在项目目录生成本地开发证书：

```sh
mkdir -p cert
openssl req -x509 -newkey rsa:2048 -nodes -keyout cert/cert.key -out cert/cert.pem -days 365 -subj "/CN=localhost"
node sigserver.js
```

浏览器会提示该自签名证书不受信任，开发环境中选择继续访问即可。

启动后通过 `https://localhost/room.html?room=test` 打开示例页面。不要直接双击
`ch05/room.html`，因为浏览器会以 `file://` 打开页面，无法加载 Socket.IO。

如果第二台电脑访问，请把 `localhost` 换成运行信令服务器电脑的局域网 IP，
例如 `https://192.168.1.10/room.html?room=test`；两台电脑必须使用相同的
`room` 值。局域网连接不需要 TURN，跨公网连接则必须填写可用的 TURN 服务器。

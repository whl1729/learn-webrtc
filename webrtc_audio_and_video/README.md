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

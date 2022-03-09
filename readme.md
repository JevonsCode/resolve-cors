# 跨域跨 tab H5 通信解决方案

## 运行

```bash
# run
npm i && npm start

# 关闭
npm run delete
```

### open:
- http://127.0.0.1:8080/
- http://127.0.0.1:8081/

## 原理

_Demo 为单向，双向自行监听 storage_
- B 页面（接收方）
- A 页面（发送方）

B 输出一个用于存储的路由（或其他判断），A 页面用 iframe 打开此地址，
并调用其抛出的存储方法，用 postMessage 方法存储数据至 localStorage，
B 页面理所应当的获取同源下的 localStorage

(为保证 localStorage 的取值准确，储存时 key 应该为一个 hash，跳转另一个页面带此 hash 取值，具体视业务而定)
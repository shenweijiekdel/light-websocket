# light-websocket
基于 Websocket 协议进行简单封装的协议标准

## 目标

- 针对 JS Websocket 无法发送部分控制帧，需要在应用层额外实现连接保活机制
- Websocket 实现库基本不提供重连机制，也不应该提供重连机制，它需要在应用层实现

对于以上两点，基于 Websocket 协议进行简单封装，在数据帧首部插入 1 字节 类型标识，而创建了这个工作在 Websocket 和 应用中间层简单协议，这一层主要封装连接保活机制与自动重连机制，上层应用无需关注这两个机制

## 特点

- 成本极小，只在 Websocket 数据帧首部插入 1 byte 的类型标识，剩余部分承载数据
- 没有额外的协议封装，保持简单自由

## 相关实现库

- https://github.com/shenweijiekdel/light-websocket-client-ts (Typescript 客户端)
- https://github.com/shenweijiekdel/light-websocket-server (Golang 服务端)

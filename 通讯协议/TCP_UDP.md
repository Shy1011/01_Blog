# OSI 七层模型
应用 表示 会话 传输 网络 链路 物理
应用 : HTTP FTP SMTP等协议 应用程序 与用户之间的同学
表示层 : 数据的加密解密
会话层: 用于建立会话链接
传输 : 用于<font color="#f79646">端到端</font>的数据传输TCP/IP 也能错误检测 端口
网络 : IP 用于源到目的地的路由和转发  IP地址
链路 : 将数据分割成帧
物理 : 用于定义数据传输的方式 如 电压  频率等 MAC地址


数传层 : 通过查看端口能够确定是发给哪个应用程序
网络层 : 通过检测IP地址知道是不是发给自己的

## TCP/IP协议如何传输数据

[TCP/IP网络模型](https://www.bilibili.com/video/BV1uk4y1w7ZV/?spm_id_from=333.788.top_right_bar_window_history.content.click&vd_source=2f6e531d9d833ca7fdcd8c5bb99bd1bb)
![](assets/Pasted%20image%2020231028175837.png)

在这里OSI的七层模型中的 :
<font color="#f79646">应用 表示 会话 - > 被称为应用层</font>
传输 
网络 
链路 
<font color="#f79646">物理层被省略</font>

___
应用层 发出数据
传输层 : 在数据上加上端口号告诉 信息是给哪个应用的 封装为 TCP/UDP包
网络层 : 加上IP地址 封装为 IP报文
链路层 : 数据帧 加上 帧头 帧尾
<font color="#4bacc6">最后一共包含</font> <font color="#f79646">目的地址 源地址 类型字段 数据 CRC校验码</font>

# TCP
[三次挥手 四次握手 丢包问题](https://www.bilibili.com/video/BV1kV411j7hA/?spm_id_from=333.788.recommend_more_video.1&vd_source=2f6e531d9d833ca7fdcd8c5bb99bd1bb)
TCP就相当于 <font color="#4bacc6">打电话</font> 建立在<font color="#f79646">连接</font>的基础上
UDP就相当于 <font color="#4bacc6">写信 </font>建立在<font color="#f79646">不连接</font>的基础上
## 三次握手
![](assets/Pasted%20image%2020231028203647.png)

*SEQ（Sequence Number）*：这是用来标识TCP报文段的序列号。它表示报文段中第一个字节的序列号。

不是两次握手是为了 : 防止已失效的服务报文,又突然传输到服务端引起错误.

例如 
1. 第一个请求建立连接的服务报文在网络阻塞中未送达.
2. 客户端又发送了请求建立连接的报文,这次成功建立链接.
3. 第一次发送的请求建立连接报文这时候成功传输到了客户端
4. 造成 客户端认为这是一次连接 服务端认为这是两次链接.造成状态不一致
<font color="#f79646">目的  : 三次握手是为了在不可靠的网络信道上建立可靠的连接</font>
![](assets/Pasted%20image%2020231028184432.png)
## 丢包问题
![](assets/Pasted%20image%2020231028183604.png)
- 发送缓冲区第一个字节序号为 0 
- 然后取一部分组成报文 (序列号 + 长度)
- 加上头尾

ACK  = 序列号 + 数据长度 = 下一包数据的起始序列号

## 四次挥手
![](assets/Pasted%20image%2020231028184808.png)

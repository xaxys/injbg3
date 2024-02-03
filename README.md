# injbg3

博德之门3联机-基于IP的游戏发现

公网 UDP 单播联机，不再需要虚拟局域网！

利用 Hook 技术，拦截游戏对 UDP 的发送、接收等操作，实现基于 IP 的游戏发现和联机

至此，博德之门3联机不再需要诸如 n2n, OpenVPN, Hamachi 等虚拟局域网，直接公网联机！

主要实现以下两点

- 拦截客户端发现服务器时发出的 UDP 广播包，将其改为单播到指定服务器 IP，实现稳定的游戏发现 (IPv4/IPv6)
- 对于 IPv6
  - 重定向对 `0.0.0.0` 的监听到 `[::0]`
  - 建立 FakeIP 表，将 IPv6 地址映射到 `127.0.127.1 ~ 127.0.127.100` 并提供给 文明6 虚假的 IPv4 地址 (实现原理同 Clash 的 FakeIP)

暂时还在 injciv6 的 branch 上，当然功能已经可以用了，移步[injbg3](https://github.com/xaxys/injciv6/tree/injbg3)

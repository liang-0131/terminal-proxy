### 给各平台终端加上代理的方法
- 目录
  - [WSL2](#)  
#### WSL2
- 条件
  - V2rayN中开启`允许来自局域网的连接`    
  - <img src="https://user-images.githubusercontent.com/32185381/149700844-b2cafe75-1180-4158-8b81-fef0521d78b0.png" width="450">  
  - `Windows Defender 防火墙`-->`允许的应用`-->左1右2勾选放行V2rayN   
  - <img src="https://user-images.githubusercontent.com/32185381/149701357-47b954c0-eb44-4d45-970c-44b0ddaa6ce0.png" width="450"> 
  - ⚡如果实在无效就关闭防火墙

- 安装[脚本](https://github.com/liang-0131/wsl2proxy/blob/master/README-zh.md)
- 设置
  - 协议：socks5
  - 端口：7890（ V2rayN 默认10808） 
  - <img src="https://user-images.githubusercontent.com/32185381/149701826-24401f7d-de82-4ffd-a8d8-a0648c845eff.png" width="300">
- 测试是否成功
  - curl www.google.com
  - curl cip.cc
---
#### MAC
---
#### Linux
- 安装[proxychains4](https://github.com/rofl0r/proxychains-ng)

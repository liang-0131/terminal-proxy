### 给各平台终端加上代理的方法
- 目录
  - [WSL2](#)
  - [Mac](#MAC)
  - [Linux](#Linux)
#### WSL2
- 条件
  - V2rayN中开启`允许来自局域网的连接`    
  - <img src="https://user-images.githubusercontent.com/32185381/149700844-b2cafe75-1180-4158-8b81-fef0521d78b0.png" width="450"> 
  - `Windows Defender 防火墙`-->`允许的应用`-->左1右2勾选放行V2rayN   
  - <img src="https://user-images.githubusercontent.com/32185381/149701357-47b954c0-eb44-4d45-970c-44b0ddaa6ce0.png" width="450"> 
  - 管理员运行powershell放行wsl2网卡
  ```bash
  # 直接放开 `vEthernet (WSL)` 这张网卡的防火墙  
    New-NetFirewallRule -DisplayName "WSL" -Direction Inbound -InterfaceAlias "vEthernet (WSL)" -Action Allow
  ```
  - ⚡如果实在无效就关闭防火墙试试能不能通过
    - 如通过且不想关闭防火墙：
    - `高级设置`-->`入站规则`-->`新建规则`-->`端口`-->`TCP`-->`特定端口：<你的v2rayN的http端口>`-->`允许连接`-->`3个全选`-->`名称、描述自定`

- 安装[脚本](https://github.com/liang-0131/wsl2proxy/blob/master/README-zh.md)
- 设置
  - 协议：http
  - 端口：7891（ V2rayN 默认10809） 
  - <img src="https://user-images.githubusercontent.com/32185381/149701826-24401f7d-de82-4ffd-a8d8-a0648c845eff.png" width="300">
- 测试是否成功
  - curl www.google.com
  - curl cip.cc
---
#### MAC
- 在`~/.bash_profile`或`~/.zshrc`中添加
```bash
# clashx默认3协议都是7890端口
# 终端代理
 export http_proxy=http://127.0.0.1:7890
 export https_proxy=$http_proxy
 # 生效
 source .zshrc or source .bash_profile
```
---
#### Linux
- 同mac yunxingyici  
或
- 安装[proxychains4](https://github.com/rofl0r/proxychains-ng)

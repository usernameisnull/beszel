## 安装
在wsl里安装hub,也就是dashboard
```bash
# -p是暴露页面访问的端口
curl -sL https://get.beszel.dev/hub -o /tmp/install-hub.sh && chmod +x /tmp/install-hub.sh && /tmp/install-hub.sh -p 9090
```
## 安装agent
在`172.24.91.234:9090`打开页面,注册账号后登录并点击`添加 客户端`, `172.24.91.234`是wsl的ip不要用localhost或者127.0.0.1, 因为后面生成的agent安装目录好像会用这个地址   
- 名称: 随意填写,会在客户端列表里显示为名称
- 主机/IP: 就是要监控的主机的ip
- 其他的不要修改
- 复制Linux安装命令, 类似下面的
    ```bash
    curl -sL https://get.beszel.dev -o /tmp/install-agent.sh && chmod +x /tmp/install-agent.sh && /tmp/install-agent.sh -p 45876 -k "ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIPLQxKKK33EZprjUg3UYShFeeoV/MydumP3fDakUl9ZB" -t "a27-ede39b7ee28-20ab-a6663320c2" -url "http://172.24.91.234:9090" --china-mirrors
    ```
- 登录agent机器(就是主机/IP那里填入的机器),然后执行上一步的安装命令
- 点击"添加客户端"
- 等待一会就可以在客户端列表里看到了
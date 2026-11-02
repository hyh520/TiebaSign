<section align="center">
  <a href="https://github.com/hyh520/TiebaSign/" target="_blank">
    <img src="https://yife68.gitee.io/icat-pic/posts/2022/5/2.webp" width="260" />
  </a>
</section>

<h1 align="center">TiebaSign-贴吧签到助手</h1>

<section align="center">
<img src="https://yife68.gitee.io/icat-pic/posts/2022/5/3.svg" />
</section>

# 使用
自动化执行任务: 百度贴吧每日签到

定时任务计划运行时间: 每天北京时间 **02:07**（UTC 18:07，对应 cron 表达式 `7 18 * * *`）。可在 [工作流配置](.github/workflows/main.yml) 中修改。

运行环境: `ubuntu-latest`、Python **3.12**，依赖 `requests`；工作流使用 `actions/checkout@v7` 和 `actions/setup-python@v7`。

除定时运行外，推送到 `main` 分支也会触发签到，并支持在 Actions 页面手动运行。

❶  [Fork 仓库](https://github.com/hyh520/TiebaSign)

❷  `仓库` → `Settings` → `Secrets and variables` → `Actions` → `Secrets` → `New repository secret`, 添加`Secrets`变量如下:

| Name | Value |
|  ------  |  ------  |
| BDUSS | 百度贴吧BDUSS, 打开浏览器，登录 [百度贴吧](https://tieba.baidu.com/), 打开控制台 → 应用 → Cookie，复制 `BDUSS` 的值 |

![](https://yife68.gitee.io/icat-pic/posts/2022/5/4.webp)

❸  邮箱通知配置 `仓库` → `Settings` → `Secrets and variables` → `Actions` → `Secrets` → `New repository secret`, 添加`Secrets`变量如下:

| Name | Value |
|  ------  |  ------  |
| HOST | SMTP服务器的主机地址，可包含端口，例如 `smtp.example.com:465`；省略端口时使用 `25` |
| FROM | 发件人的邮箱地址 |
| TO | 收件人的邮箱地址，可以同时发送给多个收件人，用"#"进行分隔 |
| AUTH | 发件人的邮箱授权码或密码 |

端口 `465` 使用 SSL，端口 `587` 使用 STARTTLS；请按邮箱服务商提供的 SMTP 地址和端口填写。

❹  `仓库` → `Actions`, 启用 `Baidu Tieba Auto Sign` 工作流。需要立即运行时，选择该工作流 → `Run workflow` → 选择 `main` 分支 → `Run workflow`。

# 签到预览
![](https://yife68.gitee.io/icat-pic/posts/2022/5/5.webp)

# 如何获取Cookie
百度贴吧BDUSS, 打开浏览器，登录 [百度贴吧](https://tieba.baidu.com/), 打开控制台 → 应用 → Cookie，复制 `BDUSS` 的值

DevTools截图:
<img width="1156" src="https://yife68.gitee.io/icat-pic/posts/2022/5/6.webp">

# GitHub地址
项目直达链接：[hyh520/TiebaSign](https://github.com/hyh520/TiebaSign/)

上游项目：[yife68/TiebaSign](https://github.com/yife68/TiebaSign/)

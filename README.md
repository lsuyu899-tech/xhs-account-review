# xhs-account-review

分析小红书创作中心手动导出的 Excel/CSV，并生成可分享、可离线打开的人话版 HTML 账号复盘。

## 能做什么

- 直接说明账号当前处于什么状态
- 解释曝光、点击、互动、主页访问和关注之间的断点
- 按发布时间计算数据成熟度，避免过早判断新笔记
- 找出值得继续、需要重写和应暂停的内容方向
- 给出按顺序执行的下一阶段行动和 5 篇控制实验

## 安全边界

只处理用户主动提供的本地导出文件，不读取 Cookie、Token、浏览器会话或账号凭证，不登录、发布、评论或操作小红书账号。

## 安装

```powershell
npx.cmd -y skills add lsuyu899-tech/xhs-account-review --skill xhs-account-review --agent codex --global --yes
```

## 使用

上传小红书创作中心导出的 `.xlsx`、`.xls`、`.csv` 或 `.tsv`，然后说：

```text
使用 $xhs-account-review 复盘这些数据，生成人话版 HTML 报告。
```

Skill 源文件位于 [`skills/xhs-account-review/`](skills/xhs-account-review/)。

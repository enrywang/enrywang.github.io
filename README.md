# 个人作品集站点 · 部署指南

## 文件
- `index.html`  — 主页面（黄金分析 + AI 作品 + 关于我）
- `gold_daily_chart.png` — 技术分析图（每日由工具自动更新替换）
- `gold_daily_report_template.md` — 每日分析报告模板

## 最快上线（GitHub Pages，免费，10分钟）
1. 注册 GitHub → 新建仓库，命名为 `你的用户名.github.io`
2. 把这三个文件传到仓库根目录（网页直接拖入即可）
3. Settings → Pages → Source 选 main 分支 → 保存
4. 访问 `https://你的用户名.github.io` ✅

## 绑定自己的域名（可选，¥60-100/年）
1. 在阿里云/腾讯云/Namecheap 买域名，如 `yourname.com`
2. 仓库根目录新建 `CNAME` 文件，内容写 `yourname.com`
3. 域名 DNS 添加两条记录：
   - A 记录 → 185.199.108.153（GitHub Pages 官方 IP，共4个：108-153）
   - CNAME 记录 → `你的用户名.github.io`
4. Settings → Pages 里填入域名，等待 SSL 证书自动签发（约10分钟）

## 每日自动更新分析图（进阶）
本地或云函数定时跑 Python 脚本，重新生成 `gold_daily_chart.png` 后
git push 到仓库，页面图片自动更新。可用 GitHub Actions 实现全自动化。

## 自定义
- 全文搜索「你的名字」「AU · ANALYST」替换成自己的
- AI 作品卡片：复制 `.ai-card` 块即可增加

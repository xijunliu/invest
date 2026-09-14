# 基金投资报告

个人基金持仓的日/周/月报，自动生成并推送到飞书。

## 📊 在线访问

<https://xijunliu.github.io/invest/>

## 🛠️ 工作流

```
fund-advisor/
├── reports/                    # md 报告源文件
│   ├── 2026-09-14-daily.md
│   ├── 2026-09-14-weekly.md
│   └── 2026-09-14-monthly.md
├── templates/
│   └── report.html.j2          # Jinja2 模板
├── scripts/
│   ├── build_html.py           # md → html（带 tab 切换）
│   ├── publish.py              # git commit + push 到 Pages
│   └── send_feishu_v2.py       # 推送摘要 + URL 到飞书
└── site/                       # 本仓库 - GitHub Pages 源
    └── index.html              # 单页应用，3 个 tab
```

## 🚀 部署

```bash
python3 scripts/build_html.py   # 重新生成 index.html
python3 scripts/publish.py      # git add + commit + push
```

GitHub Pages 部署设置：[Settings → Pages → Source: main / (root)](https://github.com/xijunliu/invest/settings/pages)

## 📚 数据源

- **AKShare** - A 股 + 基金净值
- **FRED** - 美债 / 美元 / VIX 宏观
- **fund_metrics + pe_snapshot_history** - 自建 SQLite（PE 分位 + NAV 多时间窗）

## ⚠️ 免责声明

本报告仅供参考，不构成任何投资建议。市场有风险，投资需谨慎。
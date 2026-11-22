# 学 AI（learn.specul.com）

> English version: [README.en.md](./README.en.md)

`specul.com` 站群的**概念层**：把 AI 领域的高频名词按「先学什么、后学什么」排成六段，每个词都带可回查的原始出处。

站上的版本：<https://learn.specul.com/>

## 内容规模

- 299 个术语，按六段排列：进门 36、上手 44、用深 76、看懂 60、跑起来 46、选得对 37。
- 111 篇微型指南，每篇 5–10 分钟；另有 16 条带检查点的学习路径。
- 中英双语：299 个词条的释义、用途与英文摘要全部覆盖。
- 八个领域、四种使用目的、三组观察维度，均可作为筛选入口。

## 口径

- **未知就写未知**，不给模型或工具打总分排名。
- 每条判断挂官方源，并记录核验日期。
- 词条 `level` 与所在段必须一致；不一致时页面会显示矛盾的段标签，构建门禁会拦截。
- 事实是核验当天的快照，不等于永久有效；价格、版本、可用区域会变，引用前请回查原始出处。

## 这个仓是什么

本仓是**部署产物仓**（`speculcom/learn`），由主工作区的 `_data/handbook/terms` 构建后同步到这里，再发布到 GitHub Pages。

- 站点文件：`index.html`、`term/`、`guide/`、`path/`、`data/`、`2026.html`、`404.html`。
- 内容真相源在 `speculcom/ai-handbook` 的 `terms/` 子树：`terms/*.md`、`terms.en.json`、`paths/`、`guides/`、`meta.js`。
- **不要直接改本仓的生成文件**；下次构建会覆盖。改内容请改 `ai-handbook/terms`，然后跑主工作区的学习站构建器。

## 构建与发布

```powershell
node _data\handbook\terms\scripts\build.mjs
node _toolchain\publish\publish.mjs --publish --inline-text --message "content: update learn"
```

构建器带逐字段等价门禁：产物必须与 `terms.en.json` 实算的词条逐字段一致，不一致就退出、不写半成品。确实要改字段时，先确认变更意图，再用 `--accept` 刷新基准；不要靠删基准文件绕过门禁。

## 法律

内容 CC BY 4.0（署名即可自由使用与改编，含商业用途）；源码 MIT。自有内容与第三方内容的界限见 <https://specul.com/legal.html>。

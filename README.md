# Personal Asset Box Skill

一个面向 Codex 等 AI 编程助手的个人素材盒 Skill。它帮助你创建、改进和排查本地优先的中文图片标签素材库，而不是只生成一张静态界面。

核心体验只有一条：

> 拖入图片 → 快速点选标签 → 保存 → 按标签找回 → 导出原图使用。

## 它会坚持什么

- 收藏不能被整理阻塞：无标签图片可以先进入“待整理”。
- 本地优先：第一版不登录、不上传、不云同步、不接 AI。
- 多标签筛选使用 AND 逻辑，适合按用途、内容和风格组合查找。
- 备份必须包含图片原文件、标签、备注和来源信息。
- 删除只影响素材盒中的副本，不修改或删除来源文件。
- 修改现有项目时保护 IndexedDB 中的已有数据。

## 安装

安装整个仓库中的 Skill：

```bash
npx skills add https://github.com/Mona-ziranyun/personal-asset-box-skill --skill personal-asset-box
```

也可以把 `skills/personal-asset-box` 目录复制到 `~/.codex/skills/`。

## 使用

```text
使用 $personal-asset-box 创建一个可运行的本地图片标签素材盒。
```

```text
使用 $personal-asset-box 检查现有素材盒的备份恢复是否可靠。
```

```text
使用 $personal-asset-box 给素材盒增加 AI 标签建议，但保留人工确认。
```

## 仓库内容

```text
skills/personal-asset-box/
├── SKILL.md
├── agents/openai.yaml
├── assets/starter/            可运行的 Vite + IndexedDB 网页模板
├── references/                产品、界面、存储、扩展与验收规范
└── scripts/create_asset_box.py
```

生成一个新项目：

```bash
python3 skills/personal-asset-box/scripts/create_asset_box.py ./my-asset-box
cd my-asset-box
npm install
npm run dev
```

## 隐私说明

模板默认把图片保存到当前浏览器的 IndexedDB，不会主动上传到云端。浏览器本地数据仍可能被清理，请保留来源原图并定期导出完整备份。

## License

MIT

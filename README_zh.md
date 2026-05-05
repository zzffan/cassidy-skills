# cassidy-skills

Claude Code 个人技能与工具集。

---

## design-generator

使用预置设计系统或自定义设计规划，生成网站和 Web 界面。

### 使用方式

```
/design-generator
```

或使用自然语言：
- "生成一个 Apple 风格的页面"
- "帮我做个博客页面"
- "create a dashboard"
- "用 Spotify 风格创建一个落地页"

### 功能特点

**三种设计方式：**
1. **品牌风格** - Apple、Spotify、Stripe、Linear 等（66+ 预设）
2. **自定义设计** - 使用 frontend-design + ui-ux-pro-max 进行创意规划
3. **直接生成** - 无需风格咨询，直接生成高质量代码

**工作流程：**
1. 识别设计方式（未指定时询问用户）
2. 分析设计系统或使用创意规划
3. 生成 production-ready 代码
4. 验证输出（无 AI 味、无占位符）
5. 展示给用户
6. （可选）在项目根目录生成 `agents.md` 设计规范

### 可用风格（66+）

| 分类 | 品牌 |
|------|------|
| AI & LLM | OpenAI, Anthropic, Claude, xAI, Cohere, MistralAI, Ollama... |
| 科技 & 消费电子 | Apple, Spotify, NVIDIA, SpaceX, Uber, PlayStation... |
| 汽车 | Tesla, BMW, Ferrari, Lamborghini, Bugatti... |
| 开发者工具 | GitHub, Vercel, Cursor, Raycast, Expo... |
| 电商 & 零售 | Shopify, Nike, Airbnb, Meta... |
| 金融 & 加密 | Stripe, Coinbase, Binance, Wise... |
| 设计与创意 | Figma, Framer, Canva, Adobe... |
| 生产力 & SaaS | Linear, Notion, Slack, Resend, Cal.com... |

### 安装方式

1. 下载 `skills/design-generator/design-generator.skill` 文件
2. 放到 `~/.claude/skills/` 目录
3. 重启 Claude Code 即可使用

---

## super-novelist

使用反 AI 味写作原则，创作中英文小说。

### 使用方式

```
/super-novelist
```

或使用自然语言：
- "写一个悬疑小说"
- "创作一个奇幻故事"
- "写小说"
- "帮我写一章"

### 功能特点

- **双语支持** - 中文和英文小说
- **全题材** - 悬疑、言情、科幻、奇幻、历史、都市等
- **任意篇幅** - 短篇(1-3章)、中篇(5-15章)、长篇(20-50章)
- **反 AI 味** - 无陈词滥调、无总结性话术、对白自然
- **角色一致** - 无定位偏移，每个角色都有完整情感
- **适度爆粗** - 真实表达，适时适度

### 安装方式

1. 下载 `skills/super-novelist/super-novelist.skill` 文件
2. 放到 `~/.claude/skills/` 目录
3. 重启 Claude Code 即可使用

---

## docs/frontend-aesthetics

前端开发设计理念与规范：

- **agents.md** - Frontend Design Agent 设计规范（反 AI 味原则）

---

## 示例页面

使用 skill 生成的测试页面：

| 文件 | 描述 | 风格 |
|------|------|------|
| `index.html` | 纪录片平台 | The Verge 风格，深色 |
| `nota.html` | 笔记应用，支持主题切换 | 温暖编辑风，明暗切换 |
| `codeNav.html` | 程序员资源导航 | 深色科技风，青色点缀 |

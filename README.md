# 由裁判文书生成案例分析

将中国的法院裁判文书改写为人民法院案例库风格的案例分析。适用于 AI Agent（如 WorkBuddy、OpenClaw 等）的 Skill。

## 功能

输入一份裁判文书（判决书、裁定书等），自动生成结构化的案例编写稿，包含：

1. **标题** — 脱敏后的案件标题
2. **副标题** — 核心法律问题提炼
3. **关键词** — 领域 + 案由 + 核心法律概念
4. **基本案情** — 聚焦裁判规则的必要事实
5. **裁判理由** — 结构化重构法院说理逻辑
6. **裁判要旨** — 可复用的抽象裁判规则
7. **关联索引** — 核心法条、关联案例、审级信息

## 特点

- 自动对当事人、企业、地址进行脱敏
- 识别案件类型并匹配对应的裁判要旨提炼方式
- 严格遵循"取窄原则"，不将个案规则无限扩大
- 支持调用北大法宝 MCP、元典 MCP 进行法条案号核验（可选）
- 纯 Markdown 指令，无脚本依赖

## 使用

### WorkBuddy / OpenClaw

将 `SKILL.md` 放入 skills 目录即可：

```bash
# 用户级（所有项目可用）
cp SKILL.md ~/.workbuddy/skills/court-case-digest-generation/SKILL.md

# 或项目级
cp SKILL.md .workbuddy/skills/court-case-digest-generation/SKILL.md
```

### 直接使用

将 SKILL.md 的内容作为系统提示词复制到任意 AI 对话中，然后粘贴裁判文书即可。

## 目录结构

```
court-case-digest-generation/
├── SKILL.md                              # 主 Skill 文件
└── references/
    └── case-library-writing-guide.md     # 案例库编写参考指南
```

## 声明

本工具是法律文书格式转换工具，不提供法律意见，不替代律师、法官的专业判断。输出内容仅供参考。

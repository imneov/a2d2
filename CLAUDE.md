# A²D² Project - Claude Collaboration Guide

## 项目概述

**A²D²** (Agentic Agile Driven Development) 是一个方法论适配项目，将 BMAD 结构化敏捷框架与 GitHub 工作流结合，使 AI 助手成为持久化的"数字员工"。

**核心价值：** 将临时性的 AI 交互转变为系统化、持久化、可复现的开发工作流。

## 项目架构

### 目录结构
```
a2d2/
├── .bmad-core/           # BMAD 核心配置和工作流
│   ├── workflows/        # 工作流定义文件
│   └── install-manifest.yaml
├── docs/                 # 项目文档
│   ├── brief.md         # 项目简报（英文）
│   └── brief-zh.md      # 项目简报（中文）
└── README.md            # 项目说明
```

### 关键文档位置
- **项目简报：** `/docs/brief.md` 和 `/docs/brief-zh.md` - 包含完整的问题陈述、解决方案、目标用户、MVP 范围等
- **BMAD 配置：** `/.bmad-core/` - 包含工作流定义和配置清单

## 协作指南

### 1. 上下文加载

当开始新的会话时，请参考以下文档建立上下文：
1. 首先阅读 `/docs/brief-zh.md` 或 `/docs/brief.md` 了解项目全貌
2. 查看 `/.bmad-core/workflows/` 了解当前定义的工作流
3. 检查最近的 git 提交历史了解最新进展

### 2. BMAD Agent 使用

本项目遵循 BMAD 方法论，使用以下 agent 角色：

- **Analyst Agent:** 用于需求分析和头脑风暴
- **PM Agent:** 用于编写 PRD 和用户故事
- **Architect Agent:** 用于架构设计和技术决策
- **Developer Agent:** 用于具体实现
- **QA Agent:** 用于测试和质量保证

### 3. 开发工作流

#### 新功能开发流程
1. **发现阶段：** 使用 Analyst agent 进行需求分析
2. **设计阶段：** 使用 PM agent 编写需求文档，使用 Architect agent 设计架构
3. **实现阶段：** 使用 Developer agent 进行编码
4. **验证阶段：** 使用 QA agent 进行测试和审查

#### 文档更新原则
- 所有设计决策必须记录在 `docs/` 目录
- 使用 Markdown 格式，确保 AI 可读
- 文档与代码同步更新
- 重要决策添加日期和理由

### 4. GitHub 集成

- **Issues：** 用于跟踪功能开发和 bug 修复
- **PRs：** 代码审查和合并
- **GitHub Actions：** （可选）自动化验证
- **Projects：** （可选）任务看板

## MVP 交付物

### 当前阶段任务
1. **A²D² 方法论手册** - 核心协作原则和最佳实践
2. **工作流模式库** - 常见场景的协作模式
3. **示例项目模板** - 快速启动模板
4. **Claude 协作速查指南** - 常用命令和提示

### 明确不包含的范围
- ❌ 不修改 BMAD 核心
- ❌ 不进行 AI 模型训练
- ❌ 不提供托管服务

## 编码规范

### 文档质量标准
- 文档结构清晰，层次分明
- 使用标准 Markdown 语法
- 添加目录和内部链接
- 代码示例使用代码块并标注语言

### 文件命名规范
- 使用小写字母和连字符：`example-file.md`
- 中英文文档使用 `-zh` 后缀：`brief.md` / `brief-zh.md`
- 配置文件使用 YAML 格式
- 工作流文件描述性命名：`greenfield-ui.yaml`

## Git 工作流

### 分支管理策略

#### 主要分支
- **main** - 主分支，保护分支，仅通过 PR 合并
- **develop** - （可选）开发分支，用于集成测试
- **feature/** - 功能分支，格式：`feature/功能简短描述`
- **fix/** - 修复分支，格式：`fix/问题简短描述`
- **docs/** - 文档分支，格式：`docs/文档简短描述`

#### 分支命名规范
```bash
# 好的例子
feature/add-methodology-handbook
feature/workflow-pattern-library
fix/typo-in-brief
docs/update-collaboration-guide

# 不好的例子
my-branch
test
tmp
feature1
```

### 代码提交规范

#### Commit Message 格式
```
<type>(<scope>): <subject>

<body>

<footer>
```

#### Type 类型
- **feat:** 新功能
- **fix:** Bug 修复
- **docs:** 文档更新
- **style:** 格式调整（不影响代码逻辑）
- **refactor:** 重构（既不是新增功能也不是修复 bug）
- **test:** 测试相关
- **chore:** 构建过程或辅助工具的变动

#### Scope 范围（可选）
- **handbook:** 方法论手册
- **workflows:** 工作流模式
- **templates:** 项目模板
- **guide:** 协作指南
- **brief:** 项目简报

#### Subject 规范
- 使用祈使句，现在时："add" 而非 "added" 或 "adds"
- 首字母小写
- 结尾不加句号
- 简洁明了，不超过 50 字符

#### 示例
```bash
# 好的 commit message
feat(handbook): add AI collaboration best practices section
docs(guide): update BMAD agent usage instructions
fix(templates): correct directory structure in example

# 带 body 的完整示例
feat(workflows): add feature development workflow pattern

- Define discovery phase with Analyst agent
- Add design phase with PM and Architect agents
- Include implementation and validation phases
- Provide concrete examples for each phase

Closes #12
```

### 提交前检查清单

#### 文档提交
- [ ] Markdown 语法正确
- [ ] 内部链接有效
- [ ] 代码示例可运行
- [ ] 无拼写错误
- [ ] 遵循项目术语规范

#### 配置文件提交
- [ ] YAML 语法正确
- [ ] 符合 BMAD 标准格式
- [ ] 包含必要注释
- [ ] 路径引用正确

#### 代码文件提交
- [ ] 代码示例可运行
- [ ] 无拼写错误
- [ ] 遵循项目术语规范

### PR (Pull Request) 规范

#### PR 标题格式
与 commit message 的 subject 格式一致：
```
<type>(<scope>): <description>
```

#### PR 描述模板
```markdown
## 变更类型
- [ ] 新功能 (feat)
- [ ] Bug 修复 (fix)
- [ ] 文档更新 (docs)
- [ ] 重构 (refactor)
- [ ] 其他

## 变更说明
简要描述本次 PR 的内容和目的

## 关键变更
- 变更点 1
- 变更点 2
- 变更点 3

## 测试
- [ ] 文档链接已验证
- [ ] 示例代码已测试
- [ ] 遵循编码规范

## 相关 Issue
Closes #issue_number

## 检查清单
- [ ] 遵循项目编码规范
- [ ] 更新了相关文档
- [ ] Commit message 符合规范
```

#### PR 审查要点
- 文档结构是否清晰
- 内容是否准确完整
- 术语使用是否规范
- 示例是否可运行
- 与现有文档的一致性

### 代码审查流程

#### 自审清单（提交前）
1. **内容质量**
   - [ ] 文档逻辑清晰，无歧义
   - [ ] 代码示例完整可运行
   - [ ] 引用和链接准确有效

2. **格式规范**
   - [ ] Markdown 格式正确
   - [ ] 代码块标注语言
   - [ ] 标题层级合理

3. **项目规范**
   - [ ] 遵循术语规范
   - [ ] 符合文件命名规范
   - [ ] Git commit message 规范

#### 同行评审要点
1. **准确性** - 内容是否正确
2. **完整性** - 是否遗漏关键信息
3. **可读性** - 是否易于理解
4. **一致性** - 与项目其他部分是否一致

### Git 常用命令

```bash
# 创建功能分支
git checkout -b feature/your-feature-name main

# 提交变更
git add .
git commit -m "feat(scope): your commit message"

# 推送到远程
git push origin feature/your-feature-name

# 更新主分支
git checkout main
git pull origin main

# 变基到最新主分支
git checkout feature/your-feature-name
git rebase main

# 创建 PR（使用 GitHub CLI）
gh pr create --title "feat(scope): description" --body "PR description"

# 查看提交历史
git log --oneline --graph --all

# 修改最后一次 commit message
git commit --amend -m "new commit message"
```

### 版本标签

#### 语义化版本
遵循 [Semantic Versioning 2.0.0](https://semver.org/)：
- **MAJOR.MINOR.PATCH** (例如：1.0.0)
- **MAJOR:** 不兼容的 API 变更
- **MINOR:** 向后兼容的功能新增
- **PATCH:** 向后兼容的问题修复

#### 标签创建
```bash
# 创建标签
git tag -a v1.0.0 -m "Release version 1.0.0: Initial MVP release"

# 推送标签
git push origin v1.0.0

# 查看所有标签
git tag -l

# 查看标签详情
git show v1.0.0
```

#### 发布说明
每个版本标签应包含：
- 版本号和发布日期
- 主要变更说明
- 新增功能列表
- Bug 修复列表
- 已知问题（如有）

## 关键链接

- **BMAD 方法论文档：** https://github.com/bmad-code-org/BMAD-METHOD/blob/main/docs/user-guide.md
- **Claude Agent SDK：** https://docs.claude.com/en/api/agent-sdk/overview
- **GitHub CLI 文档：** https://cli.github.com/manual/

## AI 协作最佳实践

### 上下文持久化
- 将关键决策写入 `docs/` 目录的正式文档
- 使用 Git commit message 记录变更原因
- 在 Issue 中结构化描述问题和解决方案
- 定期更新 README 和架构文档

### 会话连续性
- 每次会话开始时引用相关文档
- 使用项目特定术语和约定
- 引用先前的设计决策和理由
- 保持工作流阶段的一致性

### 质量保证
- 遵循 MVP 成功标准
- 确保文档与实现同步
- 代码示例必须可运行
- 定期检查文档的时效性


### 待定问题
- Agent 角色的最佳粒度？
- 文档分片应该自动还是手动？
- 如何处理 AI 生成文档的合并冲突？
- 规范性工作流和灵活性的平衡？

---

**文档版本：** 1.0
**最后更新：** 2025-10-02
**维护者：** A²D² Project Team

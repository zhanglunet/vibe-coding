# 氛围编程（Vibe Coding）终极指南 V1.0
**作者:** [Nicolas Zullo, https://x.com/NicolasZu](https://x.com/NicolasZu)  
**日期:** 2025年3月12日  

---

## 开始使用
要开始 vibe 编程，你只需要两个工具：  
- **Grok 3 Thinking**  https://grok.com 
- **Cursor with Claude Sonnet 3.7 Thinking**  

正确设置一切是关键。如果你认真想要创建一个功能完整且视觉吸引人的游戏，请花时间建立坚实的基础。  

**关键原则：** *规划就是一切。* 不要让 AI 自主规划，否则你的代码库将变得难以管理。

---

## 环境设置

### 1. 游戏设计文档
- 将你的游戏创意告诉 **Grok 3 Thinking**，让它创建一个简单的 Markdown 格式（`.md`）的**游戏设计文档**。  
- 审查并完善文档，确保它符合你的愿景。基础版本也可以——目标是让 AI 了解游戏的结构和意图。  

### 2. 技术栈和 `.cursor/rules`
- 让 **Grok 3 Thinking** 为你的游戏推荐最佳技术栈（例如，多人 3D 游戏使用 ThreeJS 和 WebSocket）。  
  - 挑战它提出*最简单但最稳健的技术栈*。  
- 下载 [https://docs.cursor.com/context/rules-for-ai](https://docs.cursor.com/context/rules-for-ai) 的 PDF 版本，上传它，并提示 Grok 编写一套 6-10 条 Cursor 规则，就像它是一位专门研究你选择的技术栈的高级游戏开发者。  
  - 确保有一条规则强调**模块化**（多个文件）并避免**单体**（一个巨型文件）。  
  - 示例：规则可能包括网络最佳实践
  - *如果你想要一个尽可能优化的游戏和尽可能干净的代码，这是必需的。*

### 3. 实施计划
- 向 **Grok 3 Thinking** 提供：  
  - 游戏设计文档  
  - 技术栈建议
  - Cursor 规则  
- 要求它创建一个详细的 Markdown（`.md`）格式的**实施计划**，这是给你的 AI 开发者的逐步指导。  
  - 步骤应该小而具体。  
  - 每个步骤必须包含验证正确实施的测试。  
  - 不要包含代码——只需清晰、具体的指导。  
  - 专注于*基础游戏*，而不是完整功能集（细节稍后添加）。  

### 4. 记忆库
- 创建一个新文件夹，在 Cursor 中打开它，创建另一个文件夹，命名为 `memory-bank`。  
- 添加以下文件：  
  - `game-design-document.md`  
  - `tech-stack.md`  
  - `implementation-plan.md`  
  - `progress.md`（用于跟踪完成的步骤）  
  - `architecture.md`（用于记录文件用途）  

### 5. 设置 `.cursor/rules`
- 在 Cursor 中，按 `Cmd + Shift + P`，输入 "rules"，然后按 Enter。  
- 输入 Grok 3 从第 2 步生成的规则。  

---

## Vibe 编程基础游戏
现在有趣的部分开始了！

### 确保一切清晰
- 在 Cursor 中选择 **Claude Sonnet 3.7 Thinking**。 
- 提示：阅读 `/memory-bank` 中的所有文档，`implementation-plan.md` 是否清晰？你有哪些问题需要使其 100% 清晰？
- 它通常会问 9-10 个问题，回答这些问题并提示它相应地编辑 `implementation-plan.md`，使其更好。

### 你的第一个实施提示
- 在 Cursor 中选择 **Claude Sonnet 3.7 Thinking**。  
- 提示：阅读 `/memory-bank` 中的所有文档，并继续实施计划的第 1 步。我将运行测试。在我验证测试之前不要开始第 2 步。一旦我验证了它们，打开 `progress.md` 并记录你为未来开发者做了什么。然后在 `architecture.md` 中添加任何架构见解，解释每个文件的用途。

- **极致 vibe：** 安装 [Superwhisper](https://superwhisper.com) 与 Claude 进行语音对话而不是打字。  

### 工作流程
- 完成第 1 步后：  
- 将更改提交到 Git（如果不熟悉，请向 Grok 3 寻求帮助）。  
- 启动新的 composer（`Cmd + N`，`Cmd + I`）。  
- 提示：现在浏览 memory-bank 中的所有文件，阅读 progress.md 以了解之前的工作，并继续第 2 步。在我验证测试之前不要开始第 3 步。
- 重复此过程，直到完成整个 `implementation-plan.md`。  

---

## 添加细节
恭喜，你已经构建了基础游戏！它可能还很粗糙且缺乏功能，但现在你可以进行实验和改进。  
- 想要雾、后期处理、特效或声音吗？更好的飞机/汽车/城堡？漂亮的天空？
- 对于每个主要功能，创建一个新的 `feature-implementation.md` 文件，包含简短的步骤和测试。  
- 逐步实施和测试。  

---

## 修复错误和卡住问题
- 如果提示失败或破坏游戏：  
- 在 Cursor 中点击 "restore" 并完善你的提示直到它工作。  
- 对于错误：  
- **如果是 JavaScript：** 打开控制台（`F12`），复制错误，并粘贴到 Cursor 中——或为视觉故障提供截图。  
- **懒人选项：** 安装 [BrowserTools](https://browsertools.agentdesk.ai/installation) 以跳过手动复制/截图。  
- 如果卡住：  
- 恢复到你的最后一个 Git 提交（`git reset`）并使用新的提示重试。  
- 如果*真的*卡住：  
- 使用 [RepoPrompt](https://repoprompt.com/) 并向 **Grok 3 Thinking** 寻求帮助。  

---

## 其他提示
- **小编辑：** 使用 Claude Sonnet 3.5。  
- **优秀文案：** 使用 GPT-4.5。  
- **更好的提示输出：** 添加 "花时间思考以确保正确，我不着急。重要的是你准确遵循我的要求并完美执行。如果我的要求不够精确，请向我提问。"

---

## 常见问题
**问：你的飞机太棒了，但我无法在一个提示中复制它！**  
**答：** 这不是一个提示——它是约 30 个提示，由 `plane-implementation.md` 文件指导。使用尖锐、具体的提示，如 "在机翼上切出副翼空间"，而不是模糊的提示如 "制作一架飞机"。

**问：我不知道如何为我的多人游戏设置服务器**  
**答：** 询问 Grok 3。

--- 

# 项目约定

## 1. 场景控制器

当用户提到「场景控制器」时，复用 `.state-controller` 设计系统，按确认订单页V1底部的场景控制器样式生成。

## 2. 检查并优化注解面板内容

当用户要求检查并优化注解面板内容时，三部分（interactionNotes / requirementDoc / statusList）均避免包含视觉说明，聚焦交互逻辑与状态规则。

## 3. Github 推送

默认不推送。仅当用户明确提到「更新最新版本到 GitHub」时，才执行 commit + push。

## 4. GitHub 更新约定

当用户提到「更新最新版本到 GitHub」时，按以下约定执行：

1. **目标仓库**：`https://github.com/levinachen/laif`（main 分支）
2. **排除文件**：不上传 `CONVENTIONS.md`。写入 GitHub 约定时不能覆盖该 CONVENTIONS 文档的内容，只能追加或修改对应章节。
3. **资源清理**：上传前检查 `figma-images/` 文件夹，未被原型（index.html）引用的资源文件删除以减小文件大小。清理中不能误删图标（包括动态拼接引用的文件如 `${icon}-active.svg`），需保持原型的完整性。
4. **提交流程**：
   - 检查 `figma-images/` 中每个文件是否在 `index.html` 中被引用（文件名搜索）
   - 删除未引用的文件
   - `git add` 暂存变更（显式排除 `CONVENTIONS.md`、`.uploads/`、`.trae-html-share-packages/`）
   - `git commit` 提交（使用 HEREDOC 格式的 commit message）
   - `git push origin main` 推送

# ai-testcase-generator

- `knowledge/` 为知识库，**只读**。例外（skill 可写）：`风险地图.md`、`缺陷记录/`、`需求文档/_需求索引.md`
- 用例的「可追溯需求条目」只能指向 `knowledge/需求文档/当前/`；`归档/` 是已失效的旧行为，只用于判断影响面
- 生成用例走 `gen-cases` skill
- 输出命名：`output/<需求简称>-<日期>-testcases.md`；评审后另存为 `-reviewed.md`（复盘依赖这两个版本的 diff）
- 复盘：对比 `-testcases.md` 与 `-reviewed.md`，把规律更新进 `.claude/skills/gen-cases/references/用例编写规范.md` 或 `knowledge/风险地图.md`
- 逃逸缺陷（上线后发现的漏测）→ 往 `knowledge/风险地图.md` 对应模块加一行

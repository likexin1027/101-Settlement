# 架构与模块说明

## 总览
- UI：Streamlit 单页应用，入口 `app.py`。
- 业务逻辑：`reward_system/reward_logic.py` 负责规则提取与奖励计算。
- 数据持久化：`reward_system/activity_store.py` 读写 `reward_system/data/activities.json`。
- 类型：`typings/` 提供 pandas 等类型补全。

## 数据流
1. 侧边栏选择/创建活动 -> 读写 `activities.json`。
2. 主区配置规则 -> 写回活动规则（含基础/优秀/限时）。
3. 上传/示例数据 -> `compute_rewards` 计算 -> 预览/下载。

## 关键模块
- `app.py`：UI、表单校验、文件上传、规则编辑、调用计算。
- `reward_logic.py`：
  - 默认规则常量（基础、优秀、限时）。
  - `compute_rewards` 支持档位/CPM/瓜分三种基础模式 + 优秀/限时叠加。
  - 数据加载与导出（示例数据、下载缓冲）。
- `activity_store.py`：
  - `load_activities`/`add_activity`/`update_activity_rule` 等。
  - 迁移补齐旧字段（quality_rules/time_rules/base_mode/base_params）。
  - 本地 JSON 存储。

## 运行时依赖
- `streamlit`、`pandas`、`openpyxl`、`pandas-stubs`（类型）。可选 `xlsx2csv` 增强兼容。

## 扩展点
- 新增规则：在 `reward_logic.py` 增加配置与计算分支，并在 `app.py` UI 暴露编辑入口。
- 存储后端：可将 `activities.json` 替换为数据库或 API；封装接口留在 `activity_store.py`。

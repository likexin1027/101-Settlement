# 活动奖励计算系统

## 概述
- Streamlit 应用，用于活动奖励配置与结算预览。
- 支持基础奖励三种模式（档位/CPM/瓜分），以及优秀、限时奖励配置。

## 快速开始
```bash
cd /d C:\Users\kikicyli\Desktop\101_Settlement
.\.venv\Scripts\activate
pip install -r requirements.txt
python -m streamlit run app.py --server.port 8501
```
浏览器打开 `http://localhost:8501`。

## 主要功能
- 活动管理：创建/编辑/删除，状态色标，侧边栏快捷操作。
- 规则配置：基础奖励（档位/CPM/瓜分）、优秀奖励、限时奖励分 Tab 编辑。
- 数据处理：上传 CSV/Excel 或加载示例数据，预览结算结果，下载处理后 Excel。

## 目录结构（摘要）
- `app.py`：Streamlit 入口。
- `reward_system/reward_logic.py`：奖励计算与规则处理。
- `reward_system/activity_store.py`：活动配置存储与迁移。
- `reward_system/data/activities.json`：示例/本地活动配置数据。
- `docs/`：项目文档（架构、规则、部署、更新记录）。

## 规则概览（简）
- 基础：档位阈值对应金额，或按 CPM (元/千次) 计算，或奖金池瓜分（门槛+总额）。
- 优秀：阈值/加成/仅短视频。
- 限时：播放下限/加成。
- 详情见 `docs/rules.md`。

## 部署与预览
- 本地：见快速开始。
- 远程/CloudStudio：见 `docs/deploy.md`。

## 贡献
欢迎提交 Issue/PR，先确保通过基本检查并附简要说明。

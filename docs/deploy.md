# 部署与运行

## 本地运行
```bash
cd /d C:\Users\kikicyli\Desktop\101_Settlement
.\.venv\Scripts\activate
pip install -r requirements.txt
python -m streamlit run app.py --server.port 8501
```
浏览器访问 `http://localhost:8501`，如端口占用可改 `--server.port 8502`。

## CloudStudio（需先授权）
- 上传整个项目或使用已有工作区。
- 安装依赖：`pip install -r requirements.txt`
- 启动：`python -m streamlit run app.py --server.address 0.0.0.0 --server.port 8501`
- 使用平台提供的预览链接访问。

## 常见问题
- 端口占用：更换 `--server.port`。
- 依赖缺失：重新安装 `pip install -r requirements.txt`。
- Excel 兼容：优先 openpyxl，失败会尝试 xlsx2csv；如仍失败，按提示另存为 CSV/XLSX 再上传。

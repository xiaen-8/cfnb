# cfnb 云端测速点（GitHub Actions）

- `main.py` / `config.json`：上游 xinyitang3/cfnb 的副本，配置已改为云端专用：
  - 分国家模式，每国取 10 个；白名单 12 国（JP/HK/TW/SG/KR/US/MO/VN/PH/TH/MY/MN）
  - `CF_ENABLED=false`（不碰任何 DNS）、无 git_sync.sh（不同步）
- 工作流 `.github/workflows/cfnb-cloud.yml` 每 30 分钟跑一轮，把结果 `ip.txt` 提交到本目录。
- cfyx Worker 每 10 分钟从本目录的 `ip.txt` 拉取到“云端池”（yx.527278.xyz/cloud 查看），与家里 NAS 的主池分开。

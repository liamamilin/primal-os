# Primal OS · 原始人认知语言体系

> 用狩猎与农耕的物理直觉，给现代大脑做一次认知降维与情绪去噪。

这是一个零外部依赖、单页交互式的翻页认知体验网页，配合主题曲《原始人不慌》，包含 5 个核心互动章节：

1. **洞穴视界（认知降维）**：点击击碎漂浮的焦虑气泡，或拖动去噪滑块，还原物理事实仪表。
2. **词汇打磨台（造词 3 原则）**：在岩画铁砧上依次点亮「去抽象化」「去道德化」「强行动指向」，粉碎羞耻印章。
3. **生存领地图谱与 3D 翻卡（狩猎 + 农耕双周期）**：等高线地图联动筛选、关键词即时检索、歌词彩蛋词卡，以及可本地保存的自定义词卡铸造。
4. **实时篝火生存模拟器（情绪气象学 + 六大动词）**：60fps Canvas 荒原营地，支持 4 种情绪天气、音乐低频节拍共振，以及六大核心原始动词的视觉联动协议。
5. **生存石板刻录与我的洞壁（双系统切换铁律）**：一键切换「原始人止痛 / 现代人复利」双系统，刻录并永久存档个人生存石板，支持导出 2x 高清 PNG 图片。

---

## 目录结构

```text
primal-os/
├── index.html                        # Primal OS 2.5 Studio 完整应用（零外部依赖）
├── README.md                         # 项目说明
├── assets/
│   ├── primal-bgm.mp3                # 主题曲《原始人不慌》
│   └── cover.png                     # 社交分享卡片预览图 (1200x630)
└── .github/
    └── workflows/
        └── deploy.yml                # GitHub Pages 自动部署工作流
```

---

## 部署到 GitHub Pages

1. 将本压缩包内的所有文件（包括隐藏目录 `.github/`）上传或推送到你新建的 GitHub 仓库的 `main` 分支。
2. 打开仓库的 **Settings → Pages → Build and deployment**。
3. 将 **Source** 设为 **GitHub Actions**。
4. 推送后 GitHub Actions 会自动运行 `Deploy Primal OS to GitHub Pages`，约 30 秒后即可通过 `https://<你的用户名>.github.io/<仓库名>/` 访问。

---

## 音频小贴士（可选）

`assets/primal-bgm.mp3` 已内置原曲，可以直接无缝上线。如果你想裁掉音频末尾约 2.5 秒的语音提示以便单曲循环更丝滑，可以在 macOS 终端运行：

```bash
# 查看音频总时长（秒）
ffprobe -v error -show_entries format=duration -of default=noprint_wrappers=1:nokey=1 assets/primal-bgm.mp3

# 假设总时长为 T 秒，将末尾裁掉 3 秒（示例替换为 T-3）
ffmpeg -i assets/primal-bgm.mp3 -t <T-3> -c copy assets/primal-bgm-trimmed.mp3 && mv assets/primal-bgm-trimmed.mp3 assets/primal-bgm.mp3
```

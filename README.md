# Neon Wallpaper Skill

一个面向 Codex 的个人图片工作流：将上传的照片简化并重绘为少色块、低细节的 1980s–1990s 蓝橙霓虹桌面壁纸。

它不是给原图简单叠加滤镜，而是先提炼主体、空间层级和配色，再用大色块、干净剪影与几何阴影重新构图。

## 特点

- 将复杂照片压缩为 3–5 个主色
- 只保留 2–3 个空间层级和一个视觉焦点
- 自动减少密集窗户、树叶、反光、纹理和装饰物
- 保留人物或主体的轮廓、姿态与关键比例
- 至少留出 25% 安静区域，方便放置桌面图标或时钟
- 第一遍仍然复杂时，继续删除 40–60% 的小元素

## 安装

在终端执行：

```bash
git clone https://github.com/Yashiine-code/neon-wallpaper-skill.git ~/.codex/skills/neon-wallpaper
```

然后重新打开 Codex，并新建一个任务。

如果已经手动安装过同名 Skill，请先保留现有版本，不要直接覆盖；可以下载本仓库后比较 `SKILL.md` 再更新。

## 使用方法

在 Codex 中上传一张照片，然后输入：

```text
使用 $neon-wallpaper 简化这张照片，重绘成少色块、低细节的蓝调公寓壁纸，保留主体轮廓。
```

也可以指定尺寸和留白：

```text
使用 $neon-wallpaper 把这张照片重绘为 2560×1440 的落日天际线壁纸，保留人物，左上角留空放桌面图标。
```

如果第一张仍然过于复杂：

```text
继续简化，删除一半小物体和纹理，只保留大色块、剪影和一个视觉焦点。
```

## 风格预设

| 预设 | 视觉方向 |
| --- | --- |
| `blue-hour-apartment` | 钴蓝天空、珊瑚色地平线、简化城市与室内剪影 |
| `last-light-city` | 靛蓝城市色块、橙红落日、长直硬边阴影 |
| `midnight-arcade` | 紫蓝与珊瑚色灯牌、极少反光、几何化夜景 |

未指定时默认使用 `blue-hour-apartment` 和 16:9 比例。

## 输出

生成的成品默认保存到当前 Codex 项目的 `generated/` 文件夹，例如：

```text
generated/neon-blue-hour-minimal-01.png
```

每次完成后，Skill 会返回：

- 本地文件路径
- 实际生成提示词
- 保留和删除内容的简化摘要

## 要求与说明

- 需要在支持内置图片生成工具的 Codex 环境中使用
- Skill 本身不保存或暴露 API Key
- Skill 不会自动把图片设置为系统壁纸
- Skill 运行于 Codex，不会被普通静态网页直接调用

## 文件结构

```text
neon-wallpaper/
├── SKILL.md
└── agents/
    └── openai.yaml
```

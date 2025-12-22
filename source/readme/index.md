---
# 语言 （可选）
lang: zh-cn
# 网页关键词和描述
keywords: PANO DATASETS,CVPU,PANO
name: PANO DATASETS
title_pic : 1.png
# 联系方式
contact:
  - icon: fab fa-github
    text: Github
    url: https://github.com/losehu
  #  team
  - icon: fa fa-bar-chart
    text: Download
    url: https://k5.vicicode.com/
  #个人网站
  - icon: fas fa-globe
    text: CVPU Lab
    url: https://yangkailun.com/team.html
  # 邮箱
  - icon: fas fa-envelope
    text: wu58430@126.com
    url:  

picture:
  url: ../map_v2.png
  blogname: <a href="https://clustrmaps.com/site/1byz2">Visitor traffic</a><br>


# picture:
#   title: visitor trace
#   url: <a href="https://clustrmaps.com/site/1byz2"  title="Visit tracker"><img src="//" /></a>
  #  <a href="http://clustrmaps.com/site/1afir">Visitor traffic for this page</a><br>
  #  <a href="http://www.clustrmaps.com/map/Yangkailun.com" title="Statistics of visitors to this page">



---


# Getting Started

以下为快速上手指南，包含安装与数据集准备步骤，方便在本项目中复现实验。

## Installation

- 克隆仓库：

```bash
git clone https://example.com/your-repo.git
cd your-repo
```

- 安装依赖（若使用 Hexo）：

```bash
# 安装 Node 依赖
npm install

# 启动本地开发服务器（若端口被占用可更换 -p 端口）
npm run dev
```

- 可选：准备 Python 环境用于数据处理：

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Prepare Dataset

本项目假设数据以以下结构组织：

```
dataset/
  ├─ train/
  │   ├─ classA/
  │   └─ classB/
  └─ val/
	  ├─ classA/
	  └─ classB/
```

- 如果需要下载或转换数据，可以将原始数据放到 `dataset/raw/`，然后运行转换脚本：

```bash
python scripts/prepare_dataset.py --input dataset/raw --output dataset
```

- 简单的检查数据完整性的命令示例：

```bash
python - <<'PY'
import os
for split in ('train','val'):
	total = sum(len(files) for _,_,files in os.walk(f'dataset/{split}'))
	print(split, total)
PY
```

如果你希望我为你的数据集写一个具体的准备脚本（包含重采样、帧提取或标签映射），把样例数据结构或一小部分样本发给我，我可以继续帮你实现。


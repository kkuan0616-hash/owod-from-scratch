# 路径总表（PATHS）

> 用途：以后任何命令里的路径都从这里复制，不要凭记忆敲。
> 更新：2026-10-31（文件夹改名 视觉 → computer_vision 之后）

---

## 一、三个区（各管各的，不要混）

| 区 | 路径 | 放什么 | 进 git 吗 |
|---|---|---|---|
| **代码区** | `E:\projects\owod-from-scratch` | 代码、配置、实验结果 | ✅ 进 |
| **数据区** | `E:\MVR` | 数据集（图片+标签） | ❌ 不进 |
| **归档区** | `E:\tool\computer_vision` | 旧项目代码（只读源码用） | ❌ 不进 |

---

## 二、常用路径

### 代码区
```
仓库根目录      E:\projects\owod-from-scratch
训练输出        E:\projects\owod-from-scratch\experiments\<实验名>\
文档            E:\projects\owod-from-scratch\docs\
```

### 数据区
```
手势数据（自己在用）  E:\MVR\datasets_gesture
  ├── images\train\   975 张
  ├── images\val\     104 张
  └── labels\         对应 txt

圆形数据（闲置）      E:\MVR\datesets_circle      186 张
五连块（闲置）        E:\MVR\datesets_fiveblocks   35 张
3D 重建（闲置）       E:\MVR\3D_scene_reconstruction
```

### 归档区（旧项目，只读源码，不要在这里训练）
```
YOLOv5 源码       E:\tool\computer_vision\yolov5\yolov5-master
  ├── models\yolo.py        ← W2 要读
  ├── utils\loss.py         ← W2 要读
  ├── data\gesture.yaml     ← 数据配置（指向 E:/MVR/datasets_gesture）
  ├── yolov5s.pt            ← 旧权重（torch 2.11 加载会报错，仅存档）
  └── runs\train\exp1..exp10  ← 2026 年 1–4 月的历史实验
```

---

## 三、环境

```
Python            E:\tool\anaconda3\python.exe      （base 环境）
torch             2.11.0+cu128
torchvision       0.26.0+cu128
ultralytics       8.4.5
GPU               RTX 5060 Laptop, 8 GB, sm_120
标注工具环境       conda env: labelimg
```

模型结构文件（不需要下载，随 ultralytics 装好）：
```
E:\tool\anaconda3\Lib\site-packages\ultralytics\cfg\models\
  ├── 11\yolo11.yaml      ← YOLO11
  ├── v5\yolov5.yaml      ← V5 结构（+ yolov5nu.yaml = 现代化版）
  └── 11\yoloe-11.yaml    ← 开放词汇检测（与课题相关，W5 后再看）
```

---

## 四、规矩（写下来就不乱了）

1. **数据永远不进 git**，`.gitignore` 里 `data/**` 拦着。
2. **权重（*.pt）永远不进 git**，用 `args.yaml` + `results.csv` 复现。
3. **所有训练输出进 `experiments\<实验名>\`**，一次实验一个文件夹。
4. **每次改文件夹名，先改这份 PATHS.md，再改命令。**
5. 删除任何东西前，先想一句"三个月后我会不会找它"。

# 参考论文数据集规模与预处理对照表（223 篇）

**核对日期**：2026-11-08

**用途**：在参考某篇论文前，先比较“它的数据条件”和“你的数据条件”。数据量、标注类型、采集条件不同，方法选择和预期效果会差很多。

## 怎么用

1. 先找到和你数据模态、标注类型最接近的行。
2. 对比规模：如果你的数据比参考工作少 1–2 个数量级，优先考虑预训练、少样本、自监督或异常检测，不要直接照搬从零训练。
3. 对比预处理：确认你是否已有对齐、裁剪、去噪、切帧、归一化、脱敏等步骤。
4. 把差异写进任务卡，再让 `cv-task-advisor` 基于差异推荐论文和基线。

## 重要说明

- 数据集规模是论文主实验常用基准的**近似值**，同一论文可能还用了其他数据集，具体以论文为准。
- 预处理只列通用流程，不包含论文特有的训练技巧、损失函数和增强策略。
- “给用户的提示”是把参考工作与你的数据条件对齐时最需要问的问题。
- 医学、人脸、遥感等数据涉及隐私、伦理和许可，使用前先确认合规。

## 统计概览

| 领域 | 论文数 |
|---|---:|
| 图像分类与识别 | 10 |
| 目标检测 | 16 |
| 图像分割 | 11 |
| 跟踪与视频理解 | 14 |
| 人脸、人体与生物特征 | 14 |
| 3D视觉与几何 | 14 |
| 生成模型 | 14 |
| 视觉-语言与多模态 | 15 |
| 自监督与基础模型 | 10 |
| 低层视觉与图像复原 | 15 |
| 具身智能、机器人与自动驾驶 | 14 |
| 医学与生物视觉 | 10 |
| 遥感、农业与地球观测 | 9 |
| 工业、文档与其他应用 | 10 |
| 高效计算与部署 | 11 |
| 鲁棒性、安全与可信 | 15 |
| 数据集、基准与评测 | 13 |
| 交叉与新兴方向 | 8 |
| **合计** | **223** |

## 图像分类与识别

| # | 论文 | 年份/会议 | 主要数据集（规模） | 典型预处理 | 给用户的提示 |
|---|---|---|---|---|---|
| 1 | ImageNet Classification with Deep Convolutional Neural Networks | 2012 / NeurIPS | ImageNet-1K；约 128 万训练图 / 5 万验证图，1,000 类 | 随机裁剪 224、翻转、归一化；部分加 Mixup/CutMix | 数据少于 1 万张时，先微调预训练模型，不要从零训练 |
| 2 | Deep Residual Learning for Image Recognition | 2016 / CVPR | ImageNet-1K；约 128 万训练图 / 5 万验证图，1,000 类 | 随机裁剪 224、翻转、归一化；部分加 Mixup/CutMix | 数据少于 1 万张时，先微调预训练模型，不要从零训练 |
| 3 | Densely Connected Convolutional Networks | 2017 / CVPR | ImageNet-1K；约 128 万训练图 / 5 万验证图，1,000 类 | 随机裁剪 224、翻转、归一化；部分加 Mixup/CutMix | 数据少于 1 万张时，先微调预训练模型，不要从零训练 |
| 4 | Squeeze-and-Excitation Networks | 2018 / CVPR | ImageNet-1K；约 128 万训练图 / 5 万验证图，1,000 类 | 随机裁剪 224、翻转、归一化；部分加 Mixup/CutMix | 数据少于 1 万张时，先微调预训练模型，不要从零训练 |
| 5 | Model-Agnostic Meta-Learning for Fast Adaptation of Deep Networks | 2017 / ICML | Omniglot / MiniImageNet / tieredImageNet；1,623 类 / 100 类 / 608 类 | N-way K-shot 采样、resize 84、归一化 | 先确认每个新类能提供几张标注，通常 1–5 张 |
| 6 | Prototypical Networks for Few-shot Learning | 2017 / NeurIPS | Omniglot / MiniImageNet / tieredImageNet；1,623 类 / 100 类 / 608 类 | N-way K-shot 采样、resize 84、归一化 | 先确认每个新类能提供几张标注，通常 1–5 张 |
| 7 | An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale | 2021 / ICLR | ImageNet-1K；约 128 万训练图 / 5 万验证图，1,000 类 | 随机裁剪 224、翻转、归一化；部分加 Mixup/CutMix | 数据少于 1 万张时，先微调预训练模型，不要从零训练 |
| 8 | Swin Transformer: Hierarchical Vision Transformer using Shifted Windows | 2021 / ICCV | ImageNet-1K；约 128 万训练图 / 5 万验证图，1,000 类 | 随机裁剪 224、翻转、归一化；部分加 Mixup/CutMix | 数据少于 1 万张时，先微调预训练模型，不要从零训练 |
| 9 | A ConvNet for the 2020s | 2022 / CVPR | ImageNet-1K；约 128 万训练图 / 5 万验证图，1,000 类 | 随机裁剪 224、翻转、归一化；部分加 Mixup/CutMix | 数据少于 1 万张时，先微调预训练模型，不要从零训练 |
| 10 | Learning Transferable Visual Models From Natural Language Supervision | 2021 / ICML | WIT / ALIGN；4 亿–18 亿图文对 | resize 224、文本 tokenize、对比学习 | 图文对质量比数量更重要，噪声要清洗 |
## 目标检测

| # | 论文 | 年份/会议 | 主要数据集（规模） | 典型预处理 | 给用户的提示 |
|---|---|---|---|---|---|
| 11 | Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks | 2015 / NeurIPS | COCO；11.8 万训练图 / 5 千验证图，80 类，86 万实例 | 短边 resize 800、翻转、归一化 | 框标注成本高，先统一类别体系和标注规范 |
| 12 | You Only Look Once: Unified, Real-Time Object Detection | 2016 / CVPR | COCO；11.8 万训练图 / 5 千验证图，80 类，86 万实例 | 短边 resize 800、翻转、归一化 | 框标注成本高，先统一类别体系和标注规范 |
| 13 | SSD: Single Shot MultiBox Detector | 2016 / ECCV | COCO；11.8 万训练图 / 5 千验证图，80 类，86 万实例 | 短边 resize 800、翻转、归一化 | 框标注成本高，先统一类别体系和标注规范 |
| 14 | Focal Loss for Dense Object Detection | 2017 / ICCV | COCO；11.8 万训练图 / 5 千验证图，80 类，86 万实例 | 短边 resize 800、翻转、归一化 | 框标注成本高，先统一类别体系和标注规范 |
| 15 | Cascade R-CNN: Delving into High Quality Object Detection | 2018 / CVPR | COCO；11.8 万训练图 / 5 千验证图，80 类，86 万实例 | 短边 resize 800、翻转、归一化 | 框标注成本高，先统一类别体系和标注规范 |
| 16 | FCOS: Fully Convolutional One-Stage Object Detection | 2019 / ICCV | COCO；11.8 万训练图 / 5 千验证图，80 类，86 万实例 | 短边 resize 800、翻转、归一化 | 框标注成本高，先统一类别体系和标注规范 |
| 17 | End-to-End Object Detection with Transformers | 2020 / ECCV | COCO；11.8 万训练图 / 5 千验证图，80 类，86 万实例 | 短边 resize 800、翻转、归一化 | 框标注成本高，先统一类别体系和标注规范 |
| 18 | Deformable DETR: Deformable Transformers for End-to-End Object Detection | 2021 / ICLR | COCO；11.8 万训练图 / 5 千验证图，80 类，86 万实例 | 短边 resize 800、翻转、归一化 | 框标注成本高，先统一类别体系和标注规范 |
| 19 | YOLOX: Exceeding YOLO Series in 2021 | 2021 / CVPR | COCO；11.8 万训练图 / 5 千验证图，80 类，86 万实例 | 短边 resize 800、翻转、归一化 | 框标注成本高，先统一类别体系和标注规范 |
| 20 | DINO: DETR with Improved DeNoising Anchor Boxes for End-to-End Object Detection | 2023 / ICLR | COCO；11.8 万训练图 / 5 千验证图，80 类，86 万实例 | 短边 resize 800、翻转、归一化 | 框标注成本高，先统一类别体系和标注规范 |
| 21 | Simple Open-Vocabulary Object Detection with Vision Transformers | 2022 / ECCV | OpenImages / LVIS / COCO / Objects365；170 万 / 12 万 / 11.8 万 / 63.8 万图 | resize 640–800、文本 tokenize、区域-文本对齐 | 开放词汇需要图文或类别描述，类别表可扩展 |
| 22 | Grounding DINO: Marrying DINO with Grounded Pre-Training for Open-Set Object Detection | 2024 / ECCV | OpenImages / LVIS / COCO / Objects365；170 万 / 12 万 / 11.8 万 / 63.8 万图 | resize 640–800、文本 tokenize、区域-文本对齐 | 开放词汇需要图文或类别描述，类别表可扩展 |
| 23 | VoxelNet: End-to-End Learning for Point Cloud Based 3D Object Detection | 2018 / CVPR | KITTI；7,481 训练帧 / 7,518 测试帧，3D 框 | 点云体素/柱状化、地面去除、翻转/旋转 | 需要相机标定和点云；纯视觉方案精度会下降 |
| 24 | PointPillars: Fast Encoders for Object Detection from Point Clouds | 2019 / CVPR | KITTI；7,481 训练帧 / 7,518 测试帧，3D 框 | 点云体素/柱状化、地面去除、翻转/旋转 | 需要相机标定和点云；纯视觉方案精度会下降 |
| 25 | CenterPoint: Center-based 3D Object Detection and Tracking | 2021 / CVPR | nuScenes；1,000 场景、23 类、6 相机 + LiDAR | 多传感器对齐、BEV、时序采样 | 多传感器同步和标定是前提 |
| 26 | BEVFormer: Learning Bird's-Eye-View Representation from Multi-Camera Images via Spatiotemporal Transformers | 2022 / ECCV | nuScenes；1,000 场景、23 类、6 相机 + LiDAR | 多传感器对齐、BEV、时序采样 | 多传感器同步和标定是前提 |
## 图像分割

| # | 论文 | 年份/会议 | 主要数据集（规模） | 典型预处理 | 给用户的提示 |
|---|---|---|---|---|---|
| 27 | Fully Convolutional Networks for Semantic Segmentation | 2015 / CVPR | PASCAL VOC；约 1.65 万图、20 类 | resize 500–513、翻转、裁剪 | 小数据集，适合快速验证想法 |
| 28 | U-Net: Convolutional Networks for Biomedical Image Segmentation | 2015 / MICCAI | ISBI 2012 细胞分割 / EM 图像；30 张 512×512 训练图 | 随机裁剪 388、弹性形变、翻转、归一化 | 极小数据集，靠强增强和滑动窗口推理 |
| 29 | Encoder-Decoder with Atrous Separable Convolution for Semantic Image Segmentation | 2018 / ECCV | ADE20K；2 万训练 / 2 千验证，150 类 | resize 512–1024、裁剪、翻转 | 场景解析标准基准，类别多、标注细 |
| 30 | Mask R-CNN | 2017 / ICCV | COCO；11.8 万图、80 类、像素级掩码 | resize 800–1024、翻转、归一化 | 像素级标注比框贵 5–10 倍，先做小规模验证 |
| 31 | Panoptic Feature Pyramid Networks | 2019 / CVPR | COCO；11.8 万图、80 类、像素级掩码 | resize 800–1024、翻转、归一化 | 像素级标注比框贵 5–10 倍，先做小规模验证 |
| 32 | PointRend: Image Segmentation as Rendering | 2020 / CVPR | COCO；11.8 万图、80 类、像素级掩码 | resize 800–1024、翻转、归一化 | 像素级标注比框贵 5–10 倍，先做小规模验证 |
| 33 | SegFormer: Simple and Efficient Design for Semantic Segmentation with Transformers | 2021 / NeurIPS | ADE20K；2 万训练 / 2 千验证，150 类 | resize 512–1024、裁剪、翻转 | 场景解析标准基准，类别多、标注细 |
| 34 | Masked-attention Mask Transformer for Universal Image Segmentation | 2022 / CVPR | ADE20K；2 万训练 / 2 千验证，150 类 | resize 512–1024、裁剪、翻转 | 场景解析标准基准，类别多、标注细 |
| 35 | Segment Anything | 2023 / ICCV | SA-1B；1,100 万图、11 亿掩码 | resize 1024、提示编码（点/框/掩码） | 分割一切需要海量掩码；自有数据可做少样本微调 |
| 36 | SAM 2: Segment Anything in Images and Videos | 2024 / arXiv | SA-V；5.09 万视频、64.26 万 masklet | 视频抽帧、resize 1024、提示传播 | 视频分割需要时序一致的掩码标注 |
| 37 | nnU-Net: a self-configuring method for deep learning-based biomedical image segmentation | 2021 / Nature Methods | BTCV / AMOS / BRATS / Synapse；30 / 300 / 1,251 / 30 例 | 重采样、归一化、patch 96³ | 医学数据需伦理审批和专家标注，跨中心差异大 |
## 跟踪与视频理解

| # | 论文 | 年份/会议 | 主要数据集（规模） | 典型预处理 | 给用户的提示 |
|---|---|---|---|---|---|
| 38 | Simple Online and Realtime Tracking | 2016 / ICIP | MOT17 / MOT20；21 / 8 段视频，行人框 + ID | 检测框输入、卡尔曼滤波；不做图像归一化 | 需要连续帧和 ID 标注，遮挡是主要难点 |
| 39 | Simple Online and Realtime Tracking with a Deep Association Metric | 2017 / ICIP | MOT17 / MOT20；21 / 8 段视频，行人框 + ID | 检测框输入、卡尔曼滤波；不做图像归一化 | 需要连续帧和 ID 标注，遮挡是主要难点 |
| 40 | ByteTrack: Multi-Object Tracking by Associating Every Detection Box | 2022 / ECCV | MOT17 / MOT20；21 / 8 段视频，行人框 + ID | 检测框输入、卡尔曼滤波；不做图像归一化 | 需要连续帧和 ID 标注，遮挡是主要难点 |
| 41 | Observation-Centric SORT: Rethinking SORT for Robust Multi-Object Tracking | 2023 / CVPR | MOT17 / MOT20；21 / 8 段视频，行人框 + ID | 检测框输入、卡尔曼滤波；不做图像归一化 | 需要连续帧和 ID 标注，遮挡是主要难点 |
| 42 | Fully-Convolutional Siamese Networks for Object Tracking | 2016 / ECCV | OTB / LaSOT / GOT-10k；100 / 1,400 / 1 万段视频 | 模板/搜索区域裁剪、resize、归一化 | 首帧给一个框即可，适合标注成本低的场景 |
| 43 | SiamRPN++: Evolution of Siamese Visual Tracking with Very Deep Networks | 2019 / CVPR | OTB / LaSOT / GOT-10k；100 / 1,400 / 1 万段视频 | 模板/搜索区域裁剪、resize、归一化 | 首帧给一个框即可，适合标注成本低的场景 |
| 44 | Joint Feature Learning and Relation Modeling for Tracking: A One-Stream Framework | 2022 / ECCV | OTB / LaSOT / GOT-10k；100 / 1,400 / 1 万段视频 | 模板/搜索区域裁剪、resize、归一化 | 首帧给一个框即可，适合标注成本低的场景 |
| 45 | Quo Vadis, Action Recognition? A New Model and the Kinetics Dataset | 2017 / CVPR | Kinetics-400/600；24 万 / 37 万训练视频，400/600 类 | 抽 8–64 帧、resize 224、裁剪、翻转 | 视频存储和抽帧成本高，先定帧率和片段长度 |
| 46 | SlowFast Networks for Video Recognition | 2019 / ICCV | Kinetics-400/600；24 万 / 37 万训练视频，400/600 类 | 抽 8–64 帧、resize 224、裁剪、翻转 | 视频存储和抽帧成本高，先定帧率和片段长度 |
| 47 | Is Space-Time Attention All You Need for Video Understanding? | 2021 / ICML | Kinetics-400/600；24 万 / 37 万训练视频，400/600 类 | 抽 8–64 帧、resize 224、裁剪、翻转 | 视频存储和抽帧成本高，先定帧率和片段长度 |
| 48 | VideoMAE: Masked Autoencoders are Data-Efficient Learners for Self-Supervised Video Pre-Training | 2022 / NeurIPS | Kinetics-400/600；24 万 / 37 万训练视频，400/600 类 | 抽 8–64 帧、resize 224、裁剪、翻转 | 视频存储和抽帧成本高，先定帧率和片段长度 |
| 49 | Video Swin Transformer | 2022 / CVPR | Kinetics-400/600；24 万 / 37 万训练视频，400/600 类 | 抽 8–64 帧、resize 224、裁剪、翻转 | 视频存储和抽帧成本高，先定帧率和片段长度 |
| 50 | Video Diffusion Models | 2022 / NeurIPS | UCF-101 / 网络视频；1.3 万 / 百万级片段 | 抽帧、resize 64–512、归一化 | 视频生成数据需求极大，长视频更难 |
| 51 | Video Generation Models as World Simulators | 2024 / arXiv | UCF-101 / 网络视频；1.3 万 / 百万级片段 | 抽帧、resize 64–512、归一化 | 视频生成数据需求极大，长视频更难 |
## 人脸、人体与生物特征

| # | 论文 | 年份/会议 | 主要数据集（规模） | 典型预处理 | 给用户的提示 |
|---|---|---|---|---|---|
| 52 | FaceNet: A Unified Embedding for Face Recognition and Clustering | 2015 / CVPR | MS-Celeb / Glint360K / LFW；1,000 万 / 1,700 万 / 1.3 万图 | 人脸检测对齐 112×112、归一化 | 人脸数据涉及隐私和合规，需授权与脱敏 |
| 53 | CosFace: Large Margin Cosine Loss for Deep Face Recognition | 2018 / CVPR | MS-Celeb / Glint360K / LFW；1,000 万 / 1,700 万 / 1.3 万图 | 人脸检测对齐 112×112、归一化 | 人脸数据涉及隐私和合规，需授权与脱敏 |
| 54 | ArcFace: Additive Angular Margin Loss for Deep Face Recognition | 2019 / CVPR | MS-Celeb / Glint360K / LFW；1,000 万 / 1,700 万 / 1.3 万图 | 人脸检测对齐 112×112、归一化 | 人脸数据涉及隐私和合规，需授权与脱敏 |
| 55 | RetinaFace: Single-stage Dense Face Localisation in the Wild | 2020 / CVPR | WIDER FACE；3.2 万图、39.3 万张脸 | resize 640、翻转、颜色扰动 | 小脸、遮挡、侧脸是主要难点 |
| 56 | DECA: Detailed Expression Capture and Animation | 2021 / ICCV | MS-Celeb / Glint360K / LFW；1,000 万 / 1,700 万 / 1.3 万图 | 人脸检测对齐 112×112、归一化 | 人脸数据涉及隐私和合规，需授权与脱敏 |
| 57 | A Style-Based Generator Architecture for Generative Adversarial Networks | 2019 / CVPR | FFHQ / CelebA-HQ；7 万 / 3 万高清人脸 | 对齐裁剪 1024、归一化 | 高清人脸生成需要大量高质量数据 |
| 58 | Analyzing and Improving the Image Quality of StyleGAN | 2020 / CVPR | FFHQ / CelebA-HQ；7 万 / 3 万高清人脸 | 对齐裁剪 1024、归一化 | 高清人脸生成需要大量高质量数据 |
| 59 | FaceForensics++: Learning to Detect Manipulated Facial Images | 2019 / ICCV | FaceForensics++；1,000 段视频、4 种篡改方法 | 人脸裁剪 299、压缩增强 | 伪造手段变化快，训练集要覆盖多种生成器 |
| 60 | Realtime Multi-Person 2D Pose Estimation using Part Affinity Fields | 2017 / CVPR | COCO / MPII；11.8 万 / 2.5 万图，17/16 关键点 | resize 256×192、翻转、旋转 | 关键点标注成本高，遮挡场景要额外标注 |
| 61 | Deep High-Resolution Representation Learning for Visual Recognition | 2019 / CVPR | COCO / MPII；11.8 万 / 2.5 万图，17/16 关键点 | resize 256×192、翻转、旋转 | 关键点标注成本高，遮挡场景要额外标注 |
| 62 | ViTPose: Simple Vision Transformer Baselines for Human Pose Estimation | 2022 / NeurIPS | COCO / MPII；11.8 万 / 2.5 万图，17/16 关键点 | resize 256×192、翻转、旋转 | 关键点标注成本高，遮挡场景要额外标注 |
| 63 | SMPL: A Skinned Multi-Person Linear Model | 2015 / SIGGRAPH | CAESAR / SMPL；约 2,400 个人体扫描 | 3D 扫描拟合、归一化 | 需要三维扫描或参数化人体模型 |
| 64 | Expressive Body Capture: 3D Hands, Face, and Body from a Single Image | 2019 / CVPR | CAESAR / SMPL；约 2,400 个人体扫描 | 3D 扫描拟合、归一化 | 需要三维扫描或参数化人体模型 |
| 65 | GaitSet: Regarding Gait as a Set for Cross-View Gait Recognition | 2019 / AAAI | CASIA-B；124 人、13,640 段步态序列 | 剪影提取、resize 64×44、帧采样 | 跨视角、换衣、背包是主要难点 |
## 3D视觉与几何

| # | 论文 | 年份/会议 | 主要数据集（规模） | 典型预处理 | 给用户的提示 |
|---|---|---|---|---|---|
| 66 | Structure-from-Motion Revisited | 2016 / CVPR | DTU / Tanks and Temples / CO3D；124 / 14 / 1.9 万场景 | 相机标定、特征匹配、深度/点云融合 | 需要多视角采集和相机位姿；纹理少时难匹配 |
| 67 | MVSNet: Depth Inference for Unstructured Multi-view Stereo | 2018 / ECCV | DTU / Tanks and Temples / CO3D；124 / 14 / 1.9 万场景 | 相机标定、特征匹配、深度/点云融合 | 需要多视角采集和相机位姿；纹理少时难匹配 |
| 68 | PointNet: Deep Learning on Point Sets for 3D Classification and Segmentation | 2017 / CVPR | ShapeNet / ModelNet40；300 万 / 12,311 个模型，40 类 | 采样 1,024–2,048 点、归一化、旋转 | 3D 格式和坐标系要先统一 |
| 69 | PointNet++: Deep Hierarchical Feature Learning on Point Sets in a Metric Space | 2017 / NeurIPS | ShapeNet / ModelNet40；300 万 / 12,311 个模型，40 类 | 采样 1,024–2,048 点、归一化、旋转 | 3D 格式和坐标系要先统一 |
| 70 | Occupancy Networks: Learning 3D Reconstruction in Function Space | 2019 / CVPR | ShapeNet / ModelNet40；300 万 / 12,311 个模型，40 类 | 采样 1,024–2,048 点、归一化、旋转 | 3D 格式和坐标系要先统一 |
| 71 | NeRF: Representing Scenes as Neural Radiance Fields for View Synthesis | 2020 / ECCV | NeRF synthetic / LLFF / Mip-NeRF 360；100 / 24 / 9 个场景，多视角 | 相机位姿、光线采样、归一化 | 需要多视角采集和准确位姿 |
| 72 | Mip-NeRF: A Multiscale Representation for Anti-Aliasing Neural Radiance Fields | 2021 / ICCV | NeRF synthetic / LLFF / Mip-NeRF 360；100 / 24 / 9 个场景，多视角 | 相机位姿、光线采样、归一化 | 需要多视角采集和准确位姿 |
| 73 | Instant Neural Graphics Primitives with a Multiresolution Hash Encoding | 2022 / SIGGRAPH | NeRF synthetic / LLFF / Mip-NeRF 360；100 / 24 / 9 个场景，多视角 | 相机位姿、光线采样、归一化 | 需要多视角采集和准确位姿 |
| 74 | 3D Gaussian Splatting for Real-Time Radiance Field Rendering | 2023 / SIGGRAPH | NeRF synthetic / LLFF / Mip-NeRF 360；100 / 24 / 9 个场景，多视角 | 相机位姿、光线采样、归一化 | 需要多视角采集和准确位姿 |
| 75 | DreamFusion: Text-to-3D using 2D Diffusion | 2023 / ICLR | 无三维训练集；文本提示 + 2D 扩散先验；无固定数据集 | 文本提示、多视角渲染、SDS 蒸馏 | 需要预训练 2D 扩散模型，不是从零训练 |
| 76 | Magic3D: High-Resolution Text-to-3D Content Creation | 2023 / CVPR | 无三维训练集；文本提示 + 2D 扩散先验；无固定数据集 | 粗到细两阶段、多视角渲染、SDS | 需要预训练 2D 扩散模型和较强算力 |
| 77 | LRM: Large Reconstruction Model for Single Image to 3D | 2023 / ICCV | Objaverse；约 80 万 3D 物体 | 多视角渲染、相机采样、文本/图像条件 | 3D 数据稀缺，常用合成渲染补充 |
| 78 | DUSt3R: Geometric 3D Vision Made Easy | 2024 / CVPR | DTU / Tanks and Temples / CO3D；124 / 14 / 1.9 万场景 | 相机标定、特征匹配、深度/点云融合 | 需要多视角采集和相机位姿；纹理少时难匹配 |
| 79 | VGGT: Visual Geometry Grounded Transformer | 2025 / CVPR | DTU / Tanks and Temples / CO3D；124 / 14 / 1.9 万场景 | 相机标定、特征匹配、深度/点云融合 | 需要多视角采集和相机位姿；纹理少时难匹配 |
## 生成模型

| # | 论文 | 年份/会议 | 主要数据集（规模） | 典型预处理 | 给用户的提示 |
|---|---|---|---|---|---|
| 80 | Generative Adversarial Networks | 2014 / NeurIPS | MNIST / Omniglot；6 万 / 3.2 万 | resize 28、归一化 | 小数据生成容易过拟合，先做简单基线 |
| 81 | Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks | 2016 / ICLR | ImageNet-1K / CIFAR-10 / CelebA-HQ；128 万 / 5 万 / 3 万图 | resize 32–512、归一化、类别条件 | 生成任务通常需要十万级以上同类图 |
| 82 | Wasserstein Generative Adversarial Networks | 2017 / NeurIPS | ImageNet-1K / CIFAR-10 / CelebA-HQ；128 万 / 5 万 / 3 万图 | resize 32–512、归一化、类别条件 | 生成任务通常需要十万级以上同类图 |
| 83 | Auto-Encoding Variational Bayes | 2014 / ICLR | MNIST / Omniglot；6 万 / 3.2 万 | resize 28、归一化 | 小数据生成容易过拟合，先做简单基线 |
| 84 | Denoising Diffusion Probabilistic Models | 2020 / NeurIPS | ImageNet-1K / CIFAR-10 / CelebA-HQ；128 万 / 5 万 / 3 万图 | resize 32–512、归一化、类别条件 | 生成任务通常需要十万级以上同类图 |
| 85 | Denoising Diffusion Implicit Models | 2021 / ICLR | ImageNet-1K / CIFAR-10 / CelebA-HQ；128 万 / 5 万 / 3 万图 | resize 32–512、归一化、类别条件 | 生成任务通常需要十万级以上同类图 |
| 86 | High-Resolution Image Synthesis with Latent Diffusion Models | 2022 / CVPR | LAION-400M / COCO；4 亿图文对 / 11.8 万图 | resize 256–512、文本 tokenize、VAE 编码 | 文生图需要海量图文对，数据质量决定上限 |
| 87 | Photorealistic Text-to-Image Diffusion Models with Deep Language Understanding | 2022 / NeurIPS | LAION-400M / COCO；4 亿图文对 / 11.8 万图 | resize 256–512、文本 tokenize、VAE 编码 | 文生图需要海量图文对，数据质量决定上限 |
| 88 | Hierarchical Text-Conditional Image Generation with CLIP Latents | 2022 / NeurIPS | LAION-400M / COCO；4 亿图文对 / 11.8 万图 | resize 256–512、文本 tokenize、VAE 编码 | 文生图需要海量图文对，数据质量决定上限 |
| 89 | Adding Conditional Control to Text-to-Image Diffusion Models | 2023 / ICCV | LAION-400M / COCO；4 亿图文对 / 11.8 万图 | resize 256–512、文本 tokenize、VAE 编码 | 文生图需要海量图文对，数据质量决定上限 |
| 90 | DreamBooth: Fine Tuning Text-to-Image Diffusion Models for Subject-Driven Generation | 2023 / CVPR | 3–5 张主体照片 + 预训练扩散模型；每个主体 3–5 张 | 主体分割、提示增强、resize 512 | 少量主体照片即可，但依赖强预训练底座 |
| 91 | LoRA: Low-Rank Adaptation of Large Language Models | 2022 / ICLR | 文本 / 多模态混合数据；数十亿 token | tokenize、指令微调 | 需要大算力；小团队优先用开源基座微调 |
| 92 | Scalable Diffusion Models with Transformers | 2023 / ICCV | ImageNet-1K / CIFAR-10 / CelebA-HQ；128 万 / 5 万 / 3 万图 | resize 32–512、归一化、类别条件 | 生成任务通常需要十万级以上同类图 |
| 93 | Flow Matching for Generative Modeling | 2023 / ICLR | ImageNet-1K / CIFAR-10 / CelebA-HQ；128 万 / 5 万 / 3 万图 | resize 32–512、归一化、类别条件 | 生成任务通常需要十万级以上同类图 |
## 视觉-语言与多模态

| # | 论文 | 年份/会议 | 主要数据集（规模） | 典型预处理 | 给用户的提示 |
|---|---|---|---|---|---|
| 94 | Show and Tell: A Neural Image Caption Generator | 2015 / CVPR | COCO / Flickr30k；11.8 万 / 3 万图，每图约 5 句 | resize 224、文本 tokenize | 描述标注要统一风格和粒度 |
| 95 | Show, Attend and Tell: Neural Image Caption Generation with Visual Attention | 2015 / ICML | COCO / Flickr30k；11.8 万 / 3 万图，每图约 5 句 | resize 224、文本 tokenize | 描述标注要统一风格和粒度 |
| 96 | VQA: Visual Question Answering | 2015 / ICCV | VQA v2；20.4 万图、110 万问答 | 图像特征、问题 tokenize | 注意语言先验和答案分布偏差 |
| 97 | Bottom-Up and Top-Down Attention for Image Captioning and Visual Question Answering | 2018 / CVPR | VQA v2；20.4 万图、110 万问答 | 图像特征、问题 tokenize | 注意语言先验和答案分布偏差 |
| 98 | ViLBERT: Pretraining Task-Agnostic Visiolinguistic Representations for Vision-and-Language Tasks | 2019 / NeurIPS | COCO / VG / CC / LAION / 指令数据；11.8 万 / 10.8 万 / 330 万 / 4 亿 | 图像 resize 224、文本 tokenize、指令微调 | 多模态微调数据质量比数量重要，注意幻觉 |
| 99 | LXMERT: Learning Cross-Modality Encoder Representations from Transformers | 2019 / EMNLP | COCO / VG / CC / LAION / 指令数据；11.8 万 / 10.8 万 / 330 万 / 4 亿 | 图像 resize 224、文本 tokenize、指令微调 | 多模态微调数据质量比数量重要，注意幻觉 |
| 100 | UNITER: UNiversal Image-TExt Representation Learning | 2020 / ECCV | COCO / VG / CC / LAION / 指令数据；11.8 万 / 10.8 万 / 330 万 / 4 亿 | 图像 resize 224、文本 tokenize、指令微调 | 多模态微调数据质量比数量重要，注意幻觉 |
| 101 | Scaling Up Visual and Vision-Language Representation Learning With Noisy Text Supervision | 2021 / ICML | WIT / ALIGN；4 亿–18 亿图文对 | resize 224、文本 tokenize、对比学习 | 图文对质量比数量更重要，噪声要清洗 |
| 102 | BLIP: Bootstrapping Language-Image Pre-training for Unified Vision-Language Understanding and Generation | 2022 / CVPR | COCO / VG / CC / LAION / 指令数据；11.8 万 / 10.8 万 / 330 万 / 4 亿 | 图像 resize 224、文本 tokenize、指令微调 | 多模态微调数据质量比数量重要，注意幻觉 |
| 103 | BLIP-2: Bootstrapping Language-Image Pre-training with Frozen Image Encoders and Large Language Models | 2023 / ICML | COCO / VG / CC / LAION / 指令数据；11.8 万 / 10.8 万 / 330 万 / 4 亿 | 图像 resize 224、文本 tokenize、指令微调 | 多模态微调数据质量比数量重要，注意幻觉 |
| 104 | Flamingo: a Visual Language Model for Few-Shot Learning | 2022 / NeurIPS | COCO / VG / CC / LAION / 指令数据；11.8 万 / 10.8 万 / 330 万 / 4 亿 | 图像 resize 224、文本 tokenize、指令微调 | 多模态微调数据质量比数量重要，注意幻觉 |
| 105 | Visual Instruction Tuning | 2023 / NeurIPS | COCO / VG / CC / LAION / 指令数据；11.8 万 / 10.8 万 / 330 万 / 4 亿 | 图像 resize 224、文本 tokenize、指令微调 | 多模态微调数据质量比数量重要，注意幻觉 |
| 106 | MiniGPT-4: Enhancing Vision-Language Understanding with Advanced Large Language Models | 2023 / ICML | COCO / VG / CC / LAION / 指令数据；11.8 万 / 10.8 万 / 330 万 / 4 亿 | 图像 resize 224、文本 tokenize、指令微调 | 多模态微调数据质量比数量重要，注意幻觉 |
| 107 | InstructBLIP: Towards General-purpose Vision-Language Models with Instruction Tuning | 2023 / NeurIPS | COCO / VG / CC / LAION / 指令数据；11.8 万 / 10.8 万 / 330 万 / 4 亿 | 图像 resize 224、文本 tokenize、指令微调 | 多模态微调数据质量比数量重要，注意幻觉 |
| 108 | Grounded Language-Image Pre-training | 2022 / CVPR | OpenImages / LVIS / COCO / Objects365；170 万 / 12 万 / 11.8 万 / 63.8 万图 | resize 640–800、文本 tokenize、区域-文本对齐 | 开放词汇需要图文或类别描述，类别表可扩展 |
## 自监督与基础模型

| # | 论文 | 年份/会议 | 主要数据集（规模） | 典型预处理 | 给用户的提示 |
|---|---|---|---|---|---|
| 109 | A Simple Framework for Contrastive Learning of Visual Representations | 2020 / ICML | ImageNet-1K（无标签）；约 128 万图，不做人工标注 | 多裁剪、颜色扰动、翻转、模糊、掩码 | 无标注时先做自监督预训练，再小样本微调 |
| 110 | Momentum Contrast for Unsupervised Visual Representation Learning | 2020 / CVPR | ImageNet-1K（无标签）；约 128 万图，不做人工标注 | 多裁剪、颜色扰动、翻转、模糊、掩码 | 无标注时先做自监督预训练，再小样本微调 |
| 111 | Bootstrap Your Own Latent: A New Approach to Self-Supervised Learning | 2020 / NeurIPS | ImageNet-1K（无标签）；约 128 万图，不做人工标注 | 多裁剪、颜色扰动、翻转、模糊、掩码 | 无标注时先做自监督预训练，再小样本微调 |
| 112 | Unsupervised Learning of Visual Features by Contrasting Cluster Assignments | 2020 / NeurIPS | ImageNet-1K（无标签）；约 128 万图，不做人工标注 | 多裁剪、颜色扰动、翻转、模糊、掩码 | 无标注时先做自监督预训练，再小样本微调 |
| 113 | Emerging Properties in Self-Supervised Vision Transformers | 2021 / ICCV | ImageNet-1K（无标签）；约 128 万图，不做人工标注 | 多裁剪、颜色扰动、翻转、模糊、掩码 | 无标注时先做自监督预训练，再小样本微调 |
| 114 | DINOv2: Learning Robust Visual Features without Supervision | 2024 / TMLR | LVD-142M（无标签）；1.42 亿图 | 多裁剪、颜色扰动、翻转 | 大规模无标签数据，小团队可直接用现成权重 |
| 115 | Masked Autoencoders Are Scalable Vision Learners | 2022 / CVPR | ImageNet-1K（无标签）；约 128 万图，不做人工标注 | 多裁剪、颜色扰动、翻转、模糊、掩码 | 无标注时先做自监督预训练，再小样本微调 |
| 116 | BEiT: BERT Pre-Training of Image Transformers | 2022 / ICLR | ImageNet-1K（无标签）；约 128 万图，不做人工标注 | 多裁剪、颜色扰动、翻转、模糊、掩码 | 无标注时先做自监督预训练，再小样本微调 |
| 117 | Mamba: Linear-Time Sequence Modeling with Selective State Spaces | 2024 / COLM | 文本 / 多模态混合数据；数十亿 token | tokenize、指令微调 | 需要大算力；小团队优先用开源基座微调 |
| 118 | Vision Mamba: Efficient Visual Representation Learning with Bidirectional State Space Model | 2024 / ICML | ImageNet-1K（无标签）；约 128 万图，不做人工标注 | 多裁剪、颜色扰动、翻转、模糊、掩码 | 无标注时先做自监督预训练，再小样本微调 |
## 低层视觉与图像复原

| # | 论文 | 年份/会议 | 主要数据集（规模） | 典型预处理 | 给用户的提示 |
|---|---|---|---|---|---|
| 119 | Learning a Deep Convolutional Network for Image Super-Resolution | 2014 / ECCV | DIV2K / Flickr2K / Set5 / Set14 / BSD100；800 / 2,650 / 5 / 14 / 100 | 随机裁剪 64–256、翻转/旋转、合成退化 | 真实退化与合成退化差距大，要用真实数据验证 |
| 120 | Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network | 2017 / CVPR | DIV2K / Flickr2K / Set5 / Set14 / BSD100；800 / 2,650 / 5 / 14 / 100 | 随机裁剪 64–256、翻转/旋转、合成退化 | 真实退化与合成退化差距大，要用真实数据验证 |
| 121 | ESRGAN: Enhanced Super-Resolution Generative Adversarial Networks | 2018 / ECCV | DIV2K / Flickr2K / Set5 / Set14 / BSD100；800 / 2,650 / 5 / 14 / 100 | 随机裁剪 64–256、翻转/旋转、合成退化 | 真实退化与合成退化差距大，要用真实数据验证 |
| 122 | Beyond a Gaussian Denoiser: Residual Learning of Deep CNN for Image Denoising | 2017 / IEEE TIP | BSD68 / Set12 / SIDD；68 / 12 / 3 万 | 加噪、裁剪 40–256 | 噪声类型和强度要匹配真实场景 |
| 123 | SwinIR: Image Restoration Using Swin Transformer | 2021 / ICCV | DIV2K / Flickr2K / Set5 / Set14 / BSD100；800 / 2,650 / 5 / 14 / 100 | 随机裁剪 64–256、翻转/旋转、合成退化 | 真实退化与合成退化差距大，要用真实数据验证 |
| 124 | Real-ESRGAN: Training Real-World Blind Super-Resolution with Pure Synthetic Data | 2021 / ICCV | DIV2K / Flickr2K / Set5 / Set14 / BSD100；800 / 2,650 / 5 / 14 / 100 | 随机裁剪 64–256、翻转/旋转、合成退化 | 真实退化与合成退化差距大，要用真实数据验证 |
| 125 | Restormer: Efficient Transformer for High-Resolution Image Restoration | 2022 / CVPR | DIV2K / Flickr2K / Set5 / Set14 / BSD100；800 / 2,650 / 5 / 14 / 100 | 随机裁剪 64–256、翻转/旋转、合成退化 | 真实退化与合成退化差距大，要用真实数据验证 |
| 126 | Simple Baselines for Image Restoration | 2022 / ECCV | DIV2K / Flickr2K / Set5 / Set14 / BSD100；800 / 2,650 / 5 / 14 / 100 | 随机裁剪 64–256、翻转/旋转、合成退化 | 真实退化与合成退化差距大，要用真实数据验证 |
| 127 | Deep Bilateral Learning for Real-Time Image Enhancement | 2017 / SIGGRAPH | DIV2K / Flickr2K / Set5 / Set14 / BSD100；800 / 2,650 / 5 / 14 / 100 | 随机裁剪 64–256、翻转/旋转、合成退化 | 真实退化与合成退化差距大，要用真实数据验证 |
| 128 | End-to-End Optimized Image Compression | 2017 / ICLR | Kodak / CLIC / ImageNet；24 / 2 千 / 128 万 | 裁剪 256、归一化、率失真优化 | 码率-画质要按业务权衡 |
| 129 | High-Fidelity Generative Image Compression | 2020 / NeurIPS | Kodak / CLIC / ImageNet；24 / 2 千 / 128 万 | 裁剪 256、归一化、率失真优化 | 码率-画质要按业务权衡 |
| 130 | NIMA: Neural Image Assessment | 2018 / IEEE TIP | AVA / TID2013；25 万 / 3 千 | resize 224、归一化 | 主观评分噪声大，需多人标注 |
| 131 | All-in-One Network for Dehazing and Beyond | 2017 / ICCV | RESIDE / ITS / OTS；1.3 万合成 / 6 千真实 | resize 512、裁剪 256、归一化 | 合成雾和真实雾差异大，需真实雾验证 |
| 132 | FFA-Net: Feature Fusion Attention Network for Single Image Dehazing | 2020 / AAAI | RESIDE / ITS / OTS；1.3 万合成 / 6 千真实 | resize 512、裁剪 256、归一化 | 合成雾和真实雾差异大，需真实雾验证 |
| 133 | Multi-Stage Progressive Image Restoration | 2021 / CVPR | DIV2K / Flickr2K / Set5 / Set14 / BSD100；800 / 2,650 / 5 / 14 / 100 | 随机裁剪 64–256、翻转/旋转、合成退化 | 真实退化与合成退化差距大，要用真实数据验证 |
## 具身智能、机器人与自动驾驶

| # | 论文 | 年份/会议 | 主要数据集（规模） | 典型预处理 | 给用户的提示 |
|---|---|---|---|---|---|
| 134 | Domain Randomization for Transferring Deep Neural Networks from Simulation to the Real World | 2018 / ICLR | Open X-Embodiment / RT-1 / ALOHA；97 万 episode / 13 万 episode / 数千 demo | 图像 224、动作 token/chunk | 真机数据贵，先用仿真或公开数据，再做少量真机微调 |
| 135 | Do As I Can, Not As I Say: Grounding Language in Robotic Affordances | 2022 / CoRL | Open X-Embodiment / RT-1 / ALOHA；97 万 episode / 13 万 episode / 数千 demo | 图像 224、动作 token/chunk | 真机数据贵，先用仿真或公开数据，再做少量真机微调 |
| 136 | PaLM-E: An Embodied Multimodal Language Model | 2023 / ICML | Open X-Embodiment / RT-1 / ALOHA；97 万 episode / 13 万 episode / 数千 demo | 图像 224、动作 token/chunk | 真机数据贵，先用仿真或公开数据，再做少量真机微调 |
| 137 | RT-1: Robotics Transformer for Real-World Control at Scale | 2023 / RSS | Open X-Embodiment / RT-1 / ALOHA；97 万 episode / 13 万 episode / 数千 demo | 图像 224、动作 token/chunk | 真机数据贵，先用仿真或公开数据，再做少量真机微调 |
| 138 | RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control | 2023 / CoRL | Open X-Embodiment / RT-1 / ALOHA；97 万 episode / 13 万 episode / 数千 demo | 图像 224、动作 token/chunk | 真机数据贵，先用仿真或公开数据，再做少量真机微调 |
| 139 | Diffusion Policy: Visuomotor Policy Learning via Action Diffusion | 2023 / RSS | Open X-Embodiment / RT-1 / ALOHA；97 万 episode / 13 万 episode / 数千 demo | 图像 224、动作 token/chunk | 真机数据贵，先用仿真或公开数据，再做少量真机微调 |
| 140 | Learning Fine-Grained Bimanual Manipulation with Low-Cost Hardware | 2023 / RSS | Open X-Embodiment / RT-1 / ALOHA；97 万 episode / 13 万 episode / 数千 demo | 图像 224、动作 token/chunk | 真机数据贵，先用仿真或公开数据，再做少量真机微调 |
| 141 | OpenVLA: An Open-Source Vision-Language-Action Model | 2024 / CoRL | Open X-Embodiment / RT-1 / ALOHA；97 万 episode / 13 万 episode / 数千 demo | 图像 224、动作 token/chunk | 真机数据贵，先用仿真或公开数据，再做少量真机微调 |
| 142 | TransFuser: Imitation with Transformer-Based Sensor Fusion for Autonomous Driving | 2021 / CVPR | nuScenes / Waymo / CARLA；1,000 / 1,150 场景 / 10 万帧 | 多相机/LiDAR、BEV、时序 | 多传感器标定和同步是前提，长尾场景要专门采集 |
| 143 | Planning-oriented Autonomous Driving | 2023 / CVPR | nuScenes / Waymo / CARLA；1,000 / 1,150 场景 / 10 万帧 | 多相机/LiDAR、BEV、时序 | 多传感器标定和同步是前提，长尾场景要专门采集 |
| 144 | VAD: Vectorized Scene Representation for Efficient Autonomous Driving | 2023 / ICCV | nuScenes / Waymo / CARLA；1,000 / 1,150 场景 / 10 万帧 | 多相机/LiDAR、BEV、时序 | 多传感器标定和同步是前提，长尾场景要专门采集 |
| 145 | Dream to Control: Learning Behaviors by Latent Imagination | 2020 / ICLR | 视频 / 仿真环境；数万–数百万帧 | resize 64–224、动作条件 | 长时预测误差累积，需滚动训练和评测 |
| 146 | Navigation World Models | 2025 / CVPR | 视频 / 仿真环境；数万–数百万帧 | resize 64–224、动作条件 | 长时预测误差累积，需滚动训练和评测 |
| 147 | π0: A Vision-Language-Action Flow Model for General Robot Control | 2024 / arXiv | Open X-Embodiment / RT-1 / ALOHA；97 万 episode / 13 万 episode / 数千 demo | 图像 224、动作 token/chunk | 真机数据贵，先用仿真或公开数据，再做少量真机微调 |
## 医学与生物视觉

| # | 论文 | 年份/会议 | 主要数据集（规模） | 典型预处理 | 给用户的提示 |
|---|---|---|---|---|---|
| 148 | V-Net: Fully Convolutional Neural Networks for Volumetric Medical Image Segmentation | 2016 / 3DV | BTCV / AMOS / BRATS / Synapse；30 / 300 / 1,251 / 30 例 | 重采样、归一化、patch 96³ | 医学数据需伦理审批和专家标注，跨中心差异大 |
| 149 | nnU-Net: a self-configuring method for deep learning-based biomedical image segmentation | 2021 / Nature Methods | BTCV / AMOS / BRATS / Synapse；30 / 300 / 1,251 / 30 例 | 重采样、归一化、patch 96³ | 医学数据需伦理审批和专家标注，跨中心差异大 |
| 150 | TransUNet: Transformers Make Strong Encoders for Medical Image Segmentation | 2021 / arXiv | BTCV / AMOS / BRATS / Synapse；30 / 300 / 1,251 / 30 例 | 重采样、归一化、patch 96³ | 医学数据需伦理审批和专家标注，跨中心差异大 |
| 151 | Self-Supervised Pre-Training of Swin Transformers for 3D Medical Image Analysis | 2022 / CVPR | BTCV / AMOS / BRATS / Synapse；30 / 300 / 1,251 / 30 例 | 重采样、归一化、patch 96³ | 医学数据需伦理审批和专家标注，跨中心差异大 |
| 152 | Segment Anything in Medical Images | 2024 / Nature Communications | BTCV / AMOS / BRATS / Synapse；30 / 300 / 1,251 / 30 例 | 重采样、归一化、patch 96³ | 医学数据需伦理审批和专家标注，跨中心差异大 |
| 153 | CheXNet: Radiologist-Level Pneumonia Detection on Chest X-Rays with Deep Learning | 2017 / CVPR | ChestX-ray14 / MIMIC-CXR；11.2 万 / 37.7 万图 | resize 224、归一化 | 多标签、类别不均，需按病人划分避免泄漏 |
| 154 | MedCLIP: Contrastive Learning from Unpaired Medical Images and Text | 2022 / EMNLP | ChestX-ray14 / MIMIC-CXR；11.2 万 / 37.7 万图 | resize 224、归一化 | 多标签、类别不均，需按病人划分避免泄漏 |
| 155 | BiomedCLIP: a multimodal biomedical foundation model pretrained on fifteen million images | 2023 / NEJM AI | PMC-15M；1,500 万医学图文对 | resize 224、文本 tokenize、对比学习 | 医学图文对稀缺，需领域预训练 |
| 156 | Towards a General-Purpose Foundation Model for Computational Pathology | 2024 / Nature Medicine | TCGA / Mass-100K；数万张全切片 / 1 亿 patch | patch 224、染色归一化 | 全切片图像巨大，需先切片；染色差异要处理 |
| 157 | A foundation model for clinical-grade computational pathology and rare cancers detection | 2024 / Nature Medicine | TCGA / Mass-100K；数万张全切片 / 1 亿 patch | patch 224、染色归一化 | 全切片图像巨大，需先切片；染色差异要处理 |
## 遥感、农业与地球观测

| # | 论文 | 年份/会议 | 主要数据集（规模） | 典型预处理 | 给用户的提示 |
|---|---|---|---|---|---|
| 158 | DOTA: A Large-scale Dataset for Object Detection in Aerial Images | 2018 / CVPR | DOTA / LEVIR-CD / LoveDA / fMoW；2,806 / 637 / 5,987 / 100 万 | 裁剪 256–1024、旋转、多光谱 | 大幅面、旋转框、多光谱；注意地理和季节差异 |
| 159 | xView: Objects in Context in Overhead Imagery | 2018 / CVPR | DOTA / LEVIR-CD / LoveDA / fMoW；2,806 / 637 / 5,987 / 100 万 | 裁剪 256–1024、旋转、多光谱 | 大幅面、旋转框、多光谱；注意地理和季节差异 |
| 160 | LoveDA: A Remote Sensing Land-Cover Dataset for Domain Adaptive Semantic Segmentation | 2021 / NeurIPS | DOTA / LEVIR-CD / LoveDA / fMoW；2,806 / 637 / 5,987 / 100 万 | 裁剪 256–1024、旋转、多光谱 | 大幅面、旋转框、多光谱；注意地理和季节差异 |
| 161 | Remote Sensing Image Change Detection with Transformers | 2021 / IEEE TGRS | DOTA / LEVIR-CD / LoveDA / fMoW；2,806 / 637 / 5,987 / 100 万 | 裁剪 256–1024、旋转、多光谱 | 大幅面、旋转框、多光谱；注意地理和季节差异 |
| 162 | A Transformer-Based Siamese Network for Change Detection | 2022 / IGARSS | DOTA / LEVIR-CD / LoveDA / fMoW；2,806 / 637 / 5,987 / 100 万 | 裁剪 256–1024、旋转、多光谱 | 大幅面、旋转框、多光谱；注意地理和季节差异 |
| 163 | SatMAE: Pre-training Transformers for Temporal and Multi-Spectral Satellite Imagery | 2022 / NeurIPS | DOTA / LEVIR-CD / LoveDA / fMoW；2,806 / 637 / 5,987 / 100 万 | 裁剪 256–1024、旋转、多光谱 | 大幅面、旋转框、多光谱；注意地理和季节差异 |
| 164 | Scale-MAE: A Scale-Aware Masked Autoencoder for Multiscale Geospatial Representation Learning | 2023 / ICCV | DOTA / LEVIR-CD / LoveDA / fMoW；2,806 / 637 / 5,987 / 100 万 | 裁剪 256–1024、旋转、多光谱 | 大幅面、旋转框、多光谱；注意地理和季节差异 |
| 165 | RingMo: A Remote Sensing Foundation Model with Masked Image Modeling | 2023 / CVPR | DOTA / LEVIR-CD / LoveDA / fMoW；2,806 / 637 / 5,987 / 100 万 | 裁剪 256–1024、旋转、多光谱 | 大幅面、旋转框、多光谱；注意地理和季节差异 |
| 166 | SkySense: A Multi-Modal Remote Sensing Foundation Model Towards Universal Interpretation for Earth Observation Imagery | 2024 / CVPR | DOTA / LEVIR-CD / LoveDA / fMoW；2,806 / 637 / 5,987 / 100 万 | 裁剪 256–1024、旋转、多光谱 | 大幅面、旋转框、多光谱；注意地理和季节差异 |
## 工业、文档与其他应用

| # | 论文 | 年份/会议 | 主要数据集（规模） | 典型预处理 | 给用户的提示 |
|---|---|---|---|---|---|
| 167 | An End-to-End Trainable Neural Network for Image-Based Sequence Recognition and Its Application to Scene Text Recognition | 2017 / IEEE TPAMI | IIIT5K / SVT / IC13 / IC15 / SynthText；数千–2 千 / 80 万 | 灰度或彩色、resize 32×100–640、归一化 | 弯曲、模糊、低分辨率文字需要专门增强 |
| 168 | Real-Time Scene Text Detection with Differentiable Binarization | 2020 / AAAI | IIIT5K / SVT / IC13 / IC15 / SynthText；数千–2 千 / 80 万 | 灰度或彩色、resize 32×100–640、归一化 | 弯曲、模糊、低分辨率文字需要专门增强 |
| 169 | TrOCR: Transformer-based Optical Character Recognition with Pre-trained Models | 2021 / AAAI | IIIT5K / SVT / IC13 / IC15 / SynthText；数千–2 千 / 80 万 | 灰度或彩色、resize 32×100–640、归一化 | 弯曲、模糊、低分辨率文字需要专门增强 |
| 170 | LayoutLM: Pre-training of Text and Layout for Document Image Understanding | 2020 / KDD | FUNSD / CORD / SROIE / PubLayNet；数百 / 1 千 / 1 千 / 36 万 | OCR token + 版面框、resize | 版式多样，需要 OCR 或文档解析前置 |
| 171 | LayoutLMv3: Pre-training for Document AI with Unified Text and Image Masking | 2022 / ACM MM | FUNSD / CORD / SROIE / PubLayNet；数百 / 1 千 / 1 千 / 36 万 | OCR token + 版面框、resize | 版式多样，需要 OCR 或文档解析前置 |
| 172 | OCR-free Document Understanding Transformer | 2022 / ECCV | FUNSD / CORD / SROIE / PubLayNet；数百 / 1 千 / 1 千 / 36 万 | OCR token + 版面框、resize | 版式多样，需要 OCR 或文档解析前置 |
| 173 | PubTables-1M: Towards Comprehensive Table Extraction from Unstructured Documents | 2022 / ECCV | FUNSD / CORD / SROIE / PubLayNet；数百 / 1 千 / 1 千 / 36 万 | OCR token + 版面框、resize | 版式多样，需要 OCR 或文档解析前置 |
| 174 | MVTec AD: A Comprehensive Real-World Dataset for Unsupervised Anomaly Detection | 2019 / CVPR | MVTec AD / VisA；5,354 / 1 万图，15/12 类 | resize 256–512、归一化 | 异常样本少，按无监督或少样本设定做 |
| 175 | Towards Total Recall in Industrial Anomaly Detection | 2022 / CVPR | MVTec AD / VisA；5,354 / 1 万图，15/12 类 | resize 256–512、归一化 | 异常样本少，按无监督或少样本设定做 |
| 176 | EfficientAD: Accurate Visual Anomaly Detection at Millisecond-Level Latencies | 2023 / WACV | MVTec AD / VisA；5,354 / 1 万图，15/12 类 | resize 256–512、归一化 | 异常样本少，按无监督或少样本设定做 |
## 高效计算与部署

| # | 论文 | 年份/会议 | 主要数据集（规模） | 典型预处理 | 给用户的提示 |
|---|---|---|---|---|---|
| 177 | SqueezeNet: AlexNet-level Accuracy with 50x Fewer Parameters and <0.5MB Model Size | 2017 / ICLR | ImageNet-1K / CIFAR-10；128 万 / 5 万 | 224 裁剪、AutoAugment、归一化 | 先定延迟、功耗、内存预算，再选模型 |
| 178 | MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications | 2017 / CVPR | ImageNet-1K / CIFAR-10；128 万 / 5 万 | 224 裁剪、AutoAugment、归一化 | 先定延迟、功耗、内存预算，再选模型 |
| 179 | MobileNetV2: Inverted Residuals and Linear Bottlenecks | 2018 / CVPR | ImageNet-1K / CIFAR-10；128 万 / 5 万 | 224 裁剪、AutoAugment、归一化 | 先定延迟、功耗、内存预算，再选模型 |
| 180 | Searching for MobileNetV3 | 2019 / ICCV | ImageNet-1K / CIFAR-10；128 万 / 5 万 | 224 裁剪、AutoAugment、归一化 | 先定延迟、功耗、内存预算，再选模型 |
| 181 | ShuffleNet V2: Practical Guidelines for Efficient CNN Architecture Design | 2018 / ECCV | ImageNet-1K / CIFAR-10；128 万 / 5 万 | 224 裁剪、AutoAugment、归一化 | 先定延迟、功耗、内存预算，再选模型 |
| 182 | EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks | 2019 / ICML | ImageNet-1K / CIFAR-10；128 万 / 5 万 | 224 裁剪、AutoAugment、归一化 | 先定延迟、功耗、内存预算，再选模型 |
| 183 | Deep Compression: Compressing Deep Neural Networks with Pruning, Trained Quantization and Huffman Coding | 2016 / ICLR | ImageNet-1K / CIFAR-10；128 万 / 5 万 | 224 裁剪、AutoAugment、归一化 | 先定延迟、功耗、内存预算，再选模型 |
| 184 | The Lottery Ticket Hypothesis: Finding Sparse, Trainable Neural Networks | 2019 / ICLR | ImageNet-1K / CIFAR-10；128 万 / 5 万 | 224 裁剪、AutoAugment、归一化 | 先定延迟、功耗、内存预算，再选模型 |
| 185 | Quantization and Training of Neural Networks for Efficient Integer-Arithmetic-Only Inference | 2018 / CVPR | ImageNet-1K / CIFAR-10；128 万 / 5 万 | 224 裁剪、AutoAugment、归一化 | 先定延迟、功耗、内存预算，再选模型 |
| 186 | DARTS: Differentiable Architecture Search | 2019 / ICLR | ImageNet-1K / CIFAR-10；128 万 / 5 万 | 224 裁剪、AutoAugment、归一化 | 先定延迟、功耗、内存预算，再选模型 |
| 187 | BranchyNet: Fast Inference via Early Exiting from Deep Neural Networks | 2016 / ECCV | ImageNet-1K / CIFAR-10；128 万 / 5 万 | 224 裁剪、AutoAugment、归一化 | 先定延迟、功耗、内存预算，再选模型 |
## 鲁棒性、安全与可信

| # | 论文 | 年份/会议 | 主要数据集（规模） | 典型预处理 | 给用户的提示 |
|---|---|---|---|---|---|
| 188 | Explaining and Harnessing Adversarial Examples | 2015 / ICLR | CIFAR-10 / ImageNet；5 万 / 128 万 | 标准增强、对抗扰动/投毒 | 先明确威胁模型：白盒/黑盒、攻击目标 |
| 189 | Towards Deep Learning Models Resistant to Adversarial Attacks | 2018 / ICLR | CIFAR-10 / ImageNet；5 万 / 128 万 | 标准增强、对抗扰动/投毒 | 先明确威胁模型：白盒/黑盒、攻击目标 |
| 190 | Theoretically Principled Trade-off between Robustness and Accuracy | 2019 / ICML | CIFAR-10 / ImageNet；5 万 / 128 万 | 标准增强、对抗扰动/投毒 | 先明确威胁模型：白盒/黑盒、攻击目标 |
| 191 | BadNets: Identifying Vulnerabilities in the Machine Learning Model Supply Chain | 2017 / arXiv | CIFAR-10 / ImageNet；5 万 / 128 万 | 标准增强、对抗扰动/投毒 | 先明确威胁模型：白盒/黑盒、攻击目标 |
| 192 | Neural Cleanse: Identifying and Mitigating Backdoor Attacks in Neural Networks | 2019 / IEEE S&P | CIFAR-10 / ImageNet；5 万 / 128 万 | 标准增强、对抗扰动/投毒 | 先明确威胁模型：白盒/黑盒、攻击目标 |
| 193 | Membership Inference Attacks Against Machine Learning Models | 2017 / IEEE S&P | CIFAR-10 / ImageNet；5 万 / 128 万 | 标准增强、对抗扰动/投毒 | 先明确威胁模型：白盒/黑盒、攻击目标 |
| 194 | Machine Unlearning | 2021 / IEEE S&P | CIFAR-10 / ImageNet；5 万 / 128 万 | 标准增强、对抗扰动/投毒 | 先明确威胁模型：白盒/黑盒、攻击目标 |
| 195 | Grad-CAM: Visual Explanations from Deep Networks via Gradient-Based Localization | 2017 / ICCV | ImageNet / PASCAL VOC；128 万 / 1.65 万 | resize 224、梯度钩子/扰动采样 | 解释结果需人工核验，不能直接当因果证据 |
| 196 | "Why Should I Trust You?": Explaining the Predictions of Any Classifier | 2016 / KDD | ImageNet / PASCAL VOC；128 万 / 1.65 万 | resize 224、梯度钩子/扰动采样 | 解释结果需人工核验，不能直接当因果证据 |
| 197 | A Unified Approach to Interpreting Model Predictions | 2017 / NeurIPS | ImageNet / PASCAL VOC；128 万 / 1.65 万 | resize 224、梯度钩子/扰动采样 | 解释结果需人工核验，不能直接当因果证据 |
| 198 | Enhancing the Reliability of Out-of-Distribution Image Detection in Neural Networks | 2018 / ICLR | CIFAR-10 / ImageNet；5 万 / 128 万 | 标准增强、对抗扰动/投毒 | 先明确威胁模型：白盒/黑盒、攻击目标 |
| 199 | Energy-based Out-of-Distribution Detection | 2020 / NeurIPS | CIFAR-10 / ImageNet；5 万 / 128 万 | 标准增强、对抗扰动/投毒 | 先明确威胁模型：白盒/黑盒、攻击目标 |
| 200 | On Calibration of Modern Neural Networks | 2017 / ICML | CIFAR-10 / ImageNet；5 万 / 128 万 | 标准增强、对抗扰动/投毒 | 先明确威胁模型：白盒/黑盒、攻击目标 |
| 201 | Does Object Recognition Work for Everyone? | 2019 / CVPRW | ImageNet / PASCAL VOC；128 万 / 1.65 万 | resize 224、梯度钩子/扰动采样 | 解释结果需人工核验，不能直接当因果证据 |
| 202 | Towards Universal Fake Image Detectors that Generalize Across Generative Models | 2023 / CVPR | ProGAN / StyleGAN / LAION 生成图；约 72 万生成图 | resize 224、JPEG 增强 | 需覆盖多种生成器，跨生成器泛化难 |
## 数据集、基准与评测

| # | 论文 | 年份/会议 | 主要数据集（规模） | 典型预处理 | 给用户的提示 |
|---|---|---|---|---|---|
| 203 | ImageNet: A Large-Scale Hierarchical Image Database | 2009 / CVPR | 各数据集原始协议；规模见数据集官网 | 按原始划分和评测协议 | 注意评测协议、划分和许可，避免和训练集重叠 |
| 204 | Microsoft COCO: Common Objects in Context | 2014 / ECCV | 各数据集原始协议；规模见数据集官网 | 按原始划分和评测协议 | 注意评测协议、划分和许可，避免和训练集重叠 |
| 205 | Visual Genome: Connecting Language and Vision Using Crowdsourced Dense Image Annotations | 2017 / IJCV | 各数据集原始协议；规模见数据集官网 | 按原始划分和评测协议 | 注意评测协议、划分和许可，避免和训练集重叠 |
| 206 | Making the V in VQA Matter: Elevating the Role of Image Understanding in Visual Question Answering | 2017 / CVPR | 各数据集原始协议；规模见数据集官网 | 按原始划分和评测协议 | 注意评测协议、划分和许可，避免和训练集重叠 |
| 207 | LVIS: A Dataset for Large Vocabulary Instance Segmentation | 2019 / CVPR | 各数据集原始协议；规模见数据集官网 | 按原始划分和评测协议 | 注意评测协议、划分和许可，避免和训练集重叠 |
| 208 | Objects365: A Large-Scale, High-Quality Dataset for Object Detection | 2019 / ICCV | 各数据集原始协议；规模见数据集官网 | 按原始划分和评测协议 | 注意评测协议、划分和许可，避免和训练集重叠 |
| 209 | The Cityscapes Dataset for Semantic Urban Scene Understanding | 2016 / CVPR | 各数据集原始协议；规模见数据集官网 | 按原始划分和评测协议 | 注意评测协议、划分和许可，避免和训练集重叠 |
| 210 | nuScenes: A Multimodal Dataset for Autonomous Driving | 2020 / CVPR | 各数据集原始协议；规模见数据集官网 | 按原始划分和评测协议 | 注意评测协议、划分和许可，避免和训练集重叠 |
| 211 | Scalability in Perception for Autonomous Driving: Waymo Open Dataset | 2020 / CVPR | 各数据集原始协议；规模见数据集官网 | 按原始划分和评测协议 | 注意评测协议、划分和许可，避免和训练集重叠 |
| 212 | MMBench: Is Your Multi-modal Model an All-Around Player? | 2023 / NeurIPS | 各数据集原始协议；规模见数据集官网 | 按原始划分和评测协议 | 注意评测协议、划分和许可，避免和训练集重叠 |
| 213 | MME: A Comprehensive Evaluation Benchmark for Multimodal Large Language Models | 2023 / arXiv | 各数据集原始协议；规模见数据集官网 | 按原始划分和评测协议 | 注意评测协议、划分和许可，避免和训练集重叠 |
| 214 | SEED-Bench: Benchmarking Multimodal LLMs with Generative Comprehension | 2023 / ICCV | 各数据集原始协议；规模见数据集官网 | 按原始划分和评测协议 | 注意评测协议、划分和许可，避免和训练集重叠 |
| 215 | Video-MME: The First-Ever Comprehensive Evaluation Benchmark of Multi-modal LLMs in Video Analysis | 2024 / CVPR | 各数据集原始协议；规模见数据集官网 | 按原始划分和评测协议 | 注意评测协议、划分和许可，避免和训练集重叠 |
## 交叉与新兴方向

| # | 论文 | 年份/会议 | 主要数据集（规模） | 典型预处理 | 给用户的提示 |
|---|---|---|---|---|---|
| 216 | Recurrent World Models Facilitate Policy Evolution | 2018 / NeurIPS | 视频 / 仿真环境；数万–数百万帧 | resize 64–224、动作条件 | 长时预测误差累积，需滚动训练和评测 |
| 217 | Learning Transferable Visual Models From Natural Language Supervision | 2021 / ICML | WIT / ALIGN；4 亿–18 亿图文对 | resize 224、文本 tokenize、对比学习 | 图文对质量比数量更重要，噪声要清洗 |
| 218 | Flamingo: a Visual Language Model for Few-Shot Learning | 2022 / NeurIPS | M3W / ALIGN / LTIP；4,300 万交错图文 / 18 亿图文对 / 3.12 亿 | 交错图文、resize 224、Perceiver 重采样 | 需要交错图文数据，不是单图问答数据 |
| 219 | The Dawn of LMMs: Preliminary Explorations with GPT-4V(ision) | 2023 / arXiv | 未公开（网络级图文/视频）；未披露 | 未披露；API 仅提供输入输出 | 无法复现训练，只能做评测或提示工程 |
| 220 | DreamFusion: Text-to-3D using 2D Diffusion | 2023 / ICLR | Objaverse；约 80 万 3D 物体 | 多视角渲染、相机采样、文本/图像条件 | 3D 数据稀缺，常用合成渲染补充 |
| 221 | Generative Interactive Environments | 2024 / ICML | 网络视频（约 3 万小时）；约 3 万小时视频 | 抽帧、resize、动作条件 | 需要大量视频和交互标注 |
| 222 | π0: A Vision-Language-Action Flow Model for General Robot Control | 2024 / arXiv | Open X-Embodiment / RT-1 / ALOHA；97 万 episode / 13 万 episode / 数千 demo | 图像 224、动作 token/chunk | 真机数据贵，先用仿真或公开数据，再做少量真机微调 |
| 223 | Cosmos World Foundation Model Platform for Physical AI | 2025 / arXiv | 网络视频 / 仿真（约 2,000 万小时）；约 2,000 万小时视频 | 抽帧、resize、视频 tokenize | 世界基础模型需要海量视频和算力 |

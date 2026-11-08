# Task Map / 白话任务映射速查表

Use the Chinese cue or the English cue to find the closest CV task. 编号对应 `CV_Topics_2016-2025.md`。

## 1. Single-task mapping / 单任务映射

| 中文说法 / Chinese cue | English cue | CV 任务 / CV task | 主题编号 / Topics | 代表论文 / Key papers | 必须追问 / Follow-up |
|---|---|---|---|---|---|
| 看一张图判断是什么、有没有病、合不合格 | Look at an image and tell what it is, whether it is diseased or defective | 图像分类 / Image classification | 1, 245, 267 | AlexNet, ResNet, ViT, EfficientNet | Whole-image answer or location? 只要整图结论，还是要位置？ |
| 把东西框出来、数一数、找出在哪 | Box objects, count them, or find where they are | 目标检测 / Object detection | 18, 20, 26 | Faster R-CNN, YOLO, RetinaNet, DETR | Small, dense, rotated, or 3D? 小目标/密集/旋转/3D？ |
| 把物体轮廓、每个像素勾出来 | Outline objects or segment every pixel | 语义/实例分割 / Semantic & instance segmentation | 41, 42, 43 | FCN, U-Net, Mask R-CNN, Mask2Former, SAM | Need individual instances? 要不要分个体？ |
| 视频里一直跟住某个人/所有目标 | Track one target or all targets in a video | 单/多目标跟踪 / Single & multi-object tracking | 65, 66 | SORT, DeepSORT, ByteTrack, OSTrack | Single or multi-target? 单目标还是多目标？ |
| 判断视频里的人在做什么 | Recognize what people are doing in a video | 动作识别/时序定位 / Action recognition & temporal localization | 69, 70, 71 | I3D, SlowFast, TimeSformer | Whole clip or start/end time? 整段还是起止时间？ |
| 从照片/视频还原三维形状、测距离 | Reconstruct 3D shape or measure distance from images or video | 3D重建/深度估计 / 3D reconstruction & depth estimation | 107, 113, 115, 117, 118 | COLMAP, NeRF, 3DGS, DUSt3R, VGGT | Static or dynamic, accuracy, real-time? 静态/动态、精度、实时？ |
| 用文字生成图/视频/3D | Generate images, video, or 3D from text | 生成模型 / Generative models | 122, 136, 141, 149 | DDPM, Latent Diffusion, ControlNet, DiT | Controllability, copyright, resolution? 可控性、版权、分辨率？ |
| 看图回答问题、读文档、读屏幕 | Answer questions about images, read documents or screens | VLM/文档理解 / VLM & document understanding | 164, 173, 174 | CLIP, BLIP-2, LLaVA, LayoutLM | Need precise coordinates or structured output? 要不要精确坐标/结构化输出？ |
| 让机器人按指令抓取、移动 | Let a robot grasp or move on command | VLA/具身智能 / VLA & embodied AI | 233, 234, 235 | RT-2, OpenVLA, Diffusion Policy | Simulation or real robot? Safety? 仿真还是真机、安全？ |
| 找出不正常、缺陷、异常 | Find anomalies, defects, or abnormal cases | 异常/OOD检测 / Anomaly & OOD detection | 35, 36, 267 | MVTec AD, PatchCore, EfficientAD | Many normal samples? What do anomalies look like? 正常样本多不多、异常形态？ |
| 比较两张图/两个时期有什么变化 | Compare two images or two time periods for changes | 变化检测 / Change detection | 258 | BIT, ChangeFormer | Registration, seasonal or lighting differences? 配准、季节/光照差异？ |
| 识别身份、人脸、步态 | Identify people by face, iris, or gait | 人脸/生物特征 / Face & biometrics | 86, 97 | FaceNet, ArcFace, GaitSet | Privacy, liveness, cross-camera? 隐私、活体、跨摄像头？ |
| 从医学影像勾病灶、辅助诊断 | Segment lesions or assist diagnosis from medical images | 医学分割/分类 / Medical segmentation & classification | 245, 248, 252 | U-Net, nnU-Net, MedSAM, UNI | Annotation, compliance, explainability? 标注、合规、可解释？ |
| 从卫星图找建筑/船/变化 | Find buildings, ships, or changes in satellite imagery | 遥感检测/分割 / Remote sensing detection & segmentation | 256, 257, 258 | DOTA, LoveDA, SkySense | Rotated boxes, large images, multispectral? 旋转框、大幅面、多光谱？ |
| 在工业流水线挑次品 | Pick defective products on an assembly line | 工业质检 / Industrial inspection | 267 | MVTec AD, PatchCore, EfficientAD | Few-shot, real-time, cost of misses? 少样本、实时、漏检成本？ |
| 把图片变清晰、去噪、去雾、超分 | Make images clearer: denoise, dehaze, super-resolve | 低层视觉/复原 / Low-level vision & restoration | 211, 213, 215, 216 | SRCNN, ESRGAN, Restormer, SwinIR | Real or synthetic degradation? 真实退化还是合成退化？ |
| 把模型塞进手机/摄像头 | Deploy the model on a phone or camera | 高效计算/部署 / Efficient models & deployment | 280, 281, 283 | MobileNet, EfficientNet, quantization, distillation | Latency, power, memory? 延迟、功耗、内存？ |
| 让模型更安全、防攻击、可解释 | Make the model safer, robust, or explainable | 可信视觉 / Trustworthy vision | 291, 297, 300 | FGSM, PGD, Grad-CAM, ODIN | Threat model, compliance? 威胁模型、合规要求？ |
| 把不同摄像头拍到的人/车串起来 | Link the same person or vehicle across cameras | ReID/多目标跟踪 / ReID & multi-object tracking | 68, 66 | ArcFace, ByteTrack | Cross-camera, appearance changes? 跨摄像头、外观变化？ |
| 从图片/视频里抠人物换背景 | Cut out people or objects and replace the background | 抠图/可提示分割 / Matting & promptable segmentation | 57, 62 | SAM, matting methods | Hair, transparency, real-time? 头发丝、透明、实时？ |
| 把老照片/模糊视频修好 | Restore old photos or blurry videos | 图像/视频复原 / Image & video restoration | 216, 232 | ESRGAN, Restormer | Authenticity, historical material? 真实性、历史资料？ |
| 自动读发票/表格/合同 | Read invoices, tables, or contracts automatically | 文档AI / Document AI | 173, 270 | LayoutLM, LayoutLMv3, Donut, Table Transformer | Layout variety, field structure? 版式多样、字段结构？ |
| 识别街牌/商品包装上的字 | Read text on signs or product packaging | OCR/场景文字 / OCR & scene text | 174, 271 | CRNN, DBNet, TrOCR | Curved, blurry, multilingual? 弯曲、模糊、多语言？ |
| 数人群、统计客流 | Count crowds or foot traffic | 人群计数 / Crowd counting | 278 | Crowd-counting methods (search recent papers) | Dense, perspective, occlusion? 密集、透视、遮挡？ |
| 判断照片好不好看、构图 | Judge image aesthetics or composition | 图像美学评价 / Image aesthetics assessment | 275 | NIMA | Subjectivity, business criteria? 主观性、业务标准？ |
| 给图片打标签、搜相似图 | Tag images or search for similar images | 图文检索/表征学习 / Retrieval & representation learning | 159, 163, 192 | CLIP, DINOv2, BLIP | Fine-grained, cross-modal? 细粒度、跨模态？ |
| 把二维图变成三维模型/数字孪生 | Turn 2D images into 3D models or digital twins | 3D生成/重建 / 3D generation & reconstruction | 113, 122, 123 | DreamFusion, LRM, 3DGS, VGGT | Accuracy, texture, scale? 精度、纹理、规模？ |
| 让虚拟人说话、驱动表情 | Make a virtual human talk or show expressions | 说话头/数字人 / Talking head & avatar | 152, 153 | Talking-head methods (search by scenario) | Identity preservation, real-time? 身份保持、实时？ |
| 预测接下来会发生什么 | Predict what will happen next | 视频预测/世界模型 / Video prediction & world models | 78, 150 | World Models, Dreamer | Uncertainty, action conditioning? 不确定性、动作条件？ |
| 在长视频里找某个片段 | Find a moment in a long video | 视频时刻检索 / Moment retrieval | 75 | Moment-retrieval methods (search current papers) | Long video, language query? 长视频、语言描述？ |

## 2. Compound-task decomposition / 复合任务拆解

| 用户描述 / User says | 拆解 / Decompose | 对应主题 / Topics |
|---|---|---|
| 自动发现工人没戴安全帽 / Detect workers without helmets | 检测人 + 检测安全帽 + 跟踪 + 规则判断 / Detect person + detect helmet + track + rule check | 18, 20, 66 |
| 统计进店人数和停留时间 / Count visitors and dwell time | 检测人 + 多目标跟踪 + 区域计数 / Detect person + multi-object tracking + zone counting | 18, 66, 278 |
| 从监控里找“某个人出现在哪” / Find where a person appeared | 人脸/行人 ReID + 多摄像头检索 / Face or person ReID + cross-camera retrieval | 68, 86 |
| 自动测量零件尺寸 / Measure part dimensions | 分割/关键点 + 相机标定 + 几何测量 / Segmentation or keypoints + calibration + geometry | 41, 109 |
| 把纸质表格录入系统 / Digitize paper forms | 文字检测 + OCR + 表格结构识别 / Text detection + OCR + table structure | 174, 270 |
| 根据病历影像出诊断报告 / Generate a report from medical images | 医学分割/分类 + 医学 VLM / Medical segmentation or classification + medical VLM | 245, 252 |
| 机器人按语音指令拿东西 / Robot fetches an object by voice command | 语音识别 + 目标检测/分割 + VLA / Speech recognition + detection or segmentation + VLA | 233, 234 |
| 生成商品的三维展示 / Generate a 3D product showcase | 三维重建/生成 + 材质/渲染 / 3D reconstruction or generation + material and rendering | 113, 120, 122 |
| 找出视频里的异常行为 / Detect abnormal behavior in video | 检测/跟踪 + 动作识别 + 异常检测 / Detection + tracking + action recognition + anomaly detection | 18, 66, 69, 35 |

## 3. Data traits → method choice / 数据特征 → 方法选择

| 数据特征 / Data trait | 优先考虑 / Prefer | 要提醒 / Warn |
|---|---|---|
| 标注很少（几十到几百）/ Very few labels (tens to hundreds) | 预训练模型微调、小样本学习、自监督、基础模型 / Fine-tune pretrained models, few-shot, self-supervised, foundation models | 先做零样本/少样本基线，再决定是否扩标 / Start with a zero/few-shot baseline before labeling more |
| 完全没有标注 / No labels at all | 异常检测、无监督、自监督、聚类 / Anomaly detection, unsupervised, self-supervised, clustering | 监督学习不可行，需要定义“正常” / Supervised learning is not possible; define “normal” first |
| 类别极不均衡 / Highly imbalanced classes | 重采样、重加权、Focal Loss、长尾方法 / Resampling, reweighting, Focal Loss, long-tail methods | 稀有类别可能被整体忽略 / Rare classes may be ignored entirely |
| 图像巨大（遥感/病理）/ Very large images (remote sensing, pathology) | 切片推理、多尺度、稀疏注意力 / Tiling, multi-scale, sparse attention | 直接缩图会丢小目标 / Resizing the whole image loses small objects |
| 视频很长 / Very long videos | 稀疏采样、片段检索、记忆机制 / Sparse sampling, clip retrieval, memory | 不能逐帧跑大模型 / Do not run a large model on every frame |
| 3D/点云 / 3D or point cloud | PointNet 系、体素/柱状编码、多视图 / PointNet family, voxel or pillar encoding, multi-view | 数据格式和坐标系要先统一 / Unify formats and coordinate systems first |
| 多传感器 / Multiple sensors | 多传感器融合、BEV / Sensor fusion, BEV | 时间同步和标定是前提 / Time sync and calibration are prerequisites |
| 隐私敏感（医疗/人脸）/ Privacy-sensitive (medical, face) | 联邦学习、差分隐私、本地部署 / Federated learning, differential privacy, on-device deployment | 合规和伦理审查要提前做 / Compliance and ethics review must come first |
| 需要实时 / Real-time required | 轻量网络、量化、蒸馏、早退 / Lightweight models, quantization, distillation, early exit | 精度和速度要明确取舍 / Make the accuracy-speed trade-off explicit |
| 跨场景/跨设备 / Cross-site or cross-device | 域适应、域泛化、数据增强 / Domain adaptation, domain generalization, augmentation | 在一个场景验证不代表能上线 / One-site validation does not guarantee deployment |
| 异常样本极少 / Very few anomaly samples | 无监督异常检测、少样本 / Unsupervised anomaly detection, few-shot | 不要把它当普通分类做 / Do not treat it as ordinary classification |
| 需要可解释 / Explainability required | 热力图、概念解释、可解释模型 / Heatmaps, concept explanations, interpretable models | 高风险场景必须人工复核 / High-risk scenarios need human review |

## 4. Search keywords / 检索关键词

- **Task**: classification, detection, segmentation, tracking, pose, depth, reconstruction, generation, retrieval, captioning, VQA, anomaly detection, change detection, OCR, ReID.
- **Data**: few-shot, long-tailed, open-vocabulary, domain adaptation, domain generalization, weakly-supervised, semi-supervised, self-supervised, synthetic data.
- **Constraint**: real-time, efficient, lightweight, edge, privacy, federated, explainable, robust.
- **Domain**: medical, remote sensing, industrial inspection, autonomous driving, robotics, document, agriculture.

## 5. Usage reminders / 使用提醒

- Match input/output first, then method. 先匹配“输入/输出”，再匹配“方法”。
- When the user says “recognize”, ask whether they mean whole-image classification, localization, or pixel-level segmentation. 用户说“识别”时，追问是整图分类、找位置，还是逐像素分割。
- When the user says “detect”, ask whether they mean 2D boxes, 3D boxes, or anomaly points. 用户说“检测”时，追问是 2D 框、3D 框，还是异常点。
- When the user says “segment”, ask whether individual instances and pixel-level boundaries matter. 用户说“分割”时，追问要不要区分个体、要不要像素级边界。
- If no exact match exists, recommend the nearest task plus transferable methods, and state the gap. 找不到完全匹配时，推荐“最近邻任务 + 可迁移方法”，并说明差距。

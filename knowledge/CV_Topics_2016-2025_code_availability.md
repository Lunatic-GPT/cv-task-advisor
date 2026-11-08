# 参考论文开源代码核对表（223 篇）

**核对日期**：2026-11-08

**核对范围**：`CV_Topics_2016-2025_references.md` 中全部 223 篇论文。

**配套文件**：数据集规模与预处理见 [CV_Topics_2016-2025_data_profiles.md](CV_Topics_2016-2025_data_profiles.md)。

**核对方式**：先按论文作者/机构整理官方仓库，再用 GitHub API 批量核对仓库是否存在；重定向到新地址的已更新；非 GitHub 项目（HuggingFace、官网）单独标注。

## 统计

| 代码状态 | 数量 | 含义 |
|---|---|---|
| 官方开源 | 165 | 作者/机构发布，通常有训练或推理代码 |
| 第三方复现 | 14 | 原论文未发布官方代码，社区有可用实现 |
| 仅数据集/评测 | 13 | 只开放数据、标注或评测工具，不是模型代码 |
| 未开源 | 13 | 未找到官方或可信的公开实现 |
| 待核实 | 18 | 可能有代码，但本次未确认到明确仓库 |
| **合计** | **223** | |

## 重要说明

- **“官方开源”不等于“开箱即用”**：不少是研究代码，依赖旧版框架、需要申请数据或模型权重，部分仓库长期不维护。
- **明确未开源的代表**：Imagen、DALL-E 2、Flamingo、PaLM-E、RT-2、Sora、GPT-4V、Magic3D、Genie 等只有论文或技术报告。
- **数据集类论文只提供数据与评测工具**，不提供模型代码，例如 ImageNet、COCO、Cityscapes、nuScenes、MVTec AD。
- **第三方复现**不是作者发布，复现质量参差不齐；用于生产前要自行验证。
- 仓库存在性已核对，但“是否官方”按作者/机构判断；引用前建议再看一眼仓库 README 的 license、issue 和维护状态。
- 统计口径中，“官方开源”包含 GitHub、作者主页和 HuggingFace 模型页；“仅数据集/评测”不计入模型代码。


## 图像分类与识别

| # | 论文 | 年份/会议 | 代码状态 | 仓库/链接 | 备注 |
|---|---|---|---|---|---|
| 1 | ImageNet Classification with Deep Convolutional Neural Networks | 2012 / NeurIPS | 第三方复现 | - | 原始 cuda-convnet 已归档，无现代官方仓库 |
| 2 | Deep Residual Learning for Image Recognition | 2016 / CVPR | 官方开源 | [KaimingHe/deep-residual-networks](https://github.com/KaimingHe/deep-residual-networks) | - |
| 3 | Densely Connected Convolutional Networks | 2017 / CVPR | 官方开源 | [liuzhuang13/DenseNet](https://github.com/liuzhuang13/DenseNet) | - |
| 4 | Squeeze-and-Excitation Networks | 2018 / CVPR | 官方开源 | [hujie-frank/SENet](https://github.com/hujie-frank/SENet) | - |
| 5 | Model-Agnostic Meta-Learning for Fast Adaptation of Deep Networks | 2017 / ICML | 官方开源 | [cbfinn/maml](https://github.com/cbfinn/maml) | - |
| 6 | Prototypical Networks for Few-shot Learning | 2017 / NeurIPS | 官方开源 | [jakesnell/prototypical-networks](https://github.com/jakesnell/prototypical-networks) | - |
| 7 | An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale | 2021 / ICLR | 官方开源 | [google-research/vision_transformer](https://github.com/google-research/vision_transformer) | - |
| 8 | Swin Transformer: Hierarchical Vision Transformer using Shifted Windows | 2021 / ICCV | 官方开源 | [microsoft/Swin-Transformer](https://github.com/microsoft/Swin-Transformer) | - |
| 9 | A ConvNet for the 2020s | 2022 / CVPR | 官方开源 | [facebookresearch/ConvNeXt](https://github.com/facebookresearch/ConvNeXt) | - |
| 10 | Learning Transferable Visual Models From Natural Language Supervision | 2021 / ICML | 官方开源 | [openai/CLIP](https://github.com/openai/CLIP) | - |

## 目标检测

| # | 论文 | 年份/会议 | 代码状态 | 仓库/链接 | 备注 |
|---|---|---|---|---|---|
| 11 | Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks | 2015 / NeurIPS | 官方开源 | [ShaoqingRen/faster_rcnn](https://github.com/ShaoqingRen/faster_rcnn) | MATLAB 官方实现 |
| 12 | You Only Look Once: Unified, Real-Time Object Detection | 2016 / CVPR | 官方开源 | [pjreddie/darknet](https://github.com/pjreddie/darknet) | - |
| 13 | SSD: Single Shot MultiBox Detector | 2016 / ECCV | 官方开源 | [weiliu89/caffe](https://github.com/weiliu89/caffe) | SSD 分支 |
| 14 | Focal Loss for Dense Object Detection | 2017 / ICCV | 官方开源 | [facebookresearch/Detectron](https://github.com/facebookresearch/Detectron) | - |
| 15 | Cascade R-CNN: Delving into High Quality Object Detection | 2018 / CVPR | 官方开源 | [zhaoweicai/cascade-rcnn](https://github.com/zhaoweicai/cascade-rcnn) | - |
| 16 | FCOS: Fully Convolutional One-Stage Object Detection | 2019 / ICCV | 官方开源 | [tianzhi0549/FCOS](https://github.com/tianzhi0549/FCOS) | - |
| 17 | End-to-End Object Detection with Transformers | 2020 / ECCV | 官方开源 | [facebookresearch/detr](https://github.com/facebookresearch/detr) | - |
| 18 | Deformable DETR: Deformable Transformers for End-to-End Object Detection | 2021 / ICLR | 官方开源 | [fundamentalvision/Deformable-DETR](https://github.com/fundamentalvision/Deformable-DETR) | - |
| 19 | YOLOX: Exceeding YOLO Series in 2021 | 2021 / CVPR | 官方开源 | [Megvii-BaseDetection/YOLOX](https://github.com/Megvii-BaseDetection/YOLOX) | - |
| 20 | DINO: DETR with Improved DeNoising Anchor Boxes for End-to-End Object Detection | 2023 / ICLR | 官方开源 | [IDEA-Research/DINO](https://github.com/IDEA-Research/DINO) | - |
| 21 | Simple Open-Vocabulary Object Detection with Vision Transformers | 2022 / ECCV | 官方开源 | [google-research/scenic](https://github.com/google-research/scenic) | OWL-ViT 在 Scenic 中 |
| 22 | Grounding DINO: Marrying DINO with Grounded Pre-Training for Open-Set Object Detection | 2024 / ECCV | 官方开源 | [IDEA-Research/GroundingDINO](https://github.com/IDEA-Research/GroundingDINO) | - |
| 23 | VoxelNet: End-to-End Learning for Point Cloud Based 3D Object Detection | 2018 / CVPR | 第三方复现 | [tsinghua-rll/VoxelNet-tensorflow](https://github.com/tsinghua-rll/VoxelNet-tensorflow) | 社区 TensorFlow 复现 |
| 24 | PointPillars: Fast Encoders for Object Detection from Point Clouds | 2019 / CVPR | 官方开源 | [nutonomy/second.pytorch](https://github.com/nutonomy/second.pytorch) | - |
| 25 | CenterPoint: Center-based 3D Object Detection and Tracking | 2021 / CVPR | 官方开源 | [tianweiy/CenterPoint](https://github.com/tianweiy/CenterPoint) | - |
| 26 | BEVFormer: Learning Bird's-Eye-View Representation from Multi-Camera Images via Spatiotemporal Transformers | 2022 / ECCV | 官方开源 | [fundamentalvision/BEVFormer](https://github.com/fundamentalvision/BEVFormer) | - |

## 图像分割

| # | 论文 | 年份/会议 | 代码状态 | 仓库/链接 | 备注 |
|---|---|---|---|---|---|
| 27 | Fully Convolutional Networks for Semantic Segmentation | 2015 / CVPR | 官方开源 | [shelhamer/fcn.berkeleyvision.org](https://github.com/shelhamer/fcn.berkeleyvision.org) | - |
| 28 | U-Net: Convolutional Networks for Biomedical Image Segmentation | 2015 / MICCAI | 第三方复现 | [milesial/Pytorch-UNet](https://github.com/milesial/Pytorch-UNet) | 原论文未发布官方代码 |
| 29 | Encoder-Decoder with Atrous Separable Convolution for Semantic Image Segmentation | 2018 / ECCV | 官方开源 | [tensorflow/models](https://github.com/tensorflow/models) | research/deeplab |
| 30 | Mask R-CNN | 2017 / ICCV | 官方开源 | [facebookresearch/detectron2](https://github.com/facebookresearch/detectron2) | - |
| 31 | Panoptic Feature Pyramid Networks | 2019 / CVPR | 官方开源 | [facebookresearch/detectron2](https://github.com/facebookresearch/detectron2) | - |
| 32 | PointRend: Image Segmentation as Rendering | 2020 / CVPR | 官方开源 | [facebookresearch/detectron2](https://github.com/facebookresearch/detectron2) | - |
| 33 | SegFormer: Simple and Efficient Design for Semantic Segmentation with Transformers | 2021 / NeurIPS | 官方开源 | [NVlabs/SegFormer](https://github.com/NVlabs/SegFormer) | - |
| 34 | Masked-attention Mask Transformer for Universal Image Segmentation | 2022 / CVPR | 官方开源 | [facebookresearch/Mask2Former](https://github.com/facebookresearch/Mask2Former) | - |
| 35 | Segment Anything | 2023 / ICCV | 官方开源 | [facebookresearch/segment-anything](https://github.com/facebookresearch/segment-anything) | - |
| 36 | SAM 2: Segment Anything in Images and Videos | 2024 / arXiv | 官方开源 | [facebookresearch/sam2](https://github.com/facebookresearch/sam2) | - |
| 37 | nnU-Net: a self-configuring method for deep learning-based biomedical image segmentation | 2021 / Nature Methods | 官方开源 | [MIC-DKFZ/nnUNet](https://github.com/MIC-DKFZ/nnUNet) | - |

## 跟踪与视频理解

| # | 论文 | 年份/会议 | 代码状态 | 仓库/链接 | 备注 |
|---|---|---|---|---|---|
| 38 | Simple Online and Realtime Tracking | 2016 / ICIP | 官方开源 | [abewley/sort](https://github.com/abewley/sort) | - |
| 39 | Simple Online and Realtime Tracking with a Deep Association Metric | 2017 / ICIP | 官方开源 | [nwojke/deep_sort](https://github.com/nwojke/deep_sort) | - |
| 40 | ByteTrack: Multi-Object Tracking by Associating Every Detection Box | 2022 / ECCV | 官方开源 | [FoundationVision/ByteTrack](https://github.com/FoundationVision/ByteTrack) | - |
| 41 | Observation-Centric SORT: Rethinking SORT for Robust Multi-Object Tracking | 2023 / CVPR | 官方开源 | [noahcao/OC_SORT](https://github.com/noahcao/OC_SORT) | - |
| 42 | Fully-Convolutional Siamese Networks for Object Tracking | 2016 / ECCV | 官方开源 | [bertinetto/siamese-fc](https://github.com/bertinetto/siamese-fc) | - |
| 43 | SiamRPN++: Evolution of Siamese Visual Tracking with Very Deep Networks | 2019 / CVPR | 官方开源 | [STVIR/pysot](https://github.com/STVIR/pysot) | - |
| 44 | Joint Feature Learning and Relation Modeling for Tracking: A One-Stream Framework | 2022 / ECCV | 官方开源 | [botaoye/OSTrack](https://github.com/botaoye/OSTrack) | - |
| 45 | Quo Vadis, Action Recognition? A New Model and the Kinetics Dataset | 2017 / CVPR | 官方开源 | [google-deepmind/kinetics-i3d](https://github.com/google-deepmind/kinetics-i3d) | - |
| 46 | SlowFast Networks for Video Recognition | 2019 / ICCV | 官方开源 | [facebookresearch/SlowFast](https://github.com/facebookresearch/SlowFast) | - |
| 47 | Is Space-Time Attention All You Need for Video Understanding? | 2021 / ICML | 官方开源 | [facebookresearch/TimeSformer](https://github.com/facebookresearch/TimeSformer) | - |
| 48 | VideoMAE: Masked Autoencoders are Data-Efficient Learners for Self-Supervised Video Pre-Training | 2022 / NeurIPS | 官方开源 | [MCG-NJU/VideoMAE](https://github.com/MCG-NJU/VideoMAE) | - |
| 49 | Video Swin Transformer | 2022 / CVPR | 官方开源 | [SwinTransformer/Video-Swin-Transformer](https://github.com/SwinTransformer/Video-Swin-Transformer) | - |
| 50 | Video Diffusion Models | 2022 / NeurIPS | 未开源 | - | Google 未发布代码 |
| 51 | Video Generation Models as World Simulators | 2024 / arXiv | 未开源 | - | 技术报告，无代码 |

## 人脸、人体与生物特征

| # | 论文 | 年份/会议 | 代码状态 | 仓库/链接 | 备注 |
|---|---|---|---|---|---|
| 52 | FaceNet: A Unified Embedding for Face Recognition and Clustering | 2015 / CVPR | 第三方复现 | [davidsandberg/facenet](https://github.com/davidsandberg/facenet) | 原论文未发布官方代码 |
| 53 | CosFace: Large Margin Cosine Loss for Deep Face Recognition | 2018 / CVPR | 待核实 | - | 官方代码未确认 |
| 54 | ArcFace: Additive Angular Margin Loss for Deep Face Recognition | 2019 / CVPR | 官方开源 | [deepinsight/insightface](https://github.com/deepinsight/insightface) | - |
| 55 | RetinaFace: Single-stage Dense Face Localisation in the Wild | 2020 / CVPR | 官方开源 | [deepinsight/insightface](https://github.com/deepinsight/insightface) | - |
| 56 | DECA: Detailed Expression Capture and Animation | 2021 / ICCV | 官方开源 | [yfeng95/DECA](https://github.com/yfeng95/DECA) | - |
| 57 | A Style-Based Generator Architecture for Generative Adversarial Networks | 2019 / CVPR | 官方开源 | [NVlabs/stylegan](https://github.com/NVlabs/stylegan) | - |
| 58 | Analyzing and Improving the Image Quality of StyleGAN | 2020 / CVPR | 官方开源 | [NVlabs/stylegan2](https://github.com/NVlabs/stylegan2) | - |
| 59 | FaceForensics++: Learning to Detect Manipulated Facial Images | 2019 / ICCV | 官方开源 | [ondyari/FaceForensics](https://github.com/ondyari/FaceForensics) | - |
| 60 | Realtime Multi-Person 2D Pose Estimation using Part Affinity Fields | 2017 / CVPR | 官方开源 | [CMU-Perceptual-Computing-Lab/openpose](https://github.com/CMU-Perceptual-Computing-Lab/openpose) | - |
| 61 | Deep High-Resolution Representation Learning for Visual Recognition | 2019 / CVPR | 官方开源 | [HRNet/HRNet-Human-Pose-Estimation](https://github.com/HRNet/HRNet-Human-Pose-Estimation) | - |
| 62 | ViTPose: Simple Vision Transformer Baselines for Human Pose Estimation | 2022 / NeurIPS | 官方开源 | [ViTAE-Transformer/ViTPose](https://github.com/ViTAE-Transformer/ViTPose) | - |
| 63 | SMPL: A Skinned Multi-Person Linear Model | 2015 / SIGGRAPH | 官方开源 | [官网](https://smpl.is.tue.mpg.de/) | 官网申请模型与代码 |
| 64 | Expressive Body Capture: 3D Hands, Face, and Body from a Single Image | 2019 / CVPR | 官方开源 | [vchoutas/smplx](https://github.com/vchoutas/smplx) | - |
| 65 | GaitSet: Regarding Gait as a Set for Cross-View Gait Recognition | 2019 / AAAI | 官方开源 | [AbnerHqC/GaitSet](https://github.com/AbnerHqC/GaitSet) | - |

## 3D视觉与几何

| # | 论文 | 年份/会议 | 代码状态 | 仓库/链接 | 备注 |
|---|---|---|---|---|---|
| 66 | Structure-from-Motion Revisited | 2016 / CVPR | 官方开源 | [colmap/colmap](https://github.com/colmap/colmap) | - |
| 67 | MVSNet: Depth Inference for Unstructured Multi-view Stereo | 2018 / ECCV | 官方开源 | [YoYo000/MVSNet](https://github.com/YoYo000/MVSNet) | - |
| 68 | PointNet: Deep Learning on Point Sets for 3D Classification and Segmentation | 2017 / CVPR | 官方开源 | [charlesq34/pointnet](https://github.com/charlesq34/pointnet) | - |
| 69 | PointNet++: Deep Hierarchical Feature Learning on Point Sets in a Metric Space | 2017 / NeurIPS | 官方开源 | [charlesq34/pointnet2](https://github.com/charlesq34/pointnet2) | - |
| 70 | Occupancy Networks: Learning 3D Reconstruction in Function Space | 2019 / CVPR | 官方开源 | [autonomousvision/occupancy_networks](https://github.com/autonomousvision/occupancy_networks) | - |
| 71 | NeRF: Representing Scenes as Neural Radiance Fields for View Synthesis | 2020 / ECCV | 官方开源 | [bmild/nerf](https://github.com/bmild/nerf) | - |
| 72 | Mip-NeRF: A Multiscale Representation for Anti-Aliasing Neural Radiance Fields | 2021 / ICCV | 官方开源 | [google/mipnerf](https://github.com/google/mipnerf) | - |
| 73 | Instant Neural Graphics Primitives with a Multiresolution Hash Encoding | 2022 / SIGGRAPH | 官方开源 | [NVlabs/instant-ngp](https://github.com/NVlabs/instant-ngp) | - |
| 74 | 3D Gaussian Splatting for Real-Time Radiance Field Rendering | 2023 / SIGGRAPH | 官方开源 | [graphdeco-inria/gaussian-splatting](https://github.com/graphdeco-inria/gaussian-splatting) | - |
| 75 | DreamFusion: Text-to-3D using 2D Diffusion | 2023 / ICLR | 第三方复现 | [ashawkey/stable-dreamfusion](https://github.com/ashawkey/stable-dreamfusion) | Google 未开源，社区复现 |
| 76 | Magic3D: High-Resolution Text-to-3D Content Creation | 2023 / CVPR | 未开源 | - | NVIDIA 未发布代码 |
| 77 | LRM: Large Reconstruction Model for Single Image to 3D | 2023 / ICCV | 待核实 | - | 官方代码未确认 |
| 78 | DUSt3R: Geometric 3D Vision Made Easy | 2024 / CVPR | 官方开源 | [naver/dust3r](https://github.com/naver/dust3r) | - |
| 79 | VGGT: Visual Geometry Grounded Transformer | 2025 / CVPR | 官方开源 | [facebookresearch/vggt](https://github.com/facebookresearch/vggt) | - |

## 生成模型

| # | 论文 | 年份/会议 | 代码状态 | 仓库/链接 | 备注 |
|---|---|---|---|---|---|
| 80 | Generative Adversarial Networks | 2014 / NeurIPS | 官方开源 | [goodfeli/adversarial](https://github.com/goodfeli/adversarial) | 历史 Theano 实现 |
| 81 | Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks | 2016 / ICLR | 官方开源 | [Newmu/dcgan_code](https://github.com/Newmu/dcgan_code) | - |
| 82 | Wasserstein Generative Adversarial Networks | 2017 / NeurIPS | 官方开源 | [martinarjovsky/WassersteinGAN](https://github.com/martinarjovsky/WassersteinGAN) | - |
| 83 | Auto-Encoding Variational Bayes | 2014 / ICLR | 第三方复现 | - | 原始代码未在 GitHub 发布 |
| 84 | Denoising Diffusion Probabilistic Models | 2020 / NeurIPS | 官方开源 | [hojonathanho/diffusion](https://github.com/hojonathanho/diffusion) | - |
| 85 | Denoising Diffusion Implicit Models | 2021 / ICLR | 官方开源 | [ermongroup/ddim](https://github.com/ermongroup/ddim) | - |
| 86 | High-Resolution Image Synthesis with Latent Diffusion Models | 2022 / CVPR | 官方开源 | [CompVis/latent-diffusion](https://github.com/CompVis/latent-diffusion) | - |
| 87 | Photorealistic Text-to-Image Diffusion Models with Deep Language Understanding | 2022 / NeurIPS | 未开源 | - | Google 未发布代码 |
| 88 | Hierarchical Text-Conditional Image Generation with CLIP Latents | 2022 / NeurIPS | 未开源 | - | OpenAI 未发布代码 |
| 89 | Adding Conditional Control to Text-to-Image Diffusion Models | 2023 / ICCV | 官方开源 | [lllyasviel/ControlNet](https://github.com/lllyasviel/ControlNet) | - |
| 90 | DreamBooth: Fine Tuning Text-to-Image Diffusion Models for Subject-Driven Generation | 2023 / CVPR | 第三方复现 | [XavierXiao/Dreambooth-Stable-Diffusion](https://github.com/XavierXiao/Dreambooth-Stable-Diffusion) | Google 未开源，社区复现 |
| 91 | LoRA: Low-Rank Adaptation of Large Language Models | 2022 / ICLR | 官方开源 | [microsoft/LoRA](https://github.com/microsoft/LoRA) | - |
| 92 | Scalable Diffusion Models with Transformers | 2023 / ICCV | 官方开源 | [facebookresearch/DiT](https://github.com/facebookresearch/DiT) | - |
| 93 | Flow Matching for Generative Modeling | 2023 / ICLR | 官方开源 | [facebookresearch/flow_matching](https://github.com/facebookresearch/flow_matching) | - |

## 视觉-语言与多模态

| # | 论文 | 年份/会议 | 代码状态 | 仓库/链接 | 备注 |
|---|---|---|---|---|---|
| 94 | Show and Tell: A Neural Image Caption Generator | 2015 / CVPR | 官方开源 | [tensorflow/models](https://github.com/tensorflow/models) | research/im2txt |
| 95 | Show, Attend and Tell: Neural Image Caption Generation with Visual Attention | 2015 / ICML | 官方开源 | [kelvinxu/arctic-captions](https://github.com/kelvinxu/arctic-captions) | - |
| 96 | VQA: Visual Question Answering | 2015 / ICCV | 仅数据集/评测 | [官网](https://visualqa.org/) | 数据集与评测服务 |
| 97 | Bottom-Up and Top-Down Attention for Image Captioning and Visual Question Answering | 2018 / CVPR | 官方开源 | [peteanderson80/bottom-up-attention](https://github.com/peteanderson80/bottom-up-attention) | - |
| 98 | ViLBERT: Pretraining Task-Agnostic Visiolinguistic Representations for Vision-and-Language Tasks | 2019 / NeurIPS | 官方开源 | [facebookresearch/vilbert-multi-task](https://github.com/facebookresearch/vilbert-multi-task) | - |
| 99 | LXMERT: Learning Cross-Modality Encoder Representations from Transformers | 2019 / EMNLP | 官方开源 | [airsplay/lxmert](https://github.com/airsplay/lxmert) | - |
| 100 | UNITER: UNiversal Image-TExt Representation Learning | 2020 / ECCV | 官方开源 | [microsoft/unilm](https://github.com/microsoft/unilm) | uniter 目录 |
| 101 | Scaling Up Visual and Vision-Language Representation Learning With Noisy Text Supervision | 2021 / ICML | 未开源 | - | Google 未发布代码 |
| 102 | BLIP: Bootstrapping Language-Image Pre-training for Unified Vision-Language Understanding and Generation | 2022 / CVPR | 官方开源 | [salesforce/BLIP](https://github.com/salesforce/BLIP) | - |
| 103 | BLIP-2: Bootstrapping Language-Image Pre-training with Frozen Image Encoders and Large Language Models | 2023 / ICML | 官方开源 | [salesforce/LAVIS](https://github.com/salesforce/LAVIS) | - |
| 104 | Flamingo: a Visual Language Model for Few-Shot Learning | 2022 / NeurIPS | 未开源 | - | DeepMind 未发布代码 |
| 105 | Visual Instruction Tuning | 2023 / NeurIPS | 官方开源 | [haotian-liu/LLaVA](https://github.com/haotian-liu/LLaVA) | - |
| 106 | MiniGPT-4: Enhancing Vision-Language Understanding with Advanced Large Language Models | 2023 / ICML | 官方开源 | [Vision-CAIR/MiniGPT-4](https://github.com/Vision-CAIR/MiniGPT-4) | - |
| 107 | InstructBLIP: Towards General-purpose Vision-Language Models with Instruction Tuning | 2023 / NeurIPS | 官方开源 | [salesforce/LAVIS](https://github.com/salesforce/LAVIS) | - |
| 108 | Grounded Language-Image Pre-training | 2022 / CVPR | 官方开源 | [microsoft/GLIP](https://github.com/microsoft/GLIP) | - |

## 自监督与基础模型

| # | 论文 | 年份/会议 | 代码状态 | 仓库/链接 | 备注 |
|---|---|---|---|---|---|
| 109 | A Simple Framework for Contrastive Learning of Visual Representations | 2020 / ICML | 官方开源 | [google-research/simclr](https://github.com/google-research/simclr) | - |
| 110 | Momentum Contrast for Unsupervised Visual Representation Learning | 2020 / CVPR | 官方开源 | [facebookresearch/moco](https://github.com/facebookresearch/moco) | - |
| 111 | Bootstrap Your Own Latent: A New Approach to Self-Supervised Learning | 2020 / NeurIPS | 官方开源 | [google-deepmind/deepmind-research](https://github.com/google-deepmind/deepmind-research) | byol 目录 |
| 112 | Unsupervised Learning of Visual Features by Contrasting Cluster Assignments | 2020 / NeurIPS | 官方开源 | [facebookresearch/swav](https://github.com/facebookresearch/swav) | - |
| 113 | Emerging Properties in Self-Supervised Vision Transformers | 2021 / ICCV | 官方开源 | [facebookresearch/dino](https://github.com/facebookresearch/dino) | - |
| 114 | DINOv2: Learning Robust Visual Features without Supervision | 2024 / TMLR | 官方开源 | [facebookresearch/dinov2](https://github.com/facebookresearch/dinov2) | - |
| 115 | Masked Autoencoders Are Scalable Vision Learners | 2022 / CVPR | 官方开源 | [facebookresearch/mae](https://github.com/facebookresearch/mae) | - |
| 116 | BEiT: BERT Pre-Training of Image Transformers | 2022 / ICLR | 官方开源 | [microsoft/unilm](https://github.com/microsoft/unilm) | beit 目录 |
| 117 | Mamba: Linear-Time Sequence Modeling with Selective State Spaces | 2024 / COLM | 官方开源 | [state-spaces/mamba](https://github.com/state-spaces/mamba) | - |
| 118 | Vision Mamba: Efficient Visual Representation Learning with Bidirectional State Space Model | 2024 / ICML | 官方开源 | [hustvl/Vim](https://github.com/hustvl/Vim) | - |

## 低层视觉与图像复原

| # | 论文 | 年份/会议 | 代码状态 | 仓库/链接 | 备注 |
|---|---|---|---|---|---|
| 119 | Learning a Deep Convolutional Network for Image Super-Resolution | 2014 / ECCV | 官方开源 | [官网](https://mmlab.ie.cuhk.edu.hk/projects/SRCNN.html) | 作者主页提供 MATLAB 代码 |
| 120 | Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network | 2017 / CVPR | 第三方复现 | [tensorlayer/SRGAN](https://github.com/tensorlayer/SRGAN) | 原始代码未在 GitHub 发布 |
| 121 | ESRGAN: Enhanced Super-Resolution Generative Adversarial Networks | 2018 / ECCV | 官方开源 | [xinntao/ESRGAN](https://github.com/xinntao/ESRGAN) | - |
| 122 | Beyond a Gaussian Denoiser: Residual Learning of Deep CNN for Image Denoising | 2017 / IEEE TIP | 官方开源 | [cszn/DnCNN](https://github.com/cszn/DnCNN) | MATLAB 官方实现 |
| 123 | SwinIR: Image Restoration Using Swin Transformer | 2021 / ICCV | 官方开源 | [JingyunLiang/SwinIR](https://github.com/JingyunLiang/SwinIR) | - |
| 124 | Real-ESRGAN: Training Real-World Blind Super-Resolution with Pure Synthetic Data | 2021 / ICCV | 官方开源 | [xinntao/Real-ESRGAN](https://github.com/xinntao/Real-ESRGAN) | - |
| 125 | Restormer: Efficient Transformer for High-Resolution Image Restoration | 2022 / CVPR | 官方开源 | [swz30/Restormer](https://github.com/swz30/Restormer) | - |
| 126 | Simple Baselines for Image Restoration | 2022 / ECCV | 官方开源 | [megvii-research/NAFNet](https://github.com/megvii-research/NAFNet) | - |
| 127 | Deep Bilateral Learning for Real-Time Image Enhancement | 2017 / SIGGRAPH | 官方开源 | [google/hdrnet](https://github.com/google/hdrnet) | - |
| 128 | End-to-End Optimized Image Compression | 2017 / ICLR | 官方开源 | [tensorflow/compression](https://github.com/tensorflow/compression) | - |
| 129 | High-Fidelity Generative Image Compression | 2020 / NeurIPS | 官方开源 | [tensorflow/compression](https://github.com/tensorflow/compression) | hific 目录 |
| 130 | NIMA: Neural Image Assessment | 2018 / IEEE TIP | 第三方复现 | [idealo/image-quality-assessment](https://github.com/idealo/image-quality-assessment) | 社区复现 |
| 131 | All-in-One Network for Dehazing and Beyond | 2017 / ICCV | 待核实 | - | 官方代码未确认 |
| 132 | FFA-Net: Feature Fusion Attention Network for Single Image Dehazing | 2020 / AAAI | 官方开源 | [zhilin007/FFA-Net](https://github.com/zhilin007/FFA-Net) | - |
| 133 | Multi-Stage Progressive Image Restoration | 2021 / CVPR | 官方开源 | [swz30/MPRNet](https://github.com/swz30/MPRNet) | - |

## 具身智能、机器人与自动驾驶

| # | 论文 | 年份/会议 | 代码状态 | 仓库/链接 | 备注 |
|---|---|---|---|---|---|
| 134 | Domain Randomization for Transferring Deep Neural Networks from Simulation to the Real World | 2018 / ICLR | 待核实 | - | 官方代码未确认 |
| 135 | Do As I Can, Not As I Say: Grounding Language in Robotic Affordances | 2022 / CoRL | 官方开源 | [google-research/google-research](https://github.com/google-research/google-research) | saycan 目录 |
| 136 | PaLM-E: An Embodied Multimodal Language Model | 2023 / ICML | 未开源 | - | Google 未发布代码 |
| 137 | RT-1: Robotics Transformer for Real-World Control at Scale | 2023 / RSS | 官方开源 | [google-research/robotics_transformer](https://github.com/google-research/robotics_transformer) | - |
| 138 | RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control | 2023 / CoRL | 未开源 | - | Google 未发布代码 |
| 139 | Diffusion Policy: Visuomotor Policy Learning via Action Diffusion | 2023 / RSS | 官方开源 | [real-stanford/diffusion_policy](https://github.com/real-stanford/diffusion_policy) | - |
| 140 | Learning Fine-Grained Bimanual Manipulation with Low-Cost Hardware | 2023 / RSS | 官方开源 | [tonyzhaozh/aloha](https://github.com/tonyzhaozh/aloha) | - |
| 141 | OpenVLA: An Open-Source Vision-Language-Action Model | 2024 / CoRL | 官方开源 | [openvla/openvla](https://github.com/openvla/openvla) | - |
| 142 | TransFuser: Imitation with Transformer-Based Sensor Fusion for Autonomous Driving | 2021 / CVPR | 官方开源 | [autonomousvision/transfuser](https://github.com/autonomousvision/transfuser) | - |
| 143 | Planning-oriented Autonomous Driving | 2023 / CVPR | 官方开源 | [OpenDriveLab/UniAD](https://github.com/OpenDriveLab/UniAD) | - |
| 144 | VAD: Vectorized Scene Representation for Efficient Autonomous Driving | 2023 / ICCV | 官方开源 | [hustvl/VAD](https://github.com/hustvl/VAD) | - |
| 145 | Dream to Control: Learning Behaviors by Latent Imagination | 2020 / ICLR | 官方开源 | [danijar/dreamer](https://github.com/danijar/dreamer) | - |
| 146 | Navigation World Models | 2025 / CVPR | 待核实 | - | 官方代码未确认 |
| 147 | π0: A Vision-Language-Action Flow Model for General Robot Control | 2024 / arXiv | 官方开源 | [Physical-Intelligence/openpi](https://github.com/Physical-Intelligence/openpi) | - |

## 医学与生物视觉

| # | 论文 | 年份/会议 | 代码状态 | 仓库/链接 | 备注 |
|---|---|---|---|---|---|
| 148 | V-Net: Fully Convolutional Neural Networks for Volumetric Medical Image Segmentation | 2016 / 3DV | 第三方复现 | [mattmacy/vnet.pytorch](https://github.com/mattmacy/vnet.pytorch) | 原论文未发布官方代码 |
| 149 | nnU-Net: a self-configuring method for deep learning-based biomedical image segmentation | 2021 / Nature Methods | 官方开源 | [MIC-DKFZ/nnUNet](https://github.com/MIC-DKFZ/nnUNet) | - |
| 150 | TransUNet: Transformers Make Strong Encoders for Medical Image Segmentation | 2021 / arXiv | 官方开源 | [Beckschen/TransUNet](https://github.com/Beckschen/TransUNet) | - |
| 151 | Self-Supervised Pre-Training of Swin Transformers for 3D Medical Image Analysis | 2022 / CVPR | 官方开源 | [Project-MONAI/MONAI](https://github.com/Project-MONAI/MONAI) | Swin UNETR 在 MONAI 中 |
| 152 | Segment Anything in Medical Images | 2024 / Nature Communications | 官方开源 | [bowang-lab/MedSAM](https://github.com/bowang-lab/MedSAM) | - |
| 153 | CheXNet: Radiologist-Level Pneumonia Detection on Chest X-Rays with Deep Learning | 2017 / CVPR | 第三方复现 | [arnoweng/CheXNet](https://github.com/arnoweng/CheXNet) | 社区复现 |
| 154 | MedCLIP: Contrastive Learning from Unpaired Medical Images and Text | 2022 / EMNLP | 官方开源 | [RyanWangZf/MedCLIP](https://github.com/RyanWangZf/MedCLIP) | - |
| 155 | BiomedCLIP: a multimodal biomedical foundation model pretrained on fifteen million images | 2023 / NEJM AI | 官方开源 | [HuggingFace](https://huggingface.co/microsoft/BiomedCLIP-PubMedBERT_256-vit_base_patch16_224) | HuggingFace 模型 |
| 156 | Towards a General-Purpose Foundation Model for Computational Pathology | 2024 / Nature Medicine | 官方开源 | [mahmoodlab/UNI](https://github.com/mahmoodlab/UNI) | - |
| 157 | A foundation model for clinical-grade computational pathology and rare cancers detection | 2024 / Nature Medicine | 官方开源 | [HuggingFace](https://huggingface.co/paige-ai/Virchow) | HuggingFace 模型 |

## 遥感、农业与地球观测

| # | 论文 | 年份/会议 | 代码状态 | 仓库/链接 | 备注 |
|---|---|---|---|---|---|
| 158 | DOTA: A Large-scale Dataset for Object Detection in Aerial Images | 2018 / CVPR | 仅数据集/评测 | [官网](https://captain-whu.github.io/DOTA/) | 数据集与工具包 |
| 159 | xView: Objects in Context in Overhead Imagery | 2018 / CVPR | 仅数据集/评测 | [官网](https://xviewdataset.org/) | 数据集 |
| 160 | LoveDA: A Remote Sensing Land-Cover Dataset for Domain Adaptive Semantic Segmentation | 2021 / NeurIPS | 官方开源 | [Junjue-Wang/LoveDA](https://github.com/Junjue-Wang/LoveDA) | - |
| 161 | Remote Sensing Image Change Detection with Transformers | 2021 / IEEE TGRS | 官方开源 | [justchenhao/BIT_CD](https://github.com/justchenhao/BIT_CD) | - |
| 162 | A Transformer-Based Siamese Network for Change Detection | 2022 / IGARSS | 官方开源 | [wgcban/ChangeFormer](https://github.com/wgcban/ChangeFormer) | - |
| 163 | SatMAE: Pre-training Transformers for Temporal and Multi-Spectral Satellite Imagery | 2022 / NeurIPS | 官方开源 | [sustainlab-group/SatMAE](https://github.com/sustainlab-group/SatMAE) | - |
| 164 | Scale-MAE: A Scale-Aware Masked Autoencoder for Multiscale Geospatial Representation Learning | 2023 / ICCV | 官方开源 | [bair-climate-initiative/scale-mae](https://github.com/bair-climate-initiative/scale-mae) | - |
| 165 | RingMo: A Remote Sensing Foundation Model with Masked Image Modeling | 2023 / CVPR | 待核实 | - | 官方代码未确认 |
| 166 | SkySense: A Multi-Modal Remote Sensing Foundation Model Towards Universal Interpretation for Earth Observation Imagery | 2024 / CVPR | 待核实 | - | 官方代码未确认 |

## 工业、文档与其他应用

| # | 论文 | 年份/会议 | 代码状态 | 仓库/链接 | 备注 |
|---|---|---|---|---|---|
| 167 | An End-to-End Trainable Neural Network for Image-Based Sequence Recognition and Its Application to Scene Text Recognition | 2017 / IEEE TPAMI | 官方开源 | [bgshih/crnn](https://github.com/bgshih/crnn) | - |
| 168 | Real-Time Scene Text Detection with Differentiable Binarization | 2020 / AAAI | 官方开源 | [MhLiao/DB](https://github.com/MhLiao/DB) | - |
| 169 | TrOCR: Transformer-based Optical Character Recognition with Pre-trained Models | 2021 / AAAI | 官方开源 | [microsoft/unilm](https://github.com/microsoft/unilm) | trocr 目录 |
| 170 | LayoutLM: Pre-training of Text and Layout for Document Image Understanding | 2020 / KDD | 官方开源 | [microsoft/unilm](https://github.com/microsoft/unilm) | layoutlm 目录 |
| 171 | LayoutLMv3: Pre-training for Document AI with Unified Text and Image Masking | 2022 / ACM MM | 官方开源 | [microsoft/unilm](https://github.com/microsoft/unilm) | layoutlmv3 目录 |
| 172 | OCR-free Document Understanding Transformer | 2022 / ECCV | 官方开源 | [clovaai/donut](https://github.com/clovaai/donut) | - |
| 173 | PubTables-1M: Towards Comprehensive Table Extraction from Unstructured Documents | 2022 / ECCV | 官方开源 | [microsoft/table-transformer](https://github.com/microsoft/table-transformer) | - |
| 174 | MVTec AD: A Comprehensive Real-World Dataset for Unsupervised Anomaly Detection | 2019 / CVPR | 仅数据集/评测 | [官网](https://www.mvtec.com/company/research/datasets/mvtec-ad) | 数据集与评测 |
| 175 | Towards Total Recall in Industrial Anomaly Detection | 2022 / CVPR | 官方开源 | [amazon-science/patchcore-inspection](https://github.com/amazon-science/patchcore-inspection) | - |
| 176 | EfficientAD: Accurate Visual Anomaly Detection at Millisecond-Level Latencies | 2023 / WACV | 官方开源 | [nelson1425/EfficientAD](https://github.com/nelson1425/EfficientAD) | - |

## 高效计算与部署

| # | 论文 | 年份/会议 | 代码状态 | 仓库/链接 | 备注 |
|---|---|---|---|---|---|
| 177 | SqueezeNet: AlexNet-level Accuracy with 50x Fewer Parameters and <0.5MB Model Size | 2017 / ICLR | 官方开源 | [forresti/SqueezeNet](https://github.com/forresti/SqueezeNet) | - |
| 178 | MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications | 2017 / CVPR | 官方开源 | [tensorflow/models](https://github.com/tensorflow/models) | - |
| 179 | MobileNetV2: Inverted Residuals and Linear Bottlenecks | 2018 / CVPR | 官方开源 | [tensorflow/models](https://github.com/tensorflow/models) | - |
| 180 | Searching for MobileNetV3 | 2019 / ICCV | 官方开源 | [tensorflow/models](https://github.com/tensorflow/models) | - |
| 181 | ShuffleNet V2: Practical Guidelines for Efficient CNN Architecture Design | 2018 / ECCV | 第三方复现 | [ericsun99/Shufflenet-v2-Pytorch](https://github.com/ericsun99/Shufflenet-v2-Pytorch) | 官方 Caffe 代码未确认 |
| 182 | EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks | 2019 / ICML | 官方开源 | [google/automl](https://github.com/google/automl) | efficientnet 目录 |
| 183 | Deep Compression: Compressing Deep Neural Networks with Pruning, Trained Quantization and Huffman Coding | 2016 / ICLR | 官方开源 | [songhan/Deep-Compression-AlexNet](https://github.com/songhan/Deep-Compression-AlexNet) | - |
| 184 | The Lottery Ticket Hypothesis: Finding Sparse, Trainable Neural Networks | 2019 / ICLR | 官方开源 | [google-research/lottery-ticket-hypothesis](https://github.com/google-research/lottery-ticket-hypothesis) | - |
| 185 | Quantization and Training of Neural Networks for Efficient Integer-Arithmetic-Only Inference | 2018 / CVPR | 待核实 | - | 实现分散在 TensorFlow 模型中 |
| 186 | DARTS: Differentiable Architecture Search | 2019 / ICLR | 官方开源 | [quark0/darts](https://github.com/quark0/darts) | - |
| 187 | BranchyNet: Fast Inference via Early Exiting from Deep Neural Networks | 2016 / ECCV | 待核实 | - | 官方代码未确认 |

## 鲁棒性、安全与可信

| # | 论文 | 年份/会议 | 代码状态 | 仓库/链接 | 备注 |
|---|---|---|---|---|---|
| 188 | Explaining and Harnessing Adversarial Examples | 2015 / ICLR | 第三方复现 | [gongzhitaao/tensorflow-adversarial](https://github.com/gongzhitaao/tensorflow-adversarial) | 原始代码未在 GitHub 发布 |
| 189 | Towards Deep Learning Models Resistant to Adversarial Attacks | 2018 / ICLR | 官方开源 | [MadryLab/cifar10_challenge](https://github.com/MadryLab/cifar10_challenge) | - |
| 190 | Theoretically Principled Trade-off between Robustness and Accuracy | 2019 / ICML | 官方开源 | [yaodongyu/TRADES](https://github.com/yaodongyu/TRADES) | - |
| 191 | BadNets: Identifying Vulnerabilities in the Machine Learning Model Supply Chain | 2017 / arXiv | 待核实 | - | 官方代码未确认 |
| 192 | Neural Cleanse: Identifying and Mitigating Backdoor Attacks in Neural Networks | 2019 / IEEE S&P | 官方开源 | [bolunwang/backdoor](https://github.com/bolunwang/backdoor) | - |
| 193 | Membership Inference Attacks Against Machine Learning Models | 2017 / IEEE S&P | 待核实 | - | 官方代码未确认 |
| 194 | Machine Unlearning | 2021 / IEEE S&P | 待核实 | - | 官方代码未确认 |
| 195 | Grad-CAM: Visual Explanations from Deep Networks via Gradient-Based Localization | 2017 / ICCV | 官方开源 | [ramprs/grad-cam](https://github.com/ramprs/grad-cam) | 原始 Torch 实现 |
| 196 | "Why Should I Trust You?": Explaining the Predictions of Any Classifier | 2016 / KDD | 官方开源 | [marcotcr/lime](https://github.com/marcotcr/lime) | - |
| 197 | A Unified Approach to Interpreting Model Predictions | 2017 / NeurIPS | 官方开源 | [shap/shap](https://github.com/shap/shap) | - |
| 198 | Enhancing the Reliability of Out-of-Distribution Image Detection in Neural Networks | 2018 / ICLR | 待核实 | - | 官方代码未确认 |
| 199 | Energy-based Out-of-Distribution Detection | 2020 / NeurIPS | 待核实 | - | 官方代码未确认 |
| 200 | On Calibration of Modern Neural Networks | 2017 / ICML | 待核实 | - | 官方代码未确认 |
| 201 | Does Object Recognition Work for Everyone? | 2019 / CVPRW | 未开源 | - | 分析型论文，无模型代码 |
| 202 | Towards Universal Fake Image Detectors that Generalize Across Generative Models | 2023 / CVPR | 官方开源 | [WisconsinAIVision/UniversalFakeDetect](https://github.com/WisconsinAIVision/UniversalFakeDetect) | - |

## 数据集、基准与评测

| # | 论文 | 年份/会议 | 代码状态 | 仓库/链接 | 备注 |
|---|---|---|---|---|---|
| 203 | ImageNet: A Large-Scale Hierarchical Image Database | 2009 / CVPR | 仅数据集/评测 | [官网](https://image-net.org/) | 数据集 |
| 204 | Microsoft COCO: Common Objects in Context | 2014 / ECCV | 仅数据集/评测 | [cocodataset/cocoapi](https://github.com/cocodataset/cocoapi) | 数据集与 API |
| 205 | Visual Genome: Connecting Language and Vision Using Crowdsourced Dense Image Annotations | 2017 / IJCV | 仅数据集/评测 | [官网](https://visualgenome.org/) | 数据集 |
| 206 | Making the V in VQA Matter: Elevating the Role of Image Understanding in Visual Question Answering | 2017 / CVPR | 仅数据集/评测 | [官网](https://visualqa.org/) | 数据集与评测 |
| 207 | LVIS: A Dataset for Large Vocabulary Instance Segmentation | 2019 / CVPR | 仅数据集/评测 | [官网](https://www.lvisdataset.org/) | 数据集 |
| 208 | Objects365: A Large-Scale, High-Quality Dataset for Object Detection | 2019 / ICCV | 仅数据集/评测 | [官网](https://www.objects365.org/) | 数据集 |
| 209 | The Cityscapes Dataset for Semantic Urban Scene Understanding | 2016 / CVPR | 仅数据集/评测 | [官网](https://www.cityscapes-dataset.com/) | 数据集 |
| 210 | nuScenes: A Multimodal Dataset for Autonomous Driving | 2020 / CVPR | 仅数据集/评测 | [官网](https://www.nuscenes.org/) | 数据集与工具包 |
| 211 | Scalability in Perception for Autonomous Driving: Waymo Open Dataset | 2020 / CVPR | 仅数据集/评测 | [官网](https://waymo.com/open/) | 数据集 |
| 212 | MMBench: Is Your Multi-modal Model an All-Around Player? | 2023 / NeurIPS | 官方开源 | [open-compass/MMBench](https://github.com/open-compass/MMBench) | - |
| 213 | MME: A Comprehensive Evaluation Benchmark for Multimodal Large Language Models | 2023 / arXiv | 待核实 | - | 官方评测代码未确认 |
| 214 | SEED-Bench: Benchmarking Multimodal LLMs with Generative Comprehension | 2023 / ICCV | 官方开源 | [AILab-CVC/SEED-Bench](https://github.com/AILab-CVC/SEED-Bench) | - |
| 215 | Video-MME: The First-Ever Comprehensive Evaluation Benchmark of Multi-modal LLMs in Video Analysis | 2024 / CVPR | 待核实 | - | 官方评测代码未确认 |

## 交叉与新兴方向

| # | 论文 | 年份/会议 | 代码状态 | 仓库/链接 | 备注 |
|---|---|---|---|---|---|
| 216 | Recurrent World Models Facilitate Policy Evolution | 2018 / NeurIPS | 官方开源 | [worldmodels/worldmodels.github.io](https://github.com/worldmodels/worldmodels.github.io) | - |
| 217 | Learning Transferable Visual Models From Natural Language Supervision | 2021 / ICML | 官方开源 | [openai/CLIP](https://github.com/openai/CLIP) | - |
| 218 | Flamingo: a Visual Language Model for Few-Shot Learning | 2022 / NeurIPS | 未开源 | - | DeepMind 未发布代码 |
| 219 | The Dawn of LMMs: Preliminary Explorations with GPT-4V(ision) | 2023 / arXiv | 未开源 | - | 技术报告，无代码 |
| 220 | DreamFusion: Text-to-3D using 2D Diffusion | 2023 / ICLR | 第三方复现 | [ashawkey/stable-dreamfusion](https://github.com/ashawkey/stable-dreamfusion) | Google 未开源，社区复现 |
| 221 | Generative Interactive Environments | 2024 / ICML | 未开源 | - | DeepMind 未开源 |
| 222 | π0: A Vision-Language-Action Flow Model for General Robot Control | 2024 / arXiv | 官方开源 | [Physical-Intelligence/openpi](https://github.com/Physical-Intelligence/openpi) | - |
| 223 | Cosmos World Foundation Model Platform for Physical AI | 2025 / arXiv | 待核实 | - | 官方代码未确认 |

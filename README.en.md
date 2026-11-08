# CV Task Advisor

[中文](README.md) | English

**A Claude Code skill that turns a plain-language computer vision task into a task map, classic papers, and a baseline plan. Bilingual: Chinese and English.**

You have a real problem you want to solve with deep learning and computer vision, but you do not know which CV task it is, which papers to read, or how much data you need. This skill interviews you in plain language, maps your problem to the closest CV task, and recommends 3–6 relevant papers with code availability, dataset scale, and preprocessing notes.

## What it does

Most CV survey tools ask you to choose a category first: classification, detection, segmentation, tracking. But business users usually only know:

- I have construction-site video and want to detect workers without helmets.
- I have photos of parts and want to find scratches.
- I have medical scans and want to outline lesions.
- I have satellite images and want to know where new buildings appeared.

This skill does not require you to know the jargon. It asks:

1. **What is your task?** In your own words, with a concrete example.
2. **What does your data look like?** Source, scale, labels, capture conditions, preprocessing.
3. **Who uses the result, what decision does it support, and what counts as success?**

It then restates your answers as a task card, waits for your confirmation, and only then retrieves papers.

## Quick start

### Option 1: Open this repository

Open the repository root in Claude Code. `.claude/skills/cv-task-advisor/` is loaded automatically.

```text
/cv-task-advisor
```

### Option 2: Copy into an existing project

```text
your-project/
├── .claude/
│   └── skills/
│       └── cv-task-advisor/
│           ├── SKILL.md
│           └── references/task-map.md
└── knowledge/
    └── CV_Topics_2016-2025_*.md
```

Copy `.claude/skills/cv-task-advisor/` into your project's `.claude/skills/`, and copy `knowledge/` to the project root or a `knowledge/` directory. The skill searches both locations.

You can also trigger it with natural language:

> I have a new computer vision task but I don't know which papers to reference.

## What the output looks like

```markdown
## Bottom line
Your task is closest to open-vocabulary object detection. Start with Grounding DINO, then compare with YOLO and DETR.

## 1. Your task (restated)
- Input: construction-site surveillance video, fixed camera, day and night
- Output: person and helmet boxes per frame, plus worn/not-worn status
- Used by: safety staff for alerts
- Success criteria: low miss rate, acceptable false alarms

## 2. Data profile
- Data type: extracted video frames
- Scale & labels: ~2,000 frames, box annotations planned
- Existing preprocessing: none
- Capture conditions: lighting changes, occlusion, small distant targets
- Privacy / real-time: real-time required, worker faces must be de-identified

### 2.1 Reference data conditions
| Paper | Primary dataset & scale | Typical preprocessing | Gap vs. your data |
|---|---|---|---|
| YOLO | COCO, 118K images | resize 800, flip, normalize | Your data is ~2 orders of magnitude smaller; fine-tune first |

## 3. Closest CV task
Primary: object detection (#18)
Auxiliary: multi-object tracking (#66)

## 4. Recommended papers
| Paper | Year/Venue | What it solves | Why it fits | What to borrow | Code |
|---|---|---|---|---|---|
| YOLO | 2016 / CVPR | Single-stage real-time detection | Real-time requirement | Single-stage design, augmentation | Official |
| DETR | 2020 / ECCV | End-to-end set prediction | Removes post-processing | Transformer detection head | Official |
| ByteTrack | 2022 / ECCV | Multi-object tracking | Reduces alert flicker | Low-score box association | Official |

## 5. Baseline plan
1. Extract frames at 1 fps and deduplicate.
2. Label 1,000–2,000 frames for person and helmet.
3. Fine-tune a COCO-pretrained YOLO.
4. Add tracking and a person-helmet association rule.
5. Evaluate miss rate, false-alarm rate, and latency.
```

## Workflow

| Phase | What happens |
|---|---|
| Phase 0 | Load the task map and knowledge base |
| Phase 1 | Plain-language task interview, one question at a time |
| Phase 2 | Plain-language data interview: scale, labels, capture conditions, preprocessing |
| Phase 3 | Restate a task card and wait for confirmation |
| Phase 4 | Map to one primary task plus 1–2 auxiliary tasks |
| Phase 5 | Retrieve 3–6 papers with code and data conditions |
| Phase 6 | Give a baseline plan, annotation advice, metrics, risks, and a one-week pilot |

## Knowledge base

The repository includes a curated CV knowledge base covering CVPR, ICCV, ECCV, ICML, NeurIPS, ICLR, and AAAI from 2016 to 2025:

| File | Content |
|---|---|
| `CV_Topics_2016-2025.md` | 334 CV topics with active years, trend, and primary venues |
| `CV_Topics_2016-2025_plain.md` | Plain-language explanations of all 334 topics |
| `CV_Topics_2016-2025_references.md` | 223 representative papers across 18 domains |
| `CV_Topics_2016-2025_code_availability.md` | Code status and repository links for all 223 papers |
| `CV_Topics_2016-2025_data_profiles.md` | Dataset, scale, preprocessing, and data-condition hints for all 223 papers |

CSV versions are included for sorting and filtering.

### Code availability

- 165 officially open-sourced (GitHub, author page, or HuggingFace)
- 14 third-party reproductions
- 13 dataset or benchmark only
- 13 not released
- 18 unverified

“Officially open-sourced” does not mean “runs out of the box”: many are research code that depends on old frameworks or requires data/model access requests.

### Dataset scale

The range covers 30 images for the original U-Net, 3–5 subject photos for DreamBooth, 1.28M images for ImageNet, and 400M image-text pairs for CLIP. Scales are approximate values from the primary benchmarks; check the papers for exact numbers.

## Repository structure

```text
.
├── .claude/
│   └── skills/
│       └── cv-task-advisor/
│           ├── SKILL.md
│           └── references/
│               └── task-map.md
├── knowledge/
│   ├── CV_Topics_2016-2025.md
│   ├── CV_Topics_2016-2025_plain.md
│   ├── CV_Topics_2016-2025_references.md
│   ├── CV_Topics_2016-2025_code_availability.md
│   ├── CV_Topics_2016-2025_data_profiles.md
│   └── *.csv
├── README.md
└── README.en.md
```

## Design principles

- **No jargon required.** Ask “what should the computer output”, not “classification or segmentation?”
- **One question at a time.** No questionnaires.
- **Restate before retrieval.** Do not recommend papers before confirming the task.
- **Few, relevant papers.** At most six, ranked by “why it fits you”.
- **State the differences.** A similar task is not the same task.
- **Data determines the method.** If the user has 1–2 orders of magnitude less data, recommend pretraining or few-shot methods, not training from scratch.
- **Never invent citations.** Uncertain years, venues, or code status are marked “unverified”.

## Limitations

- The knowledge base is a curated selection, not a complete literature database. Missing areas are supplemented with web search.
- “Representative paper” involves judgment. Issues and PRs are welcome.
- Dataset scales are approximate. Training details should be checked against the paper and official code.
- Code status only verifies that a repository exists, not that the paper’s numbers can be reproduced.
- Medical, face, and autonomous-driving scenarios require additional compliance, ethics review, and human oversight. The skill flags this but cannot replace it.

## Data sources and acknowledgements

- Task taxonomy and some resources are inspired by [jbhuang0604/awesome-computer-vision](https://github.com/jbhuang0604/awesome-computer-vision).
- Paper and code links come from the authors’ or institutions’ public GitHub, HuggingFace, and project pages.
- Repository existence was checked via the GitHub API. Dataset scales and preprocessing were compiled from the primary benchmarks used in each paper.

## License

No open-source license is specified yet. Add a `LICENSE` file if you want MIT, Apache-2.0, or another license.

## Contributing

Issues and PRs are welcome:

- Add missing representative papers;
- Correct dataset scales or preprocessing descriptions;
- Update broken code links;
- Add new task-mapping rules.

<h1 align="center">Muhammad Talha</h1>

<p align="center">
  Computer vision &amp; ML engineer &nbsp;·&nbsp; <b>20 merged pull requests</b> in Hugging Face, MONAI, Kornia and Roboflow<br>
  BS Computer Science, AWKUM (2022–2026) &nbsp;·&nbsp; Mardan, Pakistan &nbsp;·&nbsp; <a href="mailto:muhammadtalha223@gmail.com">muhammadtalha223@gmail.com</a>
</p>

---

## About

I build computer vision and ML systems, and I fix the bugs I run into in the libraries underneath them. My thesis was an end-to-end license plate recognition system for Pakistani plates that runs on a Raspberry Pi and is deployed entirely on free-tier services. Most of my open-source work is correctness fixes in PyTorch-ecosystem libraries: numerical edge cases, ONNX export, metric definitions, and security hardening.

**Currently looking for:** graduate research opportunities (MS/PhD) in computer vision and medical imaging.

---

## Open source

**20 merged PRs** across 5 projects, plus 2 open, verified on 24 October 2026. [Browse my contributions](https://github.com/pulls?q=is%3Apr+author%3ATalhax55z).

| Project | Merged | Areas |
|---|:---:|---|
| [kornia/kornia](https://github.com/kornia/kornia/pulls?q=is%3Apr+author%3ATalhax55z+is%3Amerged) | 13 | geometry, filters, augmentation, ONNX export, integer-input numerics |
| [Project-MONAI/MONAI](https://github.com/Project-MONAI/MONAI/pulls?q=is%3Apr+author%3ATalhax55z+is%3Amerged) | 4 | security hardening, `SegResNetDS` docs and tests |
| [huggingface/transformers](https://github.com/huggingface/transformers/pull/49416) | 1 | MoE config bug |
| [roboflow/supervision](https://github.com/roboflow/supervision/pull/2701) | 1 | COCO-compliant mAR metric |
| [future-agi/future-agi](https://github.com/future-agi/future-agi/pull/3544) | 1 | API gateway warnings |

**Selected fixes**

- **supervision [#2701](https://github.com/roboflow/supervision/pull/2701):** `MeanAverageRecall` capped detections across all classes, which pushed recall below what COCO's `pycocotools` reports. It now applies `maxDets` per image *and* per class.
- **kornia [#5702](https://github.com/kornia/kornia/pull/5702):** `euler_from_quaternion` returned wrong rotations at pitch = ±π/2 (gimbal lock). Added the standard special case.
- **kornia [#5710](https://github.com/kornia/kornia/pull/5710):** Canny's hysteresis loop lost its data dependence under `torch.jit.trace`.
- **kornia [#5407](https://github.com/kornia/kornia/pull/5407), [#5417](https://github.com/kornia/kornia/pull/5417):** integer inputs overflowed or produced NaN/inf in `normalize`, `denormalize` and `mean_iou_bbox`. They are now promoted to float32.
- **MONAI [#9179](https://github.com/Project-MONAI/MONAI/pull/9179):** the MMAR format carried a security advisory (unsafe dynamic imports and TorchScript loading). Deprecated the APIs and disabled `load_from_mmar`.
- **MONAI [#8797](https://github.com/Project-MONAI/MONAI/pull/8797), [#9128](https://github.com/Project-MONAI/MONAI/pull/9128), [#9131](https://github.com/Project-MONAI/MONAI/pull/9131):** `SegResNetDS` documented only the isotropic input-shape rule. I traced `shape_factor()` and `is_valid_shape()` through the source, documented the anisotropic case, and added edge-case tests.
- **transformers [#49416](https://github.com/huggingface/transformers/pull/49416):** `Inkling-Small` resolved `moe_intermediate_size` to 3072 instead of 2048 because the dense MLP width overwrote the expert width, breaking weight loading.

**In review:** [huggingface/trl #7540](https://github.com/huggingface/trl/pull/7540) (report true epoch progress in `AsyncGRPOTrainer` and `AsyncDistillationTrainer`) · [MONAI #8795](https://github.com/Project-MONAI/MONAI/pull/8795) (package install hint in `ImageWriter` backend errors)

<details>
<summary><b>All 20 merged PRs</b></summary>
<br>

| Repo | PR | Title |
|---|---|---|
| kornia/kornia | [#6184](https://github.com/kornia/kornia/pull/6184) | Fix BoxFiltering class-list device mismatch in forward |
| kornia/kornia | [#6139](https://github.com/kornia/kornia/pull/6139) | feat(onnx): add force_download to refresh cached models |
| kornia/kornia | [#6138](https://github.com/kornia/kornia/pull/6138) | fix(augmentation): repeat CutMix parameters across video frames |
| kornia/kornia | [#6132](https://github.com/kornia/kornia/pull/6132) | fix(augmentation): allow mix augmentations in PatchSequential with random_apply |
| kornia/kornia | [#6086](https://github.com/kornia/kornia/pull/6086) | fix(onnx): fix BoxFiltering batch size for per-image outputs |
| kornia/kornia | [#5859](https://github.com/kornia/kornia/pull/5859) | fix(feature): accept device=None in OnnxLightGlue |
| kornia/kornia | [#5710](https://github.com/kornia/kornia/pull/5710) | fix(filters): keep Canny's hysteresis loop data-dependent under torch.jit.trace |
| kornia/kornia | [#5702](https://github.com/kornia/kornia/pull/5702) | fix(geometry): handle gimbal lock in euler_from_quaternion |
| kornia/kornia | [#5618](https://github.com/kornia/kornia/pull/5618) | fix(augmentation): broadcast single mask over a batched image in AugmentationSequential |
| kornia/kornia | [#5616](https://github.com/kornia/kornia/pull/5616) | fix(augmentation): ignore a hand-made batch_prob consistently at static p=1.0 |
| kornia/kornia | [#5432](https://github.com/kornia/kornia/pull/5432) | fix(filters): check the sigma_color and sigma_space batch in the bilateral blurs |
| kornia/kornia | [#5417](https://github.com/kornia/kornia/pull/5417) | fix: compute integer and bool boxes in float32 in mean_iou_bbox |
| kornia/kornia | [#5407](https://github.com/kornia/kornia/pull/5407) | fix(enhance): promote integer input to float in normalize/denormalize |
| Project-MONAI/MONAI | [#9179](https://github.com/Project-MONAI/MONAI/pull/9179) | Deprecate MMAR APIs and disable load_from_mmar |
| Project-MONAI/MONAI | [#9131](https://github.com/Project-MONAI/MONAI/pull/9131) | docs: add missing upsample_mode parameter documentation to SegResNetDS and SegResNetDS2 |
| Project-MONAI/MONAI | [#9128](https://github.com/Project-MONAI/MONAI/pull/9128) | Add anisotropic edge-case tests for SegResNetDS shape validation |
| Project-MONAI/MONAI | [#8797](https://github.com/Project-MONAI/MONAI/pull/8797) | Docs: add spatial shape constraints to SegResNetDS docstring |
| huggingface/transformers | [#49416](https://github.com/huggingface/transformers/pull/49416) | Fix Inkling moe_intermediate_size when dense_intermediate_size is present |
| roboflow/supervision | [#2701](https://github.com/roboflow/supervision/pull/2701) | fix(metrics): limit MeanAverageRecall detections per image and class |
| future-agi/future-agi | [#3544](https://github.com/future-agi/future-agi/pull/3544) | fix(gateway): flag and warn on unpriced models |

</details>

---

## Featured projects

### Smart Parking Management System (undergraduate thesis)
[**Live demo**](https://smart-parking-frontend-lyart.vercel.app) · webcam → YOLOv11 Nano plate detector → OCR → Node.js/WebSocket backend → Next.js dashboard

A parking prototype for Pakistani cities that needs no per-bay sensors, built under real budget limits (Colab free GPU, Render, Vercel, MongoDB Atlas free tiers).

- Built and annotated a 694-image Pakistani plate dataset (Kaggle, YouTube frames, simulation). The first run scored 48.4% mAP@50; the confusion matrix showed that mixing close-up plates with full road scenes was the cause. I cleaned the data and retrained.
- PaddleOCR crashed with a segmentation fault on the Raspberry Pi's ARM CPU, so the Pi build uses EasyOCR.
- CLAHE preprocessing, 10-frame majority voting per tracked vehicle, and position-aware character correction (0/O, 1/I, 5/S, 8/B).
- Real-time slot updates over WebSocket, JWT + Google/GitHub OAuth, and automatic billing.

| Metric | Result |
|---|---|
| Local YOLOv11 Nano (Colab) | ~65% mAP@50 |
| Roboflow cloud run, same data | 93.5% mAP@50 (benchmark only; weights not exportable on the free plan) |
| End-to-end exact plate match | >85% on controlled test clips |
| Detection to logged plate | ~1.3 s |
| WebSocket slot update / API p95 | 43 ms / 320 ms |

### More projects

| Project | What it shows |
|---|---|
| [**MediBot**](https://github.com/Talhax55z/medibot-rag-chatbot) | PDF-based RAG with source passages: Groq + Streamlit UI, Hugging Face terminal client, FAISS index, setup guide, and [presentation](https://github.com/Talhax55z/medibot-rag-chatbot/blob/main/medical-chatbot-ppt.pdf) |
| [**NYC Airbnb 2024: exploratory analysis**](https://github.com/Talhax55z/Air-BNB-1) | Separate analysis of 20,765 listings: data cleaning, price distributions, room types, availability, and geographic patterns |
| [**NYC Airbnb: cleaning, EDA & modeling**](https://github.com/Talhax55z/airbnb-nyc-eda-modeling) | Found that price in the dataset is synthetic and caught a leaking feature (`service_fee` is exactly 20% of price); no model beats R² ≈ 0.08 |
| [**Telco churn prediction**](https://github.com/Talhax55z/telco-churn-prediction) | SMOTEENN applied to the training split only, six models compared on a stratified held-out set (ROC-AUC 0.80–0.83) |
| [**Zomato data analysis**](https://github.com/Talhax55z/zomato-data-analysis) | Restaurant types, ratings, cost for two, and online/offline ordering patterns |
| [**Eid sales analysis**](https://github.com/Talhax55z/Eid-Sales-Analysis) | Sales exploration by demographics, location, occupation, and product category |
| [**Ola SQL and analysis index**](https://github.com/Talhax55z/data-analysis-projects) | 10 reusable MySQL views on ride bookings, cancellations, ratings, and revenue |

---

## Tech

| | |
|---|---|
| **Computer vision** | YOLOv11 (Ultralytics), OpenCV, EasyOCR, PaddleOCR, ONNX, CLAHE, multi-object tracking |
| **Deep learning** | PyTorch, MONAI, Kornia |
| **ML & data** | scikit-learn, imbalanced-learn, pandas, NumPy, SciPy, matplotlib, seaborn, Plotly |
| **LLM / RAG** | LangChain, FAISS, sentence-transformers, Groq, Hugging Face, Streamlit |
| **Web & backend** | Node.js, Express, WebSocket, MongoDB, Next.js, React, Tailwind |
| **Languages & tools** | Python, JavaScript, SQL (MySQL), C++ (basic), Git, Raspberry Pi, Google Colab, Roboflow |

---

## Contact

📫 [muhammadtalha223@gmail.com](mailto:muhammadtalha223@gmail.com)

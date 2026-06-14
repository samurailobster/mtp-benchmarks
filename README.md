# 🚀 MTP Benchmarks - AMD Strix Halo

A high-performance analysis of **Multi-Token Prediction (MTP)** capabilities using `llama.cpp` on the AMD Strix Halo platform.

## 🎯 Project Goal
Evaluating the real-world impact of speculative drafting in Large Language Models (LLMs). We specifically analyze the relationship between the number of draft tokens (`n-max`) and the resulting tokens per second (t/s), identifying the efficiency "sweet spot" for modern hardware.

## 🛠 Technical Stack
| Component | Specification |
| :--- | :--- |
| **Hardware** | AMD Strix Halo (RADV Vulkan) |
| **Inference** | `llama.cpp` (build b9198) |
| **Quantization** | Q4_K_XL |
| **Model Sizes** | 9B, 27B, 35B |

## 📈 Key Findings
- **The Optimal Point:** For most configurations, **`n-max=2`** is the golden ratio, providing a significant boost without overloading the memory bus.
- **The Scaling Wall:** Pushing draft tokens too high (e.g., `n-max=8`) can lead to severe performance degradation (up to **35% loss** on 9B models) due to bandwidth saturation.
- **Model Sensitivity:** Larger models (35B) exhibit a sharper performance drop-off when over-speculating compared to smaller models.

## 📂 Results Portal
The results are hosted as interactive HTML reports:
- [**Main Results Portal**](https://samurailobster.github.io/mtp-benchmarks/)
- [**Baseline Results**](https://samurailobster.github.io/mtp-benchmarks/results-baseline.html)
- [**Qwen 35B Detailed**](https://samurailobster.github.io/mtp-benchmarks/qwen35.html)
- [**v2 Speculation Test**](https://samurailobster.github.io/mtp-benchmarks/v2.html)

---
*Authored by Augustus, Jeff's autonomous operator.*

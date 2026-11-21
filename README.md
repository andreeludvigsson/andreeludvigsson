### Hi, I'm Andrée 👋

I build **VDB**, a Swedish house-design CAD application with an AI architect. You upload a floor plan or start a new one,
then describe the change in plain Swedish, for example *"move the kitchen window 40 cm east"*. VDB makes exactly that change.

![AMD ROCm](https://img.shields.io/badge/AMD-ROCm-ED1C24?logo=amd&logoColor=white)
![MI300X](https://img.shields.io/badge/GPU-Instinct%20MI300X-ED1C24)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?logo=pytorch&logoColor=white)
![vLLM](https://img.shields.io/badge/serving-vLLM-30A2FF)
![Qwen3](https://img.shields.io/badge/LLM-Qwen3%204B%20%2F%2030B-6E4AFF)
![ONNX](https://img.shields.io/badge/ONNX-Runtime-005CED?logo=onnx&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)

---

#### 🧱 Rekryt: walls from a floor-plan image

Rekryt finds the walls in an uploaded plan so that VDB can turn it into an editable drawing.

<img src="https://raw.githubusercontent.com/andreeludvigsson/vdb-rekryt-results/main/images/own_best.png" alt="Rekryt v5: original, ground truth in green, prediction in blue" width="100%">

| Test set | Plans | F1 | Precision | Recall |
|---|---:|---:|---:|---:|
| VDB's own drawings | 57 | 0.971 | 0.948 | 0.997 |
| CVC-FP, scanned real plans | 122 | 0.881 | 0.807 | 0.973 |

➡️ Images, worst cases and method: **[vdb-rekryt-results](https://github.com/andreeludvigsson/vdb-rekryt-results)**

#### 🤖 The AI architect, trained on AMD Instinct MI300X

A Qwen3-30B teacher, served with vLLM on ROCm, writes answers. Every answer is checked in our own CAD engine. The verified
answers train a small Qwen3-4B student that runs locally in the app.

| | Before | After |
|---|---:|---:|
| Student on the locked test set (300 questions) | 32.3 % | **50.7 %** |
| Unsafe answers | – | **0** |
| Verified training examples | 403 | **9,749** |

➡️ Full report: **[vdb-amd-results](https://github.com/andreeludvigsson/vdb-amd-results)**

---

🇸🇪 Sweden first, then the Nordics, Europe and the world: one step at a time.

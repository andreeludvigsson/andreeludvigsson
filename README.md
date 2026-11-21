### Hi, I'm Andrée Ludvigsson 👋

I build **VDB**, a Swedish planning tool for single-family houses. It takes a house from the first floor-plan sketch to
electrical, plumbing and heating drawings, with an **AI architect** that edits the drawing on request in plain Swedish.

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?logo=pytorch&logoColor=white)
![ONNX](https://img.shields.io/badge/ONNX-Runtime-005CED?logo=onnx&logoColor=white)
![LoRA](https://img.shields.io/badge/PEFT-LoRA-FFD21E?logo=huggingface&logoColor=black)
![vLLM](https://img.shields.io/badge/serving-vLLM-30A2FF)
![AMD ROCm](https://img.shields.io/badge/AMD-ROCm%20%C2%B7%20MI300X-ED1C24?logo=amd&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![React](https://img.shields.io/badge/React%20%2F%20Three.js-20232A?logo=react&logoColor=61DAFB)

---

#### 📌 Results

| Repository | What it shows | Headline |
|---|---|---|
| **[vdb-rekryt-results](https://github.com/andreeludvigsson/vdb-rekryt-results)** | Rekryt, VDB's wall detector for floor-plan images | F1 **0.97** on VDB drawings, **0.88** on scanned real plans |
| **[vdb-amd-results](https://github.com/andreeludvigsson/vdb-amd-results)** | The AI architect, trained on one AMD Instinct MI300X | Student **32.3 % → 50.7 %** on a locked test set, 0 unsafe answers |

#### 🧱 Rekryt: walls from a floor-plan image

Rekryt reads a scanned floor plan and proposes where the walls are, for the user to review. It is trained from scratch on
openly licensed data ([Swiss Dwellings](https://zenodo.org/records/7788422), CC BY 4.0) and VDB's own synthetic drawings.

<img src="https://raw.githubusercontent.com/andreeludvigsson/vdb-rekryt-results/main/images/own_best.png" alt="Rekryt v5: original, ground truth in green, prediction in blue" width="100%">

#### 🤖 The AI architect

It turns plain Swedish, such as *"flytta dörren mellan hallen och köket till x=4,2 y=3"*, into drawing edits. Every edit
is simulated in the drawing engine and checked by rule-based reviewers before the user sees it.

- **Open-weight models only** (Qwen3, Apache 2.0), running on our own machines, so customer drawings stay private.
- **Engine-verified self-training:** a larger teacher proposes answers, and the engine and a rule-based judge accept or
  reject them. Only verified answers become training data for a small model that runs on one consumer GPU.
- **Honest measurement:** a locked test split that is never trained on, and the same metrics for every model.

**Current focus:** moving objects, walls, doors, windows, conduits and pipes **to exact coordinates**, in fully equipped
test houses with two floors, electrical, plumbing, heating, rainwater and furniture.

---

🇸🇪 Sweden first, then the Nordics, Europe and the world: one step at a time.  
📫 [Facebook](https://www.facebook.com/andree.ludvigsson.7)

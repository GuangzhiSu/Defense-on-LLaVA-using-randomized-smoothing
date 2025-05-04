# Defense-on-LLaVA-using-Randomized-Smoothing

A two-stage pipeline for (1) generating adversarial/harmful images against LLaVA and (2) hardening a pre-trained LLaVA+Llama v2 model via randomized smoothing at inference time.

---

## 🚀 Features

1. **Visual Attack**  
   - Script: `llava_llama_v2_visual_attack.py`  
   - Generates adversarial or “harmful” images tailored to exploit vulnerabilities in LLaVA.  
   - Supports configurable attack parameters, batch sizes, and output logging.

2. **Randomized Smoothing Defense**  
   - Script: `llava_llama_v2_inference.py`  
   - Wraps the standard LLaVA+Llama v2 inference pipeline with randomized smoothing.  
   - No core modification to the original LLaVA codebase—defense logic lives entirely in the inference wrapper.

3. **Metrics & Calibration**  
   - Utilities under `metric/` and `cal_metrics.py` to compute detection rates, robustness scores, and calibration curves.

4. **Modular Design**  
   - Clean separation:  
     - `train/` for any extra training scripts  
     - `model/` for architecture definitions  
     - `serve/` for deployment stubs  
     - `eval/` for evaluation harnesses  
     - `conversation.py` & `generator.py` for I/O and prompt orchestration

---

## 📦 Requirements

- Python 3.8+  
- PyTorch 2.x  
- Transformers (Hugging Face)  
- OpenCV, Pillow (for image ops)  
- `botorch`, `scipy` (for smoothing noise)  
- `tqdm`, `numpy`, `pandas`

You can install most dependencies via:

```bash
pip install -r requirements.txt

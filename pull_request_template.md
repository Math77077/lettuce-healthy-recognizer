## 📝 Description
<!-- Summarize the changes introduced by this Pull Request. -->
<!-- Example: "Adds data augmentation ablation study for YOLO11l training." -->

## 🔗 Related Issue
<!-- If there is an open issue, link it here. E.g., "Closes #12" -->

## 🏷️ Type of Change
- [ ] 🐛 **Bug fix** (Fixes a pipeline error)
- [ ] ✨ **New Feature** (Adds a new model baseline, metric, or analysis)
- [ ] 📊 **Data Engineering** (Changes dataset splits or preprocessing)
- [ ] 📚 **Documentation** (Updates README, notebook markdown, or docs)
- [ ] 🔧 **Refactoring** (Code improvement without altering training/eval logic)

---

## 🧪 Testing Performed
<!-- Describe how you validated these changes in terms of ML and pipeline execution. -->
- [ ] **Full Training Run** (Model converged and generated `best.pt` weights)
- [ ] **Image Inference** (Validation script generated mAP and confusion matrix outputs)
- [ ] **Video Inference** (Processed test video without GPU VRAM OOM errors)
- [ ] **Syntax / Environment Check Only** (Validated code syntax without full training epochs)

---

## ⚡ Environment & GPU Checks
- [ ] Does this change require new external libraries not listed in `requirements.txt`?
- [ ] Does this change impact GPU VRAM consumption (e.g., increased batch size)?
  - *If YES, did you document the minimum hardware required?*

---

## ✅ Final Checklist
- [ ] The notebook runs sequentially from top to bottom without errors.
- [ ] No large datasets, `.pt` weights, or sensitive `.yaml` files were accidentally committed.
- [ ] Removed all personal API keys (Roboflow, WandB, etc.) from code.
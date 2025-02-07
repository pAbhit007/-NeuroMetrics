# 🎯 IoU (Intersection over Union)

Based on the F-measure, there are two popular metrics for Medical Image Segmentation:
* Intersection-over-Union (IoU), also known as **Jaccard Index**
* Dice similarity coefficient, also known as **F1-score**

** IoU exhibits greater sensitivity to segmentation errors compared to DSC, applying stronger penalties to both excessive and insufficient segmentation predictions."

### What is IoU? 🤔
IoU, also known as the Jaccard Index, measures how much two masks overlap compared to their total combined area. Like comparing how well two stickers overlap when placed on top of each other!

### 📐 Mathematical Formula

<div align="center">

```math
IoU = \frac{|A \cap B|}{|A \cup B|} = \frac{\text{Intersection}}{\text{Union}}
```

</div>

### 🧮 Components Breakdown

| Component | Symbol | Description | Visual |
|:---------:|:------:|:------------|:------:|
| Intersection | ∩ | Pixels present in both masks | 🟦 |
| Union | ∪ | Pixels present in either mask | 🟨 |
| Prediction | A | Your model's output | 🔵 |
| Ground Truth | B | The correct segmentation | 🔴 |

### 📊 Score Interpretation

<div align="center">

| Score Range | Quality | Description | Grade |
|:----------:|:-------:|:------------|:-----:|
| 0.9 - 1.0 | Exceptional | Near-perfect overlap | 🏆 |
| 0.8 - 0.9 | Excellent | Strong match | 🌟 |
| 0.7 - 0.8 | Good | Decent overlap | ✨ |
| 0.5 - 0.7 | Fair | Moderate match | ⭐ |
| < 0.5 | Poor | Significant mismatch | 📉 |

</div>

### ✨ Key Features

- **Range**: [0, 1] where:
  - 1️⃣ = Perfect match
  - 0️⃣ = No overlap
- **Properties**:
  - ⚖️ Symmetric measure
  - 🎯 Penalizes both over- and under-segmentation
  - 📏 Scale-invariant

### 📈 Visual Examples

<div align="center">

```
Perfect IoU (1.0)       Good IoU (0.8)        Poor IoU (0.3)
┌──────────────┐      ┌──────────────┐      ┌──────────────┐
│   ████████   │      │  ████████    │      │████    ████  │
│   ████████   │      │   ███████    │      │████  ████    │
│   ████████   │      │   ███████    │      │  ████████    │
└──────────────┘      └──────────────┘      └──────────────┘
```

</div>

### 🚀 Common Use Cases

1. **Object Detection** 
   - Evaluating bounding box accuracy
   - Non-max suppression thresholds

2. **Semantic Segmentation**
   - Per-class evaluation
   - Overall model performance

3. **Instance Segmentation**
   - Individual object accuracy
   - Multi-object scenarios

### 💡 Pro Tips

- 🎯 Use Mean IoU (mIoU) for multi-class segmentation
- 🔍 Consider class-wise IoU for imbalanced datasets
- ⚡ Optimize your model using IoU as a loss function
- 📊 Combine with other metrics for comprehensive evaluation

<div align="center">
  
  **Used in COCO, Pascal VOC, and other major computer vision benchmarks**
  
  [📚 Read More](docs/iou.md) | [💻 View Code](src/metrics.py) | [🎯 See Examples](examples/iou_examples.ipynb)
</div>

### 🔗 Related Metrics

- 📊 Dice Coefficient
- 📈 Pixel Accuracy
- 🎯 Boundary F1-Score

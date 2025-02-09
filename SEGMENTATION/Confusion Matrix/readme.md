# 🎯 Understanding Confusion Matrix in Image Segmentation

## What is a Confusion Matrix? 🤔

A Confusion Matrix is a fundamental evaluation tool that answers the question: **"How well does our segmentation model classify each pixel?"** It provides a detailed breakdown of correct and incorrect predictions for both foreground and background pixels.

## 📊 The Matrix Structure

```
             Predicted
Actual    Background  Foreground
Background    TN         FP
Foreground    FN         TP
```

Where:
- **TN (True Negatives)**: Background pixels correctly identified as background
- **FP (False Positives)**: Background pixels incorrectly identified as foreground
- **FN (False Negatives)**: Foreground pixels incorrectly identified as background
- **TP (True Positives)**: Foreground pixels correctly identified as foreground

## 🎨 Visual Examples

Let's visualize with a practical example:

**Ground Truth Mask:**
```python
[
    [0, 1, 0, 0],
    [1, 1, 0, 0],
    [0, 1, 1, 0],
    [0, 0, 0, 1]
]
```

**Predicted Mask:**
```python
[
    [0, 1, 0, 1],
    [1, 0, 0, 0],
    [0, 1, 0, 0],
    [0, 0, 0, 1]
]
```

**Resulting Confusion Matrix:**


import React from 'react';

const ConfusionMatrix = () => {
  return (
    <div className="flex flex-col items-center space-y-4">
      <div className="grid grid-cols-2 gap-4">
        <div className="text-right font-bold">Actual/Predicted</div>
        <div className="grid grid-cols-2 gap-2">
          <div className="text-center font-bold">Background</div>
          <div className="text-center font-bold">Foreground</div>
        </div>
        <div className="text-right font-bold">Background</div>
        <div className="grid grid-cols-2 gap-2">
          <div className="bg-green-100 p-4 text-center border">
            <div className="font-bold">TN</div>
            <div>7</div>
          </div>
          <div className="bg-red-100 p-4 text-center border">
            <div className="font-bold">FP</div>
            <div>1</div>
          </div>
        </div>
        <div className="text-right font-bold">Foreground</div>
        <div className="grid grid-cols-2 gap-2">
          <div className="bg-red-100 p-4 text-center border">
            <div className="font-bold">FN</div>
            <div>2</div>
          </div>
          <div className="bg-green-100 p-4 text-center border">
            <div className="font-bold">TP</div>
            <div>4</div>
          </div>
        </div>
      </div>
    </div>
  );
};

export default ConfusionMatrix;

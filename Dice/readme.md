# 🎲 Dice Score (Dice Coefficient)

The Dice Score (Dice Coefficient) is a widely used metric in image segmentation to measure the overlap between predicted and ground truth masks. It evaluates how well a segmentation model's output aligns with the actual segmentation. A **higher Dice Score** (closer to 1) means better overlap, while a **lower score** (closer to 0) indicates poor segmentation.

The Dice Score is defined as:
                      **Dice= 2∣A∩B∣/∣A∣+∣B∣**

Where:
* A is the predicted segmentation mask
* B is the ground truth mask
* ∣A∩B∣ is the number of overlapping pixels
* ∣A∣+∣B∣ represents the total pixels in both masks

#### Red regions → High overlap (where both prediction and ground truth agree).
#### Blue regions → Low overlap (mismatch or incorrect segmentation).
#### Flat areas (near 0) → No segmentation detected in either the prediction or the ground truth.

#### 2D Representation:
![dice heatmap](https://github.com/user-attachments/assets/973fc528-fd5f-4c05-851d-207991521c71)


#### 3D Representation:
![dice overlap 3d visualization](https://github.com/user-attachments/assets/47d2d840-f9d6-48b6-807c-736bbe08fa39)



​
 

​

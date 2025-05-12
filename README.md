# Corn-Disease-Detection

The project aims to help primary industries, specifically for the farms that producing corns, detect the what type of disease that racks their corn yield also assist the farmers finding out the information about the disease as well as the treatments with which they to take action.

## **Data Overview**

In the [data](https://www.kaggle.com/datasets/smaranjitghose/corn-or-maize-leaf-disease-dataset) from roboflow there are 3 types of diseases we chose for our classification such as `Corn Rust`, `Grey Leaf Spot`, `Leaf Blight`.

So let's see the picturer of the all diseases:

**Corn Common Rust**

<img src="assets\images\Corn Common Rust.jpg" alt="Corn Rust Disease" width="300"/>

**Grey Leaf Spot**

<img src="assets\images\Corn Gray Spot.jpg" alt="Corn Rust Disease" width="300"/>

**Leaf Blight**

<img src="assets\images\Corn Blight.jpg" alt="Corn Rust Disease" width="300"/>

### **Data Preparation**

The data used in this project underwent several preprocessing steps to ensure optimal model performance:

1. **Data Collection**: Images were sourced from Roboflow's dataset, containing three main corn disease categories.

2. **Image Preprocessing**:
    - Resized to uniform dimensions (640x640 pixels)
    - Normalized pixel values
    - Augmentation techniques:
      - Random rotation
      - Horizontal flip
      - Brightness adjustment
      - Contrast enhancement

3. **Dataset Split**:
    - Training set: 80%
    - Validation set: 10%
    - Test set: 10%

4. **Class**

```bash
Class names:  ['Blight', 'Common_Rust', 'Gray_Leaf_Spot', 'Healthy']
```


## **Models**

| **Model**         | **Accuracy** | **Description**                                                                 |
|--------------------|--------------|---------------------------------------------------------------------------------|
| ResNet50          | 92.5%        | A deep residual network with 50 layers, known for its high performance on image tasks. |
| MobileNetV2       | 89.8%        | A lightweight model optimized for mobile and embedded vision applications.      |
| EfficientNetB0    | 91.2%        | A model balancing accuracy and efficiency, suitable for resource-constrained environments. |

## References

[Corn Rust from Menisota University](https://ohioline.osu.edu/factsheet/plpath-cer-02)

[Gray leaf spot on corn from Menisota University](https://extension.umn.edu/corn-pest-management/gray-leaf-spot-corn)

[Corn Leaf Blight from Menisota University](https://extension.umn.edu/corn-pest-management/northern-corn-leaf-blight)
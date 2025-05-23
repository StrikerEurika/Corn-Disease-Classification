# Corn-Disease-Detection

The project aims to help primary industries, specifically for the farms that producing corns, detect the what type of disease that racks their corn yield also assist the farmers finding out the information about the disease as well as the treatments with which they to take action.

## **Data Overview**

In the [data](https://www.kaggle.com/datasets/smaranjitghose/corn-or-maize-leaf-disease-dataset) from roboflow there are 3 types of diseases we chose for our classification such as `Corn Rust`, `Grey Leaf Spot`, `Leaf Blight`.

So let's see the picturer of the all diseases:

**Corn Common Rust**

<img src="assets\images\Corn_Common_Rust.jpg" alt="Corn Rust Disease" width="300"/>

**Grey Leaf Spot**

<img src="assets\images\Corn_Gray_Spot.jpg" alt="Corn Rust Disease" width="300"/>

**Leaf Blight**

<img src="assets\images\Corn_Blight.jpg" alt="Corn Rust Disease" width="300"/>

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
| VGG16         | 92%        | A deep convolutional neural network known for its simplicity and strong performance in image classification tasks. |
| VGG19       | 91%        | A deeper variant of VGG16 with 19 layers, offering improved feature extraction capabilities for image classification tasks.        |
| MobileNetV2    | 91%        | A lightweight and efficient convolutional neural network optimized for mobile and embedded vision applications, offering fast inference with minimal resource usage. |

## References

[Corn Rust from Menisota University](https://ohioline.osu.edu/factsheet/plpath-cer-02)

[Gray leaf spot on corn from Menisota University](https://extension.umn.edu/corn-pest-management/gray-leaf-spot-corn)

[Corn Leaf Blight from Menisota University](https://extension.umn.edu/corn-pest-management/northern-corn-leaf-blight)

## **Set Up Project**


**Clone Repo**

```bash
# Clone the repository
git clone git@github.com:StrikerEurika/Corn-Disease-Classification.git

# navigate to the project directory
cd Corn-Disease-Classification
```
**Create Virtual Envirinment**

```bash
# Create a virtual environment
python -m venv venv
# Activate the virtual environment
# For Windows
venv\Scripts\activate
# For MacOS/Linux
source venv/bin/activate
```

**Install Requirements**

```bash
# Install the required packages
pip install -r requirements.txt
```
## **Set Up Models**

From your view at the file structure after cloning, you will see (If you create the `.venv` already):


```bash
Corn-Disease-Classification/
├── .venv/
├── assets/
├── model_weights/  <-- Where the model weights are stored
├── notebooks/
├── .gitignore
├── requirements.txt
└── README.md
```

In the `model_weights` folder, you will see the model weights for the models we used in this project. You can use any of them to test the model. The model weights are saved in `.json` and `.h5` format. The `.json` file contains the model architecture, while the `.h5` file contains the model weights.

```bash
├── model_weights/
│   ├── densenet121_model.json
│   ├── densenet121_model.weights.h5
│   ├── mobilenetv2_model.json
│   ├── mobilenetv2_model.weights.h5
│   ├── resnet50_model.json
│   ├── resnet50_model.weights.h5
│   ├── vgg16_model.json
│   ├── vgg16_model.weights.h5
│   ├── vgg19_model.json
│   └── vgg19_model.weights.h5
```

You can use the following code to load the model weights and test the model:

*Let's load `resnet50_model`*

```python
from tensorflow.keras.models import model_from_json

# Load the model architecture
with open(r'../model_weights/resnet50_model.json', 'r') as json_file:
    model_json = json_file.read()

# Load the model
model = model_from_json(model_json)

# Load the model weights
model.load_weights(r'../model_weights/resnet50_model.weights.h5')
```

Make sure to change the path to the model weights according to your file structure. You can use any of the models in the `model_weights` folder. The code will work for all of them.

*Verify the Model is Ready for Use*

```python
# Check architecture summary
model.summary()

# predict a sample image
...
```

**Note**: The model weights are saved in `.json` and `.h5` format. The `.json` file contains the model architecture, while the `.h5` file contains the model weights. You can use the following code to load the model weights and test the model:
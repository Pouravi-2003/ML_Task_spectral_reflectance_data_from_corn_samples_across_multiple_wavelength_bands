## Exploratory Data Analysis (EDA) && Feature Engineering OF SPECTRAL REFLECTANCE DATA of corn samples And Build ML Model to train and test our data
### **Dataset Overview**  
This dataset contains **spectral reflectance data** from **corn samples** obtained through **hyperspectral imaging**. The objective is to use machine learning to predict the concentration of **DON (Deoxynivalenol)**, a toxic compound, in corn.

---

### **Dataset Structure**  
- **Rows (Samples):** Each row corresponds to an individual corn sample.  
- **Columns (Features):**  
  1. **"hsi_id"** (Column 1): A unique identifier for each sample.  
  2. **448 Spectral Reflectance Features** (Columns 2 to 449):  
     - These columns hold reflectance values at different **wavelength bands**.  
     - The values range between **0.26** and **0.95**.  
  3. **"vomitoxin_ppb"** (Column 450):  
     - The target variable representing **DON concentration** in parts per billion (ppb).  
     - Values range from **0 ppb** to **131,000 ppb**.  

---

### **Understanding Spectral Reflectance Features**  
- The **448 spectral reflectance values** represent how much light is reflected from the corn samples at specific wavelengths.  
- Reflectance data helps identify chemical properties that could be linked to DON contamination.  
- Patterns in the reflectance values provide clues about the sample's quality and level of contamination.  

---

### **Target Variable: DON Concentration (`vomitoxin_ppb`)**  
- DON (Deoxynivalenol) is a **mycotoxin** produced by fungi that can contaminate corn.  
- High DON levels can pose risks to both **human and animal health**.  
- The goal is to develop a model that accurately predicts the DON concentration based on spectral data.

---
### Instructions to install Libaries and run the code.

~~~
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
import seaborn as sns
from sklearn.ensemble import RandomForestRegressor
from warnings import filterwarnings
filterwarnings('ignore')
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense, Dropout
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score

from tensorflow.keras.optimizers import Adam
from tensorflow.keras.wrappers.scikit_learn import KerasRegressor
from sklearn.model_selection import RandomizedSearchCV
#import numpy as np

from tensorflow.keras.layers import Conv2D,Conv1D,MaxPooling1D, Dense, Flatten, Dropout, MaxPooling2D
from tensorflow.keras.optimizers import Adam
from tensorflow.keras.wrappers.scikit_learn import KerasRegressor
from tensorflow.keras.layers import LSTM, Dense, Dropout , Bidirectional
~~~
### **WorkFlows**
```
EDA & Feature Engineering --> Dimensionality Reduction --> Model Building & training by Given Data --> Model Evaluation
```

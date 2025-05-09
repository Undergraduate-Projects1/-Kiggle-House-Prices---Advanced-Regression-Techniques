# TensorFlow Decision Forests(TFDF)
## 🌲 What is TensorFlow Decision Forests (TFDF)?
**TensorFlow Decision Forests** is a TensorFlow-compatible library for training, serving, 
and interpreting **decision forest models** such as:

- Random Forests
- Gradient Boosted Trees (GBTs)
- Cart (Classification And Regression Trees)
- Distributed Gradient Boosted Trees Model

It was developed by Google and integrates Yggdrasil Decision Forests, 
a high-performance C++ backend.

**✅ TFDF is designed to make tree-based models easy to use in TensorFlow, 
while keeping the full power and accuracy of decision forests.**

## 🧠 Core Model Principles
TFDF builds upon the principles of **Decision Forest algorithms**, primarily:

### 1. Decision Trees
- A single model that **splits the data based on feature thresholds**.
- Each split attempts to reduce a loss function (e.g., classification impurity or regression error).
- **Leaves** contain final predictions (class or value).

[【机器学习】决策树（理论）](https://blog.csdn.net/the_ZED/article/details/129290733?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522216fd5f96201760edb19bfeb9815b30c%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=216fd5f96201760edb19bfeb9815b30c&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-129290733-null-null.142^v102^pc_search_result_base3&utm_term=%E5%86%B3%E7%AD%96%E6%A0%91&spm=1018.2226.3001.4187)
![1](https://i-blog.csdnimg.cn/blog_migrate/53b100ca513694280eb2acb552ad9cac.png#pic_center)


### 2. Random Forests
- **An ensemble of many decision trees**, each trained on a random subset of data/features.
- Final prediction is an **average (for regression)** or **majority vote (for classification)**.
- High accuracy and robustness, low overfitting.

### 3. Gradient Boosted Trees (GBT)
- Trains trees **sequentially**, with each tree **correcting the errors of the previous**.
- Often achieves state-of-the-art accuracy, but requires more careful tuning.

## 🧰 Advantages of TFDF
| Feature                            | Benefit                                                    |
| ---------------------------------- | ---------------------------------------------------------- |
| 🌐 TensorFlow-compatible           | Easily integrate with other TF/Keras workflows             |
| 🚀 High accuracy                   | Tree ensembles perform well on structured/tabular data     |
| 🎯 Minimal preprocessing           | No need to normalize or scale features                     |
| 🧩 No need for feature engineering | Trees can handle raw data better than neural nets          |
| 📊 Feature importance              | Easy to interpret and visualize what the model has learned |

## 🛠️ How to Use TFDF: Full Example
### 🔹 1. Install the Library
```cmd
pip install tensorflow_decision_forests
```
- Note that the version compatiblity of TF-DF.

### 🔹 2. Load Data
```python
import pandas as pd
import tensorflow_decision_forests as tfdf

# Example: Regression dataset
df = pd.read_csv("https://raw.githubusercontent.com/google/yggdrasil-decision-forests/main/yggdrasil_decision_forests/test_data/dataset/simple_regression.csv")
```

### 🔹 3. Convert to TensorFlow Dataset
```
# Specify the target column
train_ds = tfdf.keras.pd_dataframe_to_tf_dataset(df, label="value", task=tfdf.keras.Task.REGRESSION)
```

### 🔹 4. Train the Model
```
# Create and train a Random Forest for regression
model = tfdf.keras.RandomForestModel(task=tfdf.keras.Task.REGRESSION)
model.fit(train_ds)
```

### 🔹 5. Evaluate and Predict
```
# Evaluate on the same training data (for demo purposes)
model.compile(metrics=["mse"])
model.evaluate(train_ds)

# Predict
predictions = model.predict(train_ds)
print(predictions[:5])
```

### 🔹 6. Interpret the Model
```
# View feature importances
model.make_inspector().variable_importances()

# Visualize first few levels of a tree
tfdf.model_plotter.plot_model(model, max_depth=3)
```

## 🧩 Supported Models in TFDF
| Model                       | Description                                             |
| --------------------------- | ------------------------------------------------------- |
| `RandomForestModel`         | Robust, parallelizable, fast to train                   |
| `GradientBoostedTreesModel` | Often more accurate, but needs tuning                   |
| `CartModel`                 | A single decision tree (interpretable but low accuracy) |

## 📦 When to Use TFDF
| Use Case                  | TFDF Suitability                                |
| ------------------------- | ----------------------------------------------- |
| Tabular data (CSV, Excel) | ✅ Excellent                                     |
| Structured business data  | ✅ Excellent                                     |
| Images/audio/NLP          | ❌ Not recommended (use neural networks instead) |
| Want interpretable models | ✅ Decision forests offer insights               |
| Need quick baselines      | ✅ Easy to train and tune                        |


## 🔍 Internals: Yggdrasil Engine
- TFDF is powered by Yggdrasil Decision Forests, a C++ library.
- When training a model, TFDF actually:
  1. Converts your data to an internal binary format.
  2. Uses Yggdrasil to build the trees efficiently.
  3. Exports the model back to TensorFlow for predictions.

## 📌 Summary
| Topic               | Description                                                   |
| ------------------- | ------------------------------------------------------------- |
| ✅ Purpose           | Tree-based models for TensorFlow (easy + accurate)            |
| 📚 Models           | Random Forests, Gradient Boosted Trees, CART                  |
| ⚙️ Use cases        | Classification, regression on tabular data                    |
| 🔧 Features         | Automatic preprocessing, feature importance, interpretability |
| 🤖 Not suitable for | Raw images, audio, or unstructured text (use CNNs/RNNs)       |

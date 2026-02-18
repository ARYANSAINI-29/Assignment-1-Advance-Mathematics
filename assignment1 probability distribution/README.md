# Learn Probability Density Functions using Roll-Number-Parameterized Non-Linear Model

## 👤 Student Details
* **Name:** Aryan
* **Roll Number:** 102303666
* **Group:** 3C45


---

## 📝 Project Overview
This project involves modeling the probability density function (PDF) of NO2 emissions data. The workflow transforms the raw dataset using a non-linear function parameterized by the university roll number and then learns the optimal parameters ($\lambda$, $\mu$, $c$) for a Gaussian-based PDF model.

### 🎯 Objective
1.  **Transform Data:** Apply a sinusoidal transformation to the input feature $x$ (NO2 levels).
2.  **Learn Parameters:** Fit a custom probability density function to the transformed data.
3.  **Submit Results:** Generate the specific coefficients required for the assignment submission.

---

## ⚙️ Methodology & Configuration

### 1. Data Transformation
The raw input $x$ is transformed into $z$ using equation (1):
$$z = x + a_r \sin(b_r x)$$

Based on Roll Number **102303666**, the specific constants used for this execution were:
* **$a_r$:** 0.15
* **$b_r$:** 0.3

### 2. PDF Estimation Model
The transformed data $z$ is modeled using the function in equation (2):
$$\hat{p}(z) = c \cdot e^{-\lambda(z - \mu)^2}$$

We used `scipy.optimize.curve_fit` to minimize the error between the histogram of $z$ and our model, learning the optimal values for $\lambda$, $\mu$, and $c$.

---

## 📊 Results
Upon executing the model with the dataset, the following parameters were learned:

| Parameter | Symbol | Learned Value |
| :--- | :---: | :--- |
| **Lambda** | $\lambda$ | `0.00348087` |
| **Mean** | $\mu$ | `19.90373656` |
| **Scaling Factor** | $c$ | `0.03193281` |

> *These values match the console output from the script execution.*

---

## 🚀 How to Run

### Dependencies
Ensure you have the required Python libraries installed:
```bash
pip install pandas numpy matplotlib scipy
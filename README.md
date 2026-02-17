# PDF Learning Using Roll Number Parameterized Non-Linear Model

## Overview

This project focuses on learning a Probability Density Function (PDF) from real-world air quality data using a roll-number-dependent non-linear transformation.

The objective is to analyze how a personalized mathematical transformation affects the distribution of data and to estimate the parameters of a Gaussian distribution using Maximum Likelihood Estimation (MLE).

**University Roll Number Used:** 102303501

---

## Dataset

The dataset used in this project is the *India Air Quality Data* available on Kaggle:

https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data

---

## Feature Used

- **NO2 concentration values** are used as the input feature (x) for modeling.

---

## Methodology

### Step 1: Non-Linear Transformation

Each NO2 value \( x \) is transformed into a new variable \( z \) using:

z = x + a_r * sin(b_r * x)

Where the parameters are derived from the roll number:

a_r = 0.05 * (r mod 7)  
b_r = 0.3 * (r mod 5 + 1)

For roll number **102303501**:

r mod 7 = 1  
r mod 5 = 1  

Therefore:

a_r = 0.05  
b_r = 0.6  

Final transformation used in this project:

z = x + 0.05 * sin(0.6 * x)

---

### Step 2: Probability Density Function Learning

The transformed variable z is assumed to follow a Gaussian distribution.

The parameters are estimated using Maximum Likelihood Estimation (MLE):

- mu = mean(z)
- sigma = standard deviation(z)
- lambda = 1 / (2 * sigma^2)
- c = 1 / sqrt(2 * pi * sigma^2)

The learned probability density function is:

p_hat(z) = c * exp(-lambda * (z - mu)^2)

---

### Step 3: Model Validation

- A histogram of the transformed variable z is plotted.
- The learned Gaussian PDF is overlaid on the histogram.
- This visualization helps verify how well the model fits the data.

---

## Output Parameters

The model computes and prints the following parameters:

- Lambda (λ)
- Mu (μ)
- c

Example Output:

Lambda: 0.001460  
Mu: 25.809623  
c: 0.021561  

(Note: Actual values depend on the dataset.)

---

## Tools and Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Google Colab / Jupyter Notebook

---


---

## How to Run the Project

1. Download or clone this repository.
2. Upload `data.csv` to Google Colab or your local environment.
3. Open `assign1_ucs654.ipynb`.
4. Ensure the roll number is set to **102303501** in the code.
5. Run all cells to generate results and plots.

---

## Learning Outcomes

- Understanding non-linear data transformations
- Applying Maximum Likelihood Estimation (MLE)
- Learning Gaussian probability density modeling
- Visualizing probability distributions
- Working with real-world environmental datasets

---

## License

This project is intended strictly for academic and educational use.


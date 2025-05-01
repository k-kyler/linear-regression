# Linear Regression from Scratch

Linear regression is one of the fundamental algorithms in machine learning, used to model the relationship between a dependent variable and one or more independent variables. In this notebook, I implemented linear regression from scratch to understand its mathematical principles deeply.

## Mathematical Foundation

### The Linear Model

Linear regression is based on the simple linear equation:

$$y = ax + b$$

Where:

- $y$ is the predicted value (dependent variable)
- $x$ is the input feature (independent variable)
- $a$ is the slope (coefficient)
- $b$ is the y-intercept

For multiple features, this extends to:

$$y = a_1x_1 + a_2x_2 + ... + a_nx_n + b$$

### Loss Function

To know how well our model is performing, we need a loss function to measure the difference between the predicted and actual values, which is typically the Mean Squared Error (MSE):

$$MSE = \frac{1}{n}\sum_{i=1}^{n}(y_i - (ax_i + b))^2$$

Where:

- $n$ is the number of data points
- $y_i$ is the actual value
- $ax_i + b$ is the predicted value

### Gradient Descent

To minimize the loss function, we implemented gradient descent, which iteratively updates the parameters in the direction of the steepest decrease in the loss:

For parameter $a$:
$$\frac{\partial MSE}{\partial a} = -\frac{2}{n}\sum_{i=1}^{n}x_i(y_i - (ax_i + b))$$

For parameter $b$:
$$\frac{\partial MSE}{\partial b} = -\frac{2}{n}\sum_{i=1}^{n}(y_i - (ax_i + b))$$

The update rules:
$$a_{new} = a_{current} - L \times \frac{\partial MSE}{\partial a}$$
$$b_{new} = b_{current} - L \times \frac{\partial MSE}{\partial b}$$

Where $L$ is the learning rate, controlling the step size of each iteration.

## Implementation Details

1. **Data Exploration**: Analysis of a real estate valuation dataset
2. **Data Preprocessing**: Handling of dates and feature preparation
3. **Loss Function Implementation**: Direct implementation of the MSE formula
4. **Gradient Descent**: Implementation of the gradient descent optimization algorithm
5. **Model Training**: Iterative training process to find optimal parameters
6. **Visualization**: Plotting the regression line against the data points

## Dataset

The project uses a [real estate valuation dataset](https://archive.ics.uci.edu/dataset/477/real+estate+valuation+data+set) containing features like:

- Transaction date
- House age
- Distance to nearest MRT station
- Number of convenience stores
- Latitude and longitude
- House price of unit area

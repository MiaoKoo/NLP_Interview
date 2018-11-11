# Logistic Regression
## Sigmoid
### 函数特性
$\sigma(x) = \frac{1}{1 + e^{-x}}$
$\sigma(x)^{'} = \sigma(x) * (1 - \sigma(x))$

## 损失函数
### 似然函数
$\sigma(x \cdot \theta), y_i = 1​$
$1- \sigma(x \cdot \theta), y_i = 0​$
$L(\theta) = \prod_{i=1}^{N}{\sigma(x \cdot \theta)^{y_i} * (1- \sigma(x \cdot \theta))^{1-y_i}}​$

### 负对数似然函数
$J(\theta) = -\sum_{i=1}^{N}{y_i * log(\sigma(x \cdot \theta)) + (1-y_i) * log(1- \sigma(x \cdot \theta))}$

## 梯度求解

$w_j := w_j + \eta * \frac{\partial J(\theta)}{\partial w_j}$

$\frac{\partial J(\theta)}{\partial w_j} = \frac{\partial J(\theta)}{\partial \sigma(x \cdot \theta)} * \frac{\partial \sigma(x \cdot \theta)}{\partial w_j} $

$\frac{\partial J(\theta)}{\partial \sigma(x \cdot \theta)} = \sum_{i=1}^{N}{\frac{y_i - \sigma(x \cdot \theta)}{\sigma(x \cdot \theta) * (1 - \sigma(x \cdot \theta))}}$

$\frac{\partial \sigma(x \cdot \theta)}{\partial w_j} = \sigma(x \cdot \theta) * (1- \sigma(x \cdot \theta)) * x_{ij}$

$\frac{\partial J(\theta)}{\partial w_j} = \sum_{i=1}^{N}{(y_i - \sigma(x \cdot \theta)) * x_{ij}}$


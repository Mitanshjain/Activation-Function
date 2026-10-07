# Activation Functions

## What is an Activation Function?

An **Activation Function** is a mathematical function used in a Neural Network to introduce **non-linearity** into the data.

In simple words, it decides how the output of a neuron should behave after receiving the input.

The basic calculation inside a neuron is:

```text
z = Σ(wx) + b
```

After this calculation, the Activation Function is applied:

```text
Output = f(z)
```

The main purpose of an Activation Function is to help a Neural Network learn **complex and non-linear relationships** from the data.

---

## Commonly Used Activation Functions

### 1. Sigmoid Function (Logistic Function)

The **Sigmoid Function** maps the input value between **0 and 1**.

```text
Range: 0 to 1
```

Formula:

```text
             1
σ(x) = ---------------
         1 + e^(-x)
```

It was widely used in the past for hidden layers, but nowadays it is less popular there because it can suffer from the **Vanishing Gradient Problem**.

However, Sigmoid is still commonly used in the **output layer for binary classification problems**.

Example:

```text
0.85 → 85% probability
```

---

### 2. Hyperbolic Tangent Function (Tanh)

The **Tanh Function** is similar to Sigmoid, but it maps the input between **-1 and +1**.

```text
Range: -1 to +1
```

Formula:

```text
             eˣ - e⁻ˣ
tanh(x) = ----------------
             eˣ + e⁻ˣ
```

Tanh is **zero-centered**, which is one advantage over Sigmoid.

However, Tanh can also suffer from the **Vanishing Gradient Problem**.

---

### 3. Rectified Linear Unit (ReLU)

**ReLU** is one of the most commonly used Activation Functions in Deep Learning.

Formula:

```text
ReLU(x) = max(0, x)
```

It means:

```text
If x < 0  → Output = 0

If x > 0  → Output = x
```

Example:

```text
ReLU(-5) = 0

ReLU(5) = 5
```

ReLU is popular because it is **simple, fast and computationally efficient**.

One major problem with ReLU is the **Dying ReLU Problem**, where some neurons can become permanently inactive.

---

### 4. Leaky ReLU

**Leaky ReLU** is an improved version of ReLU.

Normal ReLU converts negative values to `0`, whereas Leaky ReLU allows a **small negative value**.

Formula:

```text
f(x) = x       if x > 0

f(x) = αx      if x ≤ 0
```

Here, `α` is usually a small value.

Example:

```text
α = 0.01

x = -5

Output = -0.05
```

This helps reduce the **Dying ReLU Problem**.

---

### 5. Parametric ReLU (PReLU)

**PReLU** is a variation of Leaky ReLU.

In Leaky ReLU, the negative slope `α` is manually selected.

In PReLU:

```text
α = Learnable Parameter
```

This means the Neural Network learns the best value of `α` during training.

Therefore, PReLU provides more flexibility than normal Leaky ReLU.

---

### 6. Exponential Linear Unit (ELU)

**ELU** is another variation of ReLU.

For positive values, it behaves similarly to ReLU.

For negative values, it uses a smooth exponential function instead of directly converting them to zero.

Formula:

```text
f(x) = x                 if x > 0

f(x) = α(eˣ - 1)         if x ≤ 0
```

ELU can help reduce the **Dying ReLU Problem** and provides smoother negative outputs.

---

### 7. Softmax Function

**Softmax** is mainly used in the **output layer for multi-class classification problems**.

It converts the output values into probabilities.

The important property of Softmax is:

```text
Sum of all probabilities = 1
```

Example:

Suppose we are predicting:

```text
Cat
Dog
Horse
```

Softmax may produce:

```text
Cat   → 0.70
Dog   → 0.20
Horse → 0.10

Total = 1.00
```

Therefore, the model predicts **Cat** because it has the highest probability.

---

# Quick Summary

| Activation Function | Range | Important Point |
|---|---|---|
| **Sigmoid** | 0 to 1 | Binary classification output |
| **Tanh** | -1 to +1 | Zero-centered |
| **ReLU** | 0 to ∞ | Commonly used in hidden layers |
| **Le
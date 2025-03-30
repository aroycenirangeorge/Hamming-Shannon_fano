# Huffman and Shannon-Fano Coding

## Problem Statement
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. Apply Huffman and Shannon-Fano coding to this source.

## Aim
To compute the **Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance** for a discrete memoryless source using **Huffman and Shannon-Fano coding** based on the given probabilities and codeword lengths.

## Tools Required
- **Python**: A versatile language for scientific computing and signal processing.
- **NumPy & Matplotlib**: Libraries for numerical operations and high-quality visualizations, essential for demonstrating sampling.

## Program
```python
import numpy as np
import math

L = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of samples: "))

for i in range(n):
    pr = float(input(f"Enter the probability of sample value {i + 1}: "))  
    p.append(pr)

for j in range(n):
    l = float(input(f"Enter the length of the sample value {j + 1}: "))  
    lk.append(l)

for k in range(n):
    L += p[k] * lk[k]

for k in range(n):
    hs += p[k] * math.log(1 / p[k], 2)
hs = round(hs, 3)

eff = round(hs / L, 3)
red = round(1 - eff, 3)

var = sum(p[k] * (lk[k] - L) ** 2 for k in range(n))
var = round(var, 3)

print("\nResults:")
print(f"Average Codeword Length: {L}")
print(f"Entropy: {hs}")
print(f"Efficiency: {eff * 100} %")
print(f"Redundancy: {red}")
print(f"Variance: {var}")
```

## Output
![image](https://github.com/user-attachments/assets/8ad642d8-8568-4fd3-8101-7edfba5df3c4)


## Calculations
![WhatsApp Image 2025-03-30 at 17 32 28_413b02f3](https://github.com/user-attachments/assets/837a5ad2-0599-4e92-8cc4-d2ea92f0b4f7)
![WhatsApp Image 2025-03-30 at 17 32 27_22c607dd](https://github.com/user-attachments/assets/afb00647-5c67-41dc-afcc-803f35ec8977)


## Result
For the given probabilities **{0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25}**:
- **Average Codeword Length**: 2.625
- **Entropy**: 2.625
- **Efficiency**: 100.0%
- **Redundancy**: 0.0
- **Variance**: 0.484


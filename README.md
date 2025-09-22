# Huffman-Shannon_fano
# Aim:
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that by drawing the tree diagram, and 
Calculate the average code word length, entropy, variance, redundancy, and efficiency.
# Tools Required:
# Program:
```
import math

# Probabilities given
p = [0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25]

# Corresponding Huffman/Shannon-Fano code lengths
lk = [3, 4, 2, 4, 3, 3, 2]

n = len(p)

# Average Codeword Length
L = sum(p[k] * lk[k] for k in range(n))

# Entropy
hs = sum(p[k] * math.log(1 / p[k], 2) for k in range(n))
hs = round(hs, 3)

# Efficiency & Redundancy
eff = round(hs / L, 3)
red = round(1 - eff, 3)

# Variance of codeword length
var = sum(p[k] * (lk[k] - L) ** 2 for k in range(n))
var = round(var, 3)

print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff * 100}%")
print(f"Redundancy is : {red}")
print(f"Variance is : {var}")

```
# Calculation:

<img width="538" height="864" alt="image" src="https://github.com/user-attachments/assets/a44b27e2-fc46-49b5-bbb8-caf0b1ee8e67" />
<img width="526" height="651" alt="image" src="https://github.com/user-attachments/assets/3fc6f318-5b49-478f-adb1-7eeb5c696a28" />



# Output
<img width="508" height="152" alt="image" src="https://github.com/user-attachments/assets/83a9c74b-a937-40cc-98c9-fec205eede41" />


# Results:
For the given discrete memoryless source with probabilities {0.125,0.0625,0.25,0.0625,0.125,0.125,0.25}, both Huffman and Shannon–Fano coding were applied. The simulation was carried out in Python (Google Colab). Since the source probabilities are exact powers of two, the codeword lengths match the ideal values, giving zero redundancy and 100% coding efficiency. Both Huffman and Shannon–Fano yield identical results.
Write the conclusion
```

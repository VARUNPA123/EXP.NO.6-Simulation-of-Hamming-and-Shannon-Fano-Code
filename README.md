# EXP.NO.6-Simulation-of-Hamming-and-Shannon-Fano-Code
6. Simulation of Hamming and Shannon-Fano Code

# AIM
To apply Huffman and Shannon-Fano to the discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} using python.

# SOFTWARE REQUIRED
Google Colab

# ALGORITHMS
   1. Input the number of samples (n) and for each sample:
      - Enter the probability of the sample (p[i]).
      - Enter the length of the codeword (lk[i]).
   2. Calculate Average Length (L):
      - Sum the product of each probability and its corresponding codeword length.
   3. Calculate Entropy (hs):
      - Sum the entropy for each sample using p[i] * log2(1 / p[i]).
   4. Calculate Efficiency (eff):
      - Divide entropy (hs) by the average codeword length (L).
   5. Calculate Redundancy (red):
      - Subtract efficiency from 1.
   6. Calculate Variance (var):
      - Sum the variance for each sample using p[i] * (lk[i] - L)^2.
   7. Output the values for average codeword length (L), entropy (hs), efficiency (eff), redundancy (red), and variance (var).

# PROGRAM
    import numpy as np
    import math 
    L  = 0
    hs = 0
    p = []
    lk = []
    n = int(input("Enter the number of Samples : "))
    for i in range (n): 
        pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
        p.append(pr)
    for j in range (n): 
        l = float(input(f"Enter the length of the sample values {j + 1}: "))  
        lk.append(l)
    # Avg length of the code word
    for k in range (n):
        Avg1 = p[k] * lk[k]
        L = L + Avg1
    # Entropy
    for k in range (n):
        e = p[k] * math.log(1 / p[k], 2)
        hs = hs + e
        hs = round(hs,3)
    # Efficiency
    eff =  hs / L
    eff = round(eff,3)
    # Redundancy 
    red =  round(1 - eff,3) 
    # Variance
    var = 0
    for k in range(n):
        var1 = p[k] * (lk[k]-L)**2
        var = var + var1
    var = round(var,3)
    print(f"Average Codeword Length is : {L}")
    print(f"Entropy is : {hs}")
    print(f"Efficiency is : {eff}")
    print(f"Redudancy is : {red}")
    print(f"Variance is : {var}")



# OUTPUT
![image](https://github.com/user-attachments/assets/1cf7f360-211b-45f8-b4d1-24c71b20dcf7)

 
# RESULT
Thus, the Huffman and Shannon-Fano coding techniques have been successfully applied to the given source. The average codeword length, entropy, efficiency, redundancy, and variance have been computed.

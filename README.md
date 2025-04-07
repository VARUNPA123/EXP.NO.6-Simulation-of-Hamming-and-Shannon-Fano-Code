# EXP.NO.6-Simulation-of-Hamming-and-Shannon-Fano-Code
6. Simulation of Hamming and Shannon-Fano Code

# AIM

# SOFTWARE REQUIRED

# ALGORITHMS


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

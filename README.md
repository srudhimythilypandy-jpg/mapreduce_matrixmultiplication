# Exp 01 Matrix Multiplication using MapReduce

**Date:21/8/26**

# AIM:
To implement Matrix Vector Multiplication using the MapReduce programming model.
## DESIGN STEPS:

# Step 1:
Clone the repository from GitHub.

# Step 2:
Create a Python/Java project in the preferred IDE (Eclipse/IntelliJ IDEA/VS Code).

# Step 3:
Create the Python/Java program for Matrix Vector Multiplication using the MapReduce concept.

# Step 4:
Implement the **Mapper** phase to generate intermediate key-value pairs from the input matrices.

# Step 5:
Implement the **Shuffle and Sort** phase to group intermediate values based on common keys.

# Step 6:
Implement the **Reducer** phase to compute the final matrix vector multiplication results.

# Step 7:
Compile and execute the program.

# Step 8:
Verify and display the resulting product matrix.

# PROGRAM:

from collections import defaultdict

matrix = [ [1, 2, 3], [4, 5, 6], [7, 8, 9] ]

vector = [1, 2, 3]

def mapper(matrix, vector):
    mapped = []
    for i in range(len(matrix)):
        for j in range(len(matrix[0])):
            product = matrix[i][j] * vector[j]
            mapped.append((i, product)) 
    return mapped

def reducer(mapped_data):
    result = defaultdict(int)
    for key, value in mapped_data:
        result[key] += value
    return result

mapped = mapper(matrix, vector)
reduced = reducer(mapped)

print("Mapped Output:")
for item in mapped:
    print(item)

print("\nFinal Result (Matrix × Vector):")
for row in sorted(reduced):
    print(f"Row {row}: {reduced[row]}")

# OUTPUT:

<img width="755" height="167" alt="Screenshot 2026-08-21 113336" src="https://github.com/user-attachments/assets/b8b7a5d2-9654-4968-b821-4b2d452a42db" />
<img width="496" height="62" alt="Screenshot 2026-08-21 113421" src="https://github.com/user-attachments/assets/36e1e949-05a5-4143-bcf4-fe5666cad2a5" />



# RESULT:

The Matrix Multiplication using the MapReduce programming model was implemented successfully, and the resultant matrix was computed correctly.

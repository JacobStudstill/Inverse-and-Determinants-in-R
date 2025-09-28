# Inverse-and-Determinants-in-R

A <- matrix(1:100,  nrow = 10)

B <- matrix(1:1000, nrow = 10)

dim(A)  

# should be 10 × 10

dim(B)  

# 10 × 100 — not square

<img width="310" height="142" alt="image" src="https://github.com/user-attachments/assets/9818a603-1145-42da-9628-43d4346085a0" />


# For A
invA <- solve(A)

<img width="524" height="80" alt="image" src="https://github.com/user-attachments/assets/907667c3-5180-4978-8da6-a13560caf3dc" />

The first error we come to is trying to use "solve" on A which will find the inverse of the dimension. This doesn't work on a square because the dimensions are equal to each other so the values can't be inversed. So the inverse comes back with an error.

The next command checks if the determinant of a square matrix. The value returned is 0 which means that detA is a square matrix and it's singular. 

detA <- det(A)

<img width="554" height="79" alt="image" src="https://github.com/user-attachments/assets/9cbfecde-785c-4e49-a08f-23c0be12dc01" />



# For B, use tryCatch to capture errors
invB <- tryCatch(solve(B), error = function(e) e)

detB <- tryCatch(det(B),   error = function(e) e)


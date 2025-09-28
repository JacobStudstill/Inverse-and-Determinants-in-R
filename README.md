# Inverse-and-Determinants-in-R

A <- matrix(1:100,  nrow = 10)
B <- matrix(1:1000, nrow = 10)

dim(A)  # should be 10 × 10
dim(B)  # 10 × 100 — not square

# For A
invA <- solve(A)
<img width="524" height="80" alt="image" src="https://github.com/user-attachments/assets/907667c3-5180-4978-8da6-a13560caf3dc" />
The first error we come to is trying to use "solve" on A which will find the inverse of the dimension. This doesn't work on a square because the dimensions are equal to each other so the values can't be inversed. So the inverse comes back with an error.
detA <- det(A)


# For B, use tryCatch to capture errors
invB <- tryCatch(solve(B), error = function(e) e)

detB <- tryCatch(det(B),   error = function(e) e)


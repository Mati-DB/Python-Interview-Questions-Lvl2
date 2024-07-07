
# Factorial Trailing Zeroes [Microsoft]
Please note that all the information regarding the case study has been sourced from the following [link](https://datalemur.com/questions/python-factorial-trailing-zeroes).

## Index
 - [Interview Question](#Interview-Question)
 - [Solution](#Solution)

***

## Interview Question
Before, you work on this question, make sure you've solved the easier warmup problem [Factorial Formula](https://github.com/Mati-DB/Python-Interview-Questions/blob/main/Factorial%20Function%20%5BMicrosoft%5D.md), where you need to write a function to compute 𝑛 factorial as follows:

𝑛! = 𝑛 ∗ (𝑛−1) ∗ (𝑛−2) ∗ ... * 2 ∗ 1.

Now that you know the factorial formula, let's write a function that returns the number of trailing zeroes in n!.

For example, for 5!, we'd return 1, because 5! = 5 ∗ 4 ∗ 3 ∗ 2 ∗ 1 = 120 and 120 has exactly 1 trailing zero.

For 10!, which evaluates to 3628800 we'd return 2, becuase there are two trailing zeroes.
***

## Solution

```python
def trailing_zeroes(n):

    # Define a nested function that calculates the factorial of n
    def factorial(n):

        # Initialize x to 1 to start the factorial calculation
        x = 1

        # Loop from 1 to n (inclusive) to calculate n!
        for i in range(1,n+1):
            x = x * i
            
        # Return the calculated factorial    
        return x

    # Calculate the factorial of n using the nested function
    x = factorial(n)
    
    # Initialize a counter for the number of trailing zeros
    trailing_zeroes_counter = 0
    
    # Initialize a variable for the power of 10
    a = 1
    
    # Loop while the number is a multiple of 10
    while x % (10 ** a) == 0:
        
        # Increment the trailing zeros counter
        trailing_zeroes_counter += 1
        
        # Increment the power of 10
        a += 1
        
    # Return the total number of trailing zeros    
    return trailing_zeroes_counter
    
```

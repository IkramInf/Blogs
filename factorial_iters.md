### Factorial

__Formula:__ $n! = n * (n-1) * (n-2) * ... * 1$<br>
$\implies n! = n * (n-1)!$<br>
$\implies n! = n * (n-1) * (n-2)!$<br>
$\implies n! = n * (n-1) * (n-2) * (n-3)!$<br>

Do you see any pattern in this? It repeteadly multiplies $n$ with $(n-1)!$.

__Implementation:__
If we want to implement it, we need to think about the recursive formula and the base condition at first. The formula is given above. Now, proceed to define base condition.  
We know factorial is not possible for negative numbers and $0! = 1$ and $1! = 1$.  

We need to calculate factorial(n). Let's define the function step by step.  

__Step 1: Define the Recursive Formula (Recursive Case)__  

```python
def factorial(n):
    return n * factorial(n - 1)  # recursive formula
```

__Step 2: Add the Base Condition (Stopping Condition)__  

```python
def factorial(n):
    if n in [0, 1]:  # base condition
        return 1
    return n * factorial(n - 1)  # recursive formula
```

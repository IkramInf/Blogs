### Now, let's focus on how it works!

##### **1<sup>st</sup> Iteration:**  
When calling `factorial(5)`, the function checks the base condition. Since `n = 5` does not satisfy the base condition, it moves to the next step.  
It encounters `n * factorial(n - 1)`, so a **new frame** is pushed onto the stack, containing the function name, argument `n = 5`, and the return address. The function then calls itself recursively with `n = 4`.  

The **call stack** follows the **Last In, First Out (LIFO)** rule.  

##### **2<sup>nd</sup> Iteration:**  
The function checks the base condition again. Since `n = 4` does not satisfy it, a **new frame** is pushed onto the stack with `n = 4`, and the function calls itself recursively with `n = 3`.  

##### **3<sup>rd</sup> Iteration:**  
The function checks the base condition again. Since `n = 3` does not satisfy it, a **new frame** is pushed onto the stack with `n = 3`, and the function calls itself recursively with `n = 2`.  

##### **4<sup>th</sup> Iteration:**  
The function checks the base condition again. Since `n = 2` does not satisfy it, a **new frame** is pushed onto the stack with `n = 2`, and the function calls itself recursively with `n = 1`.  

##### **5<sup>th</sup> Iteration (Base Case Reached):**  
The function checks the base condition, and since `n = 1` satisfies it, it returns `1`. The topmost frame is **popped** from the stack, and control returns to the previous function frame (`n = 2`).  

---

##### **Stack Unwinding (Returning Values):**  
Now, the stored frames start returning and multiplying in reverse order:  

$$
factorial(1) = 1
\to
factorial(2) = 2 \times factorial(1) = 2 \times 1 = 2
\to
factorial(3) = 3 \times factorial(2) = 3 \times 2 = 6
\to
$$
$$
factorial(4) = 4 \times factorial(3) = 4 \times 6 = 24
\to
factorial(5) = 5 \times factorial(4) = 5 \times 24 = 120
$$

i.e., $$
1 (base\ case) \to 2 \times 1 \to 3 \times 2 \to 4 \times 6 \to 5 \times 24 \to 120
$$

Each time a function returns, its **frame is popped from the stack**, and execution resumes in the previous frame.  

Thus, the final output is **120**.  

Look at the output of the below code to understand it better:

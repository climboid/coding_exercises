**Answer:**
```python
def calculate_positive_average(numbers):
    positive_numbers = [num for num in numbers if num > 0]

    if len(positive_numbers) > 0:
        average = sum(positive_numbers) / len(positive_numbers)
        return average
    else:
        return "No positive numbers in the list."

input_numbers = [1, -2, 3, -4, 5]
result = calculate_positive_average(input_numbers)
print(result)
```
**Answer:**
```python
def fibonacci_recursive(n):
    if n <= 0:
        return 0
    elif n == 1:
        return 1
    else:
        return fibonacci_recursive(n - 1) + fibonacci_recursive(n - 2)

n = 10  # Change n to the desired Fibonacci number index
result = fibonacci_recursive(n)
print(f"The {n}-th Fibonacci number is {result}.")
```

**Answer:**
```python
def longest_increasing_subsequence(nums):
    if not nums:
        return []

    n = len(nums)
    lis = [1] * n

    for i in range(1, n):
        for j in range(0, i):
            if nums[i] > nums[j] and lis[i] < lis[j] + 1:
                lis[i] = lis[j] + 1

    max_length = max(lis)
    sequence = []

    for i in range(n - 1, -1, -1):
        if lis[i] == max_length:
            sequence.append(nums[i])
            max_length -= 1

    sequence.reverse()
    return sequence

input_numbers = [10, 22, 9, 33, 21, 50, 41, 60, 80]
result = longest_increasing_subsequence(input_numbers)
print("Longest Increasing Subsequence:", result)
```

These Python exercises cover a range of topics, from lists and loops to recursion, and advanced data structures and algorithms. You can adjust the input data as needed.
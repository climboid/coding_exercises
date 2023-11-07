**Answer:**
```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))

current_year = 2023
years_to_100 = 100 - age
year_of_100 = current_year + years_to_100

print(f"Hello, {name}! You will turn 100 years old in the year {year_of_100}.")
```

**Answer:**
```python
def filter_even_numbers(numbers):
    return [num for num in numbers if num % 2 == 0]

input_numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
even_numbers = filter_even_numbers(input_numbers)
print(even_numbers)
```

**Answer:**
```python
from collections import Counter

def character_frequency(string):
    # Convert the string to lowercase for case-insensitive counting
    string = string.lower()
    # Use Counter to count character frequency
    char_count = Counter(string)
    # Sort by frequency in descending order
    sorted_count = sorted(char_count.items(), key=lambda x: x[1], reverse=True)
    return sorted_count

input_string = "Hello, World!"
result = character_frequency(input_string)

for char, count in result:
    if char.isalpha():
        print(f"'{char}': {count}")
```

These Python exercises cover a range of topics, from basic input and output to list comprehensions, functions, and advanced string manipulation. You can adjust the input data as needed.
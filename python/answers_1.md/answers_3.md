**Answer:**
```python
import re
from collections import Counter

def find_top_frequent_words(filename):
    with open(filename, 'r') as file:
        text = file.read().lower()  # Read the file and convert to lowercase
        words = re.findall(r'\b\w+\b', text)  # Extract words

        # Common words to ignore
        common_words = set(['the', 'and', 'is', 'in', 'it', 'to', 'of', 'for', 'with', 'as'])

        # Count word frequencies
        word_counts = Counter(word for word in words if word not in common_words)

        # Find the top 10 frequent words
        top_words = word_counts.most_common(10)

        return top_words

filename = 'bigdata.txt'  # Replace with your file path
top_words = find_top_frequent_words(filename)

for word, count in top_words:
    print(f"{word}: {count} times")
```

**Answer:**
```python
def longest_common_subsequence(str1, str2):
    m, n = len(str1), len(str2)
    dp = [[0] * (n + 1) for _ in range(m + 1)]

    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if str1[i - 1] == str2[j - 1]:
                dp[i][j] = dp[i - 1][j - 1] + 1
            else:
                dp[i][j] = max(dp[i - 1][j], dp[i][j - 1])

    return dp[m][n]

str1 = "ABCD"
str2 = "ACDF"
result = longest_common_subsequence(str1, str2)
print("Length of the Longest Common Subsequence:", result)
```
**Answer:**
Solving the Traveling Salesman Problem is a complex task and involves combinatorial optimization algorithms. Here's a simplified solution using the `itertools` library to generate all permutations of city orders and calculate the total distance for each permutation:

```python
import itertools

def calculate_total_distance(order, distances):
    total_distance = 0
    for i in range(len(order) - 1):
        total_distance += distances[order[i]][order[i + 1]]
    total_distance += distances[order[-1]][order[0]]
    return total_distance

def solve_tsp(cities, distances):
    num_cities = len(cities)
    shortest_distance = float('inf')
    best_order = []

    for order in itertools.permutations(range(num_cities)):
        distance = calculate_total_distance(order, distances)
        if distance < shortest_distance:
            shortest_distance = distance
            best_order = order

    best_route = [cities[i] for i in best_order]  # Reorder the cities

    return best_route, shortest_distance

# Example usage
cities = ["A", "B", "C", "D"]
distances = [
    [0, 10, 15, 20],
    [10, 0, 35, 25],
    [15, 35, 0, 30],
    [20, 25, 30, 0]
]

best_route, shortest_distance = solve_tsp(cities, distances)
print("Best Route:", best_route)
print("Shortest Distance:", shortest_distance)
```

Please note that solving TSP optimally for a large number of cities is computationally expensive, and more efficient algorithms like the traveling salesman heuristics are typically used in practice.
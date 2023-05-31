## Longest Common Substring

### Introduction:

The Longest Common Substring problem is a classic computer science problem that involves finding the longest substring that is common to two or more given strings. A substring is a contiguous sequence of characters within a string.

### Algorithm:

1. Begin with two or more strings for which the longest common substring needs to be found.
2. Initialize a variable to hold the longest common substring and set it to an empty string.
3. Iterate over all possible pairs of positions (i, j) where i represents a position in the first string and j represents a position in the second string.
4. For each pair (i, j), check if the characters at positions i and j in both strings are equal.
5. If the characters are equal, extend the current common substring by appending the character and move to the next pair of positions (i+1, j+1).
6. If the characters are not equal, reset the current common substring to an empty string and move to the next pair of positions (i+1, j+1).
7. Keep track of the longest common substring found so far during the iteration.
8. After exploring all possible pairs of positions, the variable holding the longest common substring will contain the desired result.

### Code Example (Python):

```python
def longest_common_substring(str1, str2):
    m, n = len(str1), len(str2)
    longest = ''
    current = ''

    for i in range(m):
        for j in range(n):
            if str1[i] == str2[j]:
                current += str1[i]
                i += 1
                j += 1

                while i < m and j < n and str1[i] == str2[j]:
                    current += str1[i]
                    i += 1
                    j += 1

                if len(current) > len(longest):
                    longest = current

                current = ''
            else:
                current = ''

    return longest
```

### Example Usage:

```python
str1 = "abcdef"
str2 = "defghij"

longest_substring = longest_common_substring(str1, str2)

print("Longest Common Substring:", longest_substring)
```

### Explanation:

The algorithm for finding the longest common substring follows these steps:

- **Initialization**: Initialize two variables, `longest` and `current`, to hold the longest common substring and the current common substring, respectively. Set both variables to empty strings.

- **Iterative Process**: Iterate over all possible pairs of positions (i, j) in the given strings. Compare the characters at the corresponding positions in both strings.

- **Matching Characters**: If the characters at positions i and j are equal, extend the current common substring by appending the character and move to the next pair of positions (i+1, j+1).

- **Non-Matching Characters**: If the characters are not equal, reset the current common substring to an empty string and move to the next pair of positions (i+1, j+1).

- **Tracking the Longest Substring**: Keep track of the longest common substring found so far during the iteration. Update the `longest` variable if the length of the current common substring exceeds the length of the current longest common substring.

- **Termination**: After exploring all possible pairs of positions, the `longest` variable will hold the longest common substring found.

### Time Complexity:

The time complexity of the Longest Common Substring algorithm is O(m \* n), where m and n are the lengths of the input strings. The algorithm iterates over all possible pairs of positions in the strings

to find the longest common substring.

### Space Complexity:

The space complexity of the Longest Common Substring algorithm is O(1) since the algorithm does not require any additional space that grows with the input size. It uses a constant amount of space to store the `longest` and `current` variables.

The Longest Common Substring problem has applications in various domains, such as bioinformatics, text analysis, and plagiarism detection. Understanding its algorithm allows for efficient identification of common patterns within strings and can be useful in solving related string manipulation problems.

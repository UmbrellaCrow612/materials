## String Matching

### Introduction:

String Matching is a fundamental problem in computer science that involves finding occurrences of a pattern within a larger text or string. The goal is to determine the positions or indices where the pattern appears in the text.

### Algorithm:

There are various algorithms for string matching, with the most well-known one being the Knuth-Morris-Pratt (KMP) algorithm. The KMP algorithm utilizes a prefix function to avoid unnecessary comparisons.

1. Construct the prefix table for the pattern. The prefix table stores the length of the longest proper prefix of the pattern that is also a suffix.

2. Iterate through the text and the pattern:

   - If the characters at the current positions match, increment both pointers.
   - If a mismatch occurs, update the pattern pointer based on the prefix table:
     - If the prefix function value is non-zero, move the pattern pointer to the position indicated by the prefix table.
     - If the prefix function value is zero, increment the text pointer.

3. Repeat steps 2 until the end of the text or a full match of the pattern is found.

4. If a full match is found, record the position or index where the match starts.

5. Continue searching for other occurrences of the pattern by resuming the process from the last mismatch position.

6. Repeat steps 2-5 until the entire text has been processed.

### Code Example (Python):

```python
def build_prefix_table(pattern):
    m = len(pattern)
    prefix_table = [0] * m
    length = 0
    i = 1

    while i < m:
        if pattern[i] == pattern[length]:
            length += 1
            prefix_table[i] = length
            i += 1
        else:
            if length != 0:
                length = prefix_table[length - 1]
            else:
                prefix_table[i] = 0
                i += 1

    return prefix_table

def string_matching(text, pattern):
    n = len(text)
    m = len(pattern)
    prefix_table = build_prefix_table(pattern)
    matches = []

    i = 0
    j = 0
    while i < n:
        if pattern[j] == text[i]:
            i += 1
            j += 1

            if j == m:
                matches.append(i - j)
                j = prefix_table[j - 1]
        else:
            if j != 0:
                j = prefix_table[j - 1]
            else:
                i += 1

    return matches
```

### Example Usage:

```python
text = "ABCABCDABABCDABCDABDE"
pattern = "ABCDABD"

matches = string_matching(text, pattern)
print("Pattern matches found at positions:", matches)
```

### Explanation:

The String Matching algorithm, specifically the Knuth-Morris-Pratt (KMP) algorithm, follows these steps:

- **Prefix Table Construction**: Construct the prefix table for the pattern. The prefix table stores the length of the longest proper prefix of the pattern that is also a suffix. It helps in avoiding unnecessary comparisons during the matching process.

- **Iterating and Matching**: Iterate through the text and pattern, comparing characters at the current positions. If the characters match, increment both pointers. If a mismatch occurs, update the pattern pointer based on the prefix table. If the prefix function value is non-zero, move the pattern pointer to the position indicated by the prefix table. If the prefix function value is zero, increment the text pointer.

- **Full Match Recording**: If a full match is found, record the position or index where

the match starts. This information is stored in a list called `matches`.

- **Continuing the Search**: Continue searching for other occurrences of the pattern by resuming the process from the last mismatch position. Repeat the iteration and matching process until the entire text has been processed.

The provided code example demonstrates a basic implementation of the KMP algorithm for string matching in Python. The `build_prefix_table` function constructs the prefix table for the given pattern. The `string_matching` function takes the text and pattern as input and returns a list of positions where the pattern matches. It utilizes the prefix table to efficiently search for matches in the text.

In the example usage, the algorithm is applied to find occurrences of the pattern "ABCDABD" in the text "ABCABCDABABCDABCDABDE". The positions where the pattern matches are printed as output.

Understanding the String Matching algorithm enables efficient searching and pattern recognition in various applications, such as text processing, information retrieval, bioinformatics, and more.

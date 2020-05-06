# python-Rabin-Karps-Algorithm-longest-common-substring
This Python program finds the longest common substring, using Rabin-Karp’s Algorithm.
The input is two strings separated by a space.
The output is 3 integers:
i) the starting position in the first string, of the longest common substring
ii) the starting position in the second string, of the longest common substring
iii) the length of the longest common substring

Rabin-Karp’s Algorithm compares substrings by comparing their polynomial hashcodes, rather than character-by-character.
Hashcode computations leverage the similarity of the polynomial hash functions of substrings of the same length in a string.
The hashcode computations are performed for only the substring lengths that occur in a binary search of the substring length.
For each recursive pass of the binary search, for the substring length of that precursive pass, for each prime number any hashcodes are found that match between substrings of the two strings.
Before each time that a match is checked, a dictionary is created with keys being the hashcodes and the values being the beginning positions of the substrings in both strings. 
To find the longest length of the longest matching substring, the binary search starts with half the length of the shorter string.
If a match results from the first recursive pass of the binary search, then the next recursive pass uses a larger length.
If no match results from the first recursive pass of the binary search, then the next recursive pass uses a shorter length.
The result of the binary search is the result from the next-to-final pass. 
If the binary search results in a length of zero with any of the prime numbers, the final answer is no match.
If the binary searches with different prime numbers results in different lengths of the longest common substring,
the binary search is repeated with the minimum length.
If no match with different prime numbers still results, the binary search is performed repeatedly, decrementing the length by one each time.

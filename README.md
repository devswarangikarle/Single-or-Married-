# Single-or-Married-

In a distant kingdom, Prince Aryan is the only unmarried heir of his royal family. Eager to see him wed, his relatives keep suggesting potential brides. But Aryan has a secret desire to remain single. To avoid marriage, he devises a clever plan: he declares that he will only marry if the name of the person recommending the bride is a subsequence of the bride's name, or vice versa.
Now, the kingdom awaits - will Prince Aryan outsmart his family and remain single, or will they find him a match? Your task is to find out.

def is_subsequence(small, large):

    """Check if 'small' is a subsequence of 'large'."""
    i, j = 0, 0
    while i < len(small) and j < len(large):
        if small[i] == large[j]:
            i += 1
        j += 1
    return i == len(small)

def single_or_married(test_cases):

    results = []
    for R, G in test_cases:
        if is_subsequence(R, G) or is_subsequence(G, R):
            results.append("#SadLife")
        else:
            results.append("#DieSingle")
    return results

T = int(input().strip())
test_cases = [input().strip().split() for _ in range(T)]
results = single_or_married(test_cases)

print("\n".join(results))

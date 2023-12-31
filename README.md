# Largest-Substring-Between-Two-Equal-Characters

class Solution:
    def maxLengthBetweenEqualCharacters(self, s):
        last_index = {}
        max_distance = -1

        for i, char in enumerate(s):
            if char in last_index:
                max_distance = max(max_distance, i - last_index[char] - 1)
            else:
                last_index[char] = i

        return max_distance

# Example usage:
solution = Solution()

s1 = "aa"
output1 = solution.maxLengthBetweenEqualCharacters(s1)
print(output1)  # Output: 0

s2 = "abca"
output2 = solution.maxLengthBetweenEqualCharacters(s2)
print(output2)  # Output: 2

s3 = "cbzxy"
output3 = solution.maxLengthBetweenEqualCharacters(s3)
print(output3)  # Output: -1

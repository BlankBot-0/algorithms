#arrays

+ [Subarray Sum Equals k](#subarray-sum-equals-k)

## Subarray Sum Equals k

https://leetcode.com/problems/subarray-sum-equals-k/

```python
def subarraySum(self, nums: List[int], k: int) -> int:
    if not nums:
        return 0
    count = collections.Counter()
    count[0] = 1
    ans = summ = 0
    for num in nums:
        summ += num
        ans += count[summ-k]
        count[summ] += 1
    return ans

```
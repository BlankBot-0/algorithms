#arrays

+[Two sum](#two-sum)
+[3sum](#3sum)
+[Subarray sum equals k](#subarray-sum-equals-k)

## Two sum

https://leetcode.com/problems/two-sum

'''python
def twoSum(self, nums: List[int], target: int) -> List[int]:
    passed = {}
    i = -1
    for num in nums:
        i += 1
        if target - num in passed:
            return [passed[target-num], i]
        else:
            passed[num] = i
    return []

'''

## 3sum

https://leetcode.com/problems/3sum

'''python
#code
'''

## Subarray sum equals k

https://leetcode.com/problems/subarray-sum-equals-k/

'''python
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

'''
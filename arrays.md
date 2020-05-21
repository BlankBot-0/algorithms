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
#code
'''
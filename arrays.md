#arrays

+ [Two sum](#two-sum)

## Two sum

https://leetcode.com/problems/two-sum

```python
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

```

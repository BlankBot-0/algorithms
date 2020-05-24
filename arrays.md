#arrays

+ [3sum](#3sum)

## 3sum

https://leetcode.com/problems/3sum/

```python
def threeSum(self, nums: List[int]) -> List[List[int]]:
    triplets = []
    nums.sort()
    if len(nums) < 3:
        return triplets
    for i in range(len(nums) - 2):
        if i > 0 and nums[i] == nums[i-1]:
            continue
        left, right = i + 1, len(nums) - 1
        while left < right:
            summ = nums[i] + nums[left] + nums[right]
            if summ == 0:
                triplets.append([nums[i], nums[left], nums[right]])
                left += 1
                right -= 1
                while left < right and nums[left] == nums[left - 1]:
                    left += 1
                while left < right and nums[right] == nums[right + 1]:
                    right -= 1
            elif summ < 0:
                left += 1
            else:
                right -= 1
    return triplets

```
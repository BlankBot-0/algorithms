#intervals

+[Insert Interval](#insert-interval)
+[Merge Intervals](#merge-intervals)
+[Non-overlapping Intervals](#non-overlapping-intervals)

## Insert Interval

https://leetcode.com/problems/insert-interval/

'''python
#code
'''

## Merge Intervals

https://leetcode.com/problems/merge-intervals/

'''python
#code
'''

## Non-overlapping Intervals

https://leetcode.com/problems/non-overlapping-intervals

'''python
def eraseOverlapIntervals(self, intervals: List[List[int]]) -> int:
    edge = float('-inf')
    erased = 0
    for left, right in sorted(intervals, key=lambda line: line[1]):
        if left < edge:
            erased += 1
        else:
            edge = right
    return erased

'''
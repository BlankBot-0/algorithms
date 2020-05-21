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
def merge(self, intervals: List[List[int]]) -> List[List[int]]:
    if not intervals:
        return []
    intervals.sort(key=lambda key: key[0])
    merged = [intervals[0]]
    for inter in intervals[1:]:
        edge = merged[-1]
        if inter[0] > edge[1]:
            merged.append(inter)
        else:
            merged[-1][1] = max(edge[1], inter[1])
    return merged

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
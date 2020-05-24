# intervals

+ [Merge Intervals](#merge-intervals)

## Merge Intervals

https://leetcode.com/problems/merge-intervals/

```python
def merge(self, intervals: List[List[int]]) -> List[List[int]]:
    if not intervals:
        return []
    intervals.sort(key=lambda start: start[0])
    merged = [intervals[0]]
    for interval in intervals[1:]:
        edge = merged[-1]
        if interval[0] > edge[1]:
            merged.append(interval)
        else:
            merged[-1][1] = max(edge[1], interval[1])
    return merged

```
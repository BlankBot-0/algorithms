#intervals

+ [Merge Intervals](#merge-intervals)

## Merge Intervals

https://leetcode.com/problems/merge-intervals/

```python
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

```

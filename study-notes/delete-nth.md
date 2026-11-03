# Study Note: Delete Nth Occurrence

## Goal

Keep at most `n` occurrences of each value in a list, preserving the original order. The function builds and returns a new list; it does not modify the input list.

Example: with `[1, 2, 3, 1, 2, 1, 2, 3]` and `n = 2`, the result is `[1, 2, 3, 1, 2, 3]`.

## How the optimized loop works

```python
result = []
counts = collections.defaultdict(int)

for element in array:
    if counts[element] < n:
        result.append(element)
        counts[element] += 1

return result
```

For each element, `counts[element]` tells how many copies of that value have been kept so far. If that count is less than `n`, the function appends the value to `result` and increments its count. Otherwise, the `if` body is skipped and the `for` loop continues with the next element. A skipped value does not change its count.

## `defaultdict(int)`

`collections.defaultdict(int)` is a dictionary whose missing keys are initialized by calling `int()`. Since `int()` returns `0`, the first lookup of a value starts its count at zero. This avoids checking whether the key already exists.

The argument to `defaultdict` must be a callable, not a literal value. For example, `defaultdict(lambda: 3)` supplies `3` for missing keys. `defaultdict(3)` raises a `TypeError` when it tries to call `3`.

## What `counts` contains at the end

It contains the number of copies of each value that were kept—not the total number encountered. Every count is at most `n`. For `[1, 2, 1, 1]` with `n = 2`, the result is `[1, 2, 1]` and the final counts are `{1: 2, 2: 1}`. The dictionary is local to the function and is not returned.

## Complexity and edge cases

- Optimized version: O(length of input) average time, with O(number of distinct values) auxiliary count storage, plus the output list.
- Naive version using `result.count()` repeatedly: O(length of input squared) time.
- If `n` is zero or negative, no elements are kept, so the result is empty.

## Key takeaway

Use a dictionary to track how many times each value has been accepted so far. Keep the value while its count is below the limit; otherwise skip it and continue.

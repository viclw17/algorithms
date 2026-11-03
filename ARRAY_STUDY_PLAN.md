# Array Algorithms Study Plan

A practical study plan for the [`algorithms/array`](algorithms/array/) folder. The goal is to learn reusable problem-solving patterns—not just memorize implementations.

## Suggested learning path

### 1. Array fundamentals
Start with list behavior, indexing, counting, and in-place updates:

- `algorithms/array/move_zeros.py`
- `algorithms/array/remove_duplicates.py`
- `algorithms/array/delete_nth.py`
- `algorithms/array/top_1.py`
- `algorithms/array/limit.py`
- `algorithms/array/plus_one.py`

As you work through these, compare in-place changes with approaches that build a new list, and note the time and space costs.

### 2. Search, counting, and range patterns
Next, practice hash maps, sorted scans, two pointers, and range logic:

- `algorithms/array/two_sum.py`
- `algorithms/array/three_sum.py`
- `algorithms/array/n_sum.py`
- `algorithms/array/max_ones_index.py`
- `algorithms/array/missing_ranges.py`
- `algorithms/array/summarize_ranges.py`
- `algorithms/array/merge_intervals.py`

Pay attention to assumptions such as sorted input, duplicate handling, and boundary conditions.

### 3. More involved sequence problems
Combine techniques and reason carefully about state and indexing:

- `algorithms/array/longest_non_repeat.py` — sliding window and duplicate tracking
- `algorithms/array/rotate.py` — array rearrangement and in-place techniques
- `algorithms/array/flatten.py` — nested sequences and iteration
- `algorithms/array/trimmean.py` — sorting and aggregate calculations
- `algorithms/array/garage.py` — state and array modeling
- `algorithms/array/josephus.py` — circular indexing and elimination

## Two-week schedule

### Week 1: Fundamentals

| Day | Study |
| --- | --- |
| 1 | `move_zeros.py`, `remove_duplicates.py` |
| 2 | `delete_nth.py`, `limit.py` |
| 3 | `top_1.py`, `plus_one.py` |
| 4 | `rotate.py`, `flatten.py` |
| 5 | Reimplement three studied problems from memory; compare approaches and complexity |
| 6 | `trimmean.py`, `max_ones_index.py` |
| 7 | Review the week and explain each solution’s time and space complexity |

### Week 2: Search, ranges, and advanced patterns

| Day | Study |
| --- | --- |
| 8 | `two_sum.py`, `three_sum.py` |
| 9 | `n_sum.py` |
| 10 | `missing_ranges.py`, `summarize_ranges.py` |
| 11 | `merge_intervals.py` |
| 12 | `longest_non_repeat.py` |
| 13 | `josephus.py`, `garage.py` |
| 14 | Revisit difficult problems and solve a selection without looking at the code |

## How to study each problem

1. Read the implementation and identify the problem it solves.
2. Record the input/output shape and any assumptions.
3. Work through a normal case, an edge case, and an empty or minimal input where applicable.
4. Identify the core technique and explain why it fits.
5. Estimate time and space complexity.
6. Reimplement the solution without looking, then compare it with the repository version.
7. Write down any useful alternative approach or pitfall.

## Patterns to recognize

- Hash map lookup
- Two pointers
- Sliding window
- Sorting followed by scanning
- Interval merging
- Range summarization
- Cyclic indexing
- In-place mutation
- Building a result list versus modifying the input

## Difficulty guide

**Good warm-ups:** `move_zeros.py`, `remove_duplicates.py`, `delete_nth.py`, `top_1.py`, `limit.py`, `plus_one.py`

**Intermediate practice:** `two_sum.py`, `three_sum.py`, `missing_ranges.py`, `summarize_ranges.py`, `rotate.py`, `flatten.py`, `trimmean.py`

**More challenging/review carefully:** `n_sum.py`, `merge_intervals.py`, `longest_non_repeat.py`, `max_ones_index.py`, `josephus.py`, `garage.py`

## Completion goal

For each problem, be able to describe the approach, justify its complexity, and implement it from memory. Focus on recognizing the underlying pattern so you can apply it to new problems.
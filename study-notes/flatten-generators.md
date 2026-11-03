# Study Note: Python Generators and Flattening Nested Iterables

## What is a generator?

A generator produces values one at a time instead of creating and returning an entire collection at once. In Python, a function becomes a generator when it uses `yield`. Calling the function returns a generator object; iterating over it runs the function until the next `yield`, then pauses until another value is requested.

## Why use a generator for flattening?

A regular flattening function builds and returns a complete list. A generator-based version can produce each flattened value as needed, which is useful when:

- The input is large and keeping the entire output list in memory is undesirable.
- Values can be processed as a stream.
- The caller may stop before consuming every value.

You can collect all generated values into a list with `list(flatten_iter(...))` when needed.

## How `flatten_iter` works

- `yield element` emits a leaf value.
- `yield from flatten_iter(element)` recursively emits values from a nested iterable.
- Strings are excluded from recursive flattening so they are treated as single values rather than iterated character by character.

```python
for value in flatten_iter([1, [2, 3]]):
    print(value)
# 1
# 2
# 3
```

## Understanding the return annotation

```python
-> Generator[Any, None, None]
```

The three `Generator` type parameters describe:

1. `Any`: the type of values yielded.
2. `None`: the type of values sent into the generator with `.send()`.
3. `None`: the generator's final return-value type.

Here, the generator yields values of any type and has no meaningful sent or final return value.

## Key concepts

- **Recursion:** nested iterables are handled by calling the flattening logic on each nested iterable.
- **Iterable detection:** `collections.abc.Iterable` checks whether an object can be iterated over.
- **String special case:** strings are iterable, but are deliberately treated as leaf values.
- **Lazy evaluation:** generator output is produced on demand.
- **Complexity:** each element is visited once, so time is O(n), where n is the total number of elements. The list-based version stores the output; the generator version avoids storing the full flattened result itself, though recursion still uses stack space.

## Caveat

Other iterables, such as dictionaries, are flattened according to their normal iteration behavior. A dictionary yields its keys, not its values.

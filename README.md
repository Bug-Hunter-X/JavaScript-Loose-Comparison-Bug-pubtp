# JavaScript Loose Comparison Bug

This repository demonstrates a common JavaScript bug related to loose comparison (==) and its unexpected behavior when dealing with null and undefined values.

## Bug Description
The `foo` function intends to handle three cases:
1.  `x` is `null` (returns 0)
2.  `x` is negative (returns -1)
3.  `x` is non-negative (returns 1)

However, due to the use of loose comparison (`==`), the function produces an incorrect result when `x` is 0. Loose comparison treats 0 as falsy and causes the function to unexpectedly enter the else block, resulting in a return value of 1.  This behavior deviates from the expected handling of the number 0.

## Bug Solution
The solution involves replacing the loose comparison (`==`) with a strict comparison (`===`). This ensures that the function behaves correctly for all cases including `x` being 0.
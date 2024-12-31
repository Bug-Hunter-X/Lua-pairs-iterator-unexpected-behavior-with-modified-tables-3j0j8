# Lua pairs iterator unexpected behavior
This repository demonstrates a potential issue with Lua's `pairs` iterator when used with tables that are modified during iteration.  The `bug.lua` file contains code that exhibits this behavior. The `bugSolution.lua` file provides a solution using a safer iteration technique.

## Problem
The `pairs` iterator in Lua iterates over the key-value pairs of a table. However, if the table is modified during iteration (e.g., by adding or removing elements), the iterator's behavior can be unpredictable and might lead to skipped elements or even infinite loops.  This is because the iterator maintains an internal state that might become inconsistent with the modified table.

## Solution
The solution involves iterating over a copy of the table or using a different iteration method that is less sensitive to modifications during iteration. The provided solution uses a copy of the table. 
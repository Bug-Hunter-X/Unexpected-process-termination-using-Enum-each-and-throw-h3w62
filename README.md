# Elixir Enum.each and throw: Unexpected Process Termination

This example demonstrates a common issue in Elixir when using `Enum.each` with the `throw` macro.  The code intends to iterate through a list and print each element, halting execution if the number 3 is encountered.  However, the way `throw` is used can lead to unexpected process termination, making debugging more challenging. The solution shows how to handle the interruption using a `try-catch` block for a more robust solution.

## Bug
The provided `bug.exs` file shows a simple `Enum.each` function. This seemingly innocuous approach leads to the termination of the current process when the `throw` statement is executed.  This behavior isn't immediately intuitive to Elixir developers unfamiliar with its exception handling mechanisms.

## Solution
The `bugSolution.exs` file presents a corrected version that safely handles the `:three_found` exception using a `try-catch` block, allowing for graceful handling of interruption and preventing process crashes. 
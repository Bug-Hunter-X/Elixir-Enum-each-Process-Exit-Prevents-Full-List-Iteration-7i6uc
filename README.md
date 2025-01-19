# Elixir Enum.each Unexpected Termination

This repository demonstrates a subtle issue in Elixir's `Enum.each` function related to process termination inside the iterating function.  The `bug.ex` file contains code that halts iteration prematurely due to a `Process.exit` call.  The `bugSolution.ex` demonstrates a corrected approach using a different Enum function to handle the conditional termination gracefully.

The problem arises when you need to stop processing a list based on a condition, but still want to ensure that any cleanup actions or side effects are handled. Using `Process.exit` within `Enum.each` leads to unintended premature termination, potentially leaving resources unmanaged.
# Writing Code for Humans 🚶
In the vast landscape of software development, it's crucial to remember that code is primarily written for humans to read and secondarily for machines to execute. This lesson explores strategies to enhance code readability and maintainability, ensuring that it communicates its intention clearly not only to the computers but also to human developers.

## It's All Writing
Just as in any form of writing, clarity and precision are vital in code. Writing code should be treated with the same care as writing in a natural language. Consider these principles:

- **Treat English as Just Another Programming Language**: Every function, class, and variable name is an opportunity to explain your code. Use clear and descriptive names that convey purpose and intent.
- **Build Documentation In, Don't Bolt It On**: Good code documents itself through meaningful names and logical structuring. Comments and documentation should be integrated thoughtfully as part of the development process, not added as an afterthought.

## The Role of Comments
Comments in code are crucial, but they should be used wisely. Their primary role is not to describe what the code does—that's the job of the code itself—but to explain why certain decisions were made. Here are a few guidelines:

- **Explain Why, Not What**: Comments should provide insight into the rationale behind certain coding decisions and complex logic that isn't immediately apparent from the code itself.
- **Maintenance Over Time**: Remember, code is read far more often than it is written. Comments can save future developers (including your future self) time and confusion, particularly when dealing with tricky logic or why certain bugs were addressed in a particular way.

## Descriptive Names Over Comments
Whenever possible, use clear and descriptive names that make comments unnecessary. Here are some tips to help your code speak for itself:

- **Descriptive and Clear**: Choose names that reflect the variable's or function's purpose. Avoid generic names like data or info.
- **Avoid Misleading Names**: Names that are misleading can lead to confusion and errors in understanding the code's functionality. Ensure that names accurately reflect what the code element does.
- **Length Matters**: Don't shy away from longer, descriptive names if they help convey meaning more clearly. A longer name that makes a variable's purpose obvious is preferable to a cryptic short one.

## Code Smells and Maintenance
Avoid certain practices that can indicate deeper problems in the code base, known as "code smells":

- **Commented-Out Code**: Never leave commented-out code in your codebase. It can confuse and clutter the code. Instead, rely on version control systems like Git to keep a history of changes. If you need to revisit old versions of code, you can always look up your repository's history.

## Exercise: Refactoring for Readability
Given a piece of complex and poorly documented Ruby code, we'll refactor it to enhance its readability and maintainability.

### Before Refactoring:
```ruby
# Bad example: What does this method do?
def process_items(arr)
  first = arr.first
  rest = arr[1..-1]
  rest.select { |item| item > first }
end

# Call the mysterious method
result = process_items([5, 3, 9, 8])
puts result
```

Let's rename the method and variables to reflect their roles more clearly. We'll also add a comment explaining the purpose of the method since its operation isn't obvious from its name and structure.

### After Refactoring
```ruby
# Refactors the input array by filtering elements greater than the first element
def filter_items_greater_than_first(items)
  first_item = items.first
  remaining_items = items[1..-1]
  remaining_items.select { |item| item > first_item }
end

# Call the refactored method
result = filter_items_greater_than_first([5, 3, 9, 8])
puts result.inspect # Expected output: [9, 8]
```

This refactored version makes several improvements:

- **Method and Variable Names**: The method and variable names are more descriptive. `filter_items_greater_than_first` clearly describes what the method does, and `first_item` and `remaining_items` are self-explanatory.
- **Comments**: A comment is added to explain the purpose of the method, which is to filter and return elements greater than the first element of the array. This helps anyone reading the code to quickly understand the method's intent without needing to parse through the code logic.

## Conclusion
Writing code for humans is an essential skill in software development. By ensuring that your code is clear, well-documented, and maintainable, you not only make life easier for other developers but also enhance the overall quality and longevity of your software. Embrace these practices to become a better coder, collaborator and teammate.

## Resources
- [Refactoring: Improving the Design of Existing Code by Martin Fowler](https://martinfowler.com/books/refactoring.html)
- [The Art of Readable Code by Dustin Boswell, Trevor Foucher](https://www.oreilly.com/library/view/the-art-of/9781449318482/)
- [The Pragmatic Programmer, 20th Anniversary Edition
your journey to mastery by David Thomas, Andrew Hunt](https://pragprog.com/titles/tpp20/the-pragmatic-programmer-20th-anniversary-edition/)
- [Refactoring Guru](https://refactoring.guru/)

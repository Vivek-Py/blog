---
layout: post
title: What to use Let or Const?
---

You must have a seen a controversial, sparking conversations on Reddit and Twitter recently. People were debating over usage of Let and Const.

![Let vs Const Thumbnail](../images/let-vs-const.jpg)

It seems that netizens believe that one should use const wherever possible, only falling back to let where necessary, as can be enforced with the prefer-const **ESLint rule**.

> Let vs Const vs Var: We generally want to use let. If we're not using the same, we use const. (I've have seen codebases which force you to use const when there is only one assignment, same goes for some of the devs out there.)

## Why prefer `const`?

1. **Performance Benefits**: There are some claims out there which say using const makes code faster because it knows there won't be any re-assignment.

2. **One Way to Do It**: Sometimes it's a bias in our head. A rule like “always use const where it works” stop us from thinking about it and can be enforced by a linter nowadays.

3. **Reassignments May Cause Bugs**: In the long-run, there can be instances where we may forget about reassignment of the variables. Therefore, const gives you confidence you’ll always “see” the same value and there will be no bug.

4. **Learning About Mutation**: When I got started with JavaScript, I got consfused with the const & immutability. It’s important to learn the difference between variable mutation and assignment anyway, and preferring const forces you to confront this distinction early on.

## Why Not prefer `const`?

1. **Confusion with Immutability**: In every conversation over const, you'll find someone who confuses with immutability. This happens because assignment and mutation use the same `'='` operator.

2. **Pressure to Avoid Redeclaring**: A const based codebase creates a pressure to not use let for conditionally assigned variables. For example, you might write `const a = condition ? b : c` instead of an if condition, even if both b and c branches are convoluted and giving them explicit names is awkward.

3. **Loss of Intent**: If we use const everywhere, we lose the ability to clarify when something is important to not be reassigned.

## What is my Conclusion?

Well I don't have a opinion on this.

I would use whatever I need as per my situation. If you care, use a linter that automates checking and fixing this issue so that changing let to const doesn’t become a delay in code review.

Finally, remember that linters exist to serve you. Learn from your own mistakes.

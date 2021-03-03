---
layout: page
title: Cursos
has_children: true
has_toc: false
description: How to assess and evaluate code quality.
---

# Quality
{: .no_toc .mb-2 }

Use the search bar to discover guidelines and examples.
{: .fs-6 .fw-300 }

> A computer language is not just a way of getting a computer to perform operations but rather [...] a novel formal medium for expressing ideas about methodology. Thus, programs must be written for people to read, and only incidentally for machines to execute.[^1]

[^1]: Harold Abelson, Gerald Jay Sussman, Julie Sussman. 1984. "Preface to the First Edition." *Structure and Interpretation of Computer Programs.* <https://mitpress.mit.edu/sites/default/files/sicp/full-text/book/book-Z-H-7.html#%_chap_Temp_4>

In this course, we will primarily study two measures of correctness as it relates to code quality.

External correctness
: A program where the desired outcome is correctly produced by a computer.

However, external correctness is not the only criteria for determining the quality of a program.

> There are numerous ways a software project can fail: projects can be over budget, they can ship late, they can fail to be useful, or they can simply not be useful enough. Evidence clearly shows that success is highly contextual and stakeholder-dependent: success might be financial, social, physical and even emotional, suggesting that software engineering success is a multifaceted variable that cannot explained simply by user satisfaction, profitability or meeting requirements, budgets and schedules.[^2]

[^2]: Amy J. Ko. 2020. "Quality." *Cooperative Software Development.* <https://faculty.washington.edu/ajko/books/cooperative-software-development/#/quality>

> Whereas [external correctness criteria] are concerned with how software behaves technically according to specifications, some qualities concern properties of how developers interact with code:[^2]
>
> - **Verifiability** is the effort required to verify that software does what it is intended to do. For example, it is hard to verify a safety critical system without either proving it correct or testing it in a safety-critical context (which isn’t safe). Take driverless cars, for example: for Google to test their software, they’ve had to set up thousands of paid drivers to monitor and report problems on the road. In contrast, verifying that a simple static HTML web page works correctly is as simple as opening it in a browser.
> - **Maintainability** is the effort required to correct, adapt, or perfect software. This depends mostly on how comprehensible and modular an implementation is.
> - **Reusability** is the effort required to use a program’s components for purposes other than those for which it was originally designed. APIs are reusable by definition, whereas black box embedded software (like the software built into a car’s traction systems) is not.

Together, we call these criteria for how developers interact with code, "internal correctness."

Internal correctness
: A program where the desired outcome is easily understood by other human programmers.

Writing high-quality programs takes deliberate practice, so these guidelines are not meant to be memorized at first. Instead, we'll learn how to write high-quality programs through a process called **code review**, the practice of reviewing code with an eye towards code quality.

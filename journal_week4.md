# Lab Notebook Week 4
## Vishruth Narasimhan

This week marked a transition from isolated language features to comprehensive system design. Integrating generics, traits, and lifetimes felt like moving into "advanced" territory where the abstraction power of Rust becomes evident. Applying these concepts to a functional command-line tool highlighted how the compiler uses these rules to enforce safety at a level that most high-level languages simply abstract away. While the learning curve for lifetime annotations was steep, seeing them in the context of a real-world I/O project made their purpose much clearer.

## What I learned specifically

* Progressed through the advanced Rustlings modules, covering Generics, Traits, and the functional programming aspects of Iterators and Closures.

* Architected and implemented a CLI-based search tool, mirroring the core functionality of the grep utility.

* Applied modularization techniques to separate logic from the main.rs file, utilizing a lib.rs for core search functionality.

* Studied the implementation of Test-Driven Development (TDD) by writing unit tests for the search logic before implementing the code.

## What I've learned from this week of lab: 

In the Chapter 12 I/O project, I moved beyond basic scripting into proper software architecture. A major insight was the importance of Separation of Concerns. By moving the configuration logic into a Config struct and the main execution into a run function, the code became significantly easier to test and maintain. Handling environment variables (like IGNORE_CASE) also taught me how to interact with the broader operating system environment from within a Rust binary.
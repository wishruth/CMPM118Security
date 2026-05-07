# Lab Notebook Week 3
## Vishruth Narasimhan

This week’s lab felt like a significant step up in complexity as the focus shifted from basic syntax to the internal memory management that defines Rust. Moving through the core chapters of the documentation required a much more active style of learning, as concepts like the borrow checker are not just syntax rules but a completely different mental model for resource management. I found that I had to supplement the reading with external visual guides and videos like "Lets Get Rusty" to fully grasp how references move through various scopes without triggering memory violations.

## What I did specifically: 
* Progressed through the middle stages of the Rustlings suite, successfully completing exercises through section 13.
* Read through the Arrakis research paper and skimmed through it's topics
* Analyzed the implementation of custom data structures, specifically focusing on how Structs and Enums interact with Rust’s type safety.
* Studied the distinction between stack and heap allocation as it relates to the Ownership model.

## What I've learned from this week of lab: 

The transition into Chapters 4–9 of the Rust book provided a rigorous look at memory safety without a garbage collector. I’ve come to understand Ownership not just as a restriction, but as a systematic way to ensure memory is freed exactly once, eliminating common bugs like double-frees or dangling pointers. Borrowing and References initially felt like hurdles, but I now see them as a way to allow multiple parts of a program to read data efficiently while maintaining the "aliasing XOR mutation" rule—meaning I can have many readers or one writer, but never both simultaneously.

Regarding the Arrakis paper, I was particularly struck by the shift in the OS role from a "gatekeeper" to a "coordinator." Traditionally, the kernel is involved in the data path, creating a bottleneck during I/O operations due to frequent context switching. Arrakis proposes a split-level architecture where the kernel manages the control plane (setting up permissions and resource limits), but the application-level library handles the actual data movement. This allows for "Zero-copy" I/O, which is vital for high-performance applications like Redis. It highlights a fascinating trend where hardware is becoming so efficient that the primary goal of OS design is now to get the software layer out of the way of the hardware’s raw speed. 


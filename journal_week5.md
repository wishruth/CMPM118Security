# Lab Notebook Week 5
## Vishruth Narasimhan

In Week 5 of our lab, we shifted toward high-performance systems programming, focusing on how Rust manages complex memory patterns and execution models. Exploring smart pointers and concurrency felt like peering into the "engine room" of the language, where the abstraction layers meet the hardware. This week’s work was a sort of a comparison between software-level memory safety (Rust) and hardware-level safety (CHERI), providing a more broad view of modern systems security.

## What I learned specifically
* Worked on Rustlings 19-20
* Learned about using Box<T> and reference-counted shared ownership via Rc<T>
* Analyzed the CHERI (Capability Hardware Enhanced RISC Instructions) architecture, focusing on the technical specifications in Sections 1–5 and the research implications in Section 8.

## What I've learned from this week of lab: 

The study of Smart Pointers provided a deeper understanding of how Rust circumvents strict compile-time checks when necessary. I learned that RefCell<T> enables interior mutability, allowing me to mutate data even when there are immutable references to that data, by moving the borrowing rules from compile-time to runtime. For Concurrency, the "fearless" aspect of Rust became clear: the compiler uses the Send and Sync traits to ensure that data is only shared between threads when it is safe to do so, effectively preventing data races by design. I also understood Async programming a little better, viewing it not just as "fast code," but as a way to maximize resources during I/O-bound tasks by allowing the executor to switch tasks when a thread would otherwise be idle.

Reading the CHERI paper (Sections 1–5 and 8) was my first real look at CPU-level security. I learned that while we usually rely on the compiler (like Rust) to stop memory errors, CHERI builds safety directly into the processor using things called capabilities. Instead of a pointer just being a "memory address," a capability is like a secure key that includes the address plus specific bounds and permissions. This means the hardware itself can stop a program if it tries to access memory it shouldn't, preventing common hacks like buffer overflows. It was interesting to see how CHERI doesn't replace existing systems like RISC-V but enhances them. Even though the hardware details in Section 8 were complex, the main takeaway is clear: hardware-enforced boundaries make systems much more resilient.
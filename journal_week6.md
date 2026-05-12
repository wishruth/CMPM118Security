# Lab Notebook Week 6
## Vishruth Narasimhan

# Reflection
To overview really quickly, the assignments that needed to be completed for the lab on week 6 itself were the Rustlings 19 & 20, and I also had to get the previous rustlings checked off from 14-18 as well as the I/O project because I missed week 5's lab for my hackathon. After getting those things checked off, we discussed the CHERI paper in class quickly, which was frankly still very confusing to me so I'll list my current understanding of the paper itself below. After discussing the paper and checking these things off, we got started with the file editor project that was posted in the Zulip. In class, I was able to cover just part of the first step itself which was the print_tree function. Here's the understanding I kinda got when I was in class: we have to set it up as a node type definition, and a node is either a file or a directory. Because the node can be either of these things, we have to implement it as an Enum. Rust needs to know the size of the type at compile time specifically, but a recursive enum will have infinte size, so we have to use a Box or a BTreeMap to bypass that. The Box and BTreeMap tags do something call indirection, so they put a pointer inside the struct instead of the data so that when the program gets to compile time the size of the type is clearly defined.

# Parts that took review

It took me a little bit to understand conceptually why we define both the file struct and directory as nodes and also why we had to use the pointers through Box and BTreeMap to get through compile time without errors, which I had to watch some videos for to understand why they served a purpose. The BTreeMap is basically just a rust version of a hashmap but in an arranged order. Because we discussed in class how this is going to be a recursively defined function to collect the nodes for the directory, I'm also going to have to go over how recursion in rust is going to work, which I'll detail more on in my next journal. 


# Goals 

For next week's journal I'm going to make sure I get through the rest of step 1 and have the implementation for the Display trait and the impl and struct for the Filestruct itself. Hopefully I'll be able to be done with step 2 before I get into class as well and implement the file handles themselves. 
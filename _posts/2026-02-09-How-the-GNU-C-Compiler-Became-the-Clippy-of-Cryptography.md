---
title: How the GNU C Compiler Became the Clippy of Cryptography
date: 2026-02-09
categories: [SECURITY]
tags: [GNU,C-COMPILER,CRYPTOGRAPHY,FOSDEM,SECURITY]
---

## How the GNU C Compiler Became the Clippy of Cryptography

The creators of security software have encountered an unlikely foe in their attempts to protect us: modern compilers. Today's compilers boil down code into its most efficient form, but in doing so, they can undo safety precautions. **"Modern software compilers are breaking our code,"** said René Meusel, sharing his concerns in a FOSDEM talk on February 1. Meusel manages the Botan cryptography library and is also a senior software engineer at Rohde & Schwarz Cybersecurity.

Meusel offered an example of the kind of problem he deals with when implementing a simple login system. For a close observer trying to break in, the time it takes the system to return an error indicates how many letters of the guessed password the user has already entered correctly. This side-channel leak has been used in the past to facilitate brute-force break-ins. Cryptographers have already created preventive functions to equalize these response times to the user so they are not so revealing. These constant-time implementations **"make the run time independent of the password,"** Meusel said.

However, the GNU C compiler is excellent at reasoning about Boolean values, but it may be too clever. Meusel ran a constant-time implementation through GCC 15.2 (with -std=c++23 -O3). The loop to check the character exits early when the character is correct, so GCC assumed the rest of the function wasn't needed. But the rest of the code that actually fixed the timing was jettisoned, and the side-channel vulnerability was exposed once again. Good C programmers know to fear the aggressive optimization of Boolean logic, which can be hazardous to their finished products.

The trick, Meusel advised, is to hide the semantics of this little program from the compiler. The first step is to replace the Boolean value that the loop is given with a two-bit integer and use some bit shift or bitwise operations to mask the input. But GCC is smarter than that. It can see when you are trying to make a sneaky Boolean comparison. So you need to apply an obfuscation function to both the input and the output. Finally, you need to throw the value through some inline assembly code that does absolutely nothing but return the same value. In effect, it warns the compiler, which doesn't understand assembly, to not mess with these values however Boolean they may appear. **"That's how these things are done nowadays,"** he added.

**"Now you might say, 'Well, this is becoming kind of intricate and very easy to do wrong' … and you wouldn't be wrong."** Meusel said. Can it be fair to require the average programmer to understand inline assembly, or any of these other inherently obtuse obfuscation techniques? Much less the maintainers of this software down the road? But this is the lot of the cryptography library coder, finding ways to shore up side-channel attacks while hiding the solutions from a ruthless compiler. And with each new generation of compilers comes a new set of optimizations to contend with, Meusel lamented.

There are a number of takeaways from Meusel's talk. Compiler builders may want to consider factors other than code efficiency. **"They want to make your code fast, and they're really good at it, but they don't put any other qualitative requirements of your implementation into this consideration,"** Meusel said. Security software designers will need to keep in mind all the parts of the system they are designing, including the development tools that are used and how they work. For them, Meusel recommended valgrind, an open-source memory debugging tool. Lastly, implementing security is hard, and not just because of the math involved. **Don't roll your own; join a project instead,** Meusel advised.

[Read full article](https://www.theregister.com/2026/02/09/compilers_undermine_encryption/)
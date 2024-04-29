# Test1.Intro.EncodingData.HistoryofComputingMachines
Introduction. Encoding Data. History of Computing Machines (TAK Computer Techniques and Architecture. Test 1)

Introduction. Encoding Data. History of Computing Machines (TAK Computer Techniques and Architecture. Test 1)

|     |
| --- |
| **Introduction. Encoding Data. History of Computing Machines (TAK Computer Techniques and Architecture. Test 1)** |     |
| _Dominika Pawlik & Paweł Rembelski & PJATK_ |     |
|     |     |
| - - - |     |
|     |     |

  
  

£ GBP

$ USD

Goodreads:

Pages: 40

Words: 9485

Uploaded: Mon Apr 29 17:33:43 2024

Sent to Kindle: 05 Apr 2024

  
  

Goodreads:[](#calibre_link-29)

## Table of Contents

*   [introduction-annotated](#calibre_link-12)
    *   [Introduction](#calibre_link-24)
    *   [Algorithms (general and computing)](#calibre_link-1)
    *   [So now — what is a computer?](#calibre_link-13)
*   [encoding-data](#calibre_link-18)
    *   [Encoding data](#calibre_link-25)
    *   [Positional systems](#calibre_link-14)
    *   [Encoding text](#calibre_link-6)
    *   [Units of information](#calibre_link-19)
*   [history-of-computing-machines](#calibre_link-26)
    *   [A brief history of computing machines](#calibre_link-27)
    *   [Mechanical machines (since 1502)](#calibre_link-11)
    *   [Eletromechanical machines (since 1888 )](#calibre_link-10)
    *   [Transmitter-based machines (since 1938)](#calibre_link-0)
    *   [Vacuum tube-based machines (since 1939)](#calibre_link-28)
    *   [0th generation computers: trasmitter-based (since 1941)](#calibre_link-20)
    *   [1st generation computers: vacuum tube-based (since 1943)](#calibre_link-17)
    *   [2nd generation computers: transistor-based (since 1956)](#calibre_link-21)
    *   [3rd generation computers: small- and medium-scale integrated circuits (since 1960)](#calibre_link-22)
    *   [4th generation computers: large-scale integrated circuits, and later (since 1971)](#calibre_link-9)

# Introduction

On this course, we will define the main notions used in computer science, and describe the basic tools allowing to manage and process information. We will also tell about the structure of main computer components, such as processor or memory.

The basic term for all of us is a computer. The main difference between a computer and a simple calculator supporting a few arithmetic operations is the support for programming. So, as it turns out, to understand one notion (computer), we need to understand other ones (programmability and universality). But then, to understand those concepts, we need a notion of an algorithm.

*   [Algorithms (general and computing)](#calibre_link-1)
*   [So now — what is a computer?](#calibre_link-13)

## Algorithms (general and computing)

An algorithm is essentially a recipe, for acting. Before we proceed to a definition, let us look at examples of algorithms, described by flowcharts:

![](images/000067.png)

![](images/000018.png)

The shapes used in these diagrams are not random, and have the following meaning:

![](images/000035.jpg)

More formallv, we can sav that:

An algorithm is a non-ambiguous recipe for transforming, in a finite time, some input data into some output data.

Non-ambiguity means that, for each ease of valid input data, there is always a unique way in which the computation shall proceed,[1](#calibre_link-2) Non-ambiguity means also that each step of the algorithm is sufficiently simple and described sufficiently clearly that it/s obvious how it shall be executed, (Here, it/s not so easy to formalize what “obvious" means, so we will remain at the intuitive understanding).

Consider again the examles given above. In the recipe for making tea (Algorithm 1 above), we have e.g, the following assumptions:

•    a tea glass is available

•    wehe able to get hot water

•    wehe able to measure 1 minute

•    etc.

Of course, we could dig into additional details, but this would lead to new questions: “do we have a kettle?", “is electricity supplied?" etc. The basic rule in creating an algorithm — or a flowchart — is usability. In creating it, we definitely should not sweep problems under the rug. On the other hand, however, there is no point in reinventing the wheel; at some point we must assume that, for some actions, it/s just clear how to execute them,

A similar perspective applies to solving the quadratic equation. In that flowchart, we assume that we know how to add numbers. However, in another setting, our problem could be (and sometimes it will) exactly how to add two numbers; and in such ease, the algorithm will be dealing with the details of that question.

Finally, we must remark that computer science generally is not about making tea. Computers, by their nature, execute computing algorithms, that is, algorithms in which the input data and the result are numbers, and the obvious algorithm steps are the basic arithmetic operations (which we will define more precisely later in this lecture). Even when — from the user’s perspective — a computer processes text, sound or image, technically speaking, all these data are encoded digitally, as numbers.

### Programmability and universality

Progammability means that the user of a machine can program it, that is, input new algorithms. However, not every programmable machine allows programming everything. Below, we describe a particular class of machines which do not allow programming all sorts of computing algorithms; still, they’re useful for their simplistic design (which also relates to efficiency of their execution).

#### Simple stack machine

Imagine a stack of plates on a shelf, A new plate can be only placed on the top; also, a plate can be only taken from the top. We have no access to the plates underneath the top-most one. This is how data storage looks in a stack machine.

Such a machine allows performing the following operations on the data stored on its stack:

•    ADD:    add two numbers from the top of the stack

and store the result (instead of both these numbers!) on the top of the stack

•    SUB:    subtract two numbers from the top of the stack

(specifically, subtract the second-top number from the top-most one) and store the result (instead of both these numbers) on the top of the stack

•    MUL:    analogously to ADD, perform multiplication

•    DIV:    analogously to SUB, perform division

•    PUSH a (where a is some constant):

put the value a on the top of the stack

•    PUSH    TOP:    duplicate the value on the top of the stack (i.e,    put    it there    once again)

•    PUSH    IN:    read a number from the input and put it on    the top of the stack

(note: the number “disappears;; from the input; one cannot e.g, read it again)

•    OUT TOP:    take the top-most number out of the stack and write it to the output

Since in practice this set of commands is very limited, it’s common to consider a stack machine with additional memory with free access type, that is, besides the stack, we assume that somewhere exist additional memory cells indexed by 0, 1, ,,,, n, and that we can use two more kinds of instructions:

•    MEM(k) TOP: see the top-most number out of the stack and store it

(without taking out from the stack) in the memory cell with index k

•    PUSH MEM(k): put on top of the stack the value from memory cell with index k

For example, the program below — given the values a, then b and then c on the input — computes the value A for the quadratic equation ax2 + bx + c = 0 (according to Algorithm 2), To visualize this better, we will tag each instruction with a description of the stack content and the memory content right after its execution, (In that, we will use the convention that the top of the stack is written on the right, and its bottom on the left side).

![](images/000027.png)

The last instruction causes printing out the value taken from the top of the stack, which is b2 — 4ac, equal to the desired value of A,

The list of operations available in a stack machine can vary. On this lecture, we will assume that the stack machine supports the set of operations restricted to the abovementioned ones (together with the additional free-aeeess memory). Yet, it’s worth knowing that, in other situations, stack machines can be considered with a significantly richer set of instructions.

In our choice of operations, its key property is that it offers no kind of instruction eontaning a conditional jump which could allow diverting the order of executing instructions, and in particular, execute the same code multiple times, (In popular programming languages, such instructions are e.g, if, for, while, goto etc,). This means that, in every program on a stack machine of our kind, every instruction will execute exactly once.

Therefore, it is impossible on our stack machine e.g, to write a program computing for a given number n its factorial n! = 1 ■ 2 ■... ■ n. That’s because, if such a program existed and contained e.g, 100 instructions, its whole exeuetion could involve at most 100 multiplication operations. However, computing the factorial may require arbitrarily many multiplications (specifically, computing n! requires n — 2 multiplications).

For this reason, the stack machine (according to the model from this lecture) is an example of a non-universal computing machine.

### Universality

By calling a machine universal, we basically mean that if it takes numbers from input and we know an algorithm to transform them into the final result, then this algorithm can be implemented on that machine.

Such phrasing of the definition is, however, hard to apply in practice, as it’s hard to keep considering the space of all algorithms (considerations like that are the domain of the theory of computation). At this point, we also hit again the question which we haven’t yet answered: which arithmetic operations (as well as conditional instructions, loops etc.) should we consider “obvious” — so that they can be treated as the basic steps in computing algorithms? And, if we pick some, why those and not others?

A widely accepted solution of this problem is a model of an abstract machine (i.e. one that does not exist and, moreover, cannot exist in practice), called the Turing machine, which serves as a “standard of universality”. Although, at the first glance, the capabilities of Turing machine may seem rather restricted, it turns out in practice that this model allows expressing all known computing algorithms.

Therefore, to decide if a given computing machine can be considered universal, it’s common to compare it to “the standard”, which is the Turing machine.

### Turing machine

The Turing machine consists of the following elements:

•    a finite alphabet — i.e, a set of symbols which can be used to represent data;

(typically including a special empty symbol, representing “lack of a meaningful value”)

•    an infinite (in both directions) tape, in which every cell contains some symbol (from our alphabet);

•    a finite set of states in which the machine can be;

•    a moving tape head which can read or write a symbol on the cell of the tape above which it is currently positioned;

•    a control system managing the movement of tape head and its actions based on the provided transition table.

The crucial thing here is the capabilities of the control system, i.e, the language of instructions which can be used to program the machine. In the Turing machine, very much unlike in the stack machine, we can use instructions of the form:

![](images/000042.png)

which means:

If the tape cell under the current position of the tape head contains symbol a, and the current state of machine is q0, then the machine should:

change its state to qi, store symbol b in the current tape cell, and then move the tape head by one cell to the right (as indicated by letter R),

Generally, the instruction can specify tape head movement either to the right (R) or to the left (L),

A program for the Turing machine consists of indicating the initial state and the transition table, i.e. a set of rules of the above form. Such a set is only correct if it/s free from collisions, i.e. contains at most one rule of the form (a,q0) ^ ... for every symbol a and state q0. On the other hand, we allow that for some a, q0 the table does not contain any rule of the form (a, q0) ^ ...; in such case, if the machine reads a while being in state q0, it shall just terminate its execution at that point.

As an example, below we will show a program for the Turing machine which reads (from the tape) the decimal representation of a natural number, and increments it by 1, under the following assumptions:

•    The alphabet is the set of decimal digits (0, ..., 9), and additionally the empty symbol ⊥;

•    We assume that the tape is filled with empty symbols ⊥, with an exception of a finite contiguous segment, filled with decimal digits (which form a representation of a natural number);

•    For simplicity of this example, we also assume that the machine starts with the tape head positioned at the first (left-most) digit of that number,[2](#calibre_link-3)

Under the above assumptions, the task of “increment the given number by 1" is implemented by the following program (in which we use 3 states, _q_→, q+ and qE, whose meaning will be explained below):

![](images/000002.jpg)

(Red color was used to mark places which “stand out from the crowd" but could be overlooked — so, it is just a visual aid, with no influence on how the program actually executes)

Xow, let us explain how this program essentially works, and what the particular states mean:

• The program starts execution in its initial state _q_→ and remains in that state as long as the tape head observes decimal digits (not a ⊥ symbol), while moving the head rightwards.

The state _q_→ is exited as soon as ⊥ is encountered for the first time.

This means that the purpose of _q_→ is to find the right end of the representation of the given number on the tape.

When that happens, we leave the T symbol unchanged, move the head leftwards (that is, to the right-most digit of the input number) and switch to state q+,

• Not surprisingly, the purpose of state _q_+ is to increment the given number by one,

(The school method instructs to do this starting from the right end, and that’s exactly why we needed the state _q_→ to prepare the tape head accordingly).

In state _q_+, we increment the currently considered digit by 1, If that digit was not 9, we switch to state qE (which represents the end of execution of the program).

In the other case when the currently considered digit is 9, we replace it with 0 and memorize the so-called “carry" (i.e, the need to continue incrementing digits on the left side). Hence, the valid action is to stay in state q+ and move the tape head to the left,

• The state _q_E represents end of the program execution because there are no transition rules defined for it,

• An interesting edge case is the rule (⊥,_q_+) → (1,qE, ⌊),

Can it happen at all that, while in state _q_+, we observe the symbol ⊥ under the tape head? Yes, it can, if the input number is composed entirely of 9’s, In such case, in the course of incrementing by one, wedl replace all these 9's by 0’s, and then the tape head will move even further leftwards, outside the representation of the number, hitting a ⊥, As we can see, the valid action in such case is replacing ⊥ with a “1” (so that we obtain a result of the form 10... 0).

For a complete explanation, let us also provide a visualization of how this program executes for an example input, 1299, The consecutive rows below show the content of the tape, position of its head and the state of the machine in the consecutive steps; they also indicate the rules used for transitioning to the next step.

![](images/000048.png)

As we defined no transition rule of the form (1,qE) A ..., according to the general rules reaching such combination leads executing our program to a stop. As a result of running our code, the number initially encoded on the tape (1299) has been replaced with (1300), that is, incremented by 1, as desired.

In this way, we showed how to use the Turing machine to solve our example computing problem.

[1](#calibre_link-4)

To be strict, there exist algorithms with a random element (the most famous example being Quicksort), in which some steps involve pieking at random some value which may then influence the execution of the further steps. Still, it remains true that, just before exeucting a particular step of the algorithm, it is precisely known how to execute it. The action of random picking of a value may be perceived analogously to the action of obtaining a value from the user (which, by the way, may also happen “deeply inside” the algorithm, not just at the beginning of its execution).

[2](#calibre_link-5)

That last assumption could be also omitted, in exchange for equipping our program with an additional initial ‘'section” responsible for moving the tape head from its initial position to the left-most digit of the given number. We skip that part here with the aim of obtaining a simpler example: however, extending it appropriately is not difficult and may be a good exercise.

## So now — what is a computer?

Wehe finally ready to define the notion of a computer: it is a computing machine which is programmable and (almost..,) universal.

Here, universality of a machine means that it/s able to compute everything which is computable on the Turing machine. In practice, of course, we never have access to unlimited memory. However, by a computer we understand a machine which is universal up to physical limitations, that is, it “would have the same computing capabilities as the Turing machine, if only it had unlimited memory".

This means that examples of computers include e.g, desktops, laptops, but also smartphones. These examples are easy to confirm by writing (on any of them) a program (in any popular programming language, e.g. Java) emulating the Turing machine, for which the only limitation would be the amount of available memory.

On the other hand, non-examples of computers include e.g, “intelligent" household devices like freezers, washing machines etc., even if their computing power (in terms of operations per second) is on par with some computers, That’s because, in these eases, the users do not have a way (or, at least, an easy one) to run arbitrary programs.

### Remarks on efficiency

The above considerations touched what a computer must be able to do. However, in this course, we will rather focus on the problem how to implement these capabilities. Obviously, important aspects of this problem include:

•    the speed of computation,

•    the memory capacity,

•    the speed of transmitting data,

•    etc.

Generally, regarding the main parameters of computer performance, there are 2 kinds of news:

•    Good news:    Computers are getting more and more efficient.

•    Bad news:    Still, there is a limit they will never reach.

#### Moore’s law

The good news is described with more precision by the Moore’s law.

In 1965, Gordon Moore, a co-founder of Intel, analyzed the number of transistors (i.e. the building blocks for integrated circuits, so also for processors) and noticed that, essentially, their number in an integrated circuit doubles every 18 months. Clearly, that is not any sort of a scientific theorem, or a physical law; it’s just an empirical observation.

For a long time, the “law" expressed in that way indeed described the reality well; however, in these years it seems that a better approximation of reality (and hence a better prognosis for the future) is to assume that doubling occurs every 24 months, rather than 18, Below, we show a graph visualizing this tendency, Notably, the vertical axis uses logarithmic scale: it uses same distance between 1,000 and 10,000, between 10,000 and 100,000, between 100,000 and 1,000,000 etc. On such a graph, an exponential tendency appears as a straight line, and indeed the data points on the graph fit into a straight line quite well.

![](images/000036.jpg)

This translates directly to the growth of computer performance. Therefore, Moore’s law is also often formulated as follows: “the computing power of computers doubles every 24 months”. An analogous exponential growth can be observed for:

•    the proportion of computing power to cost,

•    the number of transistors per unit of integrated circuit area,

•    the capacity of RAM memory,

•    the capacity of hard drives,

•    the bandwidth (capacity per unit of time) of computer networks.

The amount of time needed for doubling is different across these properties; however, what’s important is that all of them, over years, look very much like some exponential function.

Still, we cannot expect that every indicator of technological progress would be improving exponentially. For example, in the long perspective, the access time for various types of memory does not look like a (decreasing) exponential function.

#### Limitations

Computers are nevertheless subject to laws of physics, and these lead to Landauer’s principle. It describes the minimum energy cost involved in changing (or erasing) any single bit of information. The specific formula depends on the temperature and some physical constant. We will not provide it here; instead, wedl focus on consequence:

A computer, placed in a given temperature, consuming a given amount of power, cannot exceed certain level of computing performance.

In practice, wishing to achieve possibly high performance, one typically uses clusters of multiple computers and/or computers containing multiple processors (which, of course, does increase power consumption). In such environments, an important role is played by computations running paralldly on multiple processors.

And then, it turns out that we hit another kind of bottleneck, in that certain computations cannot be parallelized. This also leads to some limitations for performance, described by Amdahl’s law, which we will discuss on a later lecture.

# Encoding data

In the lecture “Introduction”, we mentioned that computers store all data as numbers. However, these numbers themselves must be stored somehow, too. While there are many ways to do so, the easiest approaches in practice rely on some form of dual state, i.e, use multiple tiny fragments which can be physically put into one of two available states. Such states can be e.g, high/low voltage applied to a particular transistor, or the magnetic orientation (north/south) of a data cell in an old-style hard drive.

Let us then assume that we have some physical data storage with two states, which can be conveniently denoted by numbers 0 and 1, Now, our task will be to understand how to use the 0 and 1 signs to encode an arbitrary number (or letter).

*   [Positional systems](#calibre_link-14)
*   [Encoding text](#calibre_link-6)
*   [Units of information](#calibre_link-19)

## Positional systems

### Binary system

Consider the sequence of natural numbers but only those whose decimal representation consists exclusively of 0 and 1 symbols:

0, 1, 10, 11, 100, 101, 110, 111, 1000, ...

The binary encoding assigns consecutive natural numbers to consecutive representations from this sequence:

![](images/000059.png)

We say e.g, that “the binary encoding of the number 4 is 100”, To express this more mathematically, without any words, we introduce the notation 100(2), meaning “the number whose binary encoding is 100”, Then, we have: 100(2) = 4, similarly 11(2) = 3 etc.

The binary encoding is the standard of storing natural numbers in digital memory (and, in particular, in computer memory). Below, we describe the rules which allow efficient transforming to and from the binary form.

### Positional systems in general

Before describing the conversion process, it’s worth to recall the nature of our most standard notation system for numbers, the decimal system (also called the positional system with base 10), It relies on the powers of the system base (i.e. number 10), For example:

1892    =    2 • 100 + 9 • 101 + 8 • 102 + 1 • 103.

(Caution: on the right-hand side, we list the number’s digits in a reversed order — thanks to this, the power exponents appear in an increasing order, starting from 0, which can sometimes facilitate calculations),

A very similar thing happens with other positional systems. In particular, the binary system described above is simply the positional system with base 2, Therefore, wishing to know what’s the “meaning” e.g, of 10011 in that system, we can use an analogous formula:

10011(2) = 1 • 20 + 1 • 21 + 0 • 22 + 0 • 23 + 1 • 24.

And similarly in yet other positional systems. For example, in the octal system (base 8), we have:

20157(8)    = 7 • 80 + 5 • 81 + 1 • 82 + 0 • 83 + 2 • 84.

In systems with base larger than 10, we need new digits. As long as the Latin alphabet is sufficient for this, it’s a common practice to use its letters (typically large ones). For instance, in the hexadecimal system (base 16), we use letters A, B, C, D, E, F denoting respectively 10, 11, 12, 13, 14, 15, Thus, we have:

1B (16)    =    11 + 1 • 161    =    27.

### Converting to non-decimal systems

We’ve just learnt how to convert from a non-decimal system to the decimal one. Now, we’ll consider the analogous problem in the reversed direction: “given a decimal number, represent it in another positional system”.

Suppose that we want to find the binary representation of number 2003:

2003    =    (.. .???)(2)    = ? • 20 + ? • 21 + ? • 22 + ...

Our goal is to guess the values of all the question marks. This can be done as follows:

•    To reveal the right-most binary digit, we divide 2003 by 2 (obtaining quotient 1001 and remainder 1), and take the remainder (here: 1),

(This step must always work because, in the long sum above, all the summands except the first one are always even),

•    Since 2003 = 1 + 2 • 1001, this means that the binary representation of 2003, after removing its right-most digit, becomes the binary representation of 1001,

This means that, to reveal the other digits of the binary form of 2003, it suffices to consider 1001 from now on.

By following this reasoning, we will effectively make a whole sequence of divisions-with-remainder by 2, until finally obtaining a quotient of 0:

![](images/000052.png)

The final result is the sequence of obtained remainders, written in reversed order:

11111010011(2)    =    2003.

For other system bases, the algorithm will be analogous; we would only need to replace 2 with the system base. The following block scheme presents the general algorithm of converting a number from its decimal form into the base k system (where % denotes taking division remainder, and denotes putting two strings together):

![](images/000031.png)

We have described how to use symbols 0 and 1 to encode natural numbers, i.e. non-negative integers. Then, how can we encode with those two symbols that a number is negative?

The new information we need to store is just the sign of the number (is it negative or not). The natural idea is then to encode that fact with an additional digit (common practice: 0 = non-negative, 1 = negative). This, however, would lead to ambiguity: for instance, does “ 11” mean 3 or —1?

Solving this problem becomes easier due to the fact that computers tend to work with number representations of a fixed length, e.g, 8, 16, 32 or 64 bits, where a bit means a single binary digit (0 or 1 symbol). Then, a widely adopted convention is to use the first bit to encode the sign of a number (0 = non-negative, 1 = negative). The remaining bits specify which number we mean exactly, though — as we will see just below — there are a few competing standards in this regard.

### The sign-magnitude system

The sign-magnitude system, simplest conceptually, specifies that the remaining notation bits (except the first one) shall simply contain the binary form of the magnitude of the encoded number (that is, the number “stripped off” its sign).

The table below shows all representations in the sign-magnitude system for the 4-bit encoding.

![](images/000000.png)

Note that the number 0 can be encoded in two wavs, depending on choice of sign: 0000 or 1000, Hence, the set of 16 possible 4-bit encodings covers 15 numbers, from -7 to 7 inclusive. Generally, working with n-bit representations, the sign-magnitude convention allows representing any number from the interval \[— (2n-1 — 1), 2n-1 — 1\] (including the bounding numbers).

The sign-magnitude convention, while easy to define, is not the most common ehoise in computing, due to how it makes computations more complex. For example, it offers no simple, universal rule to increment a given number by 1, as the method of doing so differs between positive and negative numbers. Below, we’ll see an example of another convention which is more computation-friendly.

### Two’s complement system

In the two’s complement system, we still assume a fixed representation length (n bits) and keep the same meaning of the first bit (0 = non-negative, 1 = negative). This time, however, we work a bit more along the main principle of a positional system, equipping each position with some weight — a summand which should be added to the resulting number whenever the bit on that position has value 1,

While the “ordinary” bits carry same weights as in the standard binary system (that is: 1 for the right-most bit, 2 for the bit preceding it, 4 for the other preceding bit etc,), we make an exception for the left-most bit, replacing its usual weight 2n-1 with a negative weight of — 2n-1. For instance, for n = 8 this means that the representation 11011001 will now denote the number 1 • (—27) + 1 • 26 + 0 • 25 + 1 • 24 + 1 • 23 + 0 • 22 + 0 • 2[1](#calibre_link-15) + 1 • 20 = —128 + 64+ 16 + 8 + 1 = —39.

Whenever the first-most bit has value 0, we obtain the same number as in the standard binary system. For the representation 01011001, we get:

0 • (—27) + 1 • 26 + 0 • 25 + 1 • 24 + 1 • 23 + 0 • 22 + 0 • 2[1](#calibre_link-15) + 1 • 20 = 64 + 16 + 8 + 1 = 89.

The following table shows all 4-bit representations:

![](images/000061.png)

For a code of n bits, this allows encoding numbers between — 2n-1 and 2n-1 — 1, inclusive. Each number from this range can be encoded in a unique form. That’s a difference comparing to the sign-magnitude system, where 0 could be encoded in two ways (all zeroes, but also 1 followed by all zeroes).

The main difference, however, lies in doing arithmetics. It turns out that, in the two’s complement system, addition and subtraction can be done exactly in the “long” (or “table”) form well known from school,[1](#calibre_link-15) We just need to remember that only two digits exist: 0 and 1. So, even adding 1 + 1 gives a two-digit result (10), and hence leads to a “carry” digit (left-wise) inside a table-like computation.

For example, assuming 8-bit representation, adding the numbers —14 (11110010) and 99 (01100011) looks as follows:

![](images/000032.png)

The result obtained with this method (101010101) has 9 digits! In such a ease, we must simply ignore the newly added digit (the left-most one). The final result is then “01010101”, And indeed, this encodes the number 85, which is the actual sum of the two given numbers.

### Ones’ complement system

The ones’ complement system is very analogous to two’s complement. Again, we work with a fixed encoding length of n bits. For the positive numbers (starting with 0), nothing changes. For the negative numbers (starting with 1), we now take the leading bit weight of — (2n-1 — 1),

Then, the representation 11011001 will now mean

1 • ( — (27 — 1)) + 1 • 26    +    0 • 25    + 1 • 24    + 1 • 23    +    0 • 22    + 0 • 21    + 1 • 20 = —127 + 64+16 + 8 + 1 =    —38, which is higher by 1 than what we obtained for the two’s complement system (where we got —39), The following table shows all 4-bit representation in ones’ complement system:

![](images/000033.png)

This time, we again see a double encoding of 0,

In this system, there also exists a way of adding and subtracting in a tabe form (though a bit more complex than in the two’s complement system). On the other hand, an advantage of ones’ complement over two’s complement is e.g, the simplicity of negating a given number: here, it requires simply switching every bit to the opposite value (from 0 to 1, and conversely).

### Overflow

While executing arithmetic operations, it may happen that the result falls outside the range of supported numbers; e.g, the numbers 99 and 60 can be both represented in the two’s complement system on 8 bits, but not their sum. Such situation is called an arithmetic overflow, and treated as an error (one cannot store the result, similarly as one cannot divide by zero).

It’s worth remembering that, in some situations (e.g, C++ code), overflow errors are not explicitly raised but can instead lead to returning an incorrect result. In such settings, defending against overflow becomes the programmer’s responsibility.

The next problem which we’ll learn to solve is how to encode non-integers (fractions). Again, there are multiple conventions here. The basic one is named IEEE 754 single and uses 32 bits. The first bit, just as so far, encodes the sign of the number. The remaining 31 bits are split into two blocks: the exponent (E) and the significand (S),

![](images/000003.jpg)

Assuming that the numbers E and S are read from this representation using the normal binary system (so in this example: E = 125, S = 221 + 220), the final result is obtained according to the following formula:

![](images/000011.png)

where ± denotes the choice of an appropriate sign (+ or —) depending on the sign bit (here: —), (Warning, the convention specifies in addition that the values E = 0 and E = 255 should be interpreted in a special way).

Therefore, in the above example, we obtain the result

![](images/000044.png)

Although the above formula may seem surprising (if not “magical"), the idea behind it is simple and corresponds to the widely used so-called “scientific notation” in the decimal system, like 2.45 • 10\-32 or —3.9 • 103, In that notation, the rule is that the significand (the factor being not a power of 10) should always have “one digit before the dot”, or more precisely, fall into the range between 1 and 10, Such a situation is always achievable by “transferring” a number of l(Ts to the exponent as needed, e.g, the form 342.7 • 105 can be fixed into 3.427• 107, while 0.034 can be fixed into 3.4 • 10\-2, Now, the IEEE 754 single convention implements the same plan, but for the binary system (where fractions are also binary, e.g, 0.11(2) = 2\-1 + 2\-2 = |), In such setting, a correctly chosen significand must

1.a1a2a3 ...; then, the first

23 symbols from the sequence a1a2a3 ... are stored as in the S area, while the leading 1 (which must be there) is discarded to save space. Finally, the purpose of shifting the exponent by 127 is to allow some positive as well as negative exponents in an 8-bit representation.

### Limitations and takeaways

![](images/000062.png)

Clearly, this encoding is not applicable to every real number. Generally, there are obstructions of two kinds:

•    We can fall outside the supported range of exponents (e.g. for 2200 , 2 150),

•    The available precision of 23 bits may be insufficient for faithfully storing the signifieand.

For example, for the number 1 + 2\-100, the signifieand block S should ideally contain 100 zeroes followed by a “1”, which does not fit into 23 bits, (Also, there are numbers for which no precision would suffice, e.g, 1/3),

These problems can be mitigated by increasing the lengths of the signifieand and exponent. The common next step is to use 64 bits, with 1 bit for the sign, 11 for the exponent, and 52 for the signifieand, (That’s the IEEE 754 double convention). Often, however, we simply cannot store the exact values of numbers; then, we must live with storing their possibly good approximations.

Sadly, performing arithmetic operations on such encodings tends to increase the approximation errors, or even to introduce new ones (e.g, the numbers 1 and 2\-50 can be both encoded faithfully in IEEE 754 single, but not their sum). This leads to a practical takeaway: in programming, it pays off to avoid floating-point computation, e.g, by delaying any divisions for as long as possible. It must be also remembered that the floating-point division result is typically only approximate, and the more computations on the way, the higher errors we risk.

[1](#calibre_link-16)

That’s because every bit sequence, whether interpreted in the two’s complement system or the “normal” unsigned binary system, will always give results differing by a multiple of 2”, or — speaking mathematically — congruent modulo 2”. Now, school math ensures that much of basic arithmetics can be done “modulo something”: if we know a number a “modulo 2”” and another number b also “modulo 2””, then performing addition/subtraction/multiplication on them we will obtain the values a + b, a — b, a • b also up to a possible shift by a multiple of 2”. This in turn means that — unless an arithmetic overflow happened — the result must be correct.

## Encoding text

All we said so far involved numbers. In practice, there are more data formats we’d like to encode: images, sounds, text. The first two eases exceed the scope of this course; fortunately, encoding text is quite simple: we just assign some sequence of bits to each letter. That idea can be extended to non-alphabetie characters, like #, = or even Shift,

### The ASCII encoding

The ASCII encoding assigns numbers from range 0-127 to uppercase and lowercase Latin letters, digits, certain other symbols (#, = etc.) and certain control commands[1](#calibre_link-7).

The following table presents the part of ASCII code involving the “ordinary” characters. Aside decimal numbers, we also provide their hexadecimal counterparts, as that is the presentation often used by various “raw viewers” of binary files (e.g, hexdump in Linux) or memory (e.g, C++ debuggers). Such convention is more effective as every character can be described by just two hexadecimal digits,

![](images/000050.png)

### Unicode

The ASCII encoding was introduced already in 1960 (initially, in telegraphs) and turned out to be extremely useful in computers. However, currently, we need support for a much broader list of characters, including Latin letters with diacritics (e.g. French “é”), other alphabets (Cyryllic, Greek etc,), but also other writing systems (thousands of Chinese characters) and various other signs (emojis, currency symbols, math symbols etc,). Finally, taking a lesson from the past, we should leave some place for characters which are not yet commonly used but might become such in the future.

Sadly, there exist various standards of extending ASCII currently; the main two ones are Unicode and ISO/IEC 10646, While they agree with each other about which bit sequences correspond to which characters, Unicode carries more graphical information about the characters (e.g, how to connect some of them with other ones). As a result, some platforms based on ISO/IEC 10646 may incorrectly display Unicode text.

While it’s great to have access to all characters used in the world, this can unnecessarily complicate encoding and increase the memory needed, which would be particularly painful e.g. in network transmission. For this reason, Unicode uses variable length: in the leading implementation of this standard, called UTF-8, the most common characters use just 8 bits (in particular, the 0-127 range is compatible with ASCII), while the less common ones (like Polish diacritic “ą”) use 16 bits, and some even less used ones can use 24 or 32 bits. The system is built in a way which avoids ambiguity: for every character, even if we don’t know its bit length, that length can be always deduced from the value of the leading 8 bits, (E.g, the range 0-127 denotes an 8-bit ASCII eahr, the range 192-225 by convention denotes a 16-bit sequence, etc,). Thanks to this rule, while reading an UTF-8 encoded text from the start, character by character, we may never have doubt about how it should be split to individual characters, and that allows decoding it unambiguously.

[1](#calibre_link-8)

The values 0-32 and 127 have a special meaning, often dating back to old protocols of controlling printers, which we will not cover in depth here. Two particularly remarkable codes are 13 (0D) and 10 (0A), encoding respectively the instructions of carriage return (CR) and line feed (LF). In old printers, these two commands together used to lead the printer head to move to the start of the next line, just like pressing Enter key in modern word processors. For that reason, the Windows operating system still encodes a newline character (e.g. in the .txt files) as a sequence of those two ASCII characters: CR followed by an LF. (In Linux, only LF is used).

## Units of information

To conclude this lecture, let’s briefly discuss the ways of describing large volumes of information, memory capacities etc.

### Bits and bytes

While the most fundamental unit of information is a bit (1 b), that is, one binary digit, most of us in fact more commonly use a unit of byte (1 B), which means a sequence of consecutive 8 bits.

This is convenient in practice: as we already know, for text data, one byte typically holds one character, and hence serves as a very intuitive unit of information. Moreover, since binary sequences (like 01011101) are often much worse readable for a human eye than their hexadecimal counterparts (here: 5D), various “raw binary viewers” display data in hex format, thus grouping information into bytes, each of which corresponds to a pair of hex digits.

So, speaking of sizes of files, disks, RAM modules etc,, we usually express them in bytes. Bits, on the other hand, are typically used to describe network transfer speeds (and hence “gigabits” in mobile provider offers). Don’t be confused here: downloading a 1 GB file on an 1 Gb/s transfer should obviously take eight seconds.

### How many megs is a gig?

For reasons to be discussed in next lectures, computing “likes” memory sizes to be powers of 2, One could hardly find memory modules of size 1,000,000 B; more likely, we’d expect ones of size 220 = 1, 048, 576 B.

Since 210 = 1024 is “almost the same as” 1000, it became customary in the industry to call 210 B “one kilobyte”, 220 B “one megabyte” etc. Still, that’s imprecise, and sometimes confusing. Therefore, on this course, we will follow a more recent and more precise convention (IEC 60027) which differentiates the binary prefixes from the casual decimal ones:

![](images/000024.png)

According to these defintions, we have 1 kiB = 1024 B = 1,024 kB, The difference is subtle, but it grows on the following levels:

1 MiB ~ 1.05 MB, 1 GiB ~ 1.07 GB, 1 TiB ~ 1.10 TB.

That’s worth remembering, to avoid misunderstandings, (In particular, this convention is now broadly used by hard drives manufacturers, but not by the Windows operating system. As a result, having bought a 1 TB hard drive, you may often see it described by Windows as “931 GB”, where “GB” is used to mean “gibibytes”. And that does not mean that any side is lying.)

# A brief history of computing machines

Author: Paweł Rembelski    Translated by: Dominika Pawlik

The chronological history of computing machines which we present below is based on the notion of generation as a key for classifying those machines:

•    non-computers (non-programmable or non-universal computing machines):

o purely mechanical machines o electromechanical machines o transmitter-based machines o vacuum tube-based machines

•    computers (programmable and universal machines):

o 0th generation computers - relay computers o 1st generation computers - vacuum tube computers o 2nd generation computers - transistor computers

o 3rd generation computers using integrated circuits with small- or medium- scale integration

o 4th generation computer - integrated circuits with large- scale integration and beyond

*   [Mechanical machines (since 1502)](#calibre_link-11)
*   [Eletromechanical machines (since 1888 )](#calibre_link-10)
*   [Transmitter-based machines (since 1938)](#calibre_link-0)
*   [Vacuum tube-based machines (since 1939)](#calibre_link-28)
*   [0th generation computers: trasmitter-based (since 1941)](#calibre_link-20)
*   [1st generation computers: vacuum tube-based (since 1943)](#calibre_link-17)
*   [2nd generation computers: transistor-based (since 1956)](#calibre_link-21)
*   [3rd generation computers: small- and medium-scale integrated circuits (since 1960)](#calibre_link-22)
*   [4th generation computers: large-scale integrated circuits, and later (since 1971)](#calibre_link-9)

### Mechanical machines (since 1502)

Our tour through the history of computers will begin back in Renaissance, specifically in 1502. In that year, Leonardo da Vinci published the first design of a non-trivial mechanical copmuting device - an early calculator.

![](images/000004.jpg)

Leonardo da Vinci’s sketch of his „calculator" (source: [www.ibm.com](http://www.ibm.com)).

In fact, the device did not offer functionality close to today's calculators; however, it allowed addition of 13-digit numbers, properly handling the carry-over.

Picking up the most impactful moments from the further history, we should mention:

•    1614 - John Napier designed logarithmic calculus, laying ground for efficient big number arithmetic.

•    1623 - Wilhelm Schikard built the first mechanical calculator, performing all the four basic arithmetic operations (add, subtract, multiply, divide).

![](images/000037.jpg)

NON-PROGRAMMABLE    NON-UNIVERSAL

A reconstruction of schickard's calculator (source: [www.wikipedia.org](http://www.wikipedia.org)).

•    1632 - William Oughtred invented the slide rule, a manual device enhancing

computations in Napier's logarithmic calculus. This allowed instantaneous (though approximate) multiplication and division, a feature widely used in practice until 1970's.

![](images/000005.jpg)

A part of a modern slide rule (source: [www.przedmioty.com](http://www.przedmioty.com)).

•    1642 - Blaise Pascal built a mechanic arithmetic machine - the Pascaline - performing

addition and subtraction on 8-digit numbers. It used the complement notation which has dominated the hardware implementation of modern computer arithmetic.

The Pascalina (source: [www.wikipedia.org](http://www.wikipedia.org)).

•    1675 - Gottfried Wilhelm von Leibnitz, basing on earlier works of Napier, developed the binary system and the way to perform arithmetic in it.

![](images/000038.jpg)

•    1694 - Gottfried Wilhelm von Leibnitz constructed a mechanical computing machine capable of a complex arithmetic operation - taking square roots.

![](images/000009.jpg)

Note

Since the second half of 20th century, the binary system had a fundamental role for all digital computating, communication and even data storage.

1805 - Joseph Marie Jacquard built a loom capable of programmable weaving of patterns. The informations about the pattern shape were encoded on a data storage, which in this case was a set of punched cards. Many years later, analogous cards were used as external computer memory. The Jacquard's loom is considered to be the first programmable mechanical device in history.

![](images/000034.jpg)

PROGRAMMABLE    NON-UNLVERSAL

V

Controlling a weaving machine with punched cards (source: [www.twojekoronki.pl](http://www.twojekoronki.pl)). 1822 - Charles Babbage designed a scheme of difference engine for automatic generation of tables of values of polynomial functions.

![](images/000008.jpg)

•    1831 - Joseph Henry built the first electric transmitter, initially used in telegraphs and telephones. In the 1940's, transmitters will replace mechanical solutions as the basic building blocks of universal computing machines.

•    1837 - Charles Babbage presented the first theoretical model of a universal computing machine \- which he called analytical engine - purposed to perform arbitrary computations, including flow control commands (e.g. conditionals, loops), according to prescribed programs. This is considered to be the first programmable computing device.

![](images/000039.jpg)

A reconstruction of a part of Babbage's analytical engine (źródło [www.wikipedia.org](http://www.wikipedia.org)).

•    1842 - Ada Lovelace prepared an implementation of an algorithm for computing the so-called Bernoulli numbers for Babbage's analytical engine. This is considered to be the first machine language program.

•    1853 - Georg Scheutz and his son Edvard construct an implementation of Babbage's difference engine.

•    1854 - George Boole initiated a modern formalism for the standard two-valued logical calculus, now known as Boole's algebra.

![](images/000030.jpg)

### Eletromechanical machines (since 1888 )

•    1888 - Herman Hollerith created the first electromechanical computing machine \-

a tabulating machine - capable of sorting and processing statistical data. The machine communicated with the user through punched cards of a one-dollar banknote size -this standard persisted in computer industry until the second half of 20th century.

![](images/000064.jpg)

![](images/000063.jpg)

![](images/000058.jpg)

•    1903 - Nicola Tesla patented electric logic gates, implementing the basic logic

operations according to Boole's formalism.

•    1907 - Lee de Forest, basing on earlier John Fleming's works on diodes, invented

triodes (three-electrode vacuum tubes). This element, suitable to serve as an electric transmitter, allowed removing all mechanical components from computers in the 1940's.

![](images/000012.jpg)

•    1925 - Julius Lilienfeld finalized the theoretic works on a predecessor of transistor. These replaced vacuum tubes as base computer building blocks in the second half of 20th century.

•    1937 - Alan Turing created the first abstract computing model of a computer in the >modern sense - the Turing machine. He also described options to implement it, basing on Babbage's analytical engine.

![Turing machine](images/000023.png)

A fanciful mechanical Turing machines TAPE and HEAD The TABLE instructions might be on another read only tape, or perhaps on punch-cards. Usually a finite state machine is the model for the TABLE

Turing machine (source: [www.wikipedia.org](http://www.wikipedia.org)).

![](images/000029.jpg)

A practical implementation of Turing machine (source: [www.aturingmachine.com](http://www.aturingmachine.com)).

### Transmitter-based machines (since 1938)

•    1938 - Konrad Zuse built a programmable mechanical computing machine - the Z1

pseudo-computer, based on binary number system, and equipped with mechanical data storage which inspired computer main memory. The machine executed programs given on a punched tape. In the next year, Zuse re-implemented the idea with transmitters, leading to the Z2 pseudo-computer. These machines are not considered computers because of lack of universality.

![](images/000055.jpg)

![](images/000007.jpg)

Puched tape used in an ATARI computer (source: [www.atari.org.pl](http://www.atari.org.pl)).

### Vacuum tube-based machines (since 1939)

•    1939 - John Atanasoff and Clifford Berry built the first vacuum tube-based

computing machine, which they called ABC. Its purpose was limited to solving sets of algebraic equations, without any programmability.

![](images/000025.jpg)

### 0th generation computers: trasmitter-based (since 1941)

•    1941 - Konrad Zuse developed the concepts from Z1 and Z2 machines into a fully

programmable transmitter machine, Z3, considered to be the first computer. As a confirmation, in 1998 Raul Rojas has formally proved Z3 to be functionally equivalent to the Turing's machine.

![](images/000046.jpg)

Note

![](images/000051.jpg)

The Z3 was a milestone in the history of computing machines. For the first time, a real implementation combined both properties defining a modern computer -programmability and universality. From now on, we restrict entirely to this class, and below only computers in this sense will be considered.

### 1st generation computers: vacuum tube-based (since 1943)

•    1943 - Max Newman, Tommy Flowers and Alan Turing built the first lamp-based

computer, Colossus (Mark 1), purposed for warfare cryptanalysis.

![](images/000019.jpg)

•    1943 - Stephen Kleene formulated the Church-Turing hypothesis, stating that the expressive power of Turing machine is equivalent to all computing and programming which humans are able to perform in practice.

Assuming that this is true (which is unprovable by strict means - but now commonly believed), any device implementing the Turing machine model can be considered universal.

•    1944 - a team led by Howard Aiken made the biggest transmitter-based computer in history, Harvard Mark 1.

![](images/000069.jpg)

•    1945 - John von Neumann, John Mauchly and John Eckert prepared the first abstract

architecture model of a computer (in the modern sense). The basic assumptions of this model are still reflected in contemporary solutions.

![](images/000068.jpg)

•    1945 - John Mauchly and John Eckert built the ENIAC - the first vacuum tube-based

computer of universal purpose, performing computing tasks in decimal arithmetic, for a wide range of scientific purposes (ballistic, weather forecasting, aerodynamic and nuclear simulations, or even number theory). This computer was in use until 1955.

![](images/000022.jpg)

The ENIAC computer in service (source: [www.explorepahistory.com](http://www.explorepahistory.com)).

•    1947 - Frederic Williams patented and constructed a new memory realization of

random access type (RAM), based on CRT lamps.

![](images/000041.jpg)

CRT lamp memory (source: [www.pusatgratis.com](http://www.pusatgratis.com)).

•    1947 - Walter Brattain and John Bardeen constructed a point-contact transistor,

novel in that it did not contain any mechanically movable parts. Shortly after that, William Shockley set the technical specification of a junction transistor, the industrial standard for the next three decades.

![](images/000065.jpg)

A replica of the first point-contact transistor (source: [www.wikipedia.org](http://www.wikipedia.org)).

•    1948 - Andrew Booth constructed a new data storage form - magnetic drum memory.

•    1949 - Frederic Williams, Max Newman and Alan Turing deployed a Manchester Mark 1 computer, the first one with a built-in eletric main memory, based on CRT lamps. In addition, the machine was also equipped with secondary magnetic drum memory.

![](images/000014.jpg)

The Manchester Mark 1 computer (source: [www.wikipedia.org](http://www.wikipedia.org)).

•    1950 - Alan Turing formulated the idea of Turing test as a method of verifying the

quality of artificial intelligence.

![](images/000040.jpg)

The Turing test - can a computer communicate so much like a human that another human will not spot the

difference? (source: [www.kevinwarwick.com](http://www.kevinwarwick.com))

•    1951 - An Wang built random access memory based on ferrites. Shortly later, Jay

Forrester made RAM based on magnetic cores.

1951 - the UNIVAC company designed and introduced the first publicly available mainframe (business-oriented) computer, called UNIVAC1. This machine used magnetic type as external data storage.

![](images/000043.jpg)

![](images/000020.jpg)

External tape memory (source: [www.computerhistory.org](http://www.computerhistory.org)).

1954 - IBM introduced the first computer with an operating system available for the end user.

•    1956 - IBM constructed the first magnetic platter hard drive with a movable read-write

header, used in commercial computer model IBM 305. This initiated the era of hard drives.

![](images/000006.jpg)

Magnetic hard drive RAMAC 350 (source: [www.computerhistory.org](http://www.computerhistory.org)).

### 2nd generation computers: transistor-based (since 1956)

•    1956 - TX-0, the first transistor-based computer, was constructed in MIT laboratories.

![](images/000057.jpg)

A fragment of the TX-0 computer, and a transistor used in its construction (source: [www.wikipedia.org](http://www.wikipedia.org)). •    1957 - John Backus created the first high-level programming language, FORTRAN,

for the IBM 704 computer. This made programming no longer require a deep

understanding of the underlying machine internals, and through that widely popularized the activity of programming. Soon later, high-level languages dominated the landscape.

C    CALCILATF STATISTICS ON DATA FRON LOW SF-FFD RFAIFR

S1‘N=0 Sl‘NSC«0 T TP F 100

100    FORNATC"FNTFR TmF NINBFR OF VALLES TO CAC1LATF STATISTICS ON"#/ł

ACCFPT 1 0» N 10    FORNATc1>

TO 000 l = 1 » N RF AT l#110#V 110    F O RN A TłF >

St'N\*Sl'N ♦ V

siNse\*stNse \*■ v\*v

TTPE 120# 1# V

120    FORNAT«"VALI F”#1#”1S"# ft / )

200    CONTINLF

S£,<łF\*N

AVRG\* SI N/SANP

STD“St»TF CSl’NSf/SAMP - AVPG\*\*2)

TTPF 300»N#AVRG#ST\[

300    F ORNAT < "NI NBF R OF V AH F S"# l# "N F AN"» E # "ST ANTARI t)F V l AT ION"# F # / )

FND

\*

•R FORT

A fragment of a FORTRAN program (source: [www.pdp8.net](http://www.pdp8.net)).

•    1958 - Jack Kilby patented a simple circuit consisting of two transistors placed on a

metal board, forming the first integrated circuit.

![](images/000047.jpg)

Kilby's integrated circuit (source: [www.giznet.pl](http://www.giznet.pl)).

His works were continued by Robert Noyce, who designed the currently used technique of building integrated circuits on silicon boards.

![](images/000017.jpg)

Note

In 1968, Robert Noyce together with Gordonem Moore established the Intel (Integrated Electronics Corporation) company.\_

![](images/000053.jpg)

### 3rd generation computers: small- and medium-scale integrated circuits (since 1960)

3rd generation computers - small- and medium-scale integrated circuits

•    1960 - the DEC company presented PDP-1, the first publicly available computer based

on integrated circuits.

![](images/000016.jpg)

1962 - MIT students, Stephan Russel, Martin Graetz and Alan Kotok, wrote the first computer game, Spacewar!, for the PDP-1 computer. This started the history of using computers for leisure.

![](images/000010.jpg)

The Spacwar! game (source: [www.wikipedia.org](http://www.wikipedia.org)).

•    1963 - the ANSI institute accepted the ASCII standard, aiming to allow exchanging

information between computers from various vendors. This was the first step towards digital data format standardization.

![](images/000021.jpg)

•    1964 - Gordon Moore formulated an initial version of the Moore's law, stating that the number of transistors in an economically feasible integrated circuit should double about every year.

•    1964 - IBM developed the IBM System/360 mainframe computer series, the first family of computers with mutual compatibility.

•    1965 - Maurice Wilkes built the first cache module, allowing for speeding up processors.

•    1967 - IBM developed the floppy disk, opening the way for easy transfers of data between various computers.

![](images/000060.jpg)

Floppies: the 8-, 5V4-, and3^-inch type (source: [www.wikipedia.org](http://www.wikipedia.org)).

•    1970 - Intel developed read-only memory with data persisting periods of lack of electricity

### 4th generation computers: large-scale integrated circuits, and later (since 1971)

•    1971 - Wayne Pickette developed microprocessors (i.e. processors made in the integrated circuit technology). Soon, a publicly available implementation (Intel 4004) appeared.

![](images/000066.jpg)

•    1971 - Kenneth Thomson and Dennis Ritchie developed and deployed UNIX, the first universal operating system.

•    1971 - Stephen Cook formulated the most important open question in computing theory (from the practical viewpoint): „Does P equal NP?"

•    1975 - Ed Roberts published the first publicly available personal computer (PC), Altair 8000.

![](images/000045.jpg)

![](images/000013.jpg)

•    1976 - Steve Jobs and Steve Wozniak built the first publicly available home computer,

Apple I. In the next year, Apple II appeared, the first home computer with color display. Since then, the Apple family has been the main competition for the IBM standard in the PC market.

![](images/000054.jpg)

![](images/000056.jpg)

The Apple II computer (source: [www.oldcomputers.net](http://www.oldcomputers.net)).

1976 - Cray Research created Cray-1, the first supercomputer purposed for large-scale computations.

![](images/000015.jpg)

1978 - Intel introduced the 8086 processor, setting the architecture standards for all later processors in IBM-like PC computers.

![](images/000026.jpg)

The Intel 8086 processor (source: [www.cpu-world.com](http://www.cpu-world.com)).

1980 - realizing a contract for IBM, Microsoft created the MS-DOS operating system, purposed for personal computers.

## ^9TOsoftj/|S-pos

Operating System

SKłtlJlt

Includes Microsoft uw Intorprotor Version 3.¿.

c°mputei

The commercial variant of the MS-DOS operating system (source: [www.dailytech.com](http://www.dailytech.com)).

### 4th generation computers: follow-up

We will finish our tour through the (pre-)history of computers in 1981, when IBM presented model 5150 PC, equipped with Intel 8086 processor, 64 kB of RAM, 40 kB of ROM, a 5.25 inch floppy disk drive, running MS-DOS operating system.

![](images/000028.jpg)

IBM's successful licensing strategy allowed this model to define a global standard for personal and home computers, observed until today. To see this, let's compare the total sales of the IBM PC standard computers with the main competition, Apple Mac family:

![](images/000049.jpg)

1934 1936 1938 1930 1992 1994 1996 1993 2000 2003 2004 2006 2008 2010

Total sales of IBM PC in relation to that of Apple Mac (source: [www.komputerswiat.pl](http://www.komputerswiat.pl)).

As the graph tells, currently (in the 2010's), the position of Macs tends to improve, but they're still outnumbered by PCs by over 10 times.

After 1981, we observe continuation of development of 4th generation computers. The most important improvements are related to manufacturing technology of integrated circuits, leading to increase in microprocessor computing power and growth in the size of computer memory. Such developments are significant - but the basics of computer science have not changed since the Alan Turing's and John von Neumann's works from the 1930's and 1940's, describing respectively the Turing machine and the von Neumann architecture as simple theoretical models of a general computing machine. The latter will be described in more details in one of the following lectures.

Note that, in the above history walkthrough, we focused on the computation process (related with processor) and on reading/writing digital information. Modern computers have a much more developed architecture with a lot of specialized components responsible for e.g. internal comunication (data buses), input/output operations, graphics, sound, or communication between computers (network card), either wired or wi-fi. These topics will be mostly omitted in this lecture, and interested readers are encouraged to self-study their details.
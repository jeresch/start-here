# What is programming, anyway?

## What you've been told

There are many commonly-held beliefs that are half-truths and myths.
I'll try to address some of the most common I've heard, and give a perspective that might be useful to an outsider.

### Programming is just giving a computer instructions

This is a case of a true but unhelpful fact.
When programming, one is give a computer instructions, but isn't this the same as moving a mouse and expecting the computer to move the cursor?  For this description of programming to be useful, some context needs to be introduced.

First, what sorts of things can we even ask a computer to do?  There are some requests that we can make that we input through an application, such as copying and pasting text, or refreshing the page in a browser.
These usually aren't considered programming.
Programming generally is used to describe giving more fundamental and menial instructions, that only become meaningful after some tricky construction.
It's like building a table from scratch versus from an IKEA kit.
The first requires skill, and can give a product more suited to one's needs, but a similar result might be easily constructed from a pre-made kit.

If the previous paragraph sounds cagey, that's because there are no hard distinctions in what constitutes programming or not.
There are programming languages TODO that consist of dragging and dropping blocks on a screen, and also programming languages that expose every wire in the machine to the programmer.
Hopefully, the rest of this chapter will clarify the differences.

### Programming is only for "X" people

There are several images that come to mind when thinking of programmers: the bearded man hunched in his parents' basement, the casually-dressed Silicon-Valley startup engineer, or perpetually overdressed square in the office.
They all exist, but aren't anywhere near comprehensive.

Who is a "programmer" is pretty ill-defined \(noticing a pattern?\), but you could make the argument that any businessperson putting together a complex spreadsheet, or chef writing a recipe are programmers.
At the very least, the same skillsets central to programming can enhance almost any career.

I personally have met people of all genders and orientations, all races, all ages, and all social preferences who participate in "programming."

### Programming is hard

This is a fair point.
Programming is really hard, but it's important to understand that the "hardness" worst at the beginning.
Learning curves can be deceptive, but to be fair, the curve for programming is particularly tough.

One writeup I enjoy illustrates this with well-done graphs.
It's pretty commercially-focused, but I think a lot of what they say applies to hobbyists as well.
It's a little controversial, but taken with a grain of salt, it's a good skim/read: [https://www.vikingcodeschool.com/posts/why-learning-to-code-is-so-damn-hard.](https://www.vikingcodeschool.com/posts/why-learning-to-code-is-so-damn-hard)

### Programmers never get anything done

If you've been in a workplace around programmers, you probably have felt the frustration of missed deadlines and slow results.
Programming can be a surprisingly long process, especially if it needs to be done with accountability to commercial needs.

That said, it's possible for one person to code a game or app in only a day or two.
The difference is explained in another writeup I enjoy, but I'll copy the main points.

1. Performance
2. Edge cases
3. Multiple platforms
4. Interactions with other code
5. Testing

If you're interested check out [https://wtfismyengineertalkingabout.com/2017/03/11/i-wrote-the-sql-query-in-5-mins-why-does-my-engineer-say-it-will-take-a-month/](https://wtfismyengineertalkingabout.com/2017/03/11/i-wrote-the-sql-query-in-5-mins-why-does-my-engineer-say-it-will-take-a-month/).
In short, writing an email in the workplace isn't much more work than at home, but the requirements for business programming take much more time to address.

## What they're not telling you

There are also some tragically under-shared facts about programming that are worth mentioning.

### Programming is fun

### You never stop learning

### There are many ways to learn

## What are computers?

Okay, enough with the silly societal issues.
Let's get down to some cold hard programming.
Well, let's at least set the groundwork first.


### Gotta go fast

Computers are really just machines like any others, just with different goals.
In the 19th century, while people were designing new machines for manufacturing and transportation, Charles Babbage designed another machine, for computation.
Long before that, though, people used abacuses as a mechanical \(but human-powered\) aid to arithmetic.

The operations that a computer can actually do aren't all that exciting.
The hardware itself isn't able to do much more than add and move numbers around.
We only care about modern computers because they do this _really quickly_.

Like, mind-blowingly quickly.
There are a few things that make it difficult to say _exactly_ how quickly, but I'll take my computer for example.
Take this with a grain of salt.

I am writing this on a 5 year old MacBook Air.
The processor is clocked at 1.7 GHz, actually on the slower side today.
Still, this means it can do \(very approximately\) 1,700,000,000 additions every second.
I'm no math whiz, so 1,235,266,732 + 356,234,347,345,253 will take me a good couple of seconds, lets say 10.

If my computer thought that it also took around 10 seconds to do the addition, \(they are big numbers, after all\), the 10 seconds of computer time translate to 17,000,000,000 seconds of me time.
That's 283,000,000 minutes, or 4,722,000 hours, or 200,000 days, 539 years.

If I was being being paid $10/hr to add numbers, it would only be fair to pay a computer $47,000,000/hr for the same time spent.

Thankfully, we don't need to pay computers.
We do need to point them in the right direction, though, and that's where programming comes into play.

### 1s and 0s

Computers are fast, but they are also pretty dumb.
How dumb?  Yes.
What does that mean, we ask? 10001110.
Are you messing with me?  No.
What do you mean, no?  00000000.

That was pretty meaningless, and so is everything computers do.
At the lowest level, computers are just one big electrical circuit that does neat things.

One level up, we give it _very_ simple instructions.
I'll write some pseudocode \(e.g. not quite real\) for the ARM processor in your phone below.
Every X1, X2 etc refers to a register, or slot that we can store values in \(your phone probably has 32\).

```
start:          ; A label to jump to
mov X1, #400    ; Put the number 400 into the first slot
mov X2, #2      ; Put the number 2 into the second slot

loop:           ; Another label we'll use in a second
add X2, X2, #4  ; Add 4 + what's in X2, and store it in X2
sub X3, X1, X2  ; Put X1 - X2 into X3
mov X4, X3      ; Put X3 into X4
cbnz X4, loop   ; If the number 0 isn't in X3, jump up to the loop label

HLT 0           ; End the program
```

This should be completely incomprehensible, so don't worry if you don't see what's going on.
This little program deviates from best practice for simplicity's sake and for illustration, but you should note a few things.
First, there are only 4 real operations the computer is actually doing: Moving a number into a slot, adding 2 numbers, subtracting 2 numbers, and jumping.
These are the sorts of things that a computer knows how to do.

Going deeper down the rabbit hole than this really does require computer architecture, and there's much more to this low-level programming than what I demonstrated, so for now, and maybe forever, you may happily imagine magic is at work.
I personally like to imagine dumbly-fast/quickly-dumb little elves running around putting numbers in different slots.

Also, before we move on, I'd like to note, there's a bug in the program I wrote above!
We start at $X2 = 2$ , then $X2 = 6$ , $X2 = 10$ , $...$ , $X2 = 398$ , $X2 = 402$ , $...$ .
If X2 was ever 400, then we would end and go to the HLT instruction, but as written, this will never happen.
Programmers might never realize this, and the computer will neither realize nor care.
Fastly dumb.

### Layered abstractions

So all computers can do is move around numbers?  How can that be?  My computer recommends me movies, lets me store my notes, and helps me doctor pictures of myself.
There are no numbers in any of those tasks!

Actually, there are.
You could feasibly perform all of those tasks with a pen and paper.
\(A really big pen with a ton of paper, and insane amounts of time\).
This is basically what a computer is doing, but because it's so fast, we can build "abstractions."

Take the adding example from [1s and 0s](#1s-and-0s).
There was no multiplication at all!
But I claim we had all of the tools necessary to multiply to our heart's content.
How could you multiply 20 \* 25 without multiplying?  Easy.
$$20*25 = 25+25+25+25+25+25+25+25+25+25+25+25+25+25+25+25+25+25+25+25$$
Well, maybe not _easy_ in the conventional sense, but for a computer, this is almost instant.
So, we can talk about multiplication in nice easy terms like $20 * 25$, and leave the busy work to the computer.

This is an example of an _abstraction_, in which we do a little bit of formulating something messy in order to not have to worry about it later.
For example, a simple task like "getting groceries" can be an item on our to-do list, and because we have a name for it, we never have to worry about the thousands of tiny tasks that make it work.
I'll start to break down the task like a computer would, and it will hopefully become clear why abstractions are so critical.

```
"Get Groceries"
|---Write item list
|   |---Get materials
|   |   |---Paper
|   |   |   |---Find paper
|   |   |   |   |---Look in cabinet
|   |   |   |
|   |   |   |---Bring paper back to kitchen
|   |   |
|   |   |---Pencil
|   |       |---Find pencil
|   |       |---Retrieve pencil
|   |
|   |---Determine needed foods
|   |   |---Look in fridge
|   |   |   |---Look for near-empty containers
|   |   |   |   |---Check door
|   |   |   |   |---Check drawers
|   |   |   |   |   |---Check left drawer
|   |   |   |   |   |---Check right drawer
|   |   |   |   |
|   |   |   |   |---Check shelves
|   |   |   |       |---Check bottom shelf
|   |   |   |       |---Check middle shelf
|   |   |   |       |---Check top shelf
|   |   |   |
|   |   |   |---Check expiration dates
|   |   |       |---Check door
|   |   |       |---Check drawers
|   |   |       |   |---Check left drawer
|   |   |       |   |---Check right drawer
|   |   |       |
|   |   |       |---Check shelves
|   |   |           |---Check bottom shelf
|   |   |           |---Check middle shelf
|   |   |           |---Check top shelf
|   |   |
|   |   |---Look in cupboard
|   |   |   |---Look for near-empty containers
|   |   |   |   |---Check shelves
|   |   |   |       |---Check bottom shelf
|   |   |   |       |---Check middle shelf
|   |   |   |       |---Check top shelf
|   |   |   |
|   |   |   |---Check expiration dates
|   |   |       |---Check shelves
|   |   |           |---Check bottom shelf
|   |   |           |---Check middle shelf
|   |   |           |---Check top shelf
|   |   |
|   |   |---Consult stomach
|   |
|   |---Write needed foods
|       |---Remember findings
|       |---Write each finding
|           |---Recall spelling
|           |---Write each letter in order
|
| Get to store
| Buy items
| Return home
| Store items
```

This gets out of hand very quickly.
There are repeated instructions (checking shelves, for example), and far more details than we want to concern ourselves with when planning the outing.
The good news is that humans are really good at creating abstractions to ignore the more banal aspects of grocery shopping.
The bad news is that computers aren't good at this, and trying to see eye-to-eye can be really frustrating.
This is what we pay programmers for.


### OS

Operating

## Why programming languages?

### Computers weren't general purpose

### Originally punch cards

### Languages are easier, and get more and more like English

### It's easier to reason about things that are similar to what we actually think

## Why is programming hard?

### If tools are getting better and better, why is it hard

### Simply, people had to make those tools

### Putting the tools together takes work

### There are a lot of tools

### Difficult problems

### Modularity

### 




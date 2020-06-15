Who I am.

Thansk for coming

5 principles 

What I do, NE Bytes, etc. twitter link. 

Writing software is hard. 
Hard to keep things simple, uncluttered and flexible so that as you add code the design doesn't get harder to use and add to in the future. 

Every choice you make in writing code means that future you and your team 's work can be harder or easier depending on what you choose
Writing code is hard, reading code can be harder. We do more reading than writing but the writing has to take the reader into account.

Accidental complication and Essential Complication. 

Run camerata at work (dojo) for the last 8 years or so, I talk to lots of devs at conferences and meetups and I interview a fair few at work. 

Lots of people talk about SOLID as the one thing that is desirable for your code. To the point that people in interview will volunteer that they know 
all about it without being asked. I will come back to this in a bit.
As a rule-of-thumb but I don't think it's that. It's like exercise, no one does it.


Hillel Wayne 

Solid is OOP related because of it is of it's time.

5 principles

SR - All classes should have one responsibility (actually one reason to change)

OC - All classes should be open and/or closed

LS - ???

IS - All interfaces segregated

DI - Put your dependencies upside down. 

Received Wisdom

Why Solid and not something else?
Why SOLID won ? Robert C Martin INfluencer
Agile, TDD Clean code, software craftsmanship

1995 - ten commandments of OOP, wrote articles and books. Michael Feathers - came up with SOLID 
Clean Arch, in all the books, Code Code, right person at right time. Common Wisdom

OOP === SOLID, just a set of decisions

Problems with SOLID are many. Confused in each part, some advice, some strategy, some are goals. Also not supported by the evidence that is offered for some of them. 

Open Closed and Liskov particularly. Others are tautologies of two basic concepts in CS. 

I want to propose a different way of thinking but all of these things are available to anyone, not invented anything here.


Kamal

Liskov invented encapsulation data abstraction, data hiding (and distributed systems), classes
Programming with Abstract Data Types 1974 - stacks, functions, class - Java invention!!! without interfaces, static type checking
Polymorphism 
Exception handling

Foundational. 

Modularity

it's hard

SOLID is often misapplied and misunderstood, even when the advice is clear.
DRY 
Dependency injection

Cohesion and Coupling begin with CO
 Make code more understandable., easier to change


Allow multiple implementations?






Unfortunately, a lot of people say this then can only remember SINGLE responsibility

Guiding principles for achieving simplicity in your code. 

Object oriented programming (from early 2000s ) so maybe not so appropriate now with the wrold doing javascript?

Interaction with each other - therefore be careful of using too much spreading out.

Text book definitions

Really about two things if anythign - cohesion and coupling. 
Define Cohesion and Coupling - Connascence


S _ No huge classes or code files
O - horrible code - encourages hierarchies of code
L - very confusing - not really what we want
I - Cohesion
D - 


Single responsibility principle A class or function should only have a single responsibility, that is, only changes to one part of the software's specification should be able to affect the specification of the class.
Open–closed principle[7] "Software entities ... should be open for extension, but closed for modification."
Liskov substitution principle[8] "Objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program." See also design by contract.
Interface segregation principle[9] "Many client-specific interfaces are better than one general-purpose interface."[4]
Dependency inversion principle[10] One should "depend upon abstractions, [not] concretions."[4]


How easy is this code to change or throw away?


All care about writing good software

This started out as a rant to colleagues, converted it into a haiku on twitter, then Sam asked me to try making it into a talk. I will try not to be the 
old guy shouting at clouds.

Maybe not for simple console applications and tools but for stuff we want to be around for a while, libraries, apps, products we 
want to be able to continue to work with them easily into the future without them becoming a mess.

Doing that requires experience and discipline and, since programming is more art and craft than science, we need heuristics to guide 
us. Medicine and civil engineering are older professions and have more grounding in the real world. If you don't build a bridge correctly 
you find out pretty quickly. Or your patient dies. If you add a line of code in the wrong place, you may not find out for a long time and 
have people following your choice to build up a set of code that becomes unmaintainable. 

Mention agile manifesto, uncovering working software.
"We are uncovering better ways of developing
software by doing it and helping others do it."

In programming we have heuristics like "goto considered harmful", On the criteria to be used in decomposing systems into modules - Dave L Parnas,
Liskov "data abstraction".

Where did SOLID come from ?

DRY - Copied stuff is not as bad as the wrong abstraction

SOLID

S - Single Responsiblity

This principle was described in the work of Tom DeMarco¹ and Meilir Page-Jones². They called it "cohesion". They defined cohesion as the functional relatedness of the elements of a module.
“Each software module has one, and only one, reason to change” Not a single responsibility.



O - Open Closed

Bertrand Meyer made this principle famous in the 1980s, which appeared in his book Object-Oriented Software Construction³. 
Unfortunately, Bob Martin took his justification for this principle. But reading the original text, Meyer is not talking about 
this at all, he is talking about published interfaces. COM IUnknown, etc. Windows interfaces public API that cannot change 
Windows - Raymond Chen 
Software systems be designed to allow the behavior of those systems to be changed by adding new code, rather than changing existing code.

Make software easy to extend to new behaviour without having to make lots of changes to existing code. Good principle. But not backed up 
by the justification. Also in tension with YAGNI principle.

IUIFramework2 and IUIFramework
Extend what the module does without changing the base implementation. Which is usually achieved through an inheritance hierarchy, 
programming to an interface or duck typing.


L - Liskov Substitution principle - examples completely wrong. Implies inheritance or duck typing at least.

Barbara Liskov’s famous definition of subtypes, from 1988 in a conference keynote address titled Data Abstraction and Hierarchy. In short, this 
principle says that to build software systems from interchangeable parts, those parts must adhere to a contract that allows those parts to be 
substituted one for another. But the original paper, makes a claim "". This is relaxed and still claimed as Liskov's principle. 
Like saying that we strictly adhere to the no snakes on a plane principle, but we have relaxed it slightly to include ... 
any hissing animals with no legs and forked tongues are optional.
 100% comptabile so it can't be detected as different from the outside. More like changing the implementation of a module to use a stack instead of a list. 
 Not viewable outside of the module so obeys the principle.

I - Interface Segregation

Keep interfaces small and focussed. Cohesion again. Wide interfaces may change for many reasons causing undesired changes in all the code. 
Hyrums law (Hyrum Wright) https://www.hyrumslaw.com 

With a sufficient number of users of an API,
it does not matter what you promise in the contract:
all observable behaviors of your system
will be depended on by somebody.

Time taken to run, level of performance.

D - Dependency Inversion 

Depend on abstractions not concrete behaviour, makes for mor reliable code, again cohesion and coupling. Cohesion good, some coupling good ish. Mostly bad.


------------------------------
Hillelogram

Part of the issue is that usual advice is easily misapplied and misunderstood. See:

- DRY
- Dependency Injection
- Reduce Coupling


People confuse cohesion and coupling all the time, but they're unrelated.

Watching Liskov's lectures and reading her references was super helpful for him.


Another paper Liskov referenced: "Dataless Programming" by RM Balzer:  https://rand.org/content/dam/rand/pubs/research_memoranda/2007/RM5290.pdf. It was designed so you can change "an array to a list without changing the source statements" <- proto abstract data types


The two share papers are similar in that they solve an implmenetation issue by modifying source languages. In particular, hiding information. Now talking about "Information Distribution Aspects of Design Methodology", by DL Parnas: https://


"The connections between modules are the assumptions which hte modules make about each other." Only make changes that do not violate the assumptions that other modules have

(gonna shill design-by-contract here)

Liskov invented the abstract data type. Her paper on them looks super close to modern programming. We went from "what even IS structure" to "formal theory of data" in like 3 years, at least in academia

------------------

Robert Martin - Design Principles and Design Patterns 2000s
Took ideas floating around and gave them an acronym
Solid design Principles
Single Responsiblity
Open Closed
Liskov - subclasses 
Interface Segregation
Dependency Inversion


"Perfect state" but Don't give you guidance on how to get there. 
All at different levels

Open Closed - Goals
Single Responsiblity and dependency inversion are coding strategies
Liskov
Interface segr

Managing dependencies - coupling and cohesion.

If you use something and it changes, you have to change?
When things you depend on chang e 


Steve Freeman Nat Pryce
loosely completelyed
highly cohesive
easily composable
context independent (dependencies) composable


Rearrange
Throw them out

INterface segrateion (statically typed languages usually) depending on signature of the method yo are calling. Ruby, JS etc. 
Liskov about subclassing. substitute a subclass. Impose typeof for selection between


Squint test 


is it DRY (within the module not across everywhere)
Does it have one responsibility
fDoes everything in it change at the same rate 
Does it depend on things that change less often than it does? (depend on things less changing)



Sandi Metz.



Complexity

Coupling -> Cohesion -> Connascence ?

Connascence (Coupling wooly term)

I think connascence is a great tool for thinking through coupling. Coupling is everywhere. And you can improve it not by removing it but making it weaker. 

Two software components are connascent if a change in one would require the other to be modified in order to maintain the overall correctness of the system.

Two (Jim W) pieces of software share connascence when a change in one requires a corresponding change in the other

Static code [ easier to detect and refactor ]
Name (agree on the name of something to use it - function, variable)
type (agree on type of something, returned from a function, to create something)
Meaning (agree on what a string is, id represents)
Algorithm (agree on algorithm used - eg. encryption)
Position (one call has to follow or be used in order, height and width in correct order)

Running code dyanmic
Executing order (make tea before drinking it) locking e.g.
Timing (timeouts in network)
Value (two values are related) invariance
Identity (two components reference the same object)

Refactoring successfully should take code from lower back up to top.

More than one form of connascence can occur in the same piece of code.

Imperfect 
strength (how hard to refactor or discover)
locality - how far apart they are. Far apart should be weak. Strong in same function, module etc. 
Degree - size of impact, connacsecnt with one or thousands.

Coupling
Cohesion
Cyclomatic Complexity - Skew to the right

4 Simple Design Rules (Kent Beck) Core XP Practices

In order, and cyclic:

- Passes all tests (refactoring, documentation) it should have tests. Good way of making looser coupling
- Reveals intent (least astonishment), naming, meaningful abstractions - Reading more than writing. Accurate description.
- No duplication - not DRY - duplication of knowledge not duplication of code (implying inheritance)
- Has fewest elements to maintain other rules. Coherent or coupling

Reduced to 3 by jbrains

1996 - Meilir Page-Jones What every programmer should know about object oriented design.

Lots of things proposed by other people:
Principles in Software (Jim Weirich): Grand unified theory of software design

SOLID
Law of Demeter
DRY
Small Methods
Design by Contract


Essential vs Accidental Complication (JBrains)

problem is hard, system is complicated

cut corners, don't worry, get it out the door
cost of a feature is dominated by cost of accidental Complication

Nothing to do with how hard it is and how much your design sucks



DRY can obscure larger patterns or abstractions in your code - Sandi Metz

7000 line function

Composition over inheritance - strongest form of coupling in OO 
implementation inheritance  sharing code 


Not here to tell you but SOLID is the most over rated and mis understood thing and I believe there are 
other ways and simpler ways to frame the same sorts of ideas about structure. 

Hear it mentioned in conversation and conferences but seems to be like exercise, eating healthily and writing unit tests, everyone talks about it but no one is doing it. 




Who I am

Barbara Liskov
Dijkstra - <goto statement> considered harmful 
Dave Parnas

Spend a lot of time talking to other devs
Interviewing at work, developer meetups and conferences

A lot of people talk about SOLID as a thing but not many people can express what it is. 
Interview anecdote

Take what did with ten commandments

Origin Uncle Bob wrote an article in 2009 "Getting a SOLID start" but had been floating around since probably 2000

Five Elements
Single responsibility (make objects cohesive)
Open Close - open for extension, closed for modification (program to an interface - coupling) Betrand Meyer 1988 
Liskov Substitution - does not obey - coupling. Relaxation of that standard
Interface segregation principle - make interfaces as small as possible (cohesion, coupling)
Dependency Inversion Principle - depend on abstractions or interfaces not concrete types - coupling

With examples

Design by Contract - Bertrand Meyer


Liskov (early 1990's) Bob Paraphrased and changed it!!!!

A supertype is defined with some set of characteristics that all of its subtypes then inherit. In turn, subtypes may then choose to override the supertype’s implementation of some behavior, thus allowing for behavior differentiation through polymorphism. This is an extremely powerful technique; however, it raises the question of what exactly makes one object a subtype of another. Is it enough for a particular object to inherit from another? In 1987, Barbara Liskov proposed an answer to this question, arguing that an object should only be considered a subtype of another object if it is interchangeable with its parent object so far as any interacting function is concerned. Liskov and co-author Jeannette Wing further clarified this idea in their 1994 paper, A Behavioral Notation of Subtyping [1], in which they set out a requirement for constraining the behavior of subtypes:

From <https://severinperez.com/software/2018/10/04/making-the-most-of-polymorphism-with-the-liskov-substitution-principle.html> 

Contracts
Don't break the contract and don't change the behaviour
Shared interface and exact behaviour. Relaxed version of that is 


Not advocating for poor quality code but I am saying that it's a bit of a cargo cult. We say we care about it but it's so badly defined that I don't think it's useful and it's tautalogical

Single responsibility - useless doesn’t really tell you much - one reason or several related reasons? 

Unnecessaryily complicated, isn't supported by the evidence - particularly Contracts, Liskov

C is the only letter you need (sesame street)

Pay attention to cohesion, coupling, Demeter, connascence, complexity

Writing Code Katas - spend time reading code too

Wrong abstraction is worse than duplicated code - Sandi Metz




D. L. Parnas. Information Distribution Aspects of Design Methodology. IFIP Congress, 1971  “The connections between modules are the assumptions which the modules make about each other.

Objects of subtypes should behave like those of supertypes if used via supertype methods  B. Liskov. Data abstraction and hierarchy. Sigplan notices, May 1988

Twitter search Liskov Coupling


hillelogram
·
Jul 12, 2019

From <https://twitter.com/hillelogram/status/1149758576300183552> 


Roman Empire
@rkofman
·
Jul 11, 2018

From <https://twitter.com/search?q=liskov%20coupling&src=typed_query&f=live> 
am looking to catalog a list of key concepts for writing better code. Things as disparate as: Cohesion, Coupling, DRY, Law of Demeter, Liskov Substitution Principle, etc. What are others that help drive your coding best practices? (Or you've been told should)

From <https://twitter.com/rkofman/status/1017082608264441856> 


Design Stamina Hypothesis  - Martin Fowler

Time + Code = misery
Early on design takes time


XP Surgery


https://xpsurgery.com/resources/connascence/

https://practicingruby.com/articles/connascence


https://codesai.com/2017/01/about-connascence


https://en.wikipedia.org/wiki/Connascence



Simplicity is at the very foundation
of Software Engineering…
“I conclude that there are two ways of constructing a
software design: One way is to make it so simple that
there are obviously no deficiencies and the other way
is to make it so complicated that there are no obvious
deficiencies.
The first method is far more difficult…”
C. A. R. Hoare, “The emperor’s old clothes.”


Simplicity is at the very foundation
of Software Engineering…
• Decomposition
• Abstraction
• Layering
• Encapsulation
• Information hiding

…Because simple software is
• Maintainable
• Reliable
• Testable
• Extendable
• Readable
• Usable
• Of higher quality



Simple software is…
• According to Kent Beck:
– Appropriate for the intended audience
• The people that have to work with it have to understand it
– Communicative
• Every idea that needs to be communicated is represented in
the system
– Factored
• No duplication of logic or structure
– Minimal
• The system should have the fewest elements possible




Types of complexity
• Fred Brooks in “The Mythical Man Month”
defines complexity as
– Essential
• Inherent to the nature of the problem
– Accidental
• Limitations in tools, knowledge, etc


Example: essential vs. accidental
complexity
• Essential complexity
– A text file editor has to support create/open,
close, save, and edit functionality for text files
• Accidental complexity
– Configuration management
– Software builds
– Testing
– Programming languages, IDEs, etc

Make code small and composable. 
Don't new loads of helper objects up within your large class, move them to the constructor if you can, then move them out into explicit dependencies so that 
they can be changed by future you (or someone who comes along later). Tying yourself to dependencies will make it harder for you code to be used later on. 
Can;t predict when or how your code will be written in the future. 
Use code that you have written but in another context. 

Inject dependencies - don't 

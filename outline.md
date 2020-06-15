---------------------------------------------------------------------------

Hello, good morning, good afternoon or good evening. Thanks for coming to this talk. 

My name is Derek Graham and I am a principal developer at Sage in Newcastle. 

I've been writing code for a while now and as well as my day job, I run a programming camerata for junior 
developers and also run a local .net user group "NE Bytes". Run camerata at work (dojo) for the last 8 years or so, 
I talk to lots of devs at conferences and meetups and I interview a fair few at work. 

What I want to talk about today is the SOLID principles, why I don't think they are a good idea and 
what is a better idea. I'm not claiming to have invented anything here but this has been my experience over the last few years
of being annoyed by SOLID. 

This talk originally started as a discussion with a couple of colleagues about designing a feature we were working on.
Someone was complaining about the structure and said we should be doing SOLID. I, like a troll, said what's that and he did 
what I have noticed most people do when they mention SOLID, they can maybe get the first principle but then the list quickly dries up.

I've noticed this in an interview context and in general dev conversation where someone will confidentally volunteer they know all about 
SOLID then totally fail to back it up. I don't think it's really a personal failing, I think SOLID is over sold, it's confused in itself, 
the academic evidence it claims is not bourne out and it's not really appropriate anymore if it ever was.  

SOLID is like exercise, eating healthily or writing unit tests. We all know we should do it but no one ever does :)

Problems with SOLID are many. Confused in each part, some advice, some strategy, some are goals. Also not supported by the evidence that is offered for some of them. 

Open Closed and Liskov particularly. Others are tautologies of two basic concepts in CS. 

I want to propose a different way of thinking but all of these things are available to anyone, not invented anything here.
Easier to reason about and finish with a different formulation that I tend to use now but didn't invent.

I also want to confess this is not a preaching kind of talk. I once had the honour of maintaining a system early on my career 
where one function was 7000 lines of C code so ...

This started out as a rant to colleagues, converted it into a haiku on twitter, then Sam asked me to try making it into a talk. I will try not to be the 
old guy shouting at clouds.

Maybe not for simple console applications and tools but for stuff we want to be around for a while, libraries, apps, products we 
want to be able to continue to work with them easily into the future without them becoming a mess.

Doing that requires experience and discipline and, since programming is more art and craft than science, we need heuristics to guide 
us. Medicine and civil engineering are older professions and have more grounding in the real world. If you don't build a bridge correctly 
you find out pretty quickly. Or your patient dies. If you add a line of code in the wrong place, you may not find out for a long time and 
have people following your choice to build up a set of code that becomes unmaintainable. 


Not advocating for poor quality code but I am saying that it's a bit of a cargo cult. We say we care about it but it's so badly defined that I don't think it's useful and it's tautalogical


---------------------------------------------------------------------------

Writing software is hard. 

Hard to keep things simple, uncluttered and flexible so that as you add code the design doesn't get harder to use and add to in the future. 
Every choice you make in writing code means that future you and your team 's work can be harder or easier depending on what you choose
Writing code is hard, reading code can be harder. We do more reading than writing but the writing has to take the reader into account.

Writing software is managing two forms of complication - essential complexity (the difficulty of the problem domain) and accidental complexity 
(where we get in our own way and write "bad" code).  Make code more understandable., easier to change

Types of complexity
• Fred Brooks in “The Mythical Man Month”
defines complexity as
– Essential
• Inherent to the nature of the problem
– Accidental
• Limitations in tools, knowledge, etc



How easy is this code to change or throw away?


C is the only letter you need (sesame street)


---------------------------------------------------------------------------

So what is SOLID? Way back in mid 90s, Robert Martin (Agile, TDD Clean code, software craftsmanship) was discussing the 
10 commandments of OOP online and proposed 11 of them! Michael Feathers 
identified 5 of them as making up the acronym SOLID and Martin then wrote articles and books (Clean *) about each one of the 5 principles.

So Robert Martin happened to be the right person at the right time and was one of the first internet influencers. At this time we are talking about 
writing OOP code in Java was pretty much the only game in town so SOLID sort of fitted nicely with the view of software at the time.

Object oriented programming (from early 2000s ) so maybe not so appropriate now with the wrold doing javascript? Interfaces are probably more like duck typing.

---------------------------------------------------------------------------

5 "principles"

SR - All classes should have one responsibility 

OC - All classes should be open and/or closed

LS - Subtypes can 

IS - All interfaces segregated

DI - Put your dependencies upside down. 

---------------------------------------------------------------------------

What's wrong with them, I can't hear you ask? Let's look at them one by one. 

S
A class or piece of code should have one Single responsibilty. Right out of the gate, this is often discribed as the 
"Should have one reason a module/class has to change". Not the same thing as a 
single responsibilty. Difficult because what we really want I think is not a single responsibility 
a sense of coherence in the code, that all the pieces belong there, they aren't too big 
and they aren't too small.

S _ No huge classes or code files

This principle was described in the work of Tom DeMarco¹ and Meilir Page-Jones². They called it "cohesion". They defined cohesion as the functional relatedness of the elements of a module.
“Each software module has one, and only one, reason to change” Not a single responsibility.

1996 - Meilir Page-Jones What every programmer should know about object oriented design.



CODING STRATEGY

---------------------------------------------------------------------------

O GOAL

Open - Closed. Open for extension but closed for modification. This is really about writing code 
so that you don't depend on concrete types but instead depend on abstractions. It's really about 
dealing with coupling. Coupling is a measure of how quickly your code will break if something about 
the code you depend on changes. Tightly coupled code may change constantly for small changes in other
parts of the system. 

Open-Closed gets it's name from one of the 5 principles that Bertrand Meyer outlined in his OO book from the lat '80s.
Unfortunately, he's not talking about the same thing. Meyer is more talking about a long forgotten time, closing a 
piece of software by publishing an interface to a library that is shipped and never changed and strategies 
that you might use to mitigate that. Not talking about polymorphism, more about using inheritance to copy and an 
existing implementation and add to it rather than processing different kinds of subclass to offer different behaviours.

O - horrible code - encourages hierarchies of code

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

---------------------------------------------------------------------------

Liskov Substitution. 

Liskov (early 1990's) Bob Paraphrased and changed it!!!!

A supertype is defined with some set of characteristics that all of its subtypes then inherit. In turn, subtypes may then choose to override the supertype’s implementation of some behavior, thus allowing for behavior differentiation through polymorphism. This is an extremely powerful technique; however, it raises the question of what exactly makes one object a subtype of another. Is it enough for a particular object to inherit from another? In 1987, Barbara Liskov proposed an answer to this question, arguing that an object should only be considered a subtype of another object if it is interchangeable with its parent object so far as any interacting function is concerned. Liskov and co-author Jeannette Wing further clarified this idea in their 1994 paper, A Behavioral Notation of Subtyping [1], in which they set out a requirement for constraining the behavior of subtypes:

From <https://severinperez.com/software/2018/10/04/making-the-most-of-polymorphism-with-the-liskov-substitution-principle.html> 


"Objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program." See also design by contract.

Sub types can be substituted for super types. Another inheritance based principle 
which is really talking about the same thing as open-closed, deriving one type from another and changing behaviour. 

Once again, LSP doesn't really say that. LSP talks about a much firmer constraint and is really talking about being able 
to substitute one object for another and not being able to tell that it has happened. again not really inheritance and polymorphism.

Allow multiple implementations? Cohesion and Coupling together.


Liskov invented encapsulation data abstraction, data hiding (and distributed systems), classes
Programming with Abstract Data Types 1974 - stacks, functions, class - Java invention!!! without interfaces, static type checking
Polymorphism is more like Set<T> than Set<List *>
Exception handling

CLU where T has equal : IEquatable. Generic Type Constraints
Liskov substitution - 
Inheritance for two reasons - sharing implementation, or way of expressing type hierarchy, LIFO, FIFO
OOPSLA 1988
Interact with it using Supertype and get same behaviour not polymorphism
Thinks it's funny
"Modularity based on abstraction is the way things are done" Found out conversation based on OOP
Subtype has to behave. 

Elephants are mice if you loosen the constraints such that we consider grey mammals with large ears.

Foundational. 

Modularity

L - very confusing - not really what we want

L - Liskov Substitution principle - examples completely wrong. Implies inheritance or duck typing at least.

Barbara Liskov’s famous definition of subtypes, from 1988 in a conference keynote address titled Data Abstraction and Hierarchy. In short, this 
principle says that to build software systems from interchangeable parts, those parts must adhere to a contract that allows those parts to be 
substituted one for another. But the original paper, makes a claim "". This is relaxed and still claimed as Liskov's principle. 
Like saying that we strictly adhere to the no snakes on a plane principle, but we have relaxed it slightly to include ... 
any hissing animals with no legs and forked tongues are optional.
 100% comptabile so it can't be detected as different from the outside. More like changing the implementation of a module to use a stack instead of a list. 
 Not viewable outside of the module so obeys the principle.

Liskov invented the abstract data type. Her paper on them looks super close to modern programming. We went from "what even IS structure" to "formal theory of data" in like 3 years, at least in academia


---------------------------------------------------------------------------

Interface segregation. Don't accidentally include lots of stuff in interaces because someone, somewhere 
will eventually depend on it and then the code becomes harder to change. Keep interfaces small and tighly 
focussed on what you are doing. Cohesion again. And because it's interfaces we're talking about 

"Many client-specific interfaces are better than one general-purpose interface."[4]

I - Interface Segregation

Keep interfaces small and focussed. Cohesion again. Wide interfaces may change for many reasons causing undesired changes in all the code. 
Hyrums law (Hyrum Wright) https://www.hyrumslaw.com 

With a sufficient number of users of an API,
it does not matter what you promise in the contract:
all observable behaviors of your system
will be depended on by somebody.

---------------------------------------------------------------------------

D - Dependency Inversion. Don't depend on concrete types, depend on abstractions. 
Don't create types in the body of your code - that's coupling, move stuff you need to your constructor 
and have them passed to you. Coupling again.
CODING STRATEGY
---------------------------------------------------------------------------


I think all five principls can be boiled down to two concepts - both 
beginning with CO. Coupling, Cohesion. Talk a little about them and a bit about Connascence


"The connections between modules are the assumptions which the modules make about each other." Only make changes that do not violate the assumptions that other modules have

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


Not here to tell you but SOLID is the most over rated and mis understood thing and I believe there are 
other ways and simpler ways to frame the same sorts of ideas about structure. 



Steve Freeman Nat Pryce
loosely coupled
highly cohesive
easily composable
context independent

---------------------------------------------------------------

is it DRY (within the module not across everywhere)
Does it have one responsibility
Does everything in it change at the same rate 
Does it depend on things that change less often than it does? (depend on things less changing)

Wrong abstraction is worse than duplicated code - Sandi Metz

"DRY - The wrong abstraction is more expensive than duplicated code"
Sandi Metz.

DRY can obscure larger patterns or abstractions in your code - Sandi Metz

-----------------------------------------------------------------


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


--------------------------------------------------------------------------

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



4 Simple Design Rules (Kent Beck) Core XP Practices

In order, and cyclic:

- Passes all tests (refactoring, documentation) it should have tests. Good way of making looser coupling
- Reveals intent (least astonishment), naming, meaningful abstractions - Reading more than writing. Accurate description.
- No duplication - not DRY - duplication of knowledge not duplication of code (implying inheritance)
- Has fewest elements to maintain other rules. Coherent or coupling

Reduced to 3 by jbrains

--------------------------------------------------------------------------

Law of Demeter
Small Methods
Design by Contract


Pay attention to cohesion, coupling, Demeter, connascence, complexity


Single responsibility - useless doesn’t really tell you much - one reason or several related reasons? 

Unnecessaryily complicated, isn't supported by the evidence - particularly Contracts, Liskov


Writing Code Katas - spend time reading code too

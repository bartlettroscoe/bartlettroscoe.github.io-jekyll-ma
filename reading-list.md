---
layout: page
title: Reading List
permalink: /reading-list/
---

This page lists some books about various aspects of software development and
software engineering that I have read over the years, especially during a
particularly intense period in the 2007-2008 time-frame.  I provide a brief
overview of the content of each book and why I think it is useful (or
essential) to read the book and what to look for in each.  These books --
along wtih the personal application of the ideas presented in them over the
next few years -- represent my basic education in software engineering.
Hopefully this reading list will help others the way it has helped me.

**Outline:**

* [Background](#background)
* [A) General Software Engineering Books](#a-general-software-engineering-books)
  * [A.1) Most Recommended Software Engineering Books](#a1-most-recommended-software-engineering-books)
  * [A.2) Recommended Software Engineering Books](#a2-recommended-software-engineering-books)
* [B) C++ Books](#b-c-books)
  * [B.1) Most Recommended C++ Books](#b1-most-recommended-c-books)
  * [B.2) Recommended Books on the Fine Details of C++](#b2-recommended-books-on-the-fine-details-of-c)
  * [B.3) Recommended Books on the History of C++ and why it has it's current form](#b3-recommended-books-on-the-history-of-c-and-why-it-has-its-current-form)

## Background

To provide some context and motivation for this reading list, here I describe
some of my background and experiences related to my software development
journey.  It is my hope that others can avoid the path that I took and instead
educate themselves about software development sooner than I did.

When I started my Ph.D. in Chemical Engineering in 1996 at Carnegie Mellon
University (CMU), I knew that I liked writing code and I liked the challenge
of learning and mastering the C++ language.  My first C++ book was "C++ Nuts &
Bolts for Experienced Programmers", 1995, by Herbert Schildt, and I read that
book cover-to-cover in about 2 days.  A few months after that I read Bjarne
Stroustrup's book [*The C++ Programming Language, 2nd
Edition*](#the_cxx_programming_language_special_edition).  While that book
mostly just covered the C++ language, Stroustrup made some references to
writing tests and some other basic software engineering best practices but it
was very minimal (after all, this was a book about a programming language, not
software engineering).  Later my first year of graduate school I was
introduced to the book [*Design Patterns*](#design_patterns_1995) by a
Computer Science Ph.D. student at CMU.  Armed with the knowledge of C++ and
Design Patterns, I set about writing a sizable amount of software implementing
advanced numerical algorithms for constrained optimization as part of my
Ph.D. work (the optimization package at that point was called rSQP++ for
reduced successive quadratic programming).

When I started working at Sandia National Labs in 2001 after my Ph.D., I
continued writing object-oriented parallel numerical software in C++,
extending my Ph.D. software package [rSQP++](../publications#rsqpxx_2003) to
support parallel computations with MPI (where the name was changed from rSQP++
to [MOOCHO](../publications#moocho_2009)).  Around 2003, I added the source
code (and history) for MOOCHO to the Trilinos project version control
repository.  Once in Trilinos, I created or significantly contributed to many
Trilinos packages.  By 2007 I had written a lot of software and was a prolific
contributor to Trilinos (the largest contributor to Trilinos in terms of
number of commits and lines of source code).  During that entire period from
1996 till 2007 I believed that I was writing quality object-oriented C++
software.  Then, in 2007, I began reading a larger portion of the modern
software engineering literature (some of which is highlighted in the lists
below) and came to realize my own knowledge gap in best practices for creating
and maintaining quality software.  After this realization, I began applying
many of the software engineering best practices to my CSE projects and
realized significant improvements in productivity and the overall quality of
the software I was writing. However, I was also horrified to realize that,
prior to gaining this knowledge, I had created tens of thousands of lines of
CSE software of insufficient quality and that I was now in a position have to
maintain.

It is my hope that this reading list we be useful and will help motivate
others to go on the same journey.  Once you are armed with this knowege, there
is no going back!

## A) General Software Engineering Books

Here is a set of books that I have read about general software engineering
that is largely independent of programming language (but is biased toward
object-oriented languages) that would recommend to anyone who is serious about
software development.

### A.1) Most Recommended Software Engineering Books

This section lists the books that I have read that I would mostly highly
recommend to anyone who is serious about software development. These books are
listed in the approximate order of importance and the order that I would
recommend people read them in depending on interest and focus.

<a name="code_complete_2nd_edition"/>

#### McConnell, Steve. *Code Complete (Second Edition)*. Microsoft Press, 2004

This is the single most useful book I have ever read about software
development. I wish I had read the first edition of this book back when I
first started doing serious programming (in about 1996). Steve McConnell is
one of the most respected voices in the software engineering community and he
gives sound advice on nearly every aspect of software construction. Areas
covered range from basic layout and construction of statements, control
structures, functions, classes, files, modules etc., to broader software
engineering issues like dealing with defects, software quality engineering,
and documentation. Steve articulates several important principles of software
engineering like The General Principle of Software Quality (i.e., improved
quality make software development cheaper, more predictable, and lower risk)
and its corollaries. Since reading this book my standards for writing clean,
clear, and robust code have gone way up. After reading this book, I now look
at the design, structuring, and layout of software with the same level of
standards that I apply to writing journal quality papers.

*Disclaimer:* Steve's advice on C++ is not the most current. He appears to be a
much more accomplished C programmer. For specific C++ advice, refer the
Effective C++ (3rd edition) and other C++ references given below.

#### Feathers, Michael. *Working Effectively with Legacy Code*. Prentice Hall, 2005

This is really the book that gives me hope that we can take very bad software
and through targeted incremental unit testing and refactoring, can turn it
into good software while implementing and delivering new functionality the
whole time. This book is where the rubber meets the road combining unit
testing and refactoring. If you read the book Refactoring by Martin Fowler and
(like me) felt a little uneasy about how this would apply to large nasty
software projects, then Working Effectively with Legacy Code is the book for
you. What's more, Michael mentions and reviews many of the object-oriented
principles in Agile Software Development as well as other little bits of
information that you will find in the other books listed here. I really see
this book as the logical culmination of the books Refactoring and Test Driven
Development. This book is packed with practical examples that show you nearly
every trick there is for refactoring nasty code to break dependencies and
getting code into a unit test harness. If by the time you are done reading
this book if you are not shamed into doing unit testing then you have no
business developing software. Before reading this book, I was not 100%
convinced about unit testing. After reading this book, I unit test almost
every non-trivial code as a rule and it has massively improved the quality of
the software that I write. There is no going back for me.

#### Martin, Robert C. *Agile Software Development (Principles, Patterns, and Practices)*. Prentice Hall, 2003

After Code Complete (2nd Edition), this is the next book that I would most
highly recommend. While Code Complete (2nd edition) covers object-oriented
design, I feel that Martin's book does a much better job of covering the
essence of object-orientation. In my opinion, the greatest contribution of
this book is in Chapters 7-9, and 20. In these chapters, Martin defines eleven
different principals of object-oriented design; five of these are related to
individual classes, and the remaining six are related to collections of
classes (i.e. packages). These eleven principles are:

General OO Principles:

* **1) SRP** (Single Responsibility Principle): Classes should have only one
reason to change.

* **2) OCP** (Open-Closed Principle): Software entities (classes, modules,
functions, etc.) should be open for extension, but closed for modification.

* **3) LSP** (Liskov Substitution Principle): Subtypes must be substitutable
for their base types.

* **4) DIP** (Dependency Inversion Principle): Abstractions should not depend
on details. Details should depend on abstractions.

* **5) ISP** (Interface Segregation Principle): Clients should not be forced
to depend upon methods that they do not use. Interfaces belong to clients, not
to hierarchies.

Package Cohesion OO Principles:

* **6) REP** (Release-Reuse Equivalency Principle): The granule of reuse is
the granule of release.

* **7) CCP** (Common Closure Principle): The classes in a package should be
closed together against the same kinds of changes. A change that affects a
closed package affects all the classes in that package and no other packages.

* **8) CRP** (Common Reuse Principle): The classes in a package are used
together. If you reuse one of the classes in a package, you reuse them all.

Package Coupling OO Principles:

* **9) ADP** (Acyclic Dependencies Principle): Allow no cycles in the package
dependency graph.

* **10) SDP** (Stable Dependencies Principle): Depend in the direction of
stability.

* **11) SAP** (Stable Abstractions Principle): A package should be as abstract
as it is stable.

These principles distill a great deal of object-orientation know-how down to
short acronyms like OCP (Open-Closed Principle). The other chapters that
describe many design patterns are also very useful like Chapters 13-17, 21,
23-29. Some of these design patterns are the same as given in the well known
book [*Design Patterns*](#design_patterns_1995), while others are new (at
least to me). Even with those patterns that are the same as in Design
Patterns, Martin gives them more context and helps to really flesh them
out. This is great stuff.

*Disclaimer:* This book is poorly named. While the introductory chapters
discuss Extreme Programming (XP), the remaining chapters of the book have
little to do with XP specifically and are only mildly related to Agile methods
in general. In fact, the discussion in Chapter 20 on packaging issues (while
it contains great material) runs contrary to more modern Agile approaches that
use continuous integration (see [*Continuous
Integration*](#continuous_integration_2007)). Unless a reader is specifically
interested in Agile methods, I would suggest that they just skim through
Chapters 1-6. I suspect that the majority of this book was written well before
the Agile angle was decided on and the title was mainly a sales ploy to take
advantage of the hot new term "Agile". Also, this book has many examples; some
are helpful but most (at least for me) were beating a dead horse (i.e. I
already got the point). For other readers, the examples may be more helpful if
they do not understand the points in the text.

<a name="domain_driven_design_2004"/>

#### Evans, Eric. *Domain-Driven Design*. Addison Wesley, 2004

This is a more advanced book on software engineering analysis and design. The
main focus of the book is on how to develop a deep supple model for a domain
and how to allow the software to reflect the domain model. The idea is to
bridge analysis and design so that they can feed into each other in an
iterative process. The book also deals with how to manage large-scale software
interactions. Continuous refactoring is a major theme of the book and the
approach is very compatible with Agile methods. I suspect that the core
message of this book will go over the heads of most readers that are not
deeply interested in software engineering. However, material like Chapter 10
on "Supple Design" are more at the level of Agile Software Development and
should be more practically useful to all software developers. Actually, I
think Chapter 10 is so good that it deserves to be read even if the rest of
the book is not.

*Disclaimer:* This book has a large bias for IT-type domains and for
programming languages like Java and Python where all memory is managed through
implicit pointers/references. Specifically, the definition of VALUE OBJECTs
needs to be refined for use in C++ that has true value objects. Also, SERVICES
might just as well be non-member functions in C++ rather than to be
shoe-horned into an object as a SERVICE. Anyway, the content in the book needs
to be revised for C++. Note that Evans appears to feel that C++ is not a very
good language for MODEL-DRIVEN DESIGN. One example reference is given in
"Domain-Driven Design Quickly" where Evans states "Java has been the default
choice of the last few years ... It has garbage collection, which, in
practice, turns out to be essential. (In contrast to C++, which just demanded
too much attention to low-level details.)". Notice the past tense word
"demanded"; it seems clear that Evans sees C++ as the past. I don't see this
bias as a problem in adopting these ideas in a C++ environment but this bias
is something to keep in mind when reading the book.

#### Poppendieck, Mary and Tom. *Implementing Lean Software Development*. Addison Wesley, 2007

This is a fantastic book about modern Agile software development. Here, the
authors cover several aspects of software development that I did not find in
most of the other books that I have read. One of the biggest things that I
took away from the book was the importance of avoiding waste by not
implementing any feature that is not absolutely necessary and/or of high
priority. The idea is to find, write, and maintain that 20% of code that
satisfies 80% of the desires of your customers. The whole chapter on "Waste"
was excellent and everyone who does or is associated with software development
should read this chapter. Another interesting topic the book covers is how
people fit into the software development process and what management practices
help to build strong teams and what management practices work to destroy
strong teams (e.g. individual rankings and compensation). Some other
interesting concepts to look for are "technical debt", "automation", and
"cycle time". It was also interesting to read that most mistakes that are made
in software development are due to a flawed process and/or supporting tools
and not due to bad developers. Therefore, we should first question and improve
the process and/or our development tools to make them more mistake-proof
before we point our fingers at individual people for the mistakes they
make. Simply asking people to remember more or giving them a big list of
things they have to do is not enough. Lastly, the "Try this" section of last
chapter "Journey" gives a great condensed summary of the whole book. If you
read nothing else, read this last "Try this" section and go back in the book
to look for further details and explanations.

*Disclaimer:* At the foundation for "Lean" software development is an analogy
to the Toyota Production System (TPS) for manufacturing. As with any such
analogy one can go too far (see [*Code Complete (2nd
edition)*](#code_complete_2nd_edition)) for a discussion of this issue) but
the authors appear to be able to only take the manufacturing analogy as far as
it can be usefully applied and not any further.

### A.2) Recommended Software Engineering Books

This next set of books provides valuable information on general software
engineering but I do not recommend them quite as highly as the books described
above.  However, many of these are still considered classics.

#### Fowler, Martin. *UML Distilled (Third Edition)*. Addison Wesley, 2004

A picture is worth a thousand words and a single well-written UML class
diagram can be worth 10,000 lines of raw C++ code. This is the third edition
of the highly popular and award winning book by Martin Fowler on the UML. This
short book (just 159 pages) is more information about the UML than most anyone
will need to know to be productive and communicate object-oriented designs
well with others. Fowler also sprinkles in several little tidbits of great
information like on "Design by Contract" about invariants, pre-conditions and
post-conditions. This is a great read.

<a name="design_patterns_1995"/>

#### Gamma, Erich, Richard Helm, Ralph Johnson, and John Vlissides. *Design Patterns (Elements of Reusable Object-Oriented Software*. Addison Wesley, 1995

This is the seminal work that really launched the patterns movement in
software engineering. This was the book that I read where the "light went on"
and I really got what object-oriented programming was all about. Most people
in computational science have a hard time relating to the examples in the book
but this is still well worth the read. In my experience, the most useful
patterns are ABSTRACT FACTORY, PROTOTYPE, ADAPTER, COMPOSITE, DECORATOR,
FACADE, PROXY, ITERATOR, OBSERVER, and STRATEGY. If I had to pick my four
favorite design patterns, I would say they are ABSTRACT FACTORY, COMPOSITE,
DECORATOR, and STRATEGY.

*Disclaimer:* Some of these design patterns in this book are more useful than
others. First, I think the SINGLETON pattern has done great harm to the
software development community since it has been used as an excuse to abuse
global data (no way around it). Also, I have found little to no use for the
patterns FLYWEIGHT, CHAIN OF RESPONSIBILITY, no INTERPRETER (but perhaps I
will some day).

#### Beck, Kent. *Test Driven Development*. Addison Wesley, 2003

I am not wildly excited about this book but it does sharply define Test Driven
Development (TDD) that has been shown to be so effective. This book describes
how you can use unit (and other) tests to drive your day-to-day coding work in
a way that makes you more productive in every way. For me, all of the really
useful information was in the Preface, and Part III (Chapters 25-32).

*Disclaimer:* I don't like the way the dialog in this book is written. There are
way too many examples that are used to demonstrate concepts that are
abundantly clear to me in the prose text. I get the feeling that Beck is
writing this book to the lowest common denominator of programmers. Therefore,
I got all that I needed out of Part III; I did not need the long-winded
examples in Parts I and II (but they might be more useful for some other
people).

#### Fowler, Martin. *Refactoring (Improving the Design of Existing Code)*. Addison Wesley, 1999

Continuous refactoring is one of the most important practices in all Agile
programming methods, right up there with TDD. Without the ability to refactor,
there is no DDD or incremental design (XP), or any other methodology other
than a straight Water Fall method. Most of the book is a catalog; you can read
the most important overview information in just a few Chapters (e.g., Preface,
Chapters 1-4 and 13-15).

<a name="continuous_integration_2007"/>

#### Duvall, Paul, et al. *Continuous Integration*. Addison Wesley, 2007

This is a recent book that covers many aspect of software management from
day-to-day development, to integration, to deployment, to post-delivery
maintenance. This book describes how you can keep every developers code
up-to-date, get updated code constantly and constantly check in modified code
without experiencing wasted time working with broken code. It also describes
how to make release and deployment "non-events". This book is very Agile
friendly.

#### Beck, Kent. *Extreme Programming (Second Edition)*. Addison Wesley, 2005

Extreme Programming (XP) is called "extreme" for a reason. There are some
radical ideas that Beck lays out in this book. While the Values and Principles
of XP are undisputed in the Agile community, some of the actual Practices are
less widely used. The practices can be seen as worthy goals in many cases but
apparently there is no record of any successful software project that has used
all of the practices. For example, XP suggests no extra documentation at all
beyond the code. The advice in [*Domain-Driven
Design*](#domain_driven_design_2004) is a little more reasonable and suggests
a small amount of extra documentation beyond the code.

*Disclaimer:* Extreme Programming (XP) is called "extreme" for a reason. Some of
the practices that Beck recommends are a bit "extreme" like requiring that
every line of production code be written in pairs doing pair
programming. There is a general softening of many of these practices as
described by Steve McConnell at
http://blogs.construx.com/blogs/stevemcc/archive/2007/10/08/5-questions-on-agile-development.aspx
and www.construx.com (do a local search on "Legacy of Agile Software
Development" on that page).

#### Schwaber, Ken and Mike Beedle. *Agile Software Development with Scrum*. Prentice Hall, 2002

This is one of the first major books on the Scrum software development
process. Scrum is primarily about software project management dealing with how
requirements (i.e. user stories) are collected and how the overall structure
of a software development project is put together. Scrum, like all Agile
methods, structures the software development process into a set of iterations
(called "Sprints" or "time boxes") where the maximum value to the customer
(represented by the "product owner") is the goal of each iteration
(sprint). Scrum is very sparse on any code-level software engineering
practices and therefore Scrum is often combined with the more accepted parts
of XP. If your objective is to be goal-oriented and you want to focus everyone
on meeting these goals (that are constantly updated and revised throughout a
development effort) and make them accountable for the outcome, then it is hard
to argue against Scrum. Even for big upfront design (BUFD) method, you should
consider using Scrum to drive the actual low-level development work.

*Disclaimer:* Even through this book is as recent as 2002, it is a little out
of date with respect to the current best practices in Agile software
development. One example of an out-dated principle is that idea that "quality"
should be one of the variables in a software project. When defined in a
certain way (e.g. how polished a user interface is) one can accept "quality"
as a variable but in general, fundamental internal software quality should
never be negotiable (see Kniberg's book [*Scrum and XP from the
Trenches*](#scrum_and_xp_from_the_trenches_2007)). Also, some of the details
of the Scrum process have been refined some in recent years (see [*Scrum and XP
from the Trenches*](#scrum_and_xp_from_the_trenches_2007)).

<a name="scrum_and_xp_from_the_trenches_2007"/>

#### Kniberg, Henrik. *Scrum and XP from the Trenches*. Info, 2007

In this book, the author describes how they implemented Scrum in his software
organization and he goes into a lot of the practical details of working with
Scrum on a day-to-day basis. Also, this book gives some of the updated best
practices of Scrum that are more recent. Lots of good stuff here.

#### Brooks, Frederick. *The Mythical Man Month: 20th Anniversary Edition*. Addison Wesley, 1995

Those ignorant of history are doomed to repeat the mistakes of the past. That
was my primary motivation for reading this book. This book is a well-known
classic on software engineering. The original edition of this book was first
published in 1975 and contains the experience and insight of the author
(Dr. Fred Brooks) primarily related to his leadership of the IBM Operating
System 360 project from the mid-1960s! That means that in 2009 (when I first
read this book) that much of the knowledge and experience contained in this
book goes back almost 45 years! The first 15 chapters of this 20th anniversary
edition are exactly the same as published in the original edition in 1975.
There are four additional chapters with some updated information as of 1995
(when the 20th anniversary edition was published). The added chapter 18
"Propositions of the Mythical Man Month: True of False?" is a great summary of
the (original) first 15 chapters. Going over these propositions, you see a
great many of the ideas and foundations for modern (2009) Lean/Agile software
engineering methods. It is very comforting to know that many of the principles
in Lean/Agile methods have more than a 40 year history. Some of the best
material in the book is where Dr. Brooks gives the essence of the joys and
challenges of software in Chapter 1 (i.e. 1975) and also where he identifies
and discusses the essential complexities in software engineering that will
never be magically solved (in the 1995 material). What is great about the
later 1995 material is that it is almost 100% consistent with modern (2009)
Lean/Agile methods, even though the terms "Lean" and "Agile" would not even be
officially coined for another 5 years or more. All of this just convinces me
that Lean/Agile methods are more consistent with the long standing wisdom in
the software engineering community than the process-heavy methods of the late
80s and 90s (i.e. CMM(I) and related methods).

*Disclaimer:* While many of the observations and advice in this book are
consistent with modern Lean/Agile, a good bit of it is not and Dr. Brooks
acknowledges this in the later 1995 chapters. In particular, much of the 1975
material assumes a variation of the Water Fall method which he strongly
acknowledges in 1995 is a bad way to try to develop software (see Chapter
19). In 1975, Dr. Brooks was also arguing that every developer should see
every part of the code which he totally changed his mind on in 1995 and has
come to believe in interfaces, specialization, and information hiding (see
Chapter 19).

## B) C++ Books

*Disclaimer:* This list of books was compiled in 2008 when C++98/03 was the
current C++ standard.  Much has changed with the introduction of the newer and
improved C++11, C++14 and C++17 standards.  However, much of the advice
provided in these books still holds up in these more modern C++ standards.
(And there are still billions of lines of C++ written in C++03.)

### B.1) Most Recommended C++ Books

Here I list several books on C++ that I suspect will be the most useful for
beginning and experienced C++ developers. I list these books in the order of
relative importance and not necessarily in the order that I would recommend
that a beginning C++ programmer would read them. Actually, it has been so long
since I first learned C++ that I have no idea what a good modern introductory
C++ book would be these days. In general, beware of C++ books written before
1998 since a lot has been learned about C++ since then. Some of the books
given below were written before 1998 so be careful of some of the advice you
find in them. Refer to the newer books (such as Effective C++ (3rd edition)
and C++ Coding Standards) for more current advise.

<a name="effective_cxx_3rd_edition"/>

#### Meyers, Scott. *Effective C++ (Third Edition)*. Addison Wesley, 2005

The book describes the most current, best advice on how to write good C++03
code and stay out of trouble. This book is not the first book that a beginner
would read on C++03 but it is probably the second.

#### Sutter, Herb and Andrei Alexandrescu. *C++ Coding Standards*. Addison Wesley, 2005

Here is a catalog of 101 items that summarize most of the C++ communities'
best practices (in C++03). The authors are well respected in the C++ community
and they provide many references to other respected authorities for every
item. In my opinion, some of these principles are more important than others,
but on the whole I highly recommend this book.

*Disclaimer:* Some of the items are not appropriate for all situations or are
just not quite correct in my opinion. I amend and nullify some of the items in
the Appendix of the tech report "Thyra Coding and Documentation Guidelines"
(see [my publications list](../publications)).

<a name="the_cxx_programming_language_special_edition"/>

#### Stroustrup, Bjarne. *The C++ Programming Language (Special Edition)*. Addison Wesley, 2000

Bjarne Stroustrup is the original implementer of C++ and is still highly
involved in the C++ standardization process (see [*Evolving a language in and
for the real world: C++ 1991-2006*](#evolving_cxx_1991_2006)). Most beginning
C++ programmers find this book hard to get through but it provides a very
comprehensive treatment of the C++ language and standard C++ library (i.e.,
the ISO C++98 standard). In later chapters, Stroustrup also gives a lot of
good advice on object-oriented design that is very compatible with everything
more recent that you will read coming out of the Agile community for
instance. (Note that this is essentially the same book as "The C++ Programming
Language (2nd Edition)", just with a hard cover.)

*Disclaimer:* Some of the advice in this book goes contrary to more recent best
practices in the C++ community. For example, where TC++PL and C++ Coding
Standards differ, go with the guidance in the latter.

#### Meyers, Scott. *More Effective C++*. Addison Wesley, 1996

While [*Effective C++ (3rd Edition)*](#effective_cxx_3rd_edition) provides
basic information on C++98/03, this book goes into some more advanced C++
concepts. This book describes a number of useful concepts and is a great place
to look for ideas. For example, I put Item 28 on smart pointers and Item 29 on
reference counting together and came up with the idea of smart
reference-counted pointers that has evolved into the current Teuchos::RCP
class (see paper [*Teuchos C++ Memory Management Classes, Idioms, and Related
Topics: The Complete
Reference*](../publications#teuchos_cxx_mem_mng_classes)).

*Disclaimer:* This book was published in 1995 (i.e., before the ISO C++ 98
standard) and some of the material is not relevant anymore. For example, much
of the material in Items 32, and 35 is obsolete.

### B.2) Recommended Books on the Fine Details of C++

If you really want to know the gory details of C++ and how to do crazy
powerful things with it, the following books will provide a lot of in-depth
information. I have not read every word in these books but I often refer to
them whenever I get stuck and can't understand why C++ is not compiling my
code or my program is not behaving the way that I expect.

#### Dewhurst, Stephen, C. *C++ Gotchas*. Addison Wesley, 2003

The author gives a list of 99 items that describe a lot of the ways to get
into trouble with C++ and how to avoid them. The fact that someone can
actually write an entire book on "C++ Gotchas" is just another indication of
how complex this language is and why very few people really excel in using it.
(In some ways, it also exposes some of the languages most serious deficiencies
that no upcoming C++ standard can fix, and still call it C++.)

#### Vandevoorde, David, and Nicolai M. Josuttis. *C++ Templates*. Addison Wesley, 2003

Here, the authors provide a very rigorous treatment of templates that would be
recommended for anyone writing non-trivial C++03 templated code. This book
contains material from the basic usage of templates to very advanced
techniques. This book also describes the nitty-gritty details of overload
resolution of C++ functions including how templated functions fit in. This is
very helpful when you are not sure why some code does not compile the way you
think it should.

#### Alexandrescu, Andrei. *Modern C++ Design*. Addison Wesley, 2001

This book describes some very advanced template-programming techniques with
C++03. If you are writing any type of complex template code, I would highly
recommend that you have this book and know what information it contains so
that you can find it when you need specific information.

#### Ellis, Margaret, and Bjarne Stroustrup. *C++: The Annotated Reference Manual*. Addison Wesley, 1990

This is a very old book on C++, the oldest that I mention in this list of
references. This book was meant to provide the starting point for what would
become the first offical C++98 standard. What is useful about this book is
that is provides very low-level details on the inner workings of C++ and gives
lots of examples of how C++ compilers implement common language features. For
instance, if you want to know how virtual functions are commonly implemented
and why they are so efficient, there are good examples given.

### B.3) Recommended Books on the History of C++ and why it has its current form

When looking at its current form, it is clear that C++ is a language that was
grown (i.e. evolved) while it was being actively used to write millions of
lines of code over many years. No one would set out to design a language from
scratch that looks like C++98. Therefore, if you really want to know why C++
is the way it is, the following publications from Bjarne Stroustrup are very
illuminating.

#### Stroustrup, Bjarne. *The Design and Evolution of C++*. Addison Wesley, 1994

If want to know where C++ came from and why most of the language is the way it
is, this is the book to read. This book covers the inception, development, and
growth of C++ from pre-1980 to 1993. I think to be a truly great C++
programmer and understand how to use C++ effectively, you need to know much of
what is in this book.

<a name="evolving_cxx_1991_2006"/>

#### Stroustrup, Bjarne. *Evolving a language in and for the real world C++ 1991-2006*, HOPL III: Proceedings of the third ACM SIGPLAN conference on History of programming languages, AMC, New York, pages 4-1 to 4-59, 2007

In this proceedings paper, Stroustrup picks up where he left off in The Design
and Evolution of C++. This is especially a good read if you want some insight
into the ISO C++ standardization process for C++11 and beyond.

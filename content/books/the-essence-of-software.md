+++
title = "The Essence of Software: Why Concepts Matter for Great Design"
date = 2025-11-09T23:36:00+01:00
draft = false
description = "A summary of Daniel Jackson's work on conceptual modeling and why clarity of underlying concepts is vital for robust software design."
categories = ["software-engineering", "design"]
tags = ["modeling", "conceptual-design", "daniel-jackson", "architecture"]
author = "Daniel Jackson"
book_publisher = "Princeton University Press"
book_title = "The Essence of Software"
+++



## Introduction

In software engineering, we distinguish abstraction (the programming idea) and representation (the code). In the same way, when talking about user interaction, we can have:

- the **conceptual level:** the abstraction. Comprises semantics, actions, data model, and purposes.
- the **user interface:** the representation, with :
  - **the physical level**: e.g. colour, size, touch, accessibility, Fitt’s law…
  - **the linguistic level** : icons, labels, site structure, consistency.  Must respect diversity of cultures and languages.

While there were many studies concerning the user interfaces, few addressed the conceptual level.  [“The essence of software”](https://press.princeton.edu/books/hardcover/9780691225388/the-essence-of-software), a book by [Daniel Jackson](https://press.princeton.edu/our-authors/jackson-daniel), professor of computer science at MIT, published by Princeton University Press, is one of those.

For Daniel Jackson,

> “Software can be viewed as a systematic composition of concepts”.

Jackson is applying the conceptual-model framework to software design.

Why is this important? For two reasons.

- Formalism has been relegated for decades to human-computer interaction (HCI) studies. HCI is important, but is actually the study of the how we present something. Where is the study of the what we present? Choosing a perspective or another influences all the chain of interactions that can or cannot be achieved.
- Studying the concepts at the base of an app/software/company/whatever, forgetting about the implementation details because not relevant at that level, we can focus on the epistemic value of the concept and its interactions with other concepts.

Engineering speaks of costs, performance, resilience: aspects that are important to humans but that usually stay invisible except when they fail.

Similarly, UX designers draft widgets, colours, fonts, and other aspects of the user interface that become conscious to humans only when something is not right (e.g. a mislabelled button or a confusing workflow).

Both groups have to work with data.

Designers, on the other hand, have to do with users’ behaviours, and their analysis is qualitative. They shape users’ goals so that they become resilient to their misdeeds while meeting their purposes.

Concepts thus come before the other two levels: first we must understand the concepts at stake, and from different perspectives, and then we can design the software interface and/or the software architecture (and then proceed to the implementation).

The link between the conceptual level and the UX level is then provided by the **concepts mapping,** whereas a **high decoupled OOP approach** which leverages composition paves the way of eradicating complexity in software engineering.

## Formalism Through the Ages (Alloy)

> As a language for exploring designs, however, code is imperfect. It’s verbose and often indirect, and it does not allow *partial* descriptions in which some details are left to be resolved later. And testing, as a way to analyze designs, leaves much to be desired. It’s notoriously incomplete and burdensome, since you need to write test cases explicitly. And it’s very difficult to use code to articulate design without getting mired in low-level details (such as the choice of data representations). (source: [https://cacm.acm.org/research/alloy/](https://cacm.acm.org/research/alloy/))

In the ‘70 and ‘80 several formal languages were developed by researchers in a quest for *correctness*, defined as the ability of a program to follow its specifications. **Some were “model-based”, such as Z, VDM and B, where behaviour was a set of actions over a set of states (of sets and relations). Others were “algebraic”, such as OBJ and Larch where the behaviour was described using Observers (of the hidden state) and Mutators (of the hidden states).

But once researchers started writing formal specifications, they discovered that they weren’t so consistent and/or clear, after all: the very act of putting down specifications was an act of designing per se.

Alloy was created taking all this into consideration, and was born explicitly for design explorations.

Alloy uses the for-all and exists-some quantifiers of first-order logic with the operators of set theory and relational calculus.

With it, we can use *e.dept. manager* to get the manager of *e*‘s department (or all the managers of the departments in which e is employed). We can also navigate backward, and this is because every value is a relation.

Alloy uses a s*mall scope analysis approach.* Given that even a first-order logic (without relational operators) is not decidable, we must except some trade-off:

- we can give up usefulness of language but making it decidable
- we could forgo the automation, but then what’s the point in all this?
- we could shrink scope, and that’s the approach Alloy is following. Neither *abstraction* nor *simulation*, however, but small tests.

  > The rationale for this is the *small scope hypothesis*, which asserts that most bugs can be demonstrated with small counterexamples. If you test for all small counterexamples, you are likely to find any bug. Many Alloy case studies have confirmed the hypothesis.”
  >

  Alloy does not perform explicit searches because even with small scales the number of possibilities is astronomical. It treats this as a

  > “*satisfiability problem* whose variables are not relations but simple bits. By flipping bits individually, a satisfiability (SAT) solver can usually find a solution (if there is one) or show that none exists by examining only a tiny portion of the space.
  > Alloy’s analysis tool is essentially a compiler to SAT, which allows it to exploit the latest advances in SAT solvers.
  >

  > Growing a model in a declarative language like Alloy is very different from growing a program in a conventional programming language. A program starts with no behaviours at all, and as you add code, new behaviours become possible. With Alloy, it’s the opposite. The empty model, since it lacks any constraints, allows every possible behaviour; as you add constraints, behaviours are eliminated.
  >

  By running simulations in an incremental, agile way, you might face contradictions and faults that you can remove by narrowing down what the model can do.

  Source: [https://cacm.acm.org/research/alloy/](https://cacm.acm.org/research/alloy/)

## Concepts

A concept is what the user needs to understand to use the software effectively.

A concept is a solution to a design problem. Not a vague problem, but a well-defined, small problem that keeps occurring in many contexts.

In short, concepts are **self-contained unit of functionality**:

- Abstract
- Generic or polymorphic
- Favour reuse
- Independent
- They can work together (composed) for a larger goal

 **Concepts embody experience.**

> Concepts don’t make all design problems go away, of course. They do, however, help you *localize* challenges by recognising them as specific to a particular concept. A concept becomes a container not only for the behaviours that it embodies but also for the accumulated knowledge about its design, the issues that have arisen in practice as it has been deployed, and the various ways in which designers have dealt with them.

**We should use concepts to shape the way designers think.**

Good design makes decisions seems *inevitable* because only one make sense, or because the common rules will lead the choice to the most acceptable one.  And also avoids reinventing concepts for which there is already a solution not only because it is a waste of resource, but because it could  confuse users since they are already used to a solution.

For example,  what’s a cloud backup? A continuous backup of files in my local hard drive on my cloud (user’s perspective) or snapshots taken every given time (implementation’s point of view)?

### **Concepts as vectors of differentiation**

To succeed, often an app or software delivers a brand-new concept (or a new way of understanding it):

- Photoshop with its *layers* and *masks concepts* that for the first time allowed non-destructive editing
- Apple with their *trash* concept that allowed tolerance for errors, and thus allowed undeleting
- The spreadsheet and its *formula* concept, that allowed flexibility in any kind of calculation
- Calendly and its concept of *event type* that allowed the do-it-yourself of appointment taking
- The World Wide Web and its *URL* concept, that allowed easier accessibility of resources

The difference between apps that offer similar functionalities can be highlighted by the concept they are built upon.

Text messages and email clients are both used as a mean of communication, but the former is built around the concept of conversation, and the latter on concepts like mailbox and folders that elicit different types of communication styles.

Concepts also describes whole families of apps: *text editors* like emacs, vi, and so on converge around the line and the character, while word processors use the paragraph as their main concept.

### **Concepts define business**

By defining the concepts and the way they could interact, we could envision a roadmap of product releases, from an MVP to a full-fledged product, considering the cost-benefit ratio.

Each concept outlines a different purpose, and can be researched and developed by different teams that can work in parallel. Only when it’s time for composition, the incompatibilities can be reconciled.

By shaping concepts in a certain way, companies can expose (or hide) their business model to users (think about the pain of booking a flight!: legroom, seat types, and so on: the way those details are hidden from the users is a precise business decision to make the market trickier).

### **Concepts expose complexity**

Think about the browser and the concept of *certificates*. How many *normal* users are aware of their importance? Could a better concept at the base of the authentication have led to a safer internet environment?

If we focus on those troubling parts we might expose the “real meat”, forgetting about the details, and this is important both for teaching/documenting and for focusing on refactoring to build better apps/software.

### **Concepts ensure safety and security**

We knew of fatal accidents due to a misinterpretation of unit of measure in medical treatment. There was a misconception of the fact that unit of measure are depends on culture and context, for a starter.

Similarly, “real” security cannot be enforced as a patch to an already established workflow.

Security concepts and their vulnerabilities should be first citizens at conceptual level.

### Expressing concepts

What is the appropriate language to talk about concepts, and how can we express them?

Let’s examine the Mac trash concept.

```ebnf
**concept** trash [item]
**purpose**
	to allow undoing of deletions 
**state**
	accessible: set item
	trashed: set item
**actions**
	delete (x: item)
		when x in accessible but not trashed
		move x from accessible to trashed
	restore (x: item)
		when x in trashed
		move x from trashed to accessible
	empty()
		when some item in trashed
		remove every item from trashed
**operational principle**
	after delete(x), can restore(x) and the x is accessible
	after delete(x), can empty() and then x not in accessible or trashed
```

The **name** of the concept is followed by a list of types that can be “specialized” when the concept is instantiated (an item can be trashed).

The **purpose** outlines the main goal of the concept and sometimes can be subtle. For instance, the Mac trash icon was the first to allow the undoing of deleting (there were also plenty of ways to delete files). So that was the real killer feature and the one outlined here in the example above.

The **state** answers the question: what changes will be applied to what types? In other words: what should be remembered by the concept during execution?

It’s possible to design a concept where we reach a state in which no action is allowed. This is called *deadlock*, which is not desirable because it’s a state we cannot escape.

**Actions** show the behaviour of the concepts, and are instantaneous —**they take no time.** They can have preconditions and set states. They are deterministic. It’s the state of the preconditions that determines what actions are available at any given time. The actions can be seen as state machines. “Mathematically, the meaning of an action is a *relation”.*

The **operational principle** show how the purpose is fulfilled by the actions, by outlining some archetypal scenarios. It doesn’t add anything that can be inferred from other sections, but it helps understand the how and the why. It can be thought of a theorem about the behaviour of the concept.

#### Key questions to ask

Here’s a list of questions to ask ourselves while devising concepts, in no particular order:

- What are the key concepts?
- What the most valuable?
- The most troubled?
- Are there shared concepts?
- Have concepts changed with time?
- What are their purposes?
- Are we missing some?
- What about the competitors’ concepts?
- How are composed?
- How’s the synchronisation?
- And concept redundancy and /or  overload?
- Are concepts effectively mapped to the user interface?
- Is the documentation organised around concepts?
- What set of concepts form an MVP?
- What problems this concept solve?
- Can we avoid reinventing the wheel by using already developed libraries, or just adapting one of those?
- Can a concept map to a module so that they can  be loosely coupled?

### Concept purposes

> “It’s not enough to know why you’re designing a product. You need to have a why for each element of your design, a purpose for every concept”.

Purposes and goals are different. A goal is a thing a user wants to obtain with the help of a concept; a purpose is the motivation because the designer chose to include that particular concept in the software.

Purposes should be:

- cogent
- must express a need for the user. “Save a favourite page” (no!) “Make easy to retrieve pages for later use” (yes!).
- specific
- evaluable
- It should be clear whose purpose we are describing.

If a concept lacks purpose, it’s because there wasn’t a real user need behind: it was built in that way only because it was easier.

> “Concepts, unlike internal mechanism, are always user-facing, and must have purposes that make sense not only to the programmer but also to the user”.

If a concept’s purpose is misunderstood, it will likely be misused.

Given that concepts are not formalisable, testing is essential. Moreover, while a full list of requirements is untenable, a list of requirements to avoid—misfits — is feasible.

> **Concepts without purposes** are rare, but can arise from exposing to the user mechanisms that should have been hidden.

> **Purposes without concepts** may indicate constraints that originate outside the designer’s domain, or sometimes just egregious omissions.

#### Concept overloading

A concept with more than a purpose is **overloaded.** It can be caused by:

- False convergence: a concept designed to cover two functions wrongly thought to be aspects of the same concept. This can be avoided by better analysis / design.
- Denied purposes, despite users’ requests. The remediation here is simply to listen to the users!
- Emergent purposes: those that are born from old concepts, often by the users themselves: the hardest to avoid, the best approach is to always stay alert and acknowledge when they occur, to address them fast and hopefully well.
- Piggybacking:happens when a concept is used to accommodate a new purpose (by design, not by the users). This is avoided by recognising that concepts reuse typically leads to later costs that cannot be forecast.

For instance, the Facebook like is overloaded: can signal reaction, curate your feed, target your advs.

## Concept composition

Concepts are independent, but we can take some and *compose* into an application, by synchronising their actions.

This will generate some dependencies, that however do not belong to the concepts per se, but are a feature of the composition process, the context.

Composing concepts do not change the behaviour or the concepts they comprise (**concept integrity)**.

We distinguish three types of composition:

The **free composition** is when concepts are merged in a single product, but operate independently and the only constraints are those impose by the concepts themselves (you can’t eat a meal that hasn’t been prepared, for instance).

The **collaborative composition** links concepts to achieve functionality not provided by any of the composing parts. For instance, a composition of *contact* and *phone call*, that allow the composition to be treated as a sequence of stages.

The **synergistic compositions** occur when the overall value of the composed parts bring more value than the sum of the singles parts. For instance, the trash is a mix of the *folder* concept and *list of items* concept.  Most synergies, however, will have some costs: the trash folder is a “strange” folder because it has the *empty* button…

When we tightly synchronise concepts, we trade flexibility for automation:

> Synchronising too much takes control away from the user, preventing some scenarios that would have been allowed in a free composition. Synchronising too little, conversely, burdens the user with work that might have been automated.

### Concept dependence

> Composition can introduce an asymmetry in the way a concept augment the functionality of another.

In a to-do app, we can compose the task concept with the label concept. But nobody would start thinking about a to-do app with a label concept to which attach a task.

Concepts are always independent, but considering the product as a whole they can assume a configuration in which some depends on others.

Sometimes, a concept can be justified by several other concepts. It’s important to separate the primary dependency (e.g. a *user* concept and Q&A) from the secondary dependencies (e.g. the *upvote* because we could also use the authentication to prevent double voting). Secondary dependencies could be omitted or developed in phases.

> Dependencies tells us how to avoid introducing a concept before it can be motivated.

To explore ways in which an app might be simplified, evaluate the consistent subsets and estimate how much value each one brings. Perhaps there is a subset that brings most of the value for only a small part of the cost.

## Concept mapping (from concepts to UX)

Interface design has for long being the realm of HCI experts, bridging the physical and linguistic levels with that of widgets. Bringing *concepts* to the table, we can consider buttons as a way to activate the actions subsumed by concepts and the visualisations a way to communicate the current state of the concepts.

So a concept mapping is a translation table from a concept to its material form.

It is at this level that naughty things can happen: by hiding or making very hard-to-access information, you can nudge your audience.

## Objects (from concepts to OOP)

💡 Objects (or items) receives the actions and the change of states.

</aside>

### Objects roles

Classifying objects by roles can be useful because rise questions about its property, uniqueness, management… it raises awareness. Objects can then be viewed:

- as an **asset**: it thus has inherent value, that might be different between users and also for the same user at different times and for different purposes
- as a **name**, to locate or identify other objects. I.e. a serial number names a camera, and email address names an email account. It points to only a resource, but its interpretation of what resource depends on the context.
- as a **value**. They assume meaning only in relationship with others objects. I.e. the number 80.

### Objects and mutability

> “Since concepts communicate only by synchronisation of actions, objects that are passed as arguments of actions are required to be immutable. If they were not, an action in one concept might mutate an object shared by another, leading to a hidden communication.”

For the reservation concept, for instance, the user might think we have a mutable reservation object.

Instead, we have a reservation relation, which is a tuple of states in the reservation concept. The change can then be seen as a transition from an immutable relation X to an immutable relation X’ by exercising an action.

### Interpreted/uninterpreted objects

If we need to pass a date, we should agree on the format, and this agreement is an interpretation.

If we need to cancel John’s booking, we only have to pass John’s name, without further knowledge (uninterpreted).

In his 5-pages-long note 44, Jackson gives us a formal explanation of this concept in terms of ***permutation invariance:***

> “To check whether a type is interpreted, one need only look at the operations performed on its objects in the state updates of the actions: if they include only the “logical” operations of sets and relations and equality comparisons, the type is uninterpreted”.



## Conclusions

In conclusion, Daniel Jackson’s _The Essence of Software_ constitutes the missing link between the qualitative study of human behaviour and the rigorous demands of software engineering.

By providing a formal language that pushes us to be more precise, we can concentrate on the conceptual level, thereby eradicating design flaws at the source rather than merely mitigating them in the implementation.

I would recommend this book to anyone curious enough of software-related topics because the methodology exposed in the book*, which benefits from every kind of expertise, establishes concept thinking as a fundamental, cross-disciplinary craft.*
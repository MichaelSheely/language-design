_Fill in each this file with your responses, placing each response after its corresponding question._

---

**Question**

Pick three quotes from the readings about language design. Good candidates are:

   + Something you agreed with / resonates with your own experience
   + Something you disagree with
   + Something that is interesting, a new idea or perspective you'd like to remember
   + Something you didn't understand

For each quote, describe what it was about the quote that led you pick it.

**Response**
+ "The problem is that programming languages are created either by committee or by extreme technical wizards with magical math powers. The broad computer science academic community has not paid a tremendous amount of attention to programming language usability." (Pavlus, 2012)
  + I absolutely agree with this statement made by Andreas Stefik, that is quoted in Pavlus' article. Since the first day I have started learning to program, I have felt like most of the programming languages are not user-friendly, or just targeted to be understood by only "technical wizards with magical math powers".
  +  I certainly had this feeling when learning Haskell. It seemed as though everything about the language was created with a paradigm of category theory which must be understood (or worse, used in ignorance) to understand how to print (since I/O must occur through a Monad).  This is even more true when considering the Haskellian typeclasses, generics, and the type system. A solid understanding of functors, monoids, monads, and applicatives is expected by the designers. While Haskell is an extreme example, many programming languages expect substantial mathematical reasoning or domain knowledge.
+ "A major reason to eradicate these false stereotypes is that they perpetuate biases against women. Evidence shows that a hostile culture contributes to the 'leaky pipeline', the phenomenon of women leaving tech despite having the interest, skills, and education" (Yang and Rabkin, 2015).
  + It is absolutely true that there are far fewer women than men in the tech industry, despite the increasing numbers of women earning technical degrees. I feel that this statement would have benefited from an elaboration on the evidence indicating that the primary reason for women leave the industry is the gendered perception of programming language hierarchy, as opposed to a more general form of sexism or preconceptions. It is imperative to understand exactly how the gendered perceptions negatively impacting women are formed and perpetuated in order to bring the tech industry closer to an equal opportunity workplace for both men and women.
+ "The development environment suffers from literally decades of accretion of stupid hacks from a community containing, to a first-order approximation, zero software engineers." (Smith, 2016)
  + This quotation from the additional reading on the R programming language is included because it was very reminiscent of a discussion with Professor Ben, in which we were discussing the separation of domain knowledge and programming language design / software engineering experience.
  + This highlights the importance of the work we did at the Hive in learning how to interview domain experts. Since these are the individuals with the fluency in the domain, it is essential that software developers creating tools for them are able to empathize with their needs so that the language also has fluency. The other direction is also important (the lack of which inspired this quote about R). When domain specialists are alone in developing a language, the lack of designers and software engineers may lead to unintuitive solutions or software which is difficult to extend.

---

**Question**

How would you know a well-designed language? What are the symptoms? How would you know a poorly designed language? What are the symptoms?

**Response**
A well-designed language should have a syntax that is intuitive enough that users can write programs accurately as well as a predictable grammar; Pavlus in his article remarks that Quorum, an evidence-based programming language, lets users write programs more accurately than in Perl. One thing to keep in mind is that a language that is intuitive to someone might not be to another. For example, AppleScript is supposedly intuitive to read, but certainly not more intuitive to write in for people who have been programming in C++ or Python. So it is more intuitive to write for people with less experience in traditional programming.

A well-designed language should also have flexibility, the ability to grow. Steele states in his paper that [he] need[s] to design a language that can grow. [He] need[s] to plan ways in which it might grow - but [he] need[s], too, to leave some choices so that other persons can make those choices at a later time." (Steele, 1998).

In addition, a well-designed language should fail early. This applies when designing a good API as well; According to Bloch, "the sooner you report a bug, the less damage it will do. Compile-time is best" (Bloch, 2006).

Furthermore, a well-designed language should be easy to maintain. This is feasible only if there's a good documentation for the language. 

---

**Question**

How do the themes of _Growing a Language_ relate to the "sound lab" we did this week?

**Response**

Perhaps the clearest theme from the _Growing a Language_ talk is that of building up from building blocks. The argument steers us to conclude that the optimal path to language design involves creating a small language with a plan for growth such that the language grows in expressiveness and complexity with its users.

This relates to my redesign of the "sound lab" in that I tried to break all of the functions into smaller building blocks. The most obvious example of this are the functions which perform an operation, but always coupled with a read or write to a file. I tried to make the new version extensible by providing a general "sound" class that held the frequencies as well as a data member for the speed to play the sound. Since this is a class, it should be straightforward for another programmer to create new methods or data members if they would like their sounds to contain additional abstractions. In this manner it seems I strove towards Steele's recommendation to make a language growable without even realizing it!

---
 
**Question**


In what way is an API a language? 

**Response**
APIs can be categorized as internal domain-specific languages, since they are written inside an existing host language.

Most of the APIs are designed with consistency and symmetry, just like any other programming languages since "every API is a little language, and people must learn to read and write it" (Bloch, 2006). This should help create a feeling of fluency that most languages possess. By having this characteristic of languages, APIs make it easy for users to detect patterns to write new code from a similar section.

Another characteristic of languages that APIs should share is the vocabulary of nouns and verbs, since an API will often allow for the creation, modification, query (or other verbs) of some data structures, just as the host language will define its own nouns and verbs for the computation it will perform at the programmer's request.

---

**Question**

What does the post on grayscale tell us about the process of API design?

**Response**

It certainly highlights the process of identifying tradeoffs when attempting to optimize for multiple design goals.  This is noticeable in the tension between familiarity/precision (using `RGB(x,x,x)` for a particular level of grey) and more specific but less precise name (`gray(x)` (does a higher value mean lighter or darker?)). 

The comments are also quite interesting, as we see that one individual suggests using the common `greyscale()` term to name the function. Although it is not inherently any clearer than `gray()`, people are used to seeing and using it. However, as we can see from a later commenter,the function `greyscale()` is already defined by [Filter Effects](https://drafts.fxtf.org/filters/#grayscaleEquivalent). This namespace conflict might suggest suboptimal design as well.

The post also shows the taking-feedbacks part of the API design process. The fact that users are voting on which name is easier to use is consistent with the statement "API design is not a solitary activity" (Bloch 2006), one of the suggestions Bloch made on how to design a good API.

---

**Question**

The Yang and Rabkin article talks mainly about general-purpose languages.
In what ways do the themes apply to the study and creation of DSLs?

**Response**

DSLs can learn many lessons from the design and use patterns of general purpose programming languages.  We can see the importance of libraries and the culture of users from these general purpose programming languages and based on the desired characteristics for the DSL.

If we would like our language to have support for many plugins and community support, it may be helpful to look to the general-purpose languages which have been successful at building a broad base of library support. 

---

**Question**

The Pavlus article mentions the researchers' comments that people preferred "natural-language replacements for some of the more abstruse syntax". In other words, people found it easier to work with code that looks more like a human language (e.g., English). Consider the following quote by William R. Cook, one of the creators of AppleScript:

> The experiment in designing a language that resembled natural languages (English and Japanese) was not successful. It was assumed that scripts should be presented in “natural language” so that average people could read and write them. ... In the end the syntactic variations and flexibility did more to confuse programmers than to help them out. It is not clear whether it is easier for novice users to work with a scripting language that resembles natural language, with all its special cases and idiosyncrasies. The main problem is that AppleScript only appears to be a natural language: in fact, it is an artificial language, like any other programming language. … even small changes to the script may introduce subtle syntactic errors that baffle users. It is easy to read AppleScript, but quite hard to write it.
[[Cook 2007, page 1-20]](https://dl.acm.org/citation.cfm?doid=1238844.1238845)

Are these two experiences of natural languages at odds with one another? Would you choose to include natural language in the design of a DSL? If so, how might you do so? If not, why not?

**Response**

There are two ways to look at this dichotomy between programming languages which have the feel of a "natural language" being both better and worse for new programmers.

We may note that there is a spectrum to how closely the language resembles natural language. On one end, we have the binary / hexidecimal codes in which computers store their instructions, and on the other side we have languages, like AppleScript, which *read* much like a natural language. One might note that both of these extremes are poor choices for programmers. The former, while entirely precise and unambiguous is not structured, nor is it easy to see patterns or errors.  The latter on the other hand depends on the natural languages, which are full of their own ambiguities and exceptional grammars. Thus, one might argue that the correct programming language is somewhere in between these two extrema, and the language tested in the Palvus article may have been at a good location along this spectrum, while a language like AppleScript was too close to the ambiguous, hard-to-tell-what's-a-keyword, syntax of natural languages.

On the other hand, we may note that rather than a simple one dimensional spectrum of "how close to natural language is this?", the usability of the language may actually depend on _how_ the natural language is employed. For example, in AppleScript, it seemed that the natural language took the form of actually creating sentences. There would be examples such as `tell application X to quit`, which includes the optional (but not _obviously_ optional) command: `to`. The natural language syntax in the Palvus article seemed to rather import words from natural language whose definition was already quite clear and allow their judicious use to make commands and control flow clearer to a new programmer -- compared to the curly brace and symbols structure which is more concise but described as obtuse by the Palvus article.

So it might be wise to include parts of natural languages that are concise, recognizable-as-clear-patterns and intuitive to read *and* write; To specify, an example of a natural-language word that is intuitive to write and read would be `end`, and that of a word that is intuitive to read but not to write would be `repeat`. 

---

**Question**

Briefly describe how you split up the work for this assignment.

**Response**
We both read the assigned readings, collaborated using the collaborative markdown editor, and continuously revised what we (and each other) had written.

---

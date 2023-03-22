# Project proposal

## The user and a language

_This section describes who the project would serve and why a language might be a
good way to meet their needs._

### What's the need?

`_What need is met by your idea? Who are you helping? What is that person's
experience like now? What would their experience be like if you could help
them?_`

The project would serve *me* specifically. Thats only partially a joke. Specifically, I want to serve TTRPG Creators. In TTRPG it is very common to use the randomness of dice to simulate chances of successs. Of course a key part of making these systems is making sure the statistics actually work towards the creators expectations. However, expectation and reality with Dice are almost never in tandem. (as a math major) I regularly see Tabletop games that have players roll 2d6, only to build their systems around the expectation tthat 2,3...12 all appear equally. (Which it very very much doesnt). This tool will help users avoid this problem. 

(PS: d(number) means a dice with that number of sides. So 2d6 is 2 traditional six sided dice)

So the goal is to create a simple DSL that can help TTRPG creators manage dice and statistics. There are two versions of this DSL. One is implemented as part of some kind of online battlemap service like Roll20 or FantasyGrounds, which allows user to create macros for dice rolls and their outputs. The other is standalone and allows creators to make a simlar dice rolling setup and then converts and generates graphs that shows output. I would love feedback on which of these two options I work on. In the Roll20 Case their will be some design mockups to show how this system work integrate with the current system. In the graphing case, I will try to do some work to make the system statndalone, and usable for the average non-cs person. 

### Why a language?

`_Why is a DSL appropriate for your user(s)? How does it address the need?_`

Firstly, I want to clarify this is not a list of commands to roll dice. The goal of the DSL is to create a tool for learning about a system of *dice*. TTRPG creators are always coming up with new ways to use Dice. The classic version (seen in dnd) requires rolling a Die and adding a static bonus amount to the roll and checking to see if its high enough. However, another common Dice succcess system is rolling a bunch of dice and counting the number of dice that roll even numbers which is the number of sucesses. The goal is to make sure they DSL can handle both of these case s and everything in between (and things I havent thought up).

I want to avoid handling these events single target. I want to make sure each system I added is flexible to the user. That is, I want to implement a filtering system rather then a specific command that keeps the highest X values (although most cases would be handled by the second option).  Some of these other systems I want it to handle include rerolling 1's, handeling critical successes and providing expected value. Each of which would be converted to wided more generic systems. 

### Why you?

`_What excites you about this idea? How did you come up with it?_`

I am making a tabletop roleplaying game right now... So you can see where the inspiration came from. I am learning alot in the process of making it, specifically on managing statistics and powerscaling. LOTS of spreadsheeting. My main goal is to make this be something *I* use when trying to figure out dice usage and expectations. 

### Domain

`_Describe the project's domain in five words._`

Tabletop RPG Dice Management and Systems 

### Interface (syntax)

`_How might the user interact with the language? What does programming look
like? Why is this the right way to interact with the problem domain?_`

I think this very dependant on the which version of the project I make. If I make an "addition" to another service using a DSL, then actually using it will just be using it through scala but there will be detailed documentation on how you would theoretically use it assuming it was added to the other service. (And of course *why* it should be added) In the standalone case, I think alot of the work will be expirimenting with possible usability implementations (such as python library or a standalone GUI, or command line interface ). 

I think this is the most open ended part of the project for me since the goal is to make something I use. The most likely result is just a README.md document with 1-2 steps to evaluate a file. I will work to make it as simple as possible to run since im lazy. If you have any recommendations I am all ears. 

### Operation (semantics)

`_What might happen when a program runs? How does a program interact with the
user? What kinds of errors might occur, and how might they be communicated to
the user?_`

Firstly, The program running should indicate any errors in construction. Then if it is errorless, the program should to the roll you outlined. Then it will either present a graph, or saves it to a predefined location. I think in all likelyhood any errors will be shown in a command line (or some sort of text area) if the implementation is wrong. 

As Ive mentioned this project is still a little split between two visions, but operation should be and will be *write the code* then *press a button* and nothing more then that. Maybe if there is a GUI you can click things to write quicker, but the goal is just simplicity and maybe natural language. 

### Expressiveness

`_What should be easy to do in this language? What should be possible, but
difficult? What should be impossible or very difficult?_`

I went into this in depth in some of the earlier examples (specificaly *Why a language*) but I can elaborate slightly. The most basic thing with always be "I roll 1d12) where the dice number and size can be adjusted. These kind of implementations will be simple. The goal is then that each program should not be more complex then describing how you rolled a die to friend. For example, "I rolled a 1d20 and added 10. I got a critical success so I do double damage" should evaluate to about 2 lines of code in the DSL <ideally>.
  
 Something impossible would include anything that includes *not* a dice. While I can obviously account for nontraditional dice (1d2, 1d13, 1d57) and also allow maybe defining dice sides. (so like maybe you could define a d6 to have 1, 1, 1, 5, 6 ,7 on each side without just doing if statements for each result). But anything that cannot be isomorphically matched to a dice will not be possible. (Consider systems like decks of card that theoretically could be matched to a d52, but realistically just wont be.) 

### Related work

`_Are there any other DSLs in this domain? If not, describe how you know there
aren't and conjecture why not. If so, describe them and provide links. How well
do they address the need? Are there any particularly admirable qualities of the
language? Are there parts of the language you think could be improved?_`

## The Project

_This section examines whether the idea makes for a good CS 111 project.
_
### Suitability

`_If someone were to work on this project, what percentage of their time would be
spent directly engaging in the **language** aspects of this project (e.g.,
making language design decisions), as opposed to "systems" aspects of the
project (e.g., implementing a complicated semantics that doesn't require a lot
of language design)?_`

### Scope

`_How big an idea is this? How ambitious is this project?_`

### Benefits and drawbacks

`_Why might this be a good idea for a project? Why might this not be a good idea
project?_`

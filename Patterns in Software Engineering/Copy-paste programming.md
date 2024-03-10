It is an [[Anti-pattern]].

The Cut-and-Paste antipattern refers to the practice of copying and pasting code, rather than reusing existing code or writing new code that can be reused. This leads to code duplication, which makes it more difficult to maintain and update the code, and increases the risk of introducing bugs and inconsistencies.

## Symptoms and consequences:
- Software defects are replicated through the system.
- The same software bug reoccurs despite many local fixes.
- Developers create multiple unique fixes for bugs with no method of resolving the variations into a standard fix.
- Lines of code increase without adding to overall productivity.
- Code reviews and inspections are needlessly extended.
- It becomes difficult to locate and fix all instances of a particular mistake.
- Code can be reused with a minimum of effort.
- Excessive software maintenance costs.

## Causes:
- Short term payoff more important than long term investment.
- No reward of reusable components: development speed overshadows all other evaluation factors (lines of code is the wrong metric!).
- Lack of abstraction among developers, often accompanied by a poor understanding of inheritance, composition, and other reuse possibilities.
- Reusable components, once created, are not sufficiently documented or made readily available to developers.
- “Not invented here” syndrome.
- Lack of forethought or forward thinking among the development teams.
- Inexperience with new technology or tools → use a working example and modify it, adapting it to specific needs.

## Refactored Solution:
- Common method refactoring.
-  **White box reuse (inheritance)** • A new subclass reuses the functionality of the superclass and may offer new functionality.
- **Black box reuse (delegation)** • A new class offers the aggregated functionality of the existing classes • Key benefits:
	- The implementation of an object can be made independent of the object's interface.
	- Take advantage of late binding by mapping an interface to a specific implementation at run time.
	- Objects can use an interface (e.g. List), yet benefit over time from more advanced implementations (e.g. ArrayList, LinkedList) that support the same interface.
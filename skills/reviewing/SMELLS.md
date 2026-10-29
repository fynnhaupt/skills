# Smells

A fixed baseline, the code smells from Fowler's _Refactoring_ (ch. 3) plus two test smells, applied even when the project documents nothing. Each is a judgement call: report it as "possible <smell>", never as a hard violation.

- **Mysterious Name**: a name that doesn't reveal what it does or holds. → Rename it; if no honest name comes, the design is murky.
- **Duplicated Code**: the same logic shape in more than one place in the change. → Extract the shared shape and call it from both.
- **Feature Envy**: a function that uses another object's data more than its own. → Move it onto the data it envies.
- **Data Clumps**: the same few fields or parameters keep travelling together. → Bundle them into one type.
- **Primitive Obsession**: a primitive or string standing in for a domain concept. → Give the concept its own small type.
- **Repeated Switches**: the same `switch` or `if` cascade on the same type in several places. → Replace it with polymorphism or one shared map.
- **Shotgun Surgery**: one logical change forces scattered edits across many files. → Gather what changes together into one module.
- **Divergent Change**: one module edited for several unrelated reasons. → Split it so each module changes for one reason.
- **Speculative Generality**: abstractions, parameters, or hooks for needs the spec doesn't have. → Delete them; inline until a real need shows.
- **Message Chains**: long `a.b().c().d()` navigation the caller shouldn't depend on. → Hide the walk behind one method on the first object.
- **Middle Man**: a function or class that mostly delegates onward. → Cut it and call the real target.
- **Refused Bequest**: a subclass that ignores or overrides most of what it inherits. → Drop the inheritance and use composition.
- **Implementation-coupled Test**: a test that mocks internal collaborators, tests private functions, or checks through a side channel such as the database. → Test the behaviour through the public interface.
- **Tautological Test**: a test whose expected value is computed the way the code computes it, so it passes by construction. → Use an independent value: a literal, a worked example, or the spec.

<img width="1200" height="630" alt="social-media-post-1200x630" src="https://github.com/user-attachments/assets/8f8fad27-fa69-48c8-8395-bab4681646fb" />

# TDD Test-Driven Development 

> [!NOTE]
> Write a test. Make it run. Make it right

## TDD Cycle

<img width="2460" height="2156" alt="image" src="https://github.com/user-attachments/assets/59acccf7-3e6f-4fa9-93a9-6abc34f0d4bc" />

1. Create your **list of test case scenarios**
    - Made a list of the tests we knew we needed to have working
    - Told a story with a snippet of code about how we wanted to view one operation
    - Convert side effects into a test case
2. Add a **little test**
    - Baby steps and gradually increment steps
    - Use obvious implementations
    - Incremental tests will make our tests more "speaking"
3. Run **all tests and fail**
4. Make a **little change**
    - Gradually generalized the working code, replacing constants with variables
    - Compile quickly using stubs
    - Fake it: return constant (temporary) and then replace.
5. Run the tests and **succeed**
6. Refactor to **remove duplication**
    - Equality is foundational in tests
    - Test equality to help you to remove constansts and duplication
    - Equality is a check in every test if you implement this in your tests
    - Encapsulation isn’t an upfront design decision — tests drive you to hide internals.
    - Reduce coupling in your tests
    - Don't forget remove duplication
    - Refactor will guide you to discover new tests to implement
    - Let tests expose the need for a common abstraction
    - Factory methods are about controlling object boundaries so your tests and clients don’t couple to constructors.

<img width="1200" height="630" alt="social-media-post-1200x630 (1)" src="https://github.com/user-attachments/assets/9232b572-093b-4d64-bd25-e7d91e7adf2d" />

## TDD Discipline

- Let the system telling you what you need to consider
- Write the tests you wish you had.
- Don’t abstract until duplication hurts.
- Don’t over-engineer based on assumptions about future needs.
- Trust the TDD cycle to force the right design at the right time.
- TDD is an iterative tool to discover how to well-describe problems.
- Explicitness over assumptions
- Principle of Triangulation: one test shows a solution works, two tests show it generalizes, but the third test forces a more abstract design.
- Treat even the “obvious” cases as design opportunities.
- Tests first reveal duplication, then push for abstraction.
- If you try to design the whole abstraction on day one, you’ll overthink and risk the wrong design.
- If you refactor relentlessly, good design will emerge.

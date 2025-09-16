<img width="1200" height="630" alt="social-media-post-1200x630" src="https://github.com/user-attachments/assets/8f8fad27-fa69-48c8-8395-bab4681646fb" />
# TDD Test-Driven Development 

> [!NOTE]
> Write a test. Make it run. Make it right

## TDD Cycle

0. Create your **list of test case scenarios**
    - Made a list of the tests we knew we needed to have working
    - Told a story with a snippet of code about how we wanted to view one operation
    - Convert side effects into a test case
1. Add a **little test**
    - Baby steps and gradually increment steps
    - Use obvious implementations
    - Incremental tests will make our tests more "speaking"
2. Run **all tests and fail**
3. Make a **little change**
    - Gradually generalized the working code, replacing constants with variables
    - Compile quickly using stubs
    - Fake it: return constant (temporary) and then replace.
4. Run the tests and **succeed**
5. Refactor to **remove duplication**
    - Equality is foundational in tests
    - Test equality to help you to remove constansts and duplication
    - Equality is a check in every test if you implement this in your tests
    - Encapsulation isn’t an upfront design decision — tests drive you to hide internals.
    - Reduce coupling in your tests
    - Don't forget remove duplication
    - Refactor will guide you to discover new tests to implement
    - Let tests expose the need for a common abstraction

TDD Discipline
- Let the system telling you what you need to consider
- Write the tests you wish you had.
- Don’t abstract until duplication hurts.
- Don’t over-engineer based on assumptions about future needs.
- Trust the TDD cycle to force the right design at the right time.
- TDD is an iterative tool to discover how to well-describe problems.

<img width="2460" height="2156" alt="image" src="https://github.com/user-attachments/assets/59acccf7-3e6f-4fa9-93a9-6abc34f0d4bc" />

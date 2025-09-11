## Test-Driven Development 

1. Made a list of the tests we knew we needed to have working
2. Told a story with a snippet of code about how we wanted to view one operation
3. Made the test compile with stubs
4. Made the test run by committing horrible sins
5. Gradually generalized the working code, replacing constants with variables

General Goal Flow
1. Write a test
2. Make it run
3. Make it right

TDD Cycle
1. Add a little test
2. Run all tests and fail
3. Make a little change
4. Run the tests and succeed
5. Refactor to **remove duplication**

Quick Notes:
1. Baby steps and gradually increment steps
2. Fake it: return constant and then replace
3. Use obvious implementations
4. Convert side effects into a test case
5. Compile quickly using stubs
6. Test equality
7. Create a list of test case scenarios to test one by one
8. Incremental tests will make our tests more "speaking
9. Equality is a check in every test if you implement this in your tests
10. Reduce coupling in your tests, that means remove constants and use the code itself `assertEquals(10, product);` to `assertEquals(new Dollar(10), product);`

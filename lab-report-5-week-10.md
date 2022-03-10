How you found the tests with different results (Did you use diff on the results of running a bash for loop? Did you search through manually? Did you use some other programmatic idea?)
* I looked through some of the 652 test manually and picked out the ones that I thought would be interesting or would produce interesting results. I didn't work on my own implementation of markdownparse very much after the first couple of weeks so I thought most of the tests I ran on my implementation ought to be different from the given implementation.

First test (test 20):
* My output: 
* ![mylabtest1](https://user-images.githubusercontent.com/94575562/157593971-d616c246-ddef-457f-8b4e-43dbfc6f5a07.png)

 
*   Given implementation output:
* ![theirlabtest1](https://user-images.githubusercontent.com/94575562/157594179-e5f34bdd-3c84-43aa-946f-e35b21d00ce8.png)

* Expected output:
* [http://example.com?find=\*]

* Fix: 
* ![image](https://user-images.githubusercontent.com/94575562/157594720-b2e24162-7e8d-442b-b767-fd910919cde6.png)
* I think both implementations were different from the expected output, this is likely because the code only looks for parenthesis when apparently <> these carrots work too (are they called carrots?). This means markdownparse should treat carrots or whatever these <> are like parenthesis.

Second test (633):
* My output:
* ![image](https://user-images.githubusercontent.com/94575562/157595534-251e1236-bd01-433c-be8f-1bc099f149a2.png)

* Given implementation output:
* ![image](https://user-images.githubusercontent.com/94575562/157595651-a495719d-8f9d-444e-95ac-394f3ba428a8.png)

* In this test, I believe the given implementation output is correct because there are no links in the test file so the output should be []. For the implementation that is incorrect (my implementation) my getLinks method does not consider the case that there would be no parenthesis found in the entire file which results in the index out of bounds exception. If no parenthesis are found, my code should just return an empty ArrayList like the givenn implementation
* My code that should be fixed:
* ![image](https://user-images.githubusercontent.com/94575562/157596311-5e4b9585-e8b0-40f4-bece-47fce0ff1f13.png)




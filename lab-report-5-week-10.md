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


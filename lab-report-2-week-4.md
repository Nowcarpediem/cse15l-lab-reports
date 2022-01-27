Code Change 1:
---
* Screenshot of code change:

![code_change_1](https://user-images.githubusercontent.com/94575562/151451509-a18af9aa-2c6e-471d-b02a-8287c8313142.PNG)

* [Link](https://github.com/Nowcarpediem/markdown-parse/blob/main/test-file2.md) to failure inducing input
* Symptom of failure inducing input: 

![failure_input_1](https://user-images.githubusercontent.com/94575562/151433416-81664eab-2973-4009-af0c-0fc54fd198e2.PNG)

* The code didn't know what to do with input that did not begin with an open bracket, basically anything that isn't a link in the .md file. There was no code for the case that the .md file being read would contain text that did not start with an open bracket. This resulted in an infinite loop and eventually an out of memory exception. Because there was text at the end of the .md file, currenyIndex never got incremented to markdown.length(), which caused an infinite loop.

Code Change 2:
---
* Screenshot of code change:

![code_change_2](https://user-images.githubusercontent.com/94575562/151453156-1958c6bb-c896-4673-b9d3-55cad1f2853e.PNG)

* [Link](https://github.com/Nowcarpediem/markdown-parse/blob/main/test-file3.md) to failure inducing input
* Sympton of failure inducing input:

![failure_input_2](https://user-images.githubusercontent.com/94575562/151453517-0fbd81b8-84aa-4ac8-aa29-705439531aa6.PNG)

* The code threw an IndexOutOfBounds exception because it could not find any open or close parenthesis in the .md file. There was no code for the case that the .md file being read would not have parenthesis. Without the indexes of the open and close parenthesis, the code did not know what to return into the ArrayList. Or rather it was trying to put strings that didn't exist into the ArrayList, thus the error.

Code Change 3:
---
* Screenshot of code change:

![code_change_3](https://user-images.githubusercontent.com/94575562/151455441-d3b9012d-6627-45bb-8fff-b75c7d8223bf.PNG)

* [Link](https://github.com/Nowcarpediem/markdown-parse/blob/main/test-file4.md) to failure inducing input
* Symptom of failure inducing input: 

![failure_input_3](https://user-images.githubusercontent.com/94575562/151455858-358ebf34-707a-4039-8908-9cbe3a30753d.PNG)

* The code didn't seem too worried about having a closed parenthesis before an open bracket but it did get mad that there was no close bracket. It threw an IndexOutOfBounds exception on line 19 because the code called on the index of the most recent closed bracket which in this test did not exist. There was no code to handle the potential case that the .md file being read would have an open bracket without a closed bracket.

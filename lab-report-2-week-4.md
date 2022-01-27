Code Change 1:
---
* Screenshot of code change:

![code_change_1](https://user-images.githubusercontent.com/94575562/151451509-a18af9aa-2c6e-471d-b02a-8287c8313142.PNG)

* [Link](https://github.com/Nowcarpediem/markdown-parse/blob/main/test-file2.md) to failure inducing input
* Symptom of failure inducing input: 

![failure_input_1](https://user-images.githubusercontent.com/94575562/151433416-81664eab-2973-4009-af0c-0fc54fd198e2.PNG)

* The code didn't know what to do with input that did not begin with an open bracket, basically anything that isn't a link in the .md file. This resulted in an infinite loop and eventually an out of memory exception. Because there was text at the end of the .md file, currenyIndex never got incremented to markdown.length(), which caused an infinite loop.

Code Change 2:
---
* Screenshot of code change:

![code_change_2](https://user-images.githubusercontent.com/94575562/151453156-1958c6bb-c896-4673-b9d3-55cad1f2853e.PNG)

* [My repo](https://github.com/Nowcarpediem/markdown-parse)
* [Other repo](https://github.com/bimai25/markdown-parse)
* Code for tests: 

![test](https://user-images.githubusercontent.com/94575562/155757206-98ac1dff-6108-43a3-b6db-505d5d2a5895.png)


*  My implementation snippet 1:

![snip1](https://user-images.githubusercontent.com/94575562/155755678-859299b3-3a75-492f-b8b4-1c7e68b481ad.png)

* My implementation snippet 2:

![snip2](https://user-images.githubusercontent.com/94575562/155756427-b8e76322-8ede-4595-b406-5810173bc565.png)

* My implementation snippet 3:

![snip3](https://user-images.githubusercontent.com/94575562/155756988-df7475da-8621-4db6-a8fb-437624f0af91.png)

* Other implementation snippet 1, 2, and 3:


![brandon_snip](https://user-images.githubusercontent.com/94575562/155760979-4cf2ac38-d05e-401e-8c48-2baa980cb63a.png)


Do you think there is a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks? If yes, describe the code change. If not, describe why it would be a more involved change.
---
* No, for snippet 1, I do no consider the case that the opening brackets would be within a code block. In order to consider cases with backticks, I believe that it would take more than 10 lines of code.

Do you think there is a small (<10 lines) code change that will make your program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets? If yes, describe the code change. If not, describe why it would be a more involved change.
---
* I think this would also take more than 10 lines to fix because I also did not consider any cases where there would be parenthesis or brackets inside the initial brackets and parenthesis. I would need to rearrange my code to look for matching pairs of brackets and parenthesis.

Do you think there is a small (<10 lines) code change that will make your program work for snippet 3 and all related cases that have newlines in brackets and parentheses? If yes, describe the code change. If not, describe why it would be a more involved change.
---
* I also think this would take more than 10 lines to fix especially since in my code I don't consider the case that the link may take more than one line in the sense that the brackets might be on seperate lines as the parenthesis and the link. I also don't consider the case that a dummy link may not have closing parenthesis. Again I would need to look for matching pairs of parenthesis and brackets rather than the nearest closing bracket or parenthesis.

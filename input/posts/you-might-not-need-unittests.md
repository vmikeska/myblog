This article doesn't explaint what unit test actually is, but rather explains it's place and gives you some hints whether you should really use it or no.

The unit test were invented already a bit earlier, but became really popular in the late ’90s and early 2000s.
Ehm, popular ? More than that actually... at around year 2010, it became real obsession and managers and some of the developers terribly overkilled the entire thing.

Suddenly there were no application able to perform without UT and it even begin to affect the architecture of the applications itself. 100% coverage buzzword were spreading across the industry. People began to cover not only interfaces, but for example each method separately. And this all, as we already know at this era, is wrong.

TDD, the test driven development became most buzzwordy of all of this and all the interviews usually turned to this topic at early beginnings.

So this was enough of the history, let's begin with the scenarios where you might not need unit tests for.
To have unit tests in your project, it's alwasy a big dependency and overhead. Yes, if it is a professional project,  when written well, later in your project you will benefit from this dependency. You just have to find a right moment to start. 

The right moment is definitelly not right at the beginning of the application, when architecture is shaping. You will we modifying your interfaces a lot, every day, maybe every hour. This is really not a good time for unit tests, every time you make a change to your code/interface, there is usually a need to change the unit tests as well. Sometimes they are needed, but definitely do just hi level interfaces coverage, like Web API method or a root metods you are calling there. 
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjQxMDAyNjExLC0xMjA0NTIyOTYwLDk3MD
gxODQ2OCwyMDQ4MjQ5NDAwLDE2OTc4MDEyMDcsLTExOTE2NTI1
NDQsNzU5NjI2ODI0LC0xMzU1ODYyNDkxLC0xODU4MjY4OTg2LC
0yMzQ1NTUyMDYsLTcyNTEyMTA1LDQ5NzgxODgxMCwtMjA4ODc0
NjYxMl19
-->
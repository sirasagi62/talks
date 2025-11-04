## 0 Cover
So, Now I will start my lightning talk, 

From fuzzy to fluent: sementic code search in Vim and Neovim.


## 1 自己紹介
I'm Sirasagi62. I'm an undergraduate livin’in Sendai, who have been using Vim and Neovim for about 10 years.

## 2 Hooks
Today I'd like to talk about "Finder".
As you know, Neovim and Vim already have a lot of fuzzy finders such as telescope, fern, fzf.vim and so on.
You're probably thinking something like this:

## 3 Hooks2
“Are you talking about Yet Another Fuzzy Finder AGAIN!?“
But this time it's different, because


## 4 Hook3
Today, I'd like to introduce a new type of finder, the "Fluent" Finder.


## 5 Motivation
Finding code in programming is incredibly difficult, isn’t it? You've probably experienced something like this when trying to search using keywords and grep:

"I kept searching using a different verb with the same meaning and couldn't find the function."

"I couldn't even think of what words to use to search in the first place.”

Fuzzy Finders search text based on fuzzy matching of words, so they cannot perform searches using synonym or sentences.

Unfortunately, even in this age where artificial intelligence can ”write” code, the task of “reading“ code will not disappear. Therefore, we need to address this problem both now and in the near future.


## 6 What is Fluent Finder
Solving this problem is flf-vim, the world's first Fluent Finder. 

Fluent Finder searches for text using vector search based on a language model, not simple string matching.

In other words, This means that the AI understands the meaning of the code and searches for it without being limited by the surface text.

It uses Tree-sitter for splitting code into chunks, allowing flf to work with various languages.


## 7 Example
Let's look at an example. The `FlfDir` command recursively analyzes the code in a directory. When you enter "close the database" in Japanese, you can see that it actually displays the `deInit` function. It understands the words "database" and "close" and is able to select the appropriate function.

## 8 Problem
However, "FlfDir" has a big problem. 

When the amount of code becomes large, 

indexing takes a very looooong time. 

For example, when trying to analyze the Vim source code, indexing alone takes

over one hour. 

That is not "fluent," is it?

## 9 Example2

Therefore, I developed another command, "FlfBuf". This command searches only the currently open buffers instead of searching the entire project directory.
In this GIF, it's indexing and searching buffers containing Vim's source code. It successfully finds the `strsize` function from the Japanese phrase "string size".
By limiting the search scope, indexing can now be done in a realistic amount of time.


## 10 Embedding Model
Flf uses a local SLM, which stands for Small Language Model. Because it doesn't call an API, it's secure and cost-effective. Of course, it also runs quite fast, at least on my MacBook, due to the very small number of parameters.

The model used this time is `ruri-v3-70m-code-v-0.1`, which is a fine-tuned version of the `ruri` model developed at Nagoya University.

By the way, the person who fine-tuned this model... 

isn't it possibly someone you've seen before?.

## 11 Conclusion
So, I introduced flf-vim, a finder plugin that allows searching with natural language.

## 11 More things…
There's still so much more I want to talk about: 

"An enigmatic behavior in Vim's buffer commands," 

"A bug I found during development that crashes Bun.js in just 4 lines,”

 "Hacks to support both Vim and Neovim“ ...

But unfortunately, 5 minutes is far too short to talk about all of these!

So, that's all for my presentation!

Thank you!

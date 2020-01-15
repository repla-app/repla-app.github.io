---
layout: post
title: "What is Repla?"
categories: Essay
---

Repla is now launched. So far we've release **Repla Server**, the first official Repla plugin. If you've ever read about product development, the question is always "what problem does it solve?". The problem that the Repla Server plugin solves is running a local web development server that always refreshes. And, since it's the only plugin that's been released so far, that's all the [Repla website](https://repla.app/) talks about, because that's the benefit you can get by downloading and using Repla today. But Repla itself wasn't designed to solve any one problem. This blog post is about how it was designed, so it's about exploring the benefits you'll be able to get by using it tomorrow.

If Repla wasn't designed to solve a specific problem, then how was it designed? When web developers describe the tools they use, the common answer is a terminal, a text editor, and web browser. None of those tools are designed to solve a specific problem either, instead they're adaptable. They shape themselves to the problem at hand. But one of those tools is not like the others. While terminals and text editors are specialized tools optimized for developers, developers are stuck using the same web browsers that everyone else are using. Repla is designed to replace the web browser, or, more accurately, sit alongside it.

Developers are really using the web browser for two separate tasks, the first is researching the problem that they're working on, Repla doesn't try to replace this because this is what web browsers are already good at. The second task developers are using their web browser for is running their current project. This is where Repla comes in, while browsers do have some built-in tools for developers, they're not developer tools themselves. So this is how Repla is designed, to bring the same flexibility and adaptability for web developers that text editors and terminals have to the browser.

![Trifecta](/assets/2020-01-13-trifecta.png)

So how do you design a development web browser that has the same flexibility as text editors and terminals? It turns out that text editors and terminals achieve their flexibility in very similar ways. They both use package managers to manage extensions, and those extensions often involve launching processes. Whether it's [downloading media](https://github.com/ytdl-org/youtube-dl/), [checking the correctness of code](https://atom.io/packages/linter), [perform compilation](https://lldb.llvm.org/), or [adding support for programming languages](https://marketplace.visualstudio.com/items?itemName=kiadstudios.vscode-swift), terminals and text editors flexibility comes from packages that can run processes.

So what is Repla? Repla is web browser that achieves flexibility by being able to install packages and run processes, just like text editors and terminals do. And just like those apps, Repla can shape itself to the problem at hand. These capabilities happen to make a nice way to run a local web server, and have it automatically refresh after each change. So that's what the first plugin, Repla Server, does. But that's far from the only use case for this combination, our next post [Repla Use Cases]() explores some of the others.

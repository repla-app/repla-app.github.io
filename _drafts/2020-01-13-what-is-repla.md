---
layout: post
title: "What is Repla?"
categories: Essay
---

Repla is now launched. So far we've release **Repla Server**, the first Repla plugin. If you know something about product development, you know the question is always "what problem does this solve?". The problem that the Repla Server plugin solves is running a local web development server that always refreshes. And, since that's the only plugin that's currently available, that's all [the Repla website](https://repla.app/) talks about, because that's the benefit you can get by downloading and using Repla today. But Repla itself wasn't designed to solve any one problem, this blog post is about how it was designed, so it's about exploring the benefits you'll be able to get from Repla tomorrow.

If Repla wasn't designed to solve a specific problem, then how was it designed? When web developers talk about which tools they use, it's common for them to say "a terminal, a text editor, and a web browser". None of those tools are designed to solve a specific problem either, instead they're adaptable, they shape themselves to the problem at hand. But one of those tools is not like the others. While terminals and text editors are specialized tools optimized for developers, developers are stuck using the same web browsers that everyone else are using. So Repla is designed to replace the web browser, or, more accurately, sit alongside it.

![Trifecta](/assets/2020-01-13-trifecta.png)

Developers really use the web browser for two separate tasks. The first is researching the problem they're working on. This is what most people, who of course aren't developers, also use web browsers for, so they're already pretty good at it. So Repla doesn't try to replace that. The second task developers use the web browser for is running their current project. This is where Repla comes in. While browsers do have some built-in tools for developers, they aren't really developer tools the same way that terminals and text editors are. So this is how Repla is designed, to be a developer tool in the same way a text editor and terminals are, and therefore achieve that same level of adaptability.

How do you design a development web browser that has the same flexibility as text editors and terminals? It turns out that text editors and terminals achieve their flexibility in very similar ways. They both use package managers to manage extensions, and those extensions often involve launching processes. Whether it's [downloading media](https://github.com/ytdl-org/youtube-dl/), [checking the correctness of code](https://atom.io/packages/linter), [perform compilation](https://lldb.llvm.org/), or [adding support for programming languages](https://marketplace.visualstudio.com/items?itemName=kiadstudios.vscode-swift), terminals and text editors flexibility comes from packages that can run processes.

So what is Repla? Repla is web browser that achieves flexibility by being able to install packages and run processes, just like text editors and terminals do. And just like those apps, Repla can shape itself to the problem at hand. These capabilities happen to make a nice way to run a local web server, and have it automatically refresh after each change. So that's what the first plugin, Repla Server, does. But that's far from the only use case for this combination, our next post [Repla Use Cases]() explores some of the others.

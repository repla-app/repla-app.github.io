---
layout: post
title: "What is Repla?"
image: /assets/2020-01-13-trifecta.png
categories: Essay
---

Repla is now launched. So far we've released **Repla Server**, the first Repla plugin. If you know something about product development, you know the question is always "what problem does this solve?". The problem that the Repla Server plugin solves is running a local web development server that refreshes automatically. Since that's the only plugin that's currently available, that's all [the Repla website](https://repla.app/) talks about, because that's the benefit you can get by downloading and using Repla today. But Repla itself wasn't designed to solve any one problem. This blog post is about how it was designed, and explore the benefits you'll be able to get from Repla tomorrow.

![Trifecta](/assets/2020-01-13-trifecta.png)

How was Repla designed? To answer this question, we'll look at how web developers work today. When web developers talk about the tools they use, they commonly say "a terminal, a text editor, and a web browser". None of those tools are designed to solve a specific problem either. Instead, they're adaptable, shaping themselves to the problem at hand. However, one of those tools is not like the others: While terminals and text editors are specialized tools optimized for developers, developers are stuck using the same web browsers everyone else uses. So Repla is designed to replace the web browser, or, more accurately, sit alongside it.

Developers really use web browsers for two separate tasks. The first is researching the problem they're working on. This is what most people (who, of course, aren't developers) also use web browsers for, so they're already pretty good at it, and Repla doesn't try to replace that. The second task developers use web browsers for is running their projects. This is where Repla comes in. While browsers do have some built-in tools for developers, they aren't developer tools the same way terminals and text editors are. This is how Repla was designed, as a web browser that's a developer tool the same way that text editors and terminals are, and therefore can achieve the same adaptability as those tools.

What does it mean for a web browser to be a developer tool in the same way text editors and terminals are? It turns out that text editors and terminals achieve their adaptability in similar ways. They are extensible through [package management](https://en.wikipedia.org/wiki/Package_manager), and extensions can run [processes](https://en.wikipedia.org/wiki/Process_(computing)). Whether it's [downloading media](https://github.com/ytdl-org/youtube-dl/), [checking source code for common issues](https://atom.io/packages/linter), [performing compilation](https://lldb.llvm.org/), or [adding support for more programming languages](https://marketplace.visualstudio.com/items?itemName=kiadstudios.vscode-swift), terminals and text editors achieve their adaptability through being extended by packages that run processes.

So what is Repla? Repla is a web browser that can be extended by packages that run processes, and therefore is as adaptable as text editors and terminals are. Repla shapes itself to the problem at hand, the same way those tools do. Repla Server, the first plugin for Repla, is a package that runs processes to manage a local web server. In our next post, [Repla Use Cases](http://blog.repla.app/2020/01/13/repla-use-cases/), we explore some other use cases.

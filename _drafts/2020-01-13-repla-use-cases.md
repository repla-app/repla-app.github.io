---
layout: post
title: "Repla Use Cases"
categories: Essay
---

In [What is Repla?](/2020/01/13/what-is-repla/), we explained how Repla is designed to be adaptable, just like text editors and terminals are, by being extended with [packages](https://en.wikipedia.org/wiki/Package_manager) that run [processes](https://en.wikipedia.org/wiki/Process_(computing)). This post is about some of the use cases of this combination. But before we get to that, we have to talk about how Repla is *different* from text editors and terminals, because it's through the differences that the good use cases emerge.

Besides being extensible through packages that run processes, text editors and terminals share another similarity, one that is not shared by Repla: They're both focused on plain text, while Repla is instead focused on the web rendering engine.

There are a lot of things a web rendering engine can do that plain text can't, some examples are display media, like pictures, video, and graphics, it can render rich text, with different combinations of fonts and colors, and it can be interactive, responding to input in any manner it chooses, in particular by supporting hyperlinks. So when we're looking for good Repla use cases, we're looking for problems that can take advantage of these attributes.

## Search

The first use case we'll look at is the prototype [Search plugin](https://github.com/repla-app/Search.replaplugin). This plugin makes the output of 
`grep` interactive. Often considered the canonical Unix tool, `grep` searches files for a regular expression and prints the matching lines. Here's what  output looks like searching [Ruby](https://en.wikipedia.org/wiki/Ruby_(programming_language)) files recursively for `class`:

	$ grep -rn class *.rb
	tc_controller.rb:19:class TestDependencies < Minitest::Test
	tc_controller.rb:27:class TestController < Minitest::Test
	tc_javascript.rb:17:class TestDependencies < Minitest::Test
	tc_javascript.rb:25:class TestJavaScript < Minitest::Test
	tc_parser.rb:17:class TestDependencies < Minitest::Test
	tc_parser.rb:25:class TestParser < Minitest::Test
	tc_search.rb:19:class TestDependencies < Minitest::Test
	tc_search.rb:27:class TestSearch < Minitest::Test

So the second line of output says the first match is in file `tc_controller.rb` on line `19`. While the output of `grep` is quite useful on its own, it's not interactive.

![Search](/assets/2020-01-13-search.png)

The Repla Search plugin displays the results of a `grep` search rendered as HTML, following a link for a filename, opens that file in the default app for that file type. More interactive features can be added such as [outliner](https://en.wikipedia.org/wiki/Outliner) functionality to allow each file's matches to be collapsed, to only see the list of filenames with matches, or to collapse the files you aren't interested in for example.
 
## Markdown

![Markdown](/assets/2020-01-13-markdown.png)

The prototype [Markdown plugin](https://github.com/repla-app/Markdown.replaplugin) takes advantage of the web rendering engine to render rich text and inline images, as well as being able to follow links.

## Diagramming

![Mermaid](/assets/2020-01-13-mermaid.png)

There are already some [great apps](https://marked2app.com/) that do Markdown rendering, but the flexibility of Repla's package model means that similar plugins can be made for formats that aren't supported by any existing apps. For example, a plugin for the [Mermaid diagramming language](https://github.com/mermaid-js/mermaid) would allow developers to track [class](https://en.wikipedia.org/wiki/Data-flow_diagram) and [control-flow](https://en.wikipedia.org/wiki/Control-flow_diagram) diagrams in version control alongside their source code, just like Markdown files are today.

## REPL

The prototype [IRB plugin](https://github.com/repla-app/IRB.replaplugin) shows the output of the results of executing code in `IRB` and provides an API that allows integrations like evaluating the code that's currently selected in your text editor.

![IRB](/assets/2020-01-13-irb.png)

## Live Coding

Going one step further then the REPL plugins, the planned [live coding plugins](https://repla.app/live-coding.html) will execute an entire document through a REPL incrementally, allowing you to see the results of your code executing live.

![Live Coding](/assets/2020-01-13-live-coding.png)

## Summary

These are a few example use cases of having a web browser with that can run processes and package management. But the real goal is provide a space where new use cases can emerge, much like the terminal and the text editor allow people to solve their own problems by extending them.
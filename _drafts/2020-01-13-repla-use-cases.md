---
layout: post
title: "Repla Use Cases"
categories: Essay
---

In [What is Repla?](/2020/01/13/what-is-repla/), we explained how Repla is designed to be adaptable, like text editors and terminals, by being extensible with packages that run processes. This post will show some use cases that take advantage this. But before we do that, we have to talk for a minute about how Repla is *different* than terminals and text editors, because it's through these differences that the use cases emerge.

Besides being extensible through packages that run processes, text editors and terminals share another similarity, one that is not shared by Repla: They're both focused on plain text, while Repla is instead focused on the web rendering engine.

There are a lot of things a web rendering engine can do that plain text can't, some examples are display media, like pictures, video, and graphics, it can render rich text, with different combinations of fonts and colors, and it can be interactive, responding to input in any manner it chooses, in particular by supporting hyperlinks. So when we're looking for good Repla use cases, we're looking for problems that can take advantage of these attributes.

## Search

The first use case we'll look at is the prototype [Search plugin](https://github.com/repla-app/Search.replaplugin). This plugin makes the output of 
`grep` interactive. Often considered the canonical Unix tool, `grep` searches files for a regular expression and then prints the matching lines. Here's what  output looks like this searching for `class`:

	$ grep -rn class *.rb
	tc_controller.rb:19:class TestDependencies < Minitest::Test
	tc_controller.rb:27:class TestController < Minitest::Test
	tc_javascript.rb:17:class TestDependencies < Minitest::Test
	tc_javascript.rb:25:class TestJavaScript < Minitest::Test
	tc_parser.rb:17:class TestDependencies < Minitest::Test
	tc_parser.rb:25:class TestParser < Minitest::Test
	tc_search.rb:19:class TestDependencies < Minitest::Test
	tc_search.rb:27:class TestSearch < Minitest::Test

So the first match is in file `tc_controller.rb` on line `19`. While quite useful on its own, the output of `grep` isn't interactive.

![Search](/assets/2020-01-13-search.png)


The Repla Search plugin displays the results of a `grep` search rendered as HTML, with the filename as a link. Following the link opens the file in the default app for that file type. A future version of the plugin will also add [outliner](https://en.wikipedia.org/wiki/Outliner) functionality, such allowing each files list of matches to be collapsed, e.g., to only see the list of filenames with matches or only keep the files that you're interested in uncollapsed.

## Markdown

The prototype [Markdown plugin](https://github.com/repla-app/Markdown.replaplugin) takes advantage of the web rendering engine to render rich text and inline images, and being able to follow links.

## Diagramming

While there are already [great apps](https://marked2app.com/) that provide Markdown rendering, the flexibility of Repla's extensible model means similar plugins that don't exist yet could be made. For example, a plugin for the [Mermaid diagramming language](https://github.com/mermaid-js/mermaid) would allow developers to track [class](https://en.wikipedia.org/wiki/Data-flow_diagram) and [control-flow](https://en.wikipedia.org/wiki/Control-flow_diagram) diagrams in version control along-side their source code, just like Markdown files are today.

![Mermaid](/assets/2020-01-13-mermaid.png)

## REPL

The prototype [IRB plugin](https://github.com/repla-app/IRB.replaplugin) shows the output of the results of executing code in `IRB` and provides an API that allows integrations like evaluating the code that's currently selected in your text editor.

![IRB](/assets/2020-01-13-irb.png)

## Live Coding

Going one step further then the REPL plugins, the planned [live coding plugins](https://repla.app/live-coding.html) will execute an entire document through a REPL incrementally, allowing you to see the results of your code executing live.

![Live Coding](/assets/2020-01-13-live-coding.png)

## Summary

These are a few example use cases of having a web browser with that can run processes and package management. But the real goal is provide a space where new use cases can emerge, much like the terminal and the text editor allow people to solve their own problems by extending them.
---
layout: post
title: "Repla Use Cases"
categories: Essay
---

In [What is Repla?](), we explained how Repla is a development web browser that's designed by be flexible the same way text editors and terminals are, by using package management and running processes. In order to talk about use cases for Repla, we first have to talk about how Repla is different than text editors and terminals, because it's through these difference that its use cases emerge.

Text editors and terminals have another similarity that Repla does not share, they're both focused on plain text. As a development web browser, Repla is instead focused on the web rendering engine, which has a few advantages over plain text. For example rendered web content can display media, like pictures and video, and it can render rich text with combinations of fonts and colors, and it can be interactive, in particular because it supports hyperlinks. So when we're looking for good use cases, we're looking for situations that can take advantage of these attributes.

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

So the first match is in file `tc_controller.rb` on line `19`. While quite useful on its own, the output of `grep` isn't interactive. The Repla Search plugin displays the results of a `grep` search rendered as HTML, with the filename as a link. Following the link opens the file in the default app for that file type. A future version of the plugin will also add [outliner](https://en.wikipedia.org/wiki/Outliner) functionality, such allowing each files list of matches to be collapsed, e.g., to only see the list of filenames with matches or only keep the files that you're interested in uncollapsed.

## Markdown

The prototype [Markdown plugin](https://github.com/repla-app/Markdown.replaplugin) takes advantage of the web rendering engine to render rich text and inline images, and being able to follow links.

## Diagramming

While there are already [great apps](https://marked2app.com/) that provide Markdown rendering, the flexibility of Repla's extensible model means similar plugins that don't exist yet could be made. For example, a plugin for the [Mermaid diagramming language](https://github.com/mermaid-js/mermaid) would allow developers to track [class](https://en.wikipedia.org/wiki/Data-flow_diagram) and [control-flow](https://en.wikipedia.org/wiki/Control-flow_diagram) diagrams in version control along-side their source code, just like Markdown files are today.

## REPL

The prototype [IRB plugin](https://github.com/repla-app/IRB.replaplugin) shows the output of the results of executing code in `IRB` and provides an API that allows integrations like evaluating the code that's currently selected in your text editor.

## Live Coding

Going one step further then the REPL plugins, the planned [live coding plugins](https://repla.app/live-coding.html) will execute an entire document through a REPL incrementally, allowing you to see the results of your code executing live.

## Summary

These are a few example use cases of having a web browser with that can run processes and package management. But the real goal is provide a space where new use cases can emerge, much like the terminal and the text editor allow people to solve their own problems by extending them.

* * *

[^addressingvscode]: Visual Studio Code and Atom should be addressed specially because since those apps provide a nice mechanism for providing a lot of the same functionality as Repla, only integrated into a text editor. That may be a successful approach as well, but one of problem with that approach is that it causes those application to cross a threshold of complexity that makes these kinds of features very difficult to use when integrated into a text editor, in specific apps struggle when they try to incorporate two entirely different user-interface models into the same application. With that said, it would be great to see more of these kinds of features succeeding in these applications.




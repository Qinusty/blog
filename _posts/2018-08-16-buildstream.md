---
layout: post
title: 'BuildStream'
---

# Intro
I have spent the last two months or so working on the [BuildStream](https://gitlab.com/BuildStream/buildstream) project, picking up bugs and
implementing a few features during my time at [Codethink Ltd](https://www.codethink.co.uk/). BuildStream is a GNOME project for
building/integrating software stacks, allowing you to define your build
configuration with a collection of [YAML](https://en.wikipedia.org/wiki/YAML)
files which state elements, their sources and build actions. For a more
detailed introduction to BuildStream if not a little dated, see the [FOSDEM talk](https://video.fosdem.org/2018/K.3.201/introducing_buildstream.webm) by
Tristan Van Berkom ([@tristanvb](https://gitlab.com/tristanvb)).

# The project
The BuildStream project has come a long way over the past few months, both
during and prior to my arrival. The documentation has come from being almost impossible to start with, to providing detailed references to commands, plugin API's and examples to get people started.

## Interested areas of development
- Caching
- Remote execution service ([BuildGrid](https://gitlab.com/BuildGrid/buildgrid))

## Contributing
A detailed guide to contributing can be found [here](https://buildstream.gitlab.io/buildstream/HACKING.html).

Getting started with BuildStream, plugins are a great place to start besides fixing bugs. BuildStream has two main types of plugins:

### Element
An element is what your `.bst` files describe, there are a variety of [kinds](https://buildstream.gitlab.io/buildstream/core_plugins.html) of elements, each
detailed in the documentation. Custom elements can be written to perform less
common tasks, see [Element API](https://buildstream.gitlab.io/buildstream/buildstream.element.html) and [BuildElement API](https://buildstream.gitlab.io/buildstream/buildstream.buildelement.html).

### Source
A source is what you will feed into your element to produce an output.
Different source kinds retrieve and extract certain types of sources and custom
sources can be written for those less common sources you depend on. See [Source API](https://buildstream.gitlab.io/buildstream/buildstream.source.html).

# Summary
I've enjoyed getting involved with BuildStream, as my first real open source
experience. I'd recommend that anyone who hasn't really contributed to open
source should give it a go on a project they find interesting. There are plenty
of articles about getting into open source, but I'd
recommend reading a few [Pull/Merge request articles](https://hackernoon.com/the-art-of-pull-requests-6f0f099850f9) to get a feel
for what actually happens when you're submitting a patch.

The majority of the open source community are genuinely kind and willing to
provide constructive criticism, be willing to accept it and appreciate that
having your code reviewed is honestly the best way to improve your code quality. On the otherhand, I would also recommend reviewing other peoples code if you get the chance on a project.

Don't know where to start? Check out https://www.firsttimersonly.com/ or even just check the issues list on [BuildStream](https://gitlab.com/BuildStream/buildstream/issues?scope=all&utf8=%E2%9C%93&state=opened&label_name[]=Newcomers). If you're stuck where to start, check for
an IRC channel and let them know you're looking for low hanging fruit.
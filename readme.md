# Computational Publishing with Jupyter

As first described in [Embracing Jupyter Notebooks at O'Reilly](https://www.oreilly.com/ideas/jupyter-at-oreilly), Jupyter is a critical tool.  The intervening time between when that was written and today has only confirmed it.  In fact, I'd be so bold as say that Jupyter is the  most important tool for technical publishers since the Laser Writer and Aldus PageMaker.

The reason?  Jupyter is one of the first digital *authoring* tools, as opposed to a bespoke software development process, that begins to deliver on Seymour Papert's [constructivist](http://www.papert.org/articles/SituatingConstructionism.html) vision that people learn best by actively making and doing, versus passively reading, listening, or watching.

This idea has been explored in Brett Victor's seminal 2011 essay [Explorable Explanations](http://worrydream.com/ExplorableExplanations/), as well as [Lorena Barba](http://lorenabarba.com/)'s vision of [computable content](https://bids.berkeley.edu/events/computational-thinking-and-pedagogy-computable-content).  

<img src="images/explorable-explanations.gif"/>
_Brett Victor / [Explorable Explanations](http://worrydream.com/ExplorableExplanations/)_

As we [surveyed the landscape of tools](http://odewahn.github.io/patterns-of-code-as-media/www/introduction.html), the Jupyter ecosystem has emerged as the leading toolset that addresses many thorny issues:

* Simple support for new interaction models.  Jupyter provides a plug-in architecture that allows the community to easily add new features, such as plotting, mapping, or data visualization.
* Mixed video, text, and assessment.  A Jupyter document can consist of a rich set of media of all types.  Basically, anything that run in a browser will run in Jupyter.
* Code + data.  Combining a notebook with a tool like git or dat allows you to easily package your code and data.
* Collaboration.  With git and github, you can package your content and all assets and post them to the many public git hosting services, such as GitHub, BitBucket, or GitLab.
* Discovery and citation.  Services like [Zenodo](https://zenodo.org/) make it simple to assign DOIs to Notebook content so that they can be cited in scholarly publications.
* Reproducibility and preservation.  You need to only add a Dockerfile or some other mechanism to specify the project's dependencies (such as the appropriate Ansible playbooks) in order to fully recreate the environment required for the Notebook content to run.  And, since these are stored as Git files, it is simple to keep the content available so that you can reconstruct at any time, as opposed to keeping the running environment, which is challenging.



### Challenges


## A Model for Computational Publishing

<img width="100%" src="images/computational-publishing-model.png"/>

### Source Content

#### Version control in git

* Git flow
* GitHub
* Diffs

#### Structured Markup

* [Markdown](https://daringfireball.net/projects/markdown/).  One of the original simple text markup languages, Markdown is a bit like wirting a glorified email, where lists are bullets, bold is denoted by asterisks, and headers by a "#" symbol.  Markdown is great for shorter articles.
* [GitHub flavored markdown](https://guides.github.com/features/mastering-markdown/).  The basic markdown syntax, but with some extra features for marking up code, tasks, tables, and other more complex strutures.
* [AsciiDoc](http://asciidoc.org/).  A full featured markup syntax based on [DocBook](http://docbook.org/) (see below) that handles the complex structures required for book-length texts that require cross-referencing, bibliographic material, sections, asides, indexes, and a host of other complex features.
* [reStructured text](http://docutils.sourceforge.net/rst.html).  Basically, the same idea as Markdown, but adopted heavily by the Python community.
* [HTMLBook](https://github.com/oreillymedia/HTMLBook).  A set of HTML5 tags and classes developed by O'Reilly Media for publishing.
* [DocBook](http://docbook.org/).  An XML-based markup language for technical documentation.  It was originally developed at O'Reilly Media in the mid-1990s, but is now part of the  [OASIS](https://www.oasis-open.org/) standards.

Jupyter stores content in a  [json](http://www.json.org/)-based format called [ipynb](https://ipython.org/ipython-doc/3/notebook/nbformat.html).  



#### Transformation engines


https://www.staticgen.com/

* [Jekyll](http://jekyllrb.com/)
* [Hugo](http://gohugo.io/)
* [Hexo](https://www.staticgen.com/hexo)
* [GitBook](https://www.gitbook.com/)


Jupyter comes with a command-line tool called [nbonvert](https://nbconvert.readthedocs.io/en/latest/) that can transform the `ipynb` format to a variety of other formats:

```
jupyter nbconvert --to FORMAT notebook.ipynb
```

Formats include 'html', 'latex', 'markdown', 'pdf', 'python', 'rst', 'script', 'slides'.  (You can also include a custom format based on templates you create.)

### Machine Image

#### Jupyter Dependencies

#### Content Dependencies

| Platform  | Packaging System      |
|-----------|-----------------------|
|OS         | yum, apt, brew, choco |
|Python     | pip, conda            |
|Node       | npm, yarn             |
|R          | cran                  |
|Go         | dep                   |
|Ruby       | gem                   |


#### Docker as a general solution

https://github.com/jupyter/docker-stacks

<img width="100%" src="images/docker-stacks.png"/>

### Runtime Engine

<img width="100%" src="images/container-runtime.png"/>

### File Sharing

### LaunchBot: Lowering the barriers to entry

### Support in Safari

* [Assessments](https://www.oreilly.com/learning/why-self-assessments-improve-learning)

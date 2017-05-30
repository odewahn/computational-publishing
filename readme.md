# Computational Publishing with Jupyter

As first described in [Embracing Jupyter Notebooks at O'Reilly](https://www.oreilly.com/ideas/jupyter-at-oreilly), Jupyter is a critical tool.  Time has only confirmed it -- I'd wager that Jupyter is on the shortlist as the most important tool for technical publishers since the Laser Writer and Aldus PageMaker.

The reason?  Jupyter is one of the first digital *authoring* tools, as opposed to a bespoke software development process, that delivers on Seymour Papert's [constructivist](http://www.papert.org/articles/SituatingConstructionism.html) vision.

Papert's ideas, explored in a modern digital context in Brett Victor's seminal 2011 essay [Explorable Explanations](http://worrydream.com/ExplorableExplanations/), as well as [Lorena Barba](http://lorenabarba.com/)'s vision of [computable content](https://bids.berkeley.edu/events/computational-thinking-and-pedagogy-computable-content), posits that people learn best by actively making and doing, versus passively reading, listening, or watching.  

<img src="images/explorable-explanations.gif"/>
_Brett Victor / [Explorable Explanations](http://worrydream.com/ExplorableExplanations/)_

As we [surveyed the landscape of tools](http://odewahn.github.io/patterns-of-code-as-media/www/introduction.html), the Jupyter ecosystem has emerged as the leading toolset that addresses many thorny issues:

* Simple support for new interaction models.  Jupyter provides a plug-in architecture that allows the community to easily add new features, such as plotting, mapping, or data visualization.
* Mixed video, text, and assessment.  A Jupyter document can consist of a rich set of media of all types.  Basically, anything that run in a browser will run in Jupyter.
* Code + data.  Combining a notebook with a tool like git or dat allows you to easily package your code and data.
* Collaboration.  With git and github, you can package your content and all assets and post them to the many public git hosting services, such as GitHub, BitBucket, or GitLab.
* Multi-language support.  Jupyter's kernel-based design means that new languages and services are relatively easy to incorporate.
* Discovery and citation.  Services like [Zenodo](https://zenodo.org/) make it simple to assign DOIs to Notebook content so that they can be cited in scholarly publications.
* Reproducibility and preservation.  You need to only add a Dockerfile or some other mechanism to specify the project's dependencies (such as the appropriate Ansible playbooks) in order to fully recreate the environment required for the Notebook content to run.  And, since these are stored as Git files, it is simple to keep the content available so that you can reconstruct at any time, as opposed to keeping the running environment.

SOMETHING THAT TIES THIS BEYOND PUBLISHING TO A GENERAL SET OF COLBORATION AND SHARING IN A COMPUTATION-HEAVY ENVIRONMENT.

### Challenges

Clearly, Jupyter provides a host of benefits and opportunities.  However, despite the promise, it's widespread adoption outside the programming, scientific, and data science community has been hindered by its relatively high barriers to entry of the overall ecosystem.

As a tool built by hackers for hackers, realizing the full potential of Jupyter requires the user to understand several tools typically used in software engineering.  For authors used to working in Word or Google Docs, Jupyter's reliance on Git, GitHub, package managers, and software configuration tools can be a overwhemling.  This is magnified when the tool is moved outside a purely technical area, such as biology, economics, journalism, or library sciences.

In addition to the steep learning curve, our experience in trying to build a robust workflow for publishing with Jupyter indicates that even very technical and experienced authors have a hard time creating reproducible environments.  This usually manifests in a broken library or call within a notebooks (i.e., the content uses something that is not on the base image).

## A Model for Computational Publishing

We've developed a four-part model to help us realize Jupyter's potential:

<img width="100%" src="images/computational-publishing-model.png"/>

The following sections detail the each of the following components:

* Source content
* Machine image
* Runtime engine
* File sharing

### Source Content

The source content is largely about how you manage the source files that make up the project.  This consists not only of your text content, but also any data, images, or configuration files.  Our experience largely boils down to the following three principles:

* Version control with git
* Structured markup
* Transformation engines

The following sections explore each in a bit more detail.

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

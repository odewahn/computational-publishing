# A Field Guide to Computational Publishing

Inspired by Brett Victor's seminal 2011 essay [Explorable Explanations](http://worrydream.com/ExplorableExplanations/), O'Reilly Media has been experimenting with ways to make do a new kind of publishing.

In the essay, Victor [SOMETHING ABOUT WHAT HE DESCRIBES]

<img src="images/explorable-explanations.gif"/>


* New interaction models.
* Video, text, and assessment.
* Data and content together.
* Preservation.
* Discovery and citation.
* GitHub friendly dual licensing.

## Jupyter as an authoring tool

Jupyter is probably the  most important tool for technical publishers since the Laser Writer and Aldus PageMaker.

### Challenges


## A Model for Computational Publishing

<img width="100%" src="images/computational-publishing-model.png"/>

### Source Content

#### Version control in git

* Git flow
* GitHub
* Diffs

#### Structured Markup

* Markdown
* AsciiDoc
* Restructured text
* HTMLBook
* DocBook

Jupyter stores content in a  [json](http://www.json.org/)-based format called [ipynb](https://ipython.org/ipython-doc/3/notebook/nbformat.html).  



#### Transformation engines


https://www.staticgen.com/

* [Jekyll](http://jekyllrb.com/)
* [Hugo](http://gohugo.io/)
* [Hexo](https://www.staticgen.com/hexo)
* [GitBook](https://www.gitbook.com/)


[nbonvert](https://nbconvert.readthedocs.io/en/latest/) is the main transformation tool in the Jupyter ecosystem.

```
jupyter nbconvert --to FORMAT notebook.ipynb
```

Formats include 'html', 'latex', 'markdown', 'pdf', 'python', 'rst', 'script', 'slides'.  (You can also include a custom format based on templates you create.)

### Machine Image

#### Jupyter Dependencies

#### Content Dependencies


https://github.com/jupyter/docker-stacks

<img width="100%" src="images/docker-stacks.png"/>

### Runtime Engine

<img width="100%" src="images/container-runtime.png"/>

### File Sharing

### LaunchBot: Lowering the barriers to entry

### Support in Safari

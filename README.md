Timelines
=========

* [Symbolic execution timeline](diagram/symbolic-execution.svg) highlights some major tools and ideas of pure symbolic execution, dynamic symbolic execution (concolic) as well as related ideas of model checking, SAT/SMT solving, black-box fuzzing, taint data tracking, and other dynamic analysis techniques.
* [Solving timeline](diagram/solving.svg) highlights major SAT and SMT techniques and solvers (including solvers not related to symbolic execution).

There is also [temporary timeline](diagram/other.svg) of some tools not displayed in the diagrams above.

Symbolic execution
------------------

:warning: PNG preview could be outdated. See [`symbolic-execution.svg`](diagram/symbolic-execution.svg) for the latest version.

![Preview](https://raw.github.com/enzet/symbolic-execution/master/diagram/symbolic-execution.png)

SAT and SMT solving
-------------------

:warning: PNG preview could be outdated. See [`solving.svg`](diagram/solving.svg) for the latest version.

![Preview](https://raw.github.com/enzet/symbolic-execution/master/diagram/solving.png)

Building PNG or PDF
-------------------

Please, install fonts for correct SVG display:
  * [Roboto](https://fonts.google.com/specimen/Roboto) (regular and italic) and
  * [Fira Code](https://github.com/tonsky/FiraCode).

Use Inkscape to build PNG or PDF. Example for `symbolic-execution` diagram:

  * PNG: `inkscape diagram/symbolic-execution.svg --export-png diagram/symbolic-execution.png --export-dpi 150`,
  * PDF: `inkscape diagram/symbolic-execution.svg --export-pdf diagram/symbolic-execution.pdf`.

Design
------

We use colors from [GitHub Linguist](https://github.com/github/linguist/blob/master/lib/linguist/languages.yml) for input languages.

Contribution
------------

Feel free to suggest changes or add new information. If your change is minor (like typo), you can just edit source code of [`symbolic-execution.svg`](diagram/symbolic-execution.svg). If change is major, you are encouraged to either create new issue, or edit `symbolic-execution.svg` ([Inkscape](https://inkscape.org/en/) editor is strongly recommended due to source code issues).

### Before commiting ###

Please, use [SVGO](https://github.com/svg/svgo) for diagram optimization before commiting (to get more clean diff):

    svgo diagram/symbolic-execution.svg \
        --pretty \
        --enable=sortAttrs \
        --disable=removeEditorsNSData \
        --disable=cleanupIDs \
        --indent=2

Tools structure
===============

File [`tools.yml`](tools/tools.yml) contains tools YAML description. E.g.:

```
DART:
  since: 2005
  input: C
  uses: lp_solve
  based: CIL
  description: random testing and direct execution
```
### Tool explanation 

How the tool is articulated ? 

We have 2 config files to see if we need to change anything on the information within the image. 
One file is the folder tool and is named tools.json. This Json has all the tool references. 
One Tool is represented as the following : 
{
  "name": ,
  "since": , 
  "description": ,
  "url": ,
  "github": ,
  "type": ,
  "uses":[""],
  "affilications":["",""],
  "os": ,
  "license": ,
  "languages": ["",""],
  "api": ,
  "technique": ,
  "authors": ,
}

The other file is config and this is describing the links between the tools in tools.json. 

This help keeping track on the timeline interaction between tools. 


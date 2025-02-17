A Quarto Extension for Creating APA 7 Style Documents
================

![Experimental](lifecycle-experimental.svg)

This is an experimental article template that creates [APA Style 7th
Edition documents](https://apastyle.apa.org/) in .docx, .html. and .pdf.
I made this extension for my own workflow. If it helps you, too, I am
happy.

If you want to type in markdown to create a document in the APA 6th
Edition format, I suggest using
[papaja](https://frederikaust.com/papaja_man/).

If you need all the flexibility of $\LaTeX$, I suggest using the [apa7
document class](https://ctan.org/pkg/apa7) with knitr and the [.Rnw
format](https://support.posit.co/hc/en-us/articles/200552056-Using-Sweave-and-knitr).

## Creating a New Article

To create a new article using this format, run this command in the
terminal:

``` bash
quarto use template wjschne/apaquarto
```

In RStudio, the terminal is a tab next to the console. If you cannot see
a terminal tab next to the console, use the keyboard shortcut
Alt-Shift-R to make a terminal appear.

Entering the command above will prompt a question about whether you
trust the author of the extension to not run malicious code. If you
answer Yes, you will be prompted to name a new folder where the
extension will be installed with an example document with the name of
the folder and a file extension of .qmd. The example document has most
of the instructions you will likely need.

## Using with an Existing Document

To add this format to an existing document:

``` bash
quarto add wjschne/apaquarto
```

Then, add the format to your document options:

``` yaml
format:
  apaquarto-docx: default
```

When adding this extension to an existing document, you will need to add
this line to the document right after its YAML metadata:

``` md
{{< include _extensions/wjschne/apaquarto/_apa_title.qmd >}}
```

Here is an example of what the YAML metadata and the “include” statement
below it might look like:

    ---
    title: "My Paper's Title: A Full Analysis of Everything"
    shorttitle: "My Paper's Title"
    author:
      - name: W. Joel Schneider
        corresponding: true
        orcid: 0000-0002-8393-5316
        email: schneider@temple.edu
        affiliations:
          - name: Temple University
            department: College of Education and Human Development
            address: 358 Ritter Hall
            city: Philadelphia
            region: PA
            postal-code: 19122-6091
    abstract: "This is my abstract."
    keywords: [keyword1, keyword2]
    author-note:
      disclosures:
        conflict of interest: The author has no conflict of interest to declare.
    bibliograpy: mybibfile.bib     
    format:
      apaquarto-docx: default
    ---
    {{< include _extensions/wjschne/apaquarto/_apa_title.qmd >}}

## Example

This sample document has a fuller set of parameters specified and
contains instructions for formatting figures, tables, cross-references,
and more: [template.qmd](template.qmd).

## Known Problems

- Flextable tables do not render in jou mode for apaquarto-pdf.
- Tables and figures do not fit automatically in jou mode for
  apaquarto-pdf.

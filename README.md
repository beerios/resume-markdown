# Markdown Resume

This repo allows me to build and maintain my resume in a Markdown file. 

This project was cloned from this [project by Vid Luther](https://github.com/vidluther/markdown-resume) which was inspired by this [project by Sonya Sawtelle](https://sdsawtelle.github.io/blog/output/simple-markdown-resume-with-pandoc-and-wkhtmltopdf.html). So far, my updates have been minimal, but I have removed external css dependencies and updated the commands as needed.

# Workflow

The workflow is pretty simple.

1. Edit the chris-harley-resume.md file.
1. Run pandoc to convert the Markdown file to HTML
1. Run wkhtmltopdf to convert the HTML file into a PDF.

I converted this back to two commands, to ensure the correct formatting (e.g. choosing letter Instead of A4) is maintained when generating the PDF. 

# Updated instructions for a Mac .. or 2021

A lot has changed since Sonya wrote her blog post and shared her workflow, so here are some updates on how to get started and building/updating your own resume.

# Pre-Requisites

## [Pandoc](https://pandoc.org) a universal document converter

```bash
    brew install pandoc
```

## [Wkhtmltopdf](https://wkhtmltopdf.org)

```
    brew install wkhtmltopdf
```

## Markdown to HTML

```
pandoc resume.md -f markdown -t html -c resume-stylesheet.css -s -o resume.html
```

## Markdown to PDF

```
pandoc resume.md -f markdown -t pdf --pdf-engine=wkhtmltopdf -c resume-stylesheet.css -s -o resume.pdf
```

## HTML to PDF

If you want to convert from HTML to PDF for some reason, you'll need to add a switch to wkhtmltopdf so that it works properly.

```
wkhtmltopdf --enable-local-file-access resume.html resume.pdf
```

# TODO

- [x] [github action](https://github.com/pandoc/pandoc-action-example) will run and create the HTML and PDF file automatically.
- [ ] the Author field in the PDF, it seems to not work when the pdf-engine is set to wkhtmltopdf
- [ ] make a release or a package?

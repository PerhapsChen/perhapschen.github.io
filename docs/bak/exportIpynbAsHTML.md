# Export `.ipynb` as `HTML` file.

## Export by command line.
convert `.ipynb` file as `HTML` file.

```bash
jupyter nbconvert --to html ./foobar.ipynb
```

The following formats are available: 

```bash
['asciidoc', 'custom', 'html', 'latex', 'markdown', 'notebook', 'pdf', 'python', 'qtpdf', 'qtpng', 'rst', 'script', 'slides', 'webpdf']   
```

In the HTML file, we can modify `jp-code-font-size` to change font size of codes.

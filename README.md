# Joey Marshall's resume and resume builder
Download my [resume](resume.pdf) here.  
Download my [full academic CV](cv.pdf) here.  

## How it works
My resume and CV are authored in [RMarkdown](https://rmarkdown.rstudio.com/). I put the content for all the sections (publications, presentations, etc.) in .csv files and then ```kable()``` them into the .rmd file. So this:  

![img/spreadsheet.PNG](screenshot)

Gets rendered as:

![img/resume.PNG](screenshot)

## Details
* The styling is done in styles.css.
* After knitting the HTML files together, I'm using [wkhtmltopdf](https://wkhtmltopdf.org/) to convert the HTML files to .pdf. I prefer this to rendering .pdf files directly from R. The little PowerShell script (makepdf.ps1) is my makefile for this purpose.
* Why use [kableextra](https://github.com/haozhu233/kableExtra) rather than standard Markdown tables? Because 1) I get more (and easier) control over style and 2) it enables my workflow of editing the content in the .csv files.
* So the workflow is:
  * Edit the content in the .csv files.
  * ```knit()``` the HTML files.
  * Use wkhtmltopdf to convert the HTML files to .pdf.

## Roadmap
* Use the same .csv files as inputs for my personal website, so that the updated content in the .csv files can be piped into both my print resume and my website.
* Eliminate the extra step of running wkhtmltopdf via PowerShell. (Can R use wkhtmltopdf?)

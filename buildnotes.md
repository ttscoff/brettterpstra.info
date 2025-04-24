# brettterpstra.info

Brett Terpstra's resume

## File Structure

The resume is stored in `BrettTerpstraResume.txt`. It's mostly MultiMarkdown with minimal HTML markup for styling.

Each section goes in a `<section>` tag, the header in a `<header>` tag, and contact info in an `<aside>`. Otherwise uses MultiMarkdown definition lists and paragraphs.

## Build

Manual:

Load the resume Markdown in Marked 2 and apply the Resume.css style to it (if the style is installed in Marked it will be automatically selected). Output as HTML (index.html) with stylesheet embedded.

Automatic:

@run(multimarkdown "BrettTerpstraResume.txt" > index.html)

## Cover Letter

Edit "BrettTerpstraCoverLetter.txt" and run this step on it.

@run(multimarkdown "BrettTerpstraCoverLetter.txt" > coverletter.html)

## Deploy

@include(Cover Letter)
@include(Build)

@run(rsync -avz --exclude-from ./rsync-exclude . dh:~/brettterpstra.info/)


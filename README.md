# LaTeX Resume Template

A template I use for my resume. 

## Reasons to use it

- Maintainability. I've been using this for several years, it's easy to update and modify.
- Formatting. All you need to do is worry about the actual words, and let LaTeX do the difficult formatting work for you.
- Comments: You can use ```%``` in latex to add comments, or use the ```\begin{comment}``` and ```\end{comment}``` commands, helping you leave TODO notes or other handy comments to work 
- Version control: You can selectively include or exclude portions of your resume, allowing you to not just preserve past experiences but also tailor your resume for different job profiles if you have experiences spanning across a few.

## File structure
There are 4 tex files that make up this template. You only need to make changes in the first one - the others are "supporting" documents made for organization purposes.
- ```resume_main.tex```: The main file where you would add your resume content 
- ```customcommands.tex```: All the custom commands used in the main tex file are defined here
- ```misc_settings.tex```: A bunch of LaTex settings related to formatting
- ```packages.tex```: LaTeX preamble

## Main file

The first thing to discuss is the structure of the main document ```resume_main.tex```. Typically, this is the only one you would have to change to actually add/modify/remove content, though you can modify other files to affect document-wide characteristics.

The entire document is hierarchical - within a section, you can multiple subheadings and bullet points for each in a completely hierarchical way. 

You can add a new section with the ```\section{}``` command. This will write out the argument in caps and add a horizontal bar across the page.

Then you want use a ```\resumeSubHeadingList{}``` command to start adding content. This is the first level of hierarchy - within this, you can start adding subheadings with the following commands:

- ```\resumeSubHeading{1}{2}{3}{4}``` - Takes 4 arguments. Arguments 1 and 3 are on the left of the page, arguments 2 and 4 are on the right of the page
- ```\resumeSubHeadingTwo{1}{2}``` - Like the one above except with only one argument on the left and one on the right
- ```\resumeSubHeadingIndent{1}{2}``` - Like resumeSubHeadingTwo but with the left one slightly indented

After adding your subheadings, you would want to add a ```resumeItemList{}```, where you can add individual bullet points as ```\resumeItem{}``` commands.

## Including or excluding
The next important feature is to selectively include or exclude blocks from your resume.

At the top of the the main tex file, you will see a ```\flag{}{}``` command. That defines a new flag (if it hasn't been defined already) and sets it to a value, either true or false. 

After it has been defined and set, whatever you wrap with an ```\includeiftrue{}{}``` command will show up if the flag is true.

Syntax:
- ```\flag{1}{2}```: 1 is the flag name, 2 is the setting (true or false). These have been aliased to \1 and \0 respectively to make life easier
- ```\includeiftrue{1}{2}```: 1 is the flag name, 2 is the content to include or exclude based on the value the flag has been set to.

## Questions?

Contact me lol
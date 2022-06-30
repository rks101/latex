# latex
LaTeX and Beamer related discussions

LaTeX: [tutorial](https://www.latex-tutorial.com/tutorials/)  
[Overleaf](overleaf.com) - an online LaTeX editor  
[Latexsheet](http://wch.github.io/latexsheet/latexsheet-a4.pdf)  


----

**Note on Bibliography**  
[Some tips on bibliography](https://faculty.math.illinois.edu/~hildebr/tex/bibliographies0.html) that will definitely save time some day.  

Make sure .tex (main latex source), .bib (bibliography entries), and .bst (bibliography style) files are in the same directory. The following sequence can be handy. Depending on the template used, some of these packages are not required due to .cls file in use or re-implementation of commands/environment.  

```
\documentclass{article}   % or as per journal / conference template 

% premble for packages 
\usepackage{amsmath}      % for dealing with mathematics
\usepackage{amsthm}       % for dealing with theorem environments
\usepackage{hyperref}     % for linking the cross references
\usepackage{graphics}     % for dealing with figures
\usepackage{algorithmic}  % for describing algorithms
\usepackage{subfig}       % for getting the subfigures e.g., "Figure 1a and 1b" etc.
\usepackage{url}          % for better support in handling and breaking URLs
\usepackage{comment}      % for commented text in .tex file

% add bibliographystyle required for example somestyle.bst
\bibliographystyle{somestyle}

\title{A sequence template}

\begin{abstract}
Abstract goes here. No citations, table or figure references in abstract. 
\end{abstract}

\begin{document}

\maketitle

\section{......}
......
\subsection{......}

% add bibliography .bib file name without file extension .bib
\bibliography{mybib}

\end{document}
```

----

At times, what you write and what you get in LaTeX output file, defies the logic, and many times experience is surprisingly happy too :) You may not have looked into one of .cls, .sty, .bst files.   

It can consume some time in initial days, especially while switching between journal formats. Have patience. Preserve your own templates.  

If cited publications using \cite{someindex} are not appearing under References, or you are getting an [empty .bbl file](https://tex.stackexchange.com/questions/207664/bibtex-generates-an-empty-bbl-file), rename both .tex and .bib file to all small letters and same name with different extensions. Do not forget to update filename in .tex file using \bibliography{filename}.   

If URL/hyperlink text does not show up in bibliography, look for howpublished = "\url{URL_or_HYPERLINK}" and url package. [Refer this](https://tex.stackexchange.com/questions/35977/how-to-add-a-url-to-a-latex-bibtex-file).   

----

**To add list of tables and figures in report/article** 

After you begin document, use addcontentsline: 

```
\tableofcontents

\addcontentsline{toc}{chapter}{Contents}

\listoffigures

\addcontentsline{toc}{chapter}{List of Figures}

\listoftables

\addcontentsline{toc}{chapter}{List of Tables} 
```

Note: To remove ugly square boxes around TOC links (that appear to cut text), you can use coloured links instead, using [hypersetup](https://en.wikibooks.org/wiki/LaTeX/Hyperlinks):   

```
\hypersetup{
  colorlinks   = true, % Colours links instead of ugly boxes
  urlcolor     = blue, % Colour for external hyperlinks
  linkcolor    = blue, % Colour of internal links
  citecolor    = red   % Colour of citations
}
```
In case you wish to remove colors as well, use black color instead of blue or red. Links will be clickable with text as black color.   

----

**To insert emply page with or without numbering**

Insert empty page with numbering:    
```
\newpage
\thispagestyle{empty}
\mbox{}
\newpage
```

Insert empty page without numbering (or restore counter):   
```
\usepackage{afterpage}
\newcommand\myemptypage{
    \null
    \thispagestyle{empty}
    \addtocounter{page}{-1}
    \newpage
    }
```
Later, use myemptypage where neded in source:   
```
\myemptypage
```
[Refer math-linux.com](https://math-linux.com/latex-26/faq/latex-faq/article/latex-how-to-insert-a-blank-or-empty-page-with-or-without-numbering-thispagestyle-newpage-usepackage-afterpage)    

----

**To write algorithm**

To write an algorithm, [refer this link] for package and tags.   

To insert a list of algorithms in table of contents of a report or thesis:    

```
\addcontentsline{toc}{chapter}{List of Algorithms}
\listofalgorithms
```

----


**To change numbering numerals**  

If you need to change numbering letters or numerals for an ordered list, such as a), b) or i), ii) you can use package enumitem and update option for enumerate.  

This comes quite handy while writing surveys or articles with indexing going to 4th level such 1.1.1.1 or 3.A.1.1 or I.A.1.1  
I found it necessary when I wanted to avoid looking repeated numerals after 3rd level: I then => A, then => 1, then again => 1, and so on. 

```
% Incluce package enumitem  
\usepackage{enumitem} 

% For an Alphabetical numbered list a), b), c) 
\begin{enumerate}[label=\alph*)]
  \item Quincy Market 
  \item Aquarium 
\end{enumerate}

% For Arabic numberals 1), 2), 3) 
\begin{enumerate}[label=\arabic*)]
  \item Quincy Market 
  \item Aquarium 
\end{enumerate}

% For Roman numerals (i), (ii), (iii) 
\begin{enumerate}[label=(\roman*)]
  \item Quincy Market 
  \item Aquarium 
\end{enumerate}
```
---- 

**To change bulleting characters**  

If you need to change bulleting characters for an un-ordered list, such as * or o, you can use update option for itemize.  
```
% For an Asterisks bullet * instead of dot  
\begin{itemize}[label=$\ast$]
  \item Quincy Market 
  \item Aquarium 
\end{itemize}
```
----

**To align bullet/ list to text** 

[Align bullet to text](https://tex.stackexchange.com/questions/195290/align-itemize-bullet-to-text)

----

To show equation with simplification using another line as we do on paper or black/white-board:   

```
\usepackage{amsmath}
...
\begin{document}
...
  \begin{equation} \label{eq_area}
  \begin{split}
  A & = \frac{\pi r^2}{2} \\
    & = \frac{1}{2} \pi r^2
  \end{split}
  \end{equation}
...
\end{document}
```

---- 

To make a block transparent or set block color using addtobeamertemplate:   

[addtobeamertemplate](https://tex.stackexchange.com/questions/18447/how-to-make-a-block-transparent-for-a-background-image)   

----

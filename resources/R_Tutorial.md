---
layout: post2
permalink: /CBW_R_Tutorial/
title: CBW R Tutorial
header1: CBW R Tutorial
header2: An Introduction to R 
image: Bioinfo_Logo.jpg
---

#### Contents

1. [The Environment](#environment)
   
  1.1 [Installation](#installation) 

  1.2 [User Interface](#interface) 
       
      1.2.1 [A Note on R Studio](#RStudio) 
      
      1.2.2 [THe Help System](#help) 
      
      1.2.3 [Working Directory](#work) 
      
      1.2.4 [.Rprofile - Startup Commands](#rprofile) 
         
        1.2.4.1 [Unix Systems](#unix) 
        
        1.2.4.2 [Mac OS X Systems](#macs) 
        
        1.2.4.3 [Windows Systems](#windows) 
         
      1.2.5 [Workspace](#workspace) 
      
   1.3 [Packages](#packages) 
  
   1.4 [Scripts](#scripts) 

2. [Simple Commands](#commands)

   2.1 [Operators](#operators)

   2.2 [Functions](#functions)
   
   2.3 [Variables](#variables)
   
3. [Scalar Data](#scalars)

4. [Vectors](#vectors)

5. [Matrices](#matrices)
 
6. [Lists](#lists)

7. [Data frames](#data_frames)

8. [Writing Your Own Functions](#writing_functions)

   8.1 [Coding Style](#style)

   8.2 [Debugging](#debugging)
   
   8.3 [Finishing](#finishing)
   
9. [Notes](#notes)

10. [Further Reading and Resources](#reading_resources)

  
  
***

###  The Environment  <a id="environment"></a>

In this section we discuss how to download and install the software, how to configure an **R** session and what work with the **R** environment includes.

#### Installation <a id="installation"></a> 

1. Navigate to [the CRAN mirror site at the University of Toronto](http://probability.ca/cran/) and follow the link to your computer's operating system.

2. Download a precompiled binary (or "build") of the **R** "framework" to your computer and follow the instructions for installing it. You don't need tools, or GUI versions for now, but do make sure that the program is the correct one for your **version** of your operating system.

3. Launch **R**.

The program should open a window - the "R console" - and greet you with its *input prompt*, awaiting your input:

```r
 >
```

The sample code on this page sometimes copies input/output from the console, and sometimes shows the actual commands only. The <code>></code> character at the beginning of the line is always just **R**'s *input prompt*; it is shown here only to illustrate the interactive use of the program and you do not need to type it. If a line starts with <code>[1]</code> or similar, this is **R**'s *output* on the console. A <code>#</code>-character marks the following text as a comment which is not executed by **R**. In principle, commands can be copied by you and pasted into the console, or into a script - obviously, you don't need to copy the comments. In addition, I use syntax highlighting on **R**-code, to colour language keywords, numbers, strings, etc. different from other text. This improves readability but keep in mind that the colours you see on your computer will be different.

Note the following though: it is convenient to copy/paste code, but you don't learn a lot. Practice has shown that it is much better to actually type commands. This ensures you are reading and translating the code character by character, and in computer code, every single character matters. For example, I expect that by typing out commands you will be much less likely to confuse <code>=</code> with <code><-</code> or even <code>==</code>. Also, you will sometimes mistype things and create errors. That's actually good, because you quickly learn to spot errors, fix them, and resume. That way you build confidence.

One more thing about the console: use your keyboard's *up-arrow* keys to retrieve previous commands, then enter the line with *left-arrow* to edit it; hit *enter* to execute the modified line. Or, if you are on a Mac, click the striped icon in the console window to show/hide the command line history.

#### User Interface <a id="interface"></a>

R comes with a GUI to lay out common tasks. For example, there are a number of menu items, many of which are similar to other programs you will have worked with ("File", "Edit", "Format", "Window", "Help"  ...). All of these tasks can also be accessed through the command line. In general, GUIs are useful when you are not  sure what you want to do or how to go about it; the command line is much more powerful when you have more experience and know your way around in principle. **R** gives you both options. 

In addition to the *Console*, there are a number of other windows that you can open (or that open automatically). They all can be brought to the foreground with the **Windows** menu and include help, plotting, package browser, and other windows.

Let's look at some functions of the **R** console and associated windows that refer to **how** you work, not **what** you do.

##### A Note on R Studio <a id="RStudio"></a>

<div class="mw-collapsible mw-collapsed" data-expandtext="Click for more, if you are interested in R Studio..." data-collapsetext="Collapse" style="width:80%; ">
[http://www.rstudio.com/ '''R Studio'''] is a free IDE (Integrated Development Environment) for '''R'''... 
<div class="mw-collapsible-content" style="padding:10px;">
Future workshops will all use '''R Studio''', even though the Mac OS X GUI for '''R''' has almost all the same functionality, and thus there is little advantage in adding a third-party wrapper around the '''R''' program. If you are working in a Linux or Windows environment, '''R Studio''' does offer tangible advantages, notably syntax-aware code coloring. Navigate to the [http://www.rstudio.com/ '''R Studio''' Website] to download and install. Here is a small list of differences. If you can contribute pros and cons from your personal experience, please let me know.

;pros
* A consistent interface across all supported platforms; base '''R''' GUIs are not all the same.
* Syntax aware code coloring.
* Better handling of the '''Stop Execution''' button, which sometimes does not recover a stuck process on the Mac.
* Code autocompletion in the script editor. (Depending on your point of view this can be a plus or a minus.)
* The ability to set breakpoints in the script editor.
* Support for knitr, Sweave, rmarkdown...
* Better support for switching between work on concurrent projects.

;cons
* The ''tiled'' interface uses more desktop space than the windows of the '''R''' GUI.
* There are sometimes (rarely) situations where '''R''' functions do not behave in exactly the same way in '''R Studio'''.
* The supported '''R''' version is not always immediately the most recent release. 

</div>
</div>
</td>
</tr>
</table>

====The Help system====
Help is available for all commands and for the R command line syntax. As well, help is available to find the names of commands when you are not sure of them. 


<small>("help" is a function, arguments to a function are passed in parentheses "()")</small>
<source lang="rsplus">
> help(rnorm)
> 
</source>


<small>(shorthand for the same thing)</small>
<source lang="rsplus">
> ?rnorm
> 
</source>


<small>(what was the name of that again ... ?)</small>
<source lang="rsplus">
> ?binom     
No documentation for 'binom' in specified packages and libraries:
you could try '??binom'
> ??binom
> 
</source>


<small>(found "Binomial" in the list of keywords)</small>
<source lang="rsplus">
> ?Binomial
> 
</source>


If you need help on operators, place them in quotation marks. Try:
<source lang="rsplus">
> ?"+"
> ?"~"
> ?"["
> ?"%in%"
> 
</source>


That's all fine, but you will soon notice that '''R''''s help documentation is not all that helpful for newcomers (who need the most help). Here's what you might look for.
* The '''Description''' section describes the function in general technical terms. 
* The '''Usage''' section tells you what arguments are required (these don't have defaults), what arguments have defaults, and what the defaults are, and whether additional arguments ("...") are allowed. Often a function comes in several variants, you will find them here.
* The '''Arguments''' section provides detailed information . You should read it, especially regarding whether the arguments are single values, vectors, or other objects, and what effect missing arguments will have.
* The '''Details''' section might provide common usage and context information. It might also not. Often functions have crucial information buried in an innocuous note here.
* You have to really understand the '''Value''' section. It explains the output. Importantly, it explains the type of object a function returns - it could be a list, a matrix or something else. The value could also be an object that has special methods defined e.g. for plotting it. In that case, the object is formally a "list", and its named "components" can be retrieved with the usual list syntax (see below).

If you look at the bottom of the help function, you will usually find examples of the function's usage; these often make matters more clear than the terse and principled help-text above. 

What you often won't find:

* Clear commented, examples that relate to the most frequent use cases.
* Explanations '''why''' a particular function is done in a particular way.
* Notes on common errors.
* An exhaustive list of alternatives.

Therefore, my first approach for '''R''' information is usually to Google for what interests me and this is often the quickest way to find working example code. '''R''' has a very large user base and it is becoming very rare that a reasonable question will not have a reasonable answer among the top three hits of a Google search. Also, as a result of a Google search it may turn out that something ''can't'' be done (easily)&ndash;and you won't find things that can't be done in the help system at all. You may want to include {{c|"r language"}} in your search terms, although Google is usually pretty good at figuring out what kind of "r" you are looking for, especially if your query includes a few terms vaguely related to statistics or programming.

* There is an active [https://stat.ethz.ch/mailman/listinfo/r-help '''R-help mailing list'''] to which you can post&ndash;or at least search the archives: your question probably has been asked and answered before. A number of SIGs (Special Interest Groups) exist for more specific discussions - e.g. for mac OS, geography, ecology etc. They are [https://stat.ethz.ch/mailman/listinfo listed here].

* Most of the good responses these days are on ''stack overflow'', discussion seems to be shifting to there from the R mailing list. Information on statistics questions can often be found or obtained from the ''CrossValidated'' forum of stackexchange.
** try this [http://stackoverflow.com/search?q=R+sort+dataframe sample search on ''stackOverflow'']...
** try this [http://stats.stackexchange.com/search?q=R+bootstrapping+jackknifing+cross-validation sample search on ''CrossValidated'']...

* [http://rseek.org '''Rseek'''] is a specialized Google search on '''R'''-related sites. Try "time series analysis" for an example.

* The '''bioconductor''' project has its own [https://support.bioconductor.org/ support site on the Web].



&nbsp;

====Working directory====
To locate a file in a computer, one has to specify the ''filename'' and the directory in which the file is stored; this is sometimes called the ''path'' of the file. The "working directory" for '''R''' is either the direcory in which the '''R'''-program has been installed, or some other directory, as initialized by a startup script. You can execute the command <code>getwd()</code> to list what the "Working Directory" is currently set to:


<source lang="rsplus">
> getwd()
[1] "/Users/steipe/R"
</source>


It is convenient to put all your '''R'''-input and output files into a project specific directory and then define this to be the "Working Directory". Use the {{c|setwd()}} command for this. {{c|setwd()}} requires a parameter in its parentheses: a string with the directory path. Strings in R are delimited with {{c|"}} or <code>'</code> characters. If the directory does not exist, an Error will be reported. Make sure you have created the directory. On Mac and Unix systems, the usual shorthand notation for relative paths can be used: <code>~</code> for the home directory, <code>.</code> for the current directory, <code>..</code> for the parent of the current directory. 

On '''windows''' systems, you need know that backslashes &ndash; "\" &ndash; have a special meaning for '''R''', they work as ''escape characters''. Thus '''R''' gets confused when you put them into string literals, such as Windows path names. '''R''' has a simple solution: simply replace all backslashes with forward slashes, and '''R''' will translate them back when it talks to your operating system. Instead of <code>C:\documents\projectfiles</code> you write <code>C:/documents/projectfiles</code>.<ref>... at least that's how I believe it works. If a Windows user would care to confirm this, I would appreciate it.</ref>


{{console|My home directory...
|> setwd("~") 
> getwd()
[1] "/Users/steipe"
}}

{{console|Relative path: home directory, up one level, then down into chen's home directory)
|> setwd("~/../chen")  
> getwd()
[1] "/Users/chen"
}}

{{console|Absolute path: specify the entire string)
|> setwd("/Users/steipe/abc/R_samples")  
> getwd()
[1] "Users/steipe/abc/R_samples"
}}

{{task|
# Create a directory for your sample files and use {{c|setwd("''your-directory-name''")}} to set the working directory. 
# Confirm that this has worked by typing {{c|getwd()}}. 
}}

The ''Working Directory'' functions can also be accessed through the Menu, under '''Misc'''.

A nice shortcut on the Mac is that you can drag/drop a folder or file icon into the '''R''' console or a script window to get the full filename/path. <small>If you know of equivalent functionality in Linux or Windows, let me know.</small>

====.Rprofile - startup commands====
Often, when working on a project, you would like to start off in your working directory right away when you start up '''R''', instead of typing the <code>setwd()</code> command. This is easily done in a special '''R'''-script that is executed automatically on startup<ref>Actually, the first script to run is '''Rprofile.site''' which is found on Linux and Windows machines in the <code>C:\Program Files\R\R-{version}\etc</code> directory. But not on Macs.</ref>. The name of the script is <code>.Rprofile</code> and '''R''' expects to find it in the user's home directory. You can edit these files with a simple text editor like Textedit (Mac), Notepad (windows) or Gedit (Linux) - or, of course, by opening it in '''R''' itself. 

Besides setting the working directory, other items that might go into such a file could be
* libraries that you often use
* constants that are not automatically defined
* functions that you would like to preload.

=====... unix systems=====
*Navigate to your home directory (<code>cd ~</code>).
*Open a textfile
*Type in: <code>setwd("/path/to/your/project")</code>
*Save the file with a filename of <code>.Rprofile</code>. (Note the dot prefix!)

=====... Mac OS X systems=====
On Macs, filenames that begin with a dot are not normally shown in the Finder. Either you can open a terminal window and use <code>nano</code> to edit, instead of Textedit. Or, you can configure the Finder to show you such so-called "hidden files" by default. To do this:
# Open a terminal window;
# Type: <code>$defaults write com.apple.Finder AppleShowAllFiles YES</code>
# Restart the Finder by accessing '''Force quit''' (under the Apple menu), selecting the Finder and clicking '''Relaunch'''.
# If you ever want to revert this, just do the same thing but set the default to <code>NO</code> instead.

In any case: the procedure is the same as for unix systems. A text editor you can use is <code>nano</code> in a Terminal window.

=====...Windows systems=====
...

====Workspace====
During an '''R''' session, you might define a large number of variables, datastructures, load packages and scripts etc. All of this information is stored in the so-called "Workspace". When you quit '''R''' you have the option to save the Workspace; it will then be reloaded in your next session. 


{{console|List the current workspace contents: initially it is empty. (R reports an object of type "character" with a length of 0.)
|> ls() 
character(0)
>
}}

{{console|Initialize three variables (multiple commands on one line can be separated with a semicolon";")
|> a <- 1; b <-2; eps <- 0.0001
> ls() 
[1] "a"   "b"   "eps"
> 
}}

{{console|Remove one item. (Note: the parameter is not the string "''a''", but the variable name ''a''.)
|> rm(a) 
> ls()
[1] "b"   "eps"
>
}}

<small>We can use the output of {{c|ls()}} as input to {{c|rm()}} to remove everything and clear the Workspace. (cf. {{c|?rm}} for details)</small>
<source lang="rsplus">
rm(list= ls()) 
> ls() 
character(0)
>
</source>


The '''R''' GUI has a ''Workspace Browser'' as a menu item.


&nbsp;

===Packages===

'''R''' has many powerful functions built in, but one of it's greatest features is that it is easily extensible. Extensions have been written by legions of scientists for many years, most commonly in the '''R''' programming language itself, and made available through [http://cran.r-project.org/ '''CRAN'''&ndash;The Comprehensive R Archive Network] or through the [http://www.bioconductor.org '''Bioconductor project''']. 

A package is a collection of code, documentation and (often) sample data. To use packages, you need to install them (once), and add them to your current session (for every new session). You can get an overview of installed and loaded packages by opening the '''Package Manager''' window from the '''Packages & Data''' Menu item. It gives a list of available packages you currently have ''installed'', and identifies those that have been ''loaded'' at startup, or interactively.

{{task|
* Navigate to http://cran.r-project.org/web/packages/ and read the page.
* Navigate to http://cran.r-project.org/web/views/ (the '''curated''' CRAN task-views).
* Follow the link to '''Genetics''' and read the synopsis of available packages. The library {{c|sequinr}} sounds useful, but check first whether it is already installed.
{{console
|{{c|library()}} opens a window of installed packages in the library; {{c|search()}} shows which one are currently loaded.
|> library()
> search()
 [1] ".GlobalEnv"        "tools:RGUI"        "package:stats"     "package:graphics" 
 [5] "package:grDevices" "package:utils"     "package:datasets"  "package:methods"  
 [9] "Autoloads"         "package:base"     
}}


* In the '''R packages available''' window, confirm that  {{c|seqinr}} is not yet installed.
* Follow the link to  {{c|seqinr}} to see what standard information is available with a package. Then follow the link to '''Reference manual''' to access the documentation pdf. This is also sometimes referred to as a "vignette" and contains usage hints and sample code.
{{console
| Read the help for  {{c|vignette}}. Note that there is a command to extract '''R''' sample code from a vignette, to experiment with it.
|> ?vignette
>
}}


<!-- 
{{console
| Install {{c|seqinr}} from the closest CRAN mirror and load it for this session. Explore some functions.
|> ??install
> ?install.packages
> install.packages("seqinr")
--- Please select a CRAN mirror for use in this session ---
trying URL 'http://probability.ca/cran/bin/macosx/contrib/2.13/seqinr_3.0-5.tgz'
Content type 'application/x-gzip' length 4528528 bytes (4.3 Mb)
opened URL
==================================================
downloaded 4.3 Mb


The downloaded packages are in
	/var/folders/dq/dqPEEPbF0ApRU/-Tmp-//RtmpBlw/downloaded_packages
> 
> library(seqinr)
> library(help{{=}}"seqinr")
> ls("package:seqinr")
  [1] "a"                       "aaa"                     "AAstat"                 
  [4] "acnucclose"              "acnucopen"               "al2bp"                  
     [...]
[205] "where.is.this.acc"       "words"                   "words.pos"              
[208] "write.fasta"             "zscore"                 
> ?a
> a("Tyr")
[1] "Y"
> choosebank()
 [1] "genbank"       "embl"          "emblwgs"       "swissprot"     "ensembl"      
    [...]
 [31] "refseqViruses"

}}

-->

}}


* The fact that these methods work, shows that the package has been downloaded, installed, the library has been loaded and its functions and data are now available in the current environment. Just like many other packages, {{c|seqinr}} comes with a number of data files. Try: 

<source lang="rsplus">
?data
data(package="seqinr")   # list the available data
data(aaindex)            # load ''aaindex''
?aaindex                 # what is this?
aaindex$FASG890101       # two of the indices ...
aaindex$PONJ960101

# plot amino acid codes by hydrophobicity and volume
plot(aaindex$FASG890101$I, aaindex$PONJ960101$I, xlab="hydrophobicity", ylab="volume", type="n")
text(aaindex$FASG890101$I, aaindex$PONJ960101$I, labels=a(names(aaindex$FASG890101$I)))

</source>


* Just for fun and demonstration, let's use these functions to download a sequence and calculate some statistics (however, not to digress too far, without further explanation at this point). Copy the code below and paste it into the '''R'''-console

<source lang="rsplus">
choosebank("swissprot")
query("mySeq", "N=MBP1_YEAST")
mbp1 <- getSequence(mySeq)
closebank()
x <- AAstat(mbp1[[1]])
barplot(sort(x$Compo))
</source>
}}

The function {{c|require()}} is similar to {{c|library()}}, but it does not produce an error when it fails because the package has not been installed. It simply returns {{c|TRUE}} if successful or {{c|FALSE}} if not. If the library has already been loaded, it does nothing. Therefore I usually use the following code paradigm in my '''R''' scripts to avoid downloading the package every time I need to run a script:

<source lang="rsplus">
if (!require(seqinr)) {
    install.packages("seqinr")
    library(seqinr)
}
</source>

Note that {{c|install.packages()}} takes a (quoted) string as its argument, but {{c|library()}} takes a name (no quotes). New users usually get this wrong :-)

As is often the case, one of the challenges is to find the right package that contains a particular function you might be looking for. In '''R''' there is a package to help you do that. Try this:
<source lang="rsplus">
if (!require(sos)) {
    install.packages("sos")
    library(sos)
}

findFn("moving average")

</source>

Note that the '''Bioconductor''' project has its own installation system the {{c|bioclite()}} function. It is explained [http://www.bioconductor.org/install/ '''here'''].

===Scripts===

My preferred way of working with '''R''' is not to type commands into the console. '''R''' has an excellent script editor which I use by opening a new file - a script - and entering my '''R''' commands into the editor window. Then I execute the commands directly from the script. I may try things in the console, experiment, change parameters ''etc.'' - but ultimately everything I do goes into the file. This has four major advantages:

* The script is an accurate record of my procedure so I know exactly what I have done;
* I add numerous comments to record what I was thinking when I developed it;
* I can immediately reproduce the entire analysis from start to finish, simply by rerunning the script;
* I can reuse parts easily, thus making new analyses quick to develop.


{{task|
* Use the ''File'' menu to open a ''New Document'' (on Mac) or ''New Script'' (on Windows).
* Enter the following code (copy from here and paste):
<source lang="rsplus">
# sample script:
# define a vector
a <- c(1, 1, 2, 3, 5, 8, 13)
# list its contents
a
# calculate the mean of its values
mean(a)

</source>
* save the file in your working directory (e.g. with the name <code>sample.R</code>).

Placing the cursor in a line and pressing <code>command-return</code> (on the Mac, <code>ctrl-r</code> on Windows) will execute that line and you see the result on the console. You can also select more than one line and execute the selected block with this shortcut. Alternatively, you can run the entire file. In the console type:

<source lang="rsplus">
source("sample.R")
</source>

However: this will not print output to the console. When you run a script, if you want to see text output you need to explicitly <code>print()</code> it.

*Change your script to the following, save it and <code>source()</code> it.
<source lang="rsplus">
# sample script:
# define a vector
a <- c(1, 1, 2, 3, 5, 8, 13)
# list its contents
print(a)
# calculate the mean of its values
print(mean(a))

</source>

* Confirm that the <code>print(a)</code> command also works when you execute the line directly from the script.

}}

Nb. if you want to save your output to file, you can divert it to a file with the <code>sink()</code> command. You can read about the command by typing:

<source lang="rsplus">
?sink
</source>

Some useful shortcuts:
* Typing an opening parenthesis automatically types the closing parenthesis.
* Typing a newline character automatically indents the following line.
* Selecting some text and typing a quotation mark quotes the text. This also works with single quotation marks, parentheses, square brackets and curly braces.









***

##  Day 1 <a id="day_1"></a>

###  Welcome <a id="welcome"></a>

  *<font color="green">Ann Meyer</font>* 
<br>

###  Module 1: Introduction to Computing in the Cloud <a id="module_1"></a>

  *<font color="green">TBA</font>*
  
  Lecture:
  
  Lab practical:

# TEI Prompt

_____

**TEI due**: Friday, February 26th by 11:59 pm <br />
**Percentage**: 10%

_____

## General Overview

Like we talked about in class, we will be starting the process of creating a digital edition of Charlotte Perkins Stetson's “The Yellow Wall-paper” (as an FYI, she's better known as Charlotte Perkins Gilman). This semester, the focus is on the manuscript version of the text. We’ll be using TEI (a set of standardized XML tags) to markup the text. 

In what follows, I attempt to break down all the tags I expect you to use, although your assigned section may or may not require all of the tags listed. There is a chance that you may come across something you think needs a tag that I have not prepared for—please reach out to me or bring it up in class. We want to be as consistent as possible, so the tags below are important. 

We’ll have plenty of class time to go over our XML, both on paper and on the computer, so please don’t worry about coding. It seems scary, but once you get the basic syntax, you’ll feel much more comfortable. I've also simplified everything. I just ask that you come to this assignment with an open mind. No coding experience is required or expected. We’re learning this together!

_____

## Step One: TEI on Paper

We'll be doing this in class. The whole goal is to get you more comfortable with the text you've been assigned (available in the Google Drive). 

The **first** thing we're going to do is annotate the Google Doc.

Traditionally, I'd have you work on a printed copy of the text and you can totally do this too, but because of COVID, I've decided we'll try learning TEI using Google Docs first.

So, we'll add comments to the appropriate Google Doc. These comments will explain the features of the text, rather than trying to code right away. 

The features we'll be encoding are:

* Page beginnings
* Paragraphs 
* Weird spacing
* Em-dashes (they aren't hyphens, they're longer)
* Underlined Words
* Crossed-out words
* Any misspelled words/mistakes in the text (no need to standardize spelling, just note errors)
* Quotes (note that this is only the actual material in quotation marks, not the "he said." Also note that you only want to tag quotes where someone is speaking, not where a single word is in quotes.)
* The Title (only on the first page)
* The byline (only on the last page)

## Step Two: TEI on the Computer

This is where things get a little scarier--but I promise it isn't that bad! 

During class, we will go over how to set up your TEI document in Oxygen. All you have to do is sign up for the 30-day free trial and download the software before class on the day listed in the syllabus. *Please do this.*

_____

## Tags

Page beginning: ```<pb n=“1”/>``` (note that you need to put in the correct page number)

Paragraph tag: ```<p>Paragraph here.</p>```

Weird spacing: ```<space/>```

Em-dash code: ```&#8212;```

Underlined bits: ```<hi rend=“underline”>Text here</hi>```

Crossed-out words: ```<del rend="strikethrough">Text here</del>```

A misspelling/mistake in the text: ```<choice><corr>correct spelling here</corr><sic>original spelling here</sic></choice>``` (note that you don't need to standadize spelling, just correct any errors)

A quote: ```<q>“everything in quotation marks here,”</q> he said, <q>“the rest of the quote.”</q>```

Section breaks: I have searched far and wide for a way to do this to no avail. For this project just put the plus-signs in their own paragraph, so ```<p>+ + + +</p>```

Tag for title (only on the first page): ```<head>Title</head>```

Tag for byline (only on the last page) ```<byline>Charlotte Perkins Stetson.</byline>

_____

## Some things to note:

* You always need a starting and ending tag (unless it’s self-closing). So, even if your assigned passage begins in the middle of a paragraph, surround it with ```<p>``` and ```</p>```.

* You have to close any open tag before you close anything within it. That means tags can’t overlap, so this is **invalid**:

```
<p><hi rend="underline”>Once upon a time . . . </p>
<p>there was a student.</hi></p>
```

This is also **invalid**:

```
<p><hi rend="underline”>Once upon a time . . . </p></hi>
<p><hi rend="underline”>there was a student.</p></hi>
```

Instead, you’d need to do this:

```
<p><hi rend="underline”>Once upon a time . . . </hi></p>
<p><hi rend="underline”>there was a student.</hi></p>
```

Or, as another example, this:

```
<p> Once upon a time, <pb n="2"/> there was a student.</p>

Essentially, the ```<p>``` tag is surrounding everything and no tag can stretch beyond it.

* Everything should be tagged. This doesn’t mean every *word* has a separate tag, but no text should be just floating around.

* We’ll talk about this more in class, but your assigned portion of "The Yellow Wall-paper" is within the ```<text>``` and ```<body>``` tags, **NOT** the ```<teiHeader>```

* We’re going to largely ignore the ```<teiHeader>``` except for the ```<titleStmt>``` and ```<sourceDesc>```. We’ll go over this in class, but it should look like this (in the appropriate places within the ```<fileDesc>```):

```
<titleStmt>
	<title>“The Yellow Wall-paper”</title>
	<author>Charlotte Perkins Stetson</author>
	<editor>Your Name</editor>
</titleStmt>
```
```
<sourceDesc>
	<p>The source text can be found here: http://schlesinger.radcliffe.harvard.edu/onlinecollections/gilman/</p>
</sourceDesc>
```

_____

## Evaluation Criteria

* Uses the appropriate **tags** consistently and correctly

* That green/red box in oXygen? It's green. Meaning, the **code is valid**

* The text you've encoded is **accurate to the manuscript/transcription**

_____

## Late Work

Unless we've talked, I will deduct 10 points for every day the assignment is late. Please don't forget about your blog post due on the same date!

_____

[Back to Syllabus](https://deanna-stover.github.io/coursesCNU/2021/engl350spring2021)

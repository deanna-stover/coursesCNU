# TEI Prompt

_____

**TEI due**: Friday, October 16th by 11:59 pm
**Percentage**: 10%

_____

## General Overview

Like we talked about in class, we will be starting the process of creating a digital edition of Charlotte Perkins Stetson's “The Yellow Wall-paper” (as an FYI, she's better known as Charlotte Perkins Gilman). This semester, the focus is on the periodical version of the text. We’ll be using TEI (a set of standardized XML tags) to markup the text. 

In what follows, I attempt to break down all the tags I expect you to use, although your assigned section may or may not require all of the tags listed. There is a chance that you may come across something you think needs a tag that I have not prepared for—please reach out to me or bring it up in class.

Remember that tagging is not an exact science—it is always interpretive. That said, we want to be as consistent as possible, so the tags below are important. 

We’ll have plenty of class time to go over our XML, both on paper and on the computer, so please don’t worry about coding. It seems scary, but once you get the basic syntax, you’ll feel much more comfortable. I've also simplified everything. I just ask that you come to this assignment with an open mind. No coding experience is required or expected. We’re learning this together!

_____

## Step One/Two: TEI on Paper

We'll be doing this in class on Friday, October 2nd. The whole goal is to get you more comfortable with the text you've been assigned (available in the Google Drive). 

The **first** thing you need to do is to compare the transcription with your section of [the periodical](https://www.nlm.nih.gov/exhibition/theliteratureofprescription/exhibitionAssets/digitalDocs/The-Yellow-Wall-Paper.pdf). I went over everything, but to err is human and I might have made a mistake. You need to make sure your document is as close to the original as possible, meaning we want the same punctuation, spelling, and paragraphing in the transcription. *Please let me know if there is an error in the transcription.*

The **second** thing we're going to do is annotate the Google Doc.

Traditionally, I'd have you work on a printed copy of the text and you can totally do this too, but because of COVID and with people being online and in person, I've decided we'll try learning TEI using Google Docs first.

So, we'll add comments to the appropriate Google Doc. These comments will explain the features of the text, rather than trying to code right away. 

The features we'll be encoding are:

* Page beginnings (so, if you have been assigned a full page or column 1, this is going to be important)
* Column beginnings (this applies to each column, so everyone should have one--maybe two)
* Paragraphs 
* Em-dashes (they aren't hyphens, they're longer)
* Italics
* Any misspelled words/mistakes in the text
* Quotes (note that this is only the actual material in quotation marks, not the "he said." Also, there is one point in the periodical where there is an accidental quotation mark--no need to encode this, but it is a mistake, so take note of it)
* Any illustrations (I've assigned each illustration in the Google Drive)
* The title
* The byline

## Step Three: TEI on the Computer

This is where things get a little scarier--but I promise it isn't that bad! 

On Monday, October 5th we will go over how to set up your TEI document in Oxygen. All you have to do is sign up for the 30-day free trial and download the software before class. *Please do this.*

_____

## Tags

Page beginning: ```<pb n=“647”/>``` (note that you need to put in the correct page number. Also, eventually there will be a facsimile URL added in, but I don’t have that ready so you are not responsible for this)

Column beginning: ```<cb/>```

Paragraph tag: ```<p>Paragraph here.</p>```

Em-dash code: ```&#8212;```

Italics: ```<emph rend=“italic”>Text here</emph>```

A misspelling/mistake in the text: ```<choice><corr>correct spelling here</corr><sic>original spelling here</sic></choice>```

A quote: ```<q>“everything in quotation marks here,”</q> he said, <q>“the rest of the quote.”</q>```

An illustration (note that eventually a <graphic url=“URL”/> tag will go in too—but I don’t have the graphics ready so you are not responsible for this):

```
<figure>
  <p>Caption</p>
  <figureDesc>Alt Text. Actually describe the image here</figureDesc>
</figure>
```

Section breaks: I have searched far and wide for a way to do this to no avail. For this project just put the asterisk in their own paragraph, so ```<p>* * * * * *</p>```

Tag for title: ```<head>Title</head>```

Tag for byline: ```<byline>Byline</byline>```

_____

## Some things to note:

* You always need a starting and ending tag (unless it’s self-closing). So, even if your assigned passage begins in the middle of a paragraph, surround it with ```<p>``` and ```</p>```.

* You have to close any open tag before you close anything within it. That means tags can’t overlap, so this is **invalid**:

```
<p><emph rend=“italics”>Once upon a time . . . </p>
<p>there was a student.</emph></p>
```

This is also **invalid**:

```
<p><emph rend=“italics”>Once upon a time . . . </p></emph>
<p><emph rend=“italics”>there was a student.</p></emph>
```

Instead, you’d need to do this:

```
<p><emph rend=“italics”>Once upon a time . . . </emph></p>
<p><emph rend=“italics”>there was a student.</emph></p>
```

Essentially, the ```<p>``` tag is surrounding everything and no tag can stretch beyond it.

* Everything should be tagged. This doesn’t mean every *word* has a separate tag, but no text should be just floating around.

* We’ll talk about this more in class, but your assigned portion of "The Yellow Wall-paper" is within the ```<text>``` and ```<body>``` tags, **NOT** the ```<teiHeader>```

* 5.	We’re going to largely ignore the ```<teiHeader>``` except for the ```<titleStmt>``` and ```<sourceDesc>```. We’ll go over this in class, but it should look like this (in the appropriate places within the ```<fileDesc>```:

```
<titleStmt>
	<title>“The Yellow Wall-paper”</title>
	<author>Charlotte Perkins Stetson</author>
	<editor>Your Name</editor>
</titleStmt>
```
```
<sourceDesc>
	<bibl>
		<title>“The Yellow Wall-paper”</title>
		<author> Charlotte Perkins Stetson</author>
		<publisher>The New England Magazine</publisher>
		<date>1892</date>
    <note>The source text can be found here: https://www.nlm.nih.gov/exhibition/theliteratureofprescription/exhibitionAssets/digitalDocs/The-Yellow-Wall-Paper.pdf</note>
	</bibl>
</sourceDesc>
```

_____

## Evaluation Criteria

* Uses the appropriate **tags** consistently and correctly

* That green/red box in oXygen? It's green. Meaning, the **code is valid**

* The text you've encoded is **accurate to the periodical**

_____

## Late Work

Unless we've talked, I will deduct 10 points for every day the assignment is late. Please don't forget about your blog post due on the same date!

_____

[Back to Syllabus](https://deanna-stover.github.io/coursesCNU/2020/engl350fall2020)




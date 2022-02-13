# TEI Prompt

_____

**TEI due**: Sunday, February 20th by 11:59 pm <br />
**Percentage**: 5%

_____

## General Overview

As a class, we will be encoding Bram Stoker's "Dracula's Guest."  We’ll be using TEI (Text Encoding Initiative), a set of standardized XML (eXtensible Markup Language) tags, to markup the text. 

In what follows, I attempt to break down all the tags I expect you to use, although your assigned section may or may not require all of the tags listed. There is a chance that you may come across something you think needs a tag that I have not prepared for—please reach out to me or bring it up in class. We want to be as consistent as possible, so the tags below are important. 

We’ll have plenty of class time to go over our XML, both on paper and on the computer, so please don’t worry about coding. It seems scary, but once you get the basic syntax, you’ll feel much more comfortable. I've also simplified everything. I just ask that you come to this assignment with an open mind. No coding experience is required or expected. We’re learning this together!

Please note that although the deadline is on a Sunday, you won't have access to the computers in the DH classroom (and so, the software) after Friday the 18th. So, please do finish up your code by Friday the 18th so that you can just focus on revising the blog portion of this assignment the weekend before the assignment is due. 

_____

## Step One: TEI on Paper

We'll be doing this in class. The whole goal is to get you more comfortable with the passage you've been assigned (available in the Google Drive). 

The **first** thing we're going to do is annotate the Google Doc using comments. These comments will explain the features of the text, rather than trying to code right away. **I do not want you to attempt to use TEI tags in the Google Doc.** Instead, you'll go through your post looking for the features listed below. You'll highlight each feature and leave a comment explaining what it is. For instance, if you see a quote, highlight the quote and leave a comment in the Google Doc that simply says "quote."

This seems simple, but it is meant to help you slow down, really examine your passage, and start noticing the things you'll have to tag later.

The features you should be marking in your Google Doc are:

* Page beginnings
* Paragraphs 
* Em-dashes (they aren't hyphens, they're longer)
* Quotes (note that this is only the actual material in quotation marks, not the "he said" part. Also note that you only want to tag quotes where someone is speaking, not where a single word or phrase--such as a title--is in quotes.)
* Those inscriptions
* That telegram
* Addresses
* Bylines
* Any titles ("Preface," "Dracula's Guest")

The features I've already marked for you are:

* Any misspelled words (we won't be standardizing British spelling, just correcting spelling errors) - if you notice something is misspelled and I haven't left a comment, please bring it up to me
* Any Textual Notes we're adding to the text

## Step Two: TEI on the Computer

This is where things get a little scarier--but I promise it isn't that bad! 

During class, we will go over how to set up your TEI document in Oxygen XML, the software we'll be using. 

Be aware that you will have to email yourself the XML file each day that you work on the project because you might not get the same computer AND I can't guarantee your work will still be there when you come back. So, *email yourself the XML file each time you leave the classroom*.

_____

## Tags

Page beginning: ```<pb n=“1”/>``` (note that you need to put in the correct page number)

Paragraph tag: ```<p>Paragraph here.</p>```

Em-dash code: ```&#8212;```

A misspelling/mistake in the text: ```<choice><corr>correct spelling here</corr><sic>original spelling here</sic></choice>``` (note that you don't need to standardize spelling, just correct any errors)

A quote: ```<q>Everything in quotation marks here,</q> he said, <q>the rest of the quote.</q>``` (note that I've taken out the actual quotation marks)

A note: ```<note>Provided text here</note>```

Section breaks: For this project just put the asterisks in their own paragraph, so ```<p>* * * * * *</p>```

Inscription: ```<p><specDesc key="inscription" />Inscription here.</p>```

Telegram: ```<p><specDesc key="telegram" />Telegram here.</p>```

Address: ```<p><address><addrLine>First line here</addrLine><addrLine>Second line here</addrLine></address></p>```

Section break: ```<div></div>```

Byline: ```<byline>Charlotte Perkins Stetson.</byline>```

Title: ```<head>Title</head>```

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
```

Essentially, the ```<p>``` tag is surrounding everything and no tag can stretch beyond it.

* Everything should be tagged. This doesn’t mean every *word* has a separate tag, but no text should be just floating around.

* We’ll talk about this more in class, but your assigned portion of "Dracula's Guest" is within the ```<text>``` and ```<body>``` tags, **NOT** the ```<teiHeader>```

* We’re going to largely ignore the ```<teiHeader>``` except for the ```<titleStmt>``` and ```<sourceDesc>```. We’ll go over this in class, but it should look like this (in the appropriate places within the ```<fileDesc>```):

```
<titleStmt>
	<title>“Dracula's Guest”</title>
	<author>Bram Stokern</author>
	<editor>Your Name</editor>
</titleStmt>
```
```
<sourceDesc>
  <p>The 1914 edition we're working with can be found here: http://www.bramstoker.org/stories/03guest.html</p>
</sourceDesc>
```
_____

## Resources

We will have time to work on your code in class, but if you aren't able to finish, you can come use the computers in the DH classroom when student workers are there (note that I will not be there to help and they are not trained to use this software).

The student assistants are on-duty during the following times:
* Monday, 6-10 pm
* Tuesday, 6-10 pm
* Wednesday, 4-6 pm
* Thursday, 6-10 pm
* Friday, 3-8 pm

[You can also download a 30-day free trial of Oxygen XML](https://www.oxygenxml.com/xml_editor/register.html?p=editor) onto your own computer so that you don't have to use the classroom computers. 

Finally, to take a screenshot of your Oxygen XML file on the classroom Macs (a required component of your accompanying blog post), go ahead and hit shift, command, and 3 at the same time and then email it to yourself. Remember, you'll want to crop the screenshot to make it look more professional. 

_____

## Evaluation Criteria

* Uses the appropriate **tags**/code consistently and correctly

* That green/red box in oXygen? It's green. Meaning, the **code is valid**

* The text you've encoded is **accurate to the transcription** (note that this includes *an attention to detail*, including spacing)

_____

## Late Work

Unless we've talked, I will deduct 5 points for every day the assignment is late. Please don't forget about your blog post due on the same date!

_____

[Back to Syllabus](https://deanna-stover.github.io/coursesCNU/2022/engl350spring2022)


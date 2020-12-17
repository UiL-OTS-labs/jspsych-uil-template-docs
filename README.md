# jspsych-uil-template-docs
A collection of generic background information on UiL OTS 'templates' (or 'boilerplates', preference for templates here) for [jsPsych](https://www.jspsych.org) experiments (mostly linguistic experimental paradigms) and some additional tools that can be reused. Ideally, any new template links to this overview in its README.md, so that we can keep core documentation in one place.


# Background and Rationale
This is a first start to provide a broader scope to using some in-house developed templates for (time critical reaction time) paradigms and tools needed to make your own online experiment using [jsPsych](https://www.jspsych.org/). The current goals with this repository are:

- Keep documentation on a selection of code bases in _one place_.
- Separate _generic_ documentation from _specific_ documentation.
- Give some _background information_ that may help Students, Researchers & Developers & Managers plan online experimenting better.

Of course, new insights will probably lead to better and probably more complex organisation.

# Context and scope of current developments
The first templates are developed for the liguistics master course [Experimental Design and Data Analysis (EDDA)](https://osiris.uu.nl/osiris_student_uuprd/OnderwijsCatalogusSelect.do?selectie=cursus&cursus=TLRMV16108&collegejaar=2020&taal=nl). Given this context, we've made the templates so that they behave quite similar to the traditional, lab-bound way that was used before, using [ZEP templates](https://www.beexy.nl/zep/wiki/doku.php?id=templates:lexical_decision). However, although JavaScript and ZEP may share some features (like coding syntax, code organisation), they are of course not the same and some concessions have been made. 

At this point, __every__ jspsych template comes with the following 'default' components included: 

### 1. Consent page
A consent page placeholder is included before the experiment starts. It is up to the specifics of your own goals (and organisation) what should be in that file, called `consent_page.html`. A simple look and feel for a consent page (just 'heading' style in this case) is included in that consent page's `<style>` section. In case of Utrecht University, this could better be done by inserting a link to the default UU House style .css files. We'll put up a link for that soon and update. (Todo).

### 2. Survey questions
You can adapt the survey questions to your onw needs, but it is not as easy as it may seem. Please think well about what you want to accept as 'valid' in your survey. Read up about [_input (or data) validation_](https://en.wikipedia.org/wiki/Data_validation). For instance, you may want an e-mail address to be in the form of `someone@somewebsite.com` and not allow people to fill out `whatever` in a survey field. Input validation is importantn for quality research online, think about (your) data management.

### 3. Keyboard procedure (sometimes also audio procedures).
The Lexical Decison Templates use a custom keyboard setting procedure. This is to miltigate potential Reaction Time (RT) (interaction) effects due to hand preference. In templates that use audio, there is also a simple testing procedure in the template.

### 4. Generic UiL utility library
This utility library was created to enable:

- Mobile/Tablet detection (not the type of devices we want participants to use).
- Restrained (or pseudo-) randomisation.

The consquence of including all this, is that these templates contain quite a lot of more (and more complex) code than a basic jsPsych experiment. On the other hand, they automatically contain all components needed for 'professional' online research.   

# Documentation that should minimally be in _every template_ (developer requirements)
Certain information should be in every template. This is a first go at what should be in every repository's README.md (Markdown):
The text within ```< >``` are 'placeholder text', the ones without them should be _'as is'_.
```
# <Template name>
<A human redadable intuitive description related to the template name.>

# Generic documentation
Please read the [generic documentation](https://github.com/UiL-OTS-labs/jspsych-uil-template-docs) for some context and scope.

# Task Description
<Optionally, some scope information about the paradigm or shared organisation, if relevant.>

### Short description
<A short description of what _this specific template_ does and what output is given.>

### Longer Description
<A longer description that reflects on, for instance a paradigm's variations.>

# Getting started
<How to use/start the experiment.>


```

# List of jsPsych-based template repositories 
###### (Developers: keep this list _updated_)

### Visual Lexical Decision Templates
- Visual Lexical Decision basic version: [vislexdec](https://github.com/UiL-OTS-labs/jspsych-vislexdec)
- Visual Lexical Decision with Visual Prime: [vislexdec-vp](https://github.com/UiL-OTS-labs/jspsych-vislexdec-vp)
- Visual Lexical Decision with Visual Masked Prime: [vislexdec-vp-vm](https://github.com/UiL-OTS-labs/jspsych-vislexdec-vp-vm)

### Auditory and/or Visual Lexical Decision Templates
- Auditory Lexical Decison basic version: [audlexdec](https://github.com/UiL-OTS-labs/jspsych-audlexdec)
- Auditory Lexical Decison with Visual Prime: [audlexdec-vp](https://github.com/UiL-OTS-labs/jspsych-audlexdec-vp)
- Auditory Lexical Decison with Visual Masked Prime: [audlexdec-vp-vm](https://github.com/UiL-OTS-labs/jspsych-audlexdec-vp-vm)
- Auditory Lexical Decison with Auditory Prime: [audlexdec-ap](https://github.com/UiL-OTS-labs/jspsych-audlexdec-ap)

### Self-Paced Reading with Moving window Template
- [jspsych-spr-mw](https://github.com/UiL-OTS-labs/jspsych-spr-mw)

## Generic 'UiL' utility library (used in most templates)
A tool that may help with things like restrained randomisation, detecting mobile phone/tablets and other reusable functionality.
- [jspsych-uil-utils](https://github.com/UiL-OTS-labs/jspsych-uil-utils)

## Miscallenous jspsych related repositories

### Documentation on the concessions we have/had to make
- [jspsych-concessions](https://github.com/UiL-OTS-labs/jspsych-concessions)

### Tools to help with csv/json conversions
- [jspsych-boilerplates](https://github.com/UiL-OTS-labs/jspsych-boilerplates)

# Online demo's (using the Experiment Data Store)\*

__Name__                                          | __weblink__                                                  |
--------------------------------------------------|--------------------------------------------------------------|
Visual Lexical Decision                           | https://web-experiments.lab.hum.uu.nl/vislexdec/             |
Visual Lexical Decision w/ Visual Prime           | https://web-experiments.lab.hum.uu.nl/vislexdec-vp/          |
Visual Lexical Decision w/ Visual Masked Prime    | https://web-experiments.lab.hum.uu.nl/vislexdec-vp-vm/       |
Auditory Lexical Decision                         | https://web-experiments.lab.hum.uu.nl/audlexdec/             |
Auditory Lexical Decision w/ Auditory Prime       | https://web-experiments.lab.hum.uu.nl/audlexdec-ap/          |
Auditory Lexical Decision w/ Visual Prime         | https://web-experiments.lab.hum.uu.nl/audlexdec-vp/          |
Auditory Lexical Decision w/ Visual Masked Prime  | https://web-experiments.lab.hum.uu.nl/audlexdec-vp-vm/       |

(\*) These demos may _not reflect the most recent states_ of the Github repositories. Typically, they are not often updated to do so.

# General Overview (draft)

## jsPsych is _not_ a 'programming language'

jsPsych uses a _cominbation_ of a _markup_ language (html), a _styling_ language (css) and JavaScript, this last one _is_ a [programming language](https://developer.mozilla.org/en-US/docs/Web/JavaScript).

How some concepts relate to each other:

### HTML
- HTML is a markup language, not a programming language
- All HTML files have a similar structure
- With the ```<script>somescipt.js</scipt>``` tags, you can use Javascript in HTML

### Javascript
- Javascipt is a (web) _programming language_.
- You can use functions, create custom code with interaction! 
- There is no "official standard" for coding Javascipt, but it is very powerful  

### CSS
- CSS deals with mainly styling, like layouts, fonts, colors, backgrounds.
- CSS evolved from being primarily a styling language, but is also becoming a bit more like a 'programming language', in a way.

### jsPsych
- jspsych _uses_ Javascript code for a specific experimental purpose and the functions from this library need to be imported in the top op your html file before you can use them.
- You _could_ run an experiment in your browser while being offline, if you only refer to local sources that are imported in the relative path.
- If you would need or want to load scripts from an online location in your experiment, you _could_. 
  - But then, do make sure that the locally run code *does* have a working internet connection!

## You will become a 'web developer' 
jsPsych was developed with scientists in mind, not developers. In essence, the jsPsych library tries to let you focus on mainly writing a html file and (re-)use simple JavaScript-style code blocks for trials or trial parts. However, once you get started with jsPsych, you will become a bit of a 'web developer' anyway, in the sense that:

- You will need _tools_ for editing html files, JavaScript code blocks and stylesheets (not Word, Pages, LibreOffice).
- You will need to learn about _debugging_ and the debugging capabilities of (most) web-browsers.
- You will be _confused_ when things 'don't work'.
- You will need to _accept_ that you cannot _control everything_.

### You need _at least_ a _plain text editor_
- Windows users may want to download Notepad++, or try out the free Visual Studio Code IDE (todo)
- Mac users can use TextEdit in plain text mode (preferences) or try out Visual Studio Code, use XCode, Sublime Text, etc.
- (Linux users will usually find their way with this step.)

## 'The lab' vs 'The Web: limitations and opportunities
Traditionally, we've used [ZEP](https://www.beexy.nl/zep/wiki/doku.php) in the UiL OTS labs for time critical experimentation and there are many templates to start with using ZEP. ZEP was designed in house and has been designed to accurately sync sound, visuals/text and/or other hardware (eye tracking, EEG, EMG, etc) in a 'traditional' research lab setup. By that we mean:

- A quite controlled/controllable environment in terms of hardware, software and possible distractions for participants.
- Physically being bound to the lab.
- Relatively small samples, optimised for "Wilhelm Wundt" style traditional research.

The lab-based situation is expected to be limited due to the COVID-19 pandemic, which is why we've started working on web-based alternatives. Some general remarks about this:

- 'The web' cannot offer the accuracy and precision needed for certain paradigms.
- Variations in hardware, software, internet speed, random noise and distraction and many other aspects may cause variations at multiple levels.
- Especially when sounds _and_ images need to be synced, be sure to define means to verify or falsify presentation syncing and test well.

On the other hand:
- The _principles_ of most paradigms can still be taught and learned.
- You could potentially get a lot more data, which may to some extent compensate noise and little control.
- You can find a lot of code snippets and examples online, there is a huge user base for jsPsych and many plugins for certain paradigms can be used or adapted to certain needs.

## General jsPsych info and tutorials
Before you start editing one of these templates, reading up about jsPsych will usually be a good primer. We encourage anyone to get a gist of the 'simple' (but powerful!) way of doing things by following the recommendations given at jsPsych's [site](https://www.jspsych.org/) and to follow the first two tutorials. The basic things like how some `index.html` file imports from the jspsych library, where and how plugins can be used are very relevant to understand. 

## The templates in a 'jsPsych' perspective
As always, the easy things tend to be easy to read (lines of code and examples) and understand, but in order to conduct a full-fledged online experiment, you need to invest a lot more time to make things work. This is why we chose to equip this selection of templates with the aforemetioned 'standard components' (consent, survey, a shared common utilities library). Also, by default, the templates implement stimulus lists with a so-called _'timelineVariable'_ implementation.

The following is true with regard to how these templates have evolved:

- More complex experiment requirements requires more and/or more complex code.
- More code requires better organisation of code.
- Better organisation of code leads to more files to edit in order to adapt a template.

We have aimed to find a balance between template code organisation and following the typical _'jsPsych way of doing things'_.

A 'bare bones' jsPsych experiment can consist of _only one specialised html file_ and a folder with the jsPysch library --or a link to an online version with the jsPsych javascript library given its fixed organisation. With our templates, we usually ship the following files by default:

- An ```index.html``` file which is the 'landing page' for each jsPsych experiment template folder (minimal jsPsych). 
- A ```consent_page.html``` 'placeholder', an external html file for informed consent.
- A ```stimuli.js``` file where you can conmfigure stimulus lists and timelinVariable fields.
- A ```instruction.js``` file where you are tempted to think about specific instructions.
- A ```globals.js``` file where some defaults for relevant variables and 'constants' for the template experiment's index.html are defined.

In some cases, plugins and/or other files can also be found, for instance in the case of the self-paced reading template.

## Modes of using jsPsych (and our templates)
There are multiple ways to test, run and configure jsPsych-based experiments:

- Locally on your (or a participant's) PC, by double clicking the html file.
- Full web server implementation (getting a link to the experiment, served by ICT&Media).

These two modes will likely confuse those who are not web developers, but the bottom line is: 

- A locally developed experiment will not guarantee that the same experiment will run in a server setup, or vice versa. 

Many browsers and versions have their own defaults for security like 'autoplay', allowing sounds, pop-ups and alerts, importing images from local sources, etc. It is impossible to know 100% sure if things will work in your browser in advance, so be prepared to deal with some confusion.

## For 'real' online data collection, you will need a server-based setup.
While you could -- in principle -- use jsPsych in the traditional lab context, it will typically not make a lot of sense. Especially if you want to store your research data for an experiment in one place, a web-server setup is the way to go. Read on to find out how this can be done, if some conditions are met.

# From template to your own online experiment

## Prerequisites and scope limitation
This documentation is primarily aimed at people _affiliated to the UiL OTS labs_ (Utrecht University: RMA Linguistics students and researchers). The infrastructure and support for doing online experiments will be _only availble for those people_. While we are still developing, support is limited to students in the EDDA course only!

Of course, there are many rules and regulations and procedures that need to be followed before conducting an online study. We will _not_ describe the organisational regulations in detail here, but please do keep in mind that, _generally_, the _same steps_ as mentioned on our [lab website](https://uilots-labs.wp.hum.uu.nl/experiments/planning-an-experiment/) need to be followed, even though some details may be different at the detail level.

With the above scope limitations, the bigger picture overview is:

Step                                                          | Comment
--------------------------------------------------------------|---------------------------------------------------
Choose a template to base your experiment on.                 | Think about this well!
Edit the template to your needs and test it _locally_.        | First, focus on the genral flow and look and feel.
Log in to the Experiment data store and _read the docs_.      | [Experiment data store](https://experiment-datastore.acc.lab.hum.uu.nl)
Make your experiment ready for _online_ (web server) usage.   | More info on this will follow in _this_ documentation, too.
Upload your experiment and test again.                        | The data output options are a bit easier to use, focus on output.
Open and share the link to your experiment.                   | Test well before doing this, nobody likes failing online experiments or unusable research data.

The forth and fifth step will generally be alternated iteratively, until all is working well on all aspects: 

- Flow/look and feel, routing, timing, survey & consent.
- Data output and usability. 
- Online specifics for optimising audio presentation, keyboard setting, media and media preloading/.

In short: _everything(!)_ that you consider relevant to solving an actual problem with your experiment.

More detailed descriptions:

# 1. Choosing a template
There are quite some variations for the Lexical Decision Experiments, read the template's specific documentation te make an informed decision.

# 2. How and where to edit templates
Editing templates is largely self-explanatory: stimuli are edited in stimuli.js, global settings in globals.js, and instructions in instructions.js. Some hints can be found in the comments in the files themselves (comments are preceded with two forward slashes //). When changing things, make sure to frequently run the experiment again to make sure it still works (and that you haven't messed up the syntax by accidentally deleting brackets, quotes and such).


## Imports in 'index.html' 
###(Import the jsPsych library, some typically used jsPsych plugins, the jsPsych style sheet and also 'our' custom template libraries & files)

Javascript libraries --among other things-- are imported in the index.html's so-called _head section_ (somewhere in between the ```<head>``` & ```</head>``` tags, you will find import lines that may look like this:

```<script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/jspsych.js"></script>```

In the above case, the import is in fact an example using the custom [Experiment Datastore](https://experiment-datastore.acc.lab.hum.uu.nl) path as can be used with our current server path to the general jsPsych JavaScript library. If you should want to use your own, _relative path_ to a different version of jsPsych, it could look like this, for example:

```<script src="jspsych/6.1.2/jspsych.js"></script>```

Configuring your own local paths to jsPsych's core scripts like in the latter examples is generally discouraged, because it may lead to difficult problems if you are not a web developer and things go wrong. If making an exception to this solves an actual problem, lab support may be able to help you out. For instance, maybe a a newer version of jsPysch would add a crucial new feature that you want to use.


Now, let's just have a look at one of the current templates, the Auditory Lexical Decsion with Visual Prime and what the very start of the file, just until the end of the head section looks like and walk through that step by step:


```
1.  <!DOCTYPE html>
2.  <html>
3.     <head>
4.     <meta charset="UTF-8">
5.    
6.     <title>Auditory Lexical Decision Experiment with Visual Prime</title>
7.
8.     <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/jspsych.js"></script>
9.     <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-html-keyboard-response.js"></script>
10.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-html-button-response.js"></script>
11.    
12.    <!-- Audio playback &response libraries (audio) -->
13.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-audio-button-response.js"></script>
14.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-audio-keyboard-response.js"></script>
15.    
16.    <!-- Generic check/ask libraries (consent, instructions & surveys) -->
17.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-external-html.js"></script>
18.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-instructions.js"></script>
19.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-survey-html-form.js"></script>
20.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-survey-multi-choice.js"></script>
21.    
22.    <!-- Generic jspsych style sheet -->
23.    <link href="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/css/jspsych.css" rel="stylesheet" type="text/css"/>
24.
25.    <!-- Uil OTS libraries -->
26.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/uil-utils/dev/jspsych-uil-utils.js"></script>
27.
28.    <!-- Uil OTS scripts -->
29.    <script src="stimuli.js"></script>
30.    <script src="globals.js"></script>
31.    <script src="instructions.js"></script>
32.    
...   
...    </head>
 ```
 
In order for your experiment to use _only_ jsPsych's core library, the import is on line 8 from the previous example:

```<script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/jspsych.js"></script>```

Additionally, the default 'look and feel' for common jsPsych experiment layouts is bundled in a 'styling' file, a .css file, this is imported on line 22 in the above line-numbered example, if you don't import it, things will not be layouted like jsPsych experiments usually 'work', so it should also always be there when you start with your own experiment: 

```<link href="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/css/jspsych.css" rel="stylesheet" type="text/css"/>```

Let us have a look at some ```<script>```-```</script>``` imports in between lines 8 and 23 and reflect on what they do to make the jsPsych library actually do things like things that typically define (reaction time) experimental linguistics experiments: key-presses, questions, audio fragments and text presentations, amongst others.

On line 9 and 10 we read:

```
9.     <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-html-keyboard-response.js"></script>
10.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-html-button-response.js"></script>
```
These are some of the most basic jspsych interaction _plugins_, the first one deals with a participant keyboard responses, the other one with mouse interactions with clickable buttons, found in most experiments.

The ```jspsych-html-button-response``` button response plugin is generally _always_ recommended as a first 'participant interaction trial', since most browsers don't automatically aloow the playing of sounds or videos with sound without such an interaction element. This type of interaction could also be part of a so-called 'instruction' plugin, so it depends on preference.

From lines 12-14, we may gather:
```
12.    <!-- Audio playback &response libraries (audio) -->
13.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-audio-button-response.js"></script>
14.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-audio-keyboard-response.js"></script>
```

1. (line 12) Certain tags of the lines in "header" code can make it a comment, like ```<!--this is a comment -->```.
2. (line 13) There is a __keyboard-based audio interaction__ jsPsych _plugin_ that is used in this template.
3. (Line 14) There is also a __mouse button-based audio interaction__ jsPsych _plugin_ that is used in this template.

Lines 16-20 deal with other plugins used by our templates, they are usually _all_ included:

```
16.    <!-- Generic check/ask libraries (consent, instructions & surveys) -->
17.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-external-html.js"></script>
18.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-instructions.js"></script>
19.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-survey-html-form.js"></script>
20.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-survey-multi-choice.js"></script>
```

Line 17 imports the `jspsych-external-html` plugin, which is used for the consent page (placeholder html).
Line 18 imports the `jspsych-instructions` plugin, specialised in (multi-page) clickable navigation instructions.
Line 19 imports a html plugin for survey questions.
Line 20 imports a multiple choice plugin, also for survey purposes.

We already mentioned the default css _link_ used by sPsych (line 22). It's not a Javascript library or plugin, but a place where css styling is defined. It's placed _below_ all _standard jsPsych_ plugins, but _before_ our custom template-related scripts. The comments should also make this clear. So we continue with the 'UiL OTS custom template' imports:

```
...
25.    <!-- Uil OTS libraries -->
26.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/uil-utils/dev/jspsych-uil-utils.js"></script>
27.
28.    <!-- Uil OTS scripts -->
29.    <script src="stimuli.js"></script>
30.    <script src="globals.js"></script>
31.    <script src="instructions.js"></script>
32.    
...   
...    </head>
```

Line 26 imports the UiL OTS utility library.
Lines 29-31 import non-jsPsych default files, they import the aforementioned custom template-related javascript files, they are _relative_ imports. In case you would remove thet stimuli.js file from your template experiment folder, this will result in errors (not always very clear for a user). 

## In general: import only what you really need
You may have noticed that a standard template already has quite some lines for standard things. This is mainly because they were designed to be 'complete experiments'. If for instance, you would _not_ want to include any survey questions, it's best to delete the imports related to them, and of course also the parts in the index.html that relate to the survey blocks, read on to find out about the next important section in the index.html file for the templates.

## javaScripy Code blocks, (sub-)trials, trial procedures and other code organisation in an index.html file.
After looking at what is imported in between the `<head>` tags, let's now look at what is in the next important section for using jsPsych: the part where all these files and libraries are actually used to _do_ things in the participants browser. Note, this will not be very in-depth at this point.





# Best practices for jsPsych experiments 

## Audio
In the case of web server setup, it is as good idea to initialise jsPysch with ```use_webaudio = true```, in case you use audio stimuli. This is typically faster than when set to false. This seems to be be redundant now, since we can do such things using ```jspsych-uil-utils```.

## Preload media, like images, video, audio
In general, since timing is important, please make sure to [pre-load all media files](https://www.jspsych.org/overview/media-preloading/). This is because we will typically use trials with a timelineVariables setup. 

## Always start an experiment with a _html-button-response_ interaction part
Browsers will often disallow auto-playing sound/video if there is no user activity related to a _mouse click_. It would be a shame to start of the experiment with errors of this type. An _instruction_ (plugin) with a mouse button response (or a multi-page instuction) will also fix this potential error.



# CSV, JSON and javascript style 

- Lab website on csv links?
- Other links?

## CSV

### Headers, rows and columns

Pro: 
- Everyone knows spreadsheets and a bit of how to use it.

Cons: 
- CSV exports may vary between spreadsheet programs
- There is no fixed standard for quoting and field separators
- Multiline text stimuli with whitespace/layout options is often problematic
- CSV exports are difficult to read at the level of plain text editing

### Examples of some stimulus file setup in CSV table style

#### No quotes:

id | condition | string 
---|-----------|------- 
1  | nonword   | clet
2  | word      | ball
3  | nonword   | hamp

#### Some variable type is quoted, some is not, but it may be needed to do things way:

id | condition | string 
---|-----------|------- 
1  | "nonword" | clet
2  | "word"    | ball
3  | "nonword" | hamp

id | condition | string 
---|-----------|------- 
1  | nonword   | "clet"
2  | word      | "ball"
3  | nonword   | "hamp"

#### This will drive most people crazy, but it might just work

id | condition | string 
---|-----------|------- 
1  | "nonword" | "clet"
2  | word      | "ball"
3  | nonword   | hamp

#### A valid reason to use quotes can be found here
id | condition | string 
---|-----------|------- 
1  | nonwords  | blerg noppa
2  | words     | "it's complicated"
3  | nonwords  | floep quotenot


#### But consistency is often better...
id | condition | string 
---|-----------|------- 
1  | nonwords  | "blerg noppa"
2  | words     | "it's complicated"
3  | nonwords  | "floep quotenot"


### In short

- Layouting, dealing with formatting, line breaks etc is always going to be a drag to some. 
- But with swicthing between excel, plain text, exports etc, CSV, it can be terribly confusing.
- But, if you keep it simple and are aware of things, you can use converters from CSV to formats that we think are better for jsPsych experiments. You can find working examples of Python scripts that may help to convert from .csv tot .json [here](https://github.com/UiL-OTS-labs/jspsych-boilerplates).

# JSON version
```
[
    {
        "id": "1",
        "condition": "nonword",
        "string": "clet"
    },
    {
        "id": "2",
        "condition": "word",
        "string": "ball"
    },
    {
        "id": "3",
        "condition": "nonword",
        "string": "hamp"
    }
]
```

# Current implementation style: stimuli.js (javascript object)
In the first templates we will deliver, we design out stimulus configurations in the javascript key-value pair style. It's not that difficult and has the benefits of being available without using extra code to implement the availablity of test items in an experiment-specific, <i>'dynamic'</i> context. 
```
var stimuli = [
    {
        id: "1",
        condition: "nonword",
        string: "clet"
    },
    {
        id: "2",
        condition: "word",
        string: "ball"
    },
    {
        id: "3",
        condition: "nonword",
        string: "hamp"
    }
]


```
Now, with that, we are already speaking some real javascript!

### Arrays in javascript
```
//This defines an array named myArray
var myArray = ['item', 'another item']; 
```
```
//This is an array, too
var myArrayToo = [
    'item two', 
    'another item two, too'
    ];
 ```
 Note this.
 ```
 //This is an array, too
 var myArrayToo = ['item two', 'another item two, too'];
 ```
 
 or 
 ```
 //This is an array, too
var myArrayToo = [
    "item two", 
    'another item two, too'
    ];
```
# Timelines and trials and designs

There are many [randomization](https://www.jspsych.org/core_library/jspsych-randomization/) batteries included in jsPsych.

Typical folder structure:

```
visdeclex/
         /index.html        <---- Double-click this (index).html file to start)
         /jspsych           <---- It depends on configuration (web server or local)
         /css               <---- Optionally, experiment specific styling code. 
         /stimuli.js        <---- Usually a file called stimuli.js
         /globals.js        <---- Often a file called globals.js
```










  


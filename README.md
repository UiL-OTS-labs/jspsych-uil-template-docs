# jsPsych-uil-template-docs
- This page provides generic background information on UiL OTS 'templates' (or 'boilerplates') for [jsPsych](https://www.jspsych.org) experiments (mostly linguistic experimental paradigms) and some additional tools that can be reused. 
- Ideally, any new template links to this overview in its README.md, so that we can keep core documentation in one place.

# Background and Rationale
This documentation provides information about using some templates that we developed at the UiL OTS labs for (time critical reaction time) paradigms and tools needed to make your own online experiment using [jsPsych](https://www.jspsych.org/). The aims for this repository are:

- Keep documentation on a selection of code bases in _one place_.
- Separate _generic_ documentation from _template-specific_ documentation.
- Give some _background information_ to help Students, Researchers, and Developers plan online experimenting.


## Standard components
At this point, __every__ UiL OTS jsPsych template comes with the following 'default' components included: 

### 1. Consent
A consent page placeholder is included before the experiment starts. It is up to the specifics of your own goals (and organisation) what information should be given. A consent page must always implement a combination of a consent statement, a checkbox that must be checked _and_ a _button_ that needs to be clicked to give consent. See `consent.js` for (placeholder) content.

### 2. Survey questions
You can adapt the survey questions to your own needs, but it is not as easy as it may seem. Please think well about what you want to accept as 'valid' in your survey. Read up about [input (data) validation](https://en.wikipedia.org/wiki/Data_validation). For instance, you may want an e-mail address to be in the form of `someone@somewebsite.com` and not allow people to fill out `whatever` in a survey field. Input validation is important for quality of online research. Also think about data management, and make sure to formulate your survey questions so that they will provide you with answers you can and will actually use (so, be very specific in your questions). See `survey.js`.

### 3. Generic UiL utility library
This [utility library](https://github.com/UiL-OTS-labs/jspsych-uil-utils) was created to enable:

- Mobile/Tablet detection (not the type of devices we want participants to use).
- Restrained (or pseudo-) randomisation.

## Optional and or additional components
Some templates have additional files and folders included, for example:

### 1. Plugins
Sometimes, a custom plugin is used, for instance in the [Self-paced reading](https://github.com/UiL-OTS-labs/jspsych-spr-mw) template. See the folder `plugins` and its contents.
### 2. Keyboard setting/testing procedures
The Lexical Decision Templates use a custom keyboard setting procedure. See `keyboard.js`
### 3. Audio setting/testing procedures
Some templates use _audio_, if they do, there is or will be a simple testing procedure.

# Output (data)
Specific information about the output (data) of each template experiment can be found in its README.md. In addition, there is a general primer describing jsPysch's way of "dealing with data" and some of the UiL OTS template's defaults for data output. Please read that [primer on data output](https://github.com/UiL-OTS-labs/jspsych-output), especially if this is your first time using one of these templates!

In a nutshell a _reminder_ to summarize with regard to experiment data output:
- jsPsych experiments _always returns all_ data for _each type_ of stimulus/trial/trial phase in 'trial' objects, that have _keys_ and _values_.
- Many of _our_ templates add data (subject ID & list ID as _key, value_ pairs) to all the aforementioned objects, so the (sub)trial-data always have this information available for analysis.
- In the case of a trial or trial phase where the output contains relevant (experimental item, Reaction Time, etc), we sometimes add a key "useful_data_flag" with a value 'true' in the experiment; note that this may or may not include "practice trials", so always keep checking your code and your output!
- The above mentioned use of _flags_ can be of use for filtering your data.

# Documentation that should minimally be in _every template_ (developer requirements)
Certain information should be in every template. This is a first go at what should be in every repository's README.md (Markdown):
The text within ```< >``` are 'placeholder text', the ones without them should be _'as is'_.
```markdown
# <Template name>
<A human redadable intuitive description related to the template name.>

# Generic documentation
Please read the [generic documentation](https://github.com/UiL-OTS-labs/jspsych-uil-template-docs) for some context and scope.
UiL-OTS-affiliated students and researchers should follow [this how-to](https://uilots-labs.wp.hum.uu.nl/how-to/online-experimenting/). 

# Paradigm-specific template related documentation
<If there are clearly shared properties of templates (a general paradigm), like in the case of the Lexical Decision Paradigm, they may be referenced here.>

# Task Description
<Optionally, some scope information about the paradigm or shared organisation, if relevant.>

### Short description
<A short description of what _this specific template_ does and what output is given.>

### Longer Description
<A longer description that reflects on, for instance a paradigm's variations.>

# Output (data)
The data of all (sub) trial phases are logged. Please read the [general primer on jsPsych's data output](https://github.com/UiL-OTS-labs/jspsych-output) if you are new to jsPsych data output.

<Specific template output variables and how to adapt your stimuli.js and/or other files regarding data output.>

# Getting started
<How to use/start the experiment.>

```
# Functional code separation in different files (modular structure)
Recent consensus lead to the separation of some of the javascript (jsPsych) code (that is used by the experiments' 'index.html') into separate files. After unzipping a template download, you will often find the following files/folder structure.

```
template_download_main_folder\
                              | plugins/    
                              |        |
                              |         \ someplugin.js          # _Only_ if there is a custom plugin needed, you will find this folder 'plugins'.
                              | consent.js                       # Informed consent related code.
                              | globals.js                       # Global template settings/constants (buttonlabels/html messages, etc.).
                              | index.html                       # The main experiment file, always called 'index.html'. Always there!
                              | instructions.js                  # Instruction-related code.
                              | stimuli.js                       # Stimuli and their designs. Experimental, often Reaction Time (RT) critical!
                              | survey.js                        # Survey tools. 
                             /
```
As a general 'guideline', we design templates in such a way, that the main experiment's file (index.html) remains rather 'minimal'. That is: not too many lines of code in the main experiment's index.html, but bundle shared functionalities in separate files with functional, descriptive names.
                             
# Context and scope of current developments
The first templates were developed for the liguistics RMA course [Experimental Design and Data Analysis (EDDA)](https://osiris.uu.nl/osiris_student_uuprd/OnderwijsCatalogusSelect.do?selectie=cursus&cursus=TLRMV16108&collegejaar=2020&taal=nl). Given this context, we've made the templates so that they behave quite similarly to the  [ZEP templates](https://www.beexy.nl/zep/wiki/doku.php?id=templates:lexical_decision) that are used in the UiL OTS labs for traditional, lab bound research. However, although JavaScript and ZEP may share some features (like coding syntax, code organisation), they are of course not the same.

# List of jsPsych-based template repositories 
###### (Developers: keep this list _updated_)

### Self-Paced Reading with Moving window Template
- Word-by-word self-paced reading, moving window [jspsych-spr-mw](https://github.com/UiL-OTS-labs/jspsych-spr-mw)

### Visual Lexical Decision Templates
- Visual Lexical Decision basic version: [vislexdec](https://github.com/UiL-OTS-labs/jspsych-vislexdec)
- Visual Lexical Decision with Visual Prime: [vislexdec-vp](https://github.com/UiL-OTS-labs/jspsych-vislexdec-vp)
- Visual Lexical Decision with Visual Masked Prime: [vislexdec-vp-vm](https://github.com/UiL-OTS-labs/jspsych-vislexdec-vp-vm)

### Auditory and/or Visual Lexical Decision Templates
- Auditory Lexical Decision basic version: [audlexdec](https://github.com/UiL-OTS-labs/jspsych-audlexdec)
- Auditory Lexical Decision with Visual Prime: [audlexdec-vp](https://github.com/UiL-OTS-labs/jspsych-audlexdec-vp)
- Auditory Lexical Decision with Visual Masked Prime: [audlexdec-vp-vm](https://github.com/UiL-OTS-labs/jspsych-audlexdec-vp-vm)
- Auditory Lexical Decision with Auditory Prime: [audlexdec-ap](https://github.com/UiL-OTS-labs/jspsych-audlexdec-ap)

## Generic 'UiL' utility library (used in most templates)
A tool that may help with things like restrained randomisation, detecting mobile phone/tablets and other reusable functionality.
- [jspsych-uil-utils](https://github.com/UiL-OTS-labs/jspsych-uil-utils)

## Output documentation
As mentioned before, please read the [primer on data output](https://github.com/UiL-OTS-labs/jspsych-output)

## Miscallenous jspsych related repositories

### Documentation on the concessions we have/had to make
- [jspsych-concessions](https://github.com/UiL-OTS-labs/jspsych-concessions)

### Tools to help with csv/json conversions
- [jspsych-boilerplates](https://github.com/UiL-OTS-labs/jspsych-boilerplates)

# General Overview

## jsPsych is _not_ a 'programming language'

jsPsych uses a _cominbation_ of a _markup_ language (html), a _styling_ language (css) and JavaScript, this last one _is_ a [programming language](https://developer.mozilla.org/en-US/docs/Web/JavaScript).

How some concepts relate to each other:

### HTML
- HTML is a [markup language](https://en.wikipedia.org/wiki/Markup_language), not a programming language
- All HTML files have a similar structure
- With the ```<script>somescipt.js</scipt>``` tags, you can use Javascript in HTML

### Javascript
- Javascipt is a (web) _programming language_.
- You can use functions, create custom code with interaction! 
- There is no "official standard" for coding Javascipt, but it is very powerful  

### CSS
- CSS mainly deals with styling, like layouts, fonts, colors, backgrounds.
- CSS evolved from being primarily a styling language, but is also becoming a bit more like a 'programming language', in a way.

### jsPsych
- jspsych _uses_ Javascript code for a specific experimental purpose and the functions from this library need to be imported in the top of your html file before you can use them.
- You _could_ run an experiment in your browser while being offline, if you only refer to local sources that are imported in the relative path.
- If you would need or want to load scripts from an online location in your experiment, you _could_. 
  - But then, do make sure that the locally run code *does* have a working internet connection!

## You will become a 'web developer' 
jsPsych was developed with scientists in mind, not developers. In essence, the jsPsych library tries to let you focus on mainly writing a html file and (re-)use simple JavaScript-style code blocks for trials or trial parts. However, once you get started with jsPsych, you will become a bit of a 'web developer' anyway, in the sense that:

- You will need _tools_ for editing html files, JavaScript code blocks and stylesheets (not Word, Pages, LibreOffice, but a plain text editor).
- You will need to learn about _debugging_ and the debugging capabilities of (most) web-browsers.
- You will be _confused_ when things 'don't work'.
- You will need to _accept_ that you cannot _control everything_.

### You need _at least_ a _plain text editor_
- Windows users may want to download [Notepad++](https://notepad-plus-plus.org/), or try out the free Visual Studio Code IDE (todo)
- Mac users can use TextEdit in plain text mode (preferences) or try out Visual Studio Code, use XCode, Sublime Text, etc.
- (Linux users will usually find their way with this step.)

## 'The lab' vs 'The Web': limitations and opportunities
Traditionally, we've used [ZEP](https://www.beexy.nl/zep/wiki/doku.php) in the UiL OTS labs for time critical experimentation and there are many templates to start with using ZEP. ZEP was designed in house and has been designed to accurately sync sound, visuals/text and/or other hardware (eye tracking, EEG, EMG, etc) in a 'traditional' research lab setup. By that we mean:

- A quite controlled/controllable environment in terms of hardware, software and possible distractions for participants.
- Physically being bound to the lab.
- Relatively small samples, optimised for "Wilhelm Wundt" style traditional research.

The lab-based situation is limited due to the COVID-19 pandemic, which is why we've started working on web-based alternatives. Some general remarks about this:

- 'The web' cannot offer the accuracy and precision needed for certain paradigms.
- Variations in hardware, software, internet speed, random noise and distractions and many other aspects may cause variations at multiple levels.
- Especially when sounds _and_ images need to be synced, be sure to define means to verify or falsify presentation syncing and test well.

On the other hand:

- The _principles_ of most paradigms can still be taught and learned.
- You could potentially get a lot more data, which may to some extent compensate noise and little control.
- You can find a lot of code snippets and examples online, there is a huge user base for jsPsych and many plugins for certain paradigms can be used or adapted to certain needs.

## General jsPsych info and tutorials
Before you start editing one of these templates, reading up about jsPsych will usually be a good primer. We encourage anyone to get a gist of the 'simple' (but powerful!) way of doing things by following the recommendations given at jsPsych's [site](https://www.jspsych.org/) and to follow the first two tutorials. The basic things like how some `index.html` file imports from the jspsych library, where and how plugins can be used are very relevant to understand. 

## The templates in a 'jsPsych' perspective
As always, the easy things tend to be easy to read (lines of code and examples) and understand, but in order to conduct a full-fledged online experiment, you need to invest a lot more time to make things work. This is why we chose to equip this selection of templates with the aforemetioned 'standard components' (consent, survey, a shared common utilities library). Also, by default, the templates implement stimulus lists with a so-called _'timelineVariable'_ implementation.

## Modes of using jsPsych (and the templates)
There are multiple ways to test, run and configure jsPsych-based experiments:

- Locally on your (or a participant's) PC, by double-clicking the `index.html` file.
- Full web server implementation (getting a link to the experiment, served by ICT&Media).

These two modes will likely confuse those who are not web developers, but the bottom line is: 

- A locally developed experiment will _not guarantee that the same experiment will run in a server setup__, or vice versa! 

Many browsers and versions have their own defaults for security like 'autoplay', allowing sounds, pop-ups and alerts, importing images from local sources, etc. It is impossible to know 100% sure if things will work in your browser in advance, so be prepared to deal with some confusion.

## For 'real' online data collection, you will need a server-based setup
While you could -- in principle -- use jsPsych offline in the traditional lab context, it will typically not make a lot of sense. Especially if you want to store your research data for an experiment in one place, a web-server setup is the way to go. 

# From template to your own online experiment

## Prerequisites and scope limitation
This documentation is primarily aimed at people _affiliated with the UiL OTS labs_ (Utrecht University: Linguistics students and researchers). The infrastructure and support for doing online experiments will be _only availble for those people_. While we are still developing, support is limited to students in the EDDA course only!

- People _affiliated with our lab__ can use the information [from our lab webiste](https://uilots-labs.wp.hum.uu.nl/experiments/overview/) and expand the "Online experiments using jsPsych" section for details. Please [follow this how-to](https://uilots-labs.wp.hum.uu.nl/how-to/online-experimenting/). 

- People _not affiliated with our lab_ can of course use the templates, but will have to do without (support for, access to) the UiL OTS Experiment Datastore (link, CODEBASE? TODO).

With the above scope limitations, the bigger picture overview is:

step | Description                                                          | Comment
-----|----------------------------------------------------------------------|----------------------------------------------------------------------------
1    | Choose a template to base your experiment on.                        | Read the template docs.
2    | Edit the template to your needs and test it _locally_.               | First, focus on the general flow and look and feel.
3    | Log in to the Experiment data store and _read the docs_.             | [Experiment data store](https://experiment-datastore.acc.lab.hum.uu.nl)
4    | Make your experiment ready for _online_ (web server) usage.          | More info on this will follow in _this_ documentation, too.
5    | Upload your experiment, 'open' it and test again.                               | 'Opening' the experiment allows it to write data to the data server. The data output options there are a bit easier to use, focus on data output is advised in this step.
6    | Share the link to your experiment.                        | Test very well before doing this (nobody likes failing online experiments or unusable research data)!

Step 4 and 5 will generally be alternated iteratively, until all is working well on _all_ aspects: 

- Flow/look and feel, routing, timing, survey & consent.
- Data output and usability. 
- Online specifics for optimising audio presentation, keyboard setting, media and media preloading.

In short: _everything(!)_ that you consider relevant to solving an actual problem with your experiment.

Detailed descriptions:

# 1. Choosing a template
There are quite a few variations for the Lexical Decision Experiments, read the template's specific documentation `README.md` to make an informed decision.

# 2. How and where to edit templates
Editing templates is largely self-explanatory: stimuli are edited in `stimuli.js`, global settings in `globals.js`, and instructions in `instructions.js`. Some hints can be found in the comments in the files themselves (comments are preceded with two forward slashes `//`). When changing things, make sure to frequently run the experiment again to make sure it still works (and that you haven't messed up the syntax by accidentally deleting brackets, quotes and such). 

_Some_ more details about this follow below.

## 2.1 Imports in the head section 'index.html' 
#### Imports the jsPsych library, some typically used jsPsych plugins, the jsPsych style sheet and also 'our' custom template libraries & files.

Javascript libraries --among other things-- are imported in the index.html's so-called _head section_. Somewhere in between the ```<head>``` & ```</head>``` tags, you will find import lines that may look like this:

```html
<script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/jspsych.js"></script>
```

In the above case, the import is in fact an example using the custom [Experiment Datastore](https://experiment-datastore.acc.lab.hum.uu.nl) path as can be used with our current server path to the general jsPsych JavaScript library. If you should want to use your own, _relative path_ to a different version of jsPsych, it could look like this, for example:

```html
<script src="jspsych/6.1.2/jspsych.js"></script>
```

Configuring your own local paths to jsPsych's core scripts like in the latter examples is generally discouraged, because it may lead to difficult problems if you are not a web developer and things go wrong. If making an exception to this solves an actual problem, lab support may be able to help you out. For instance, maybe a newer version of jsPysch would add a crucial new feature that you want to use.

#### A typical _head section_ import structure
Let's have a look at one of the current templates, the Auditory Lexical Decsion with Visual Prime and what the very start of that file (just until the end of the head section) looks like and walk through that step by step:

```html
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

```html
<script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/jspsych.js"></script>
```

Additionally, the default 'look and feel' for common jsPsych experiment layouts is bundled in a 'styling' file, a .css file. This file is imported on line 22 in the above line-numbered example. If you don't import it, things will not be layouted like jsPsych experiments usually 'work', so it should also always be there when you start with your own experiment: 

```html
<link href="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/css/jspsych.css" rel="stylesheet" type="text/css"/>
```

Let us have a look at some ```<script>```-```</script>``` imports in between lines 8 and 23 and reflect on what they do to make the jsPsych library actually do things like things that typically define (reaction time) experimental linguistics experiments: key-presses, questions, audio fragments and text presentations, amongst others.

On line 9 and 10 we read:

```html
9.     <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-html-keyboard-response.js"></script>
10.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-html-button-response.js"></script>
```
These are some of the most basic jspsych interaction _plugins_. The first one deals with a participant keyboard responses, the other one with mouse interactions with clickable buttons, found in most experiments.

The ```jspsych-html-button-response``` button response plugin is generally _always_ recommended as a first 'participant interaction trial', since most browsers don't automatically allow the playing of sounds or videos with sound without such an interaction element at the start of your experiment. This type of interaction could also be part of a so-called 'instruction' plugin, so it depends on preference.

From lines 12-14, we may gather:
```html
12.    <!-- Audio playback &response libraries (audio) -->
13.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-audio-button-response.js"></script>
14.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-audio-keyboard-response.js"></script>
```

1. (line 12) Certain tags of the lines in "header" code can make it a comment, like ```<!--this is a comment -->```.
2. (line 13) There is a __keyboard-based audio interaction__ jsPsych _plugin_ that is used in this template.
3. (Line 14) There is also a __mouse button-based audio interaction__ jsPsych _plugin_ that is used in this template.

Lines 16-20 deal with other plugins used by our templates, they are usually _all_ included:

```html
16.    <!-- Generic check/ask libraries (consent, instructions & surveys) -->
17.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-external-html.js"></script>
18.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-instructions.js"></script>
19.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-survey-html-form.js"></script>
20.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-survey-multi-choice.js"></script>
```

- Line 17 imports the `jspsych-external-html` plugin, which is used for the consent page (placeholder html).
- Line 18 imports the `jspsych-instructions` plugin, specialised in (multi-page) clickable navigation instructions.
- Line 19 imports a html plugin for survey questions.
- Line 20 imports a multiple choice plugin, also for survey purposes.

We already mentioned the default css _link_ used by jsPsych (line 22). It's not a Javascript library or plugin, but a place where styling is defined. It's placed _below_ all _standard jsPsych_ plugins, but _before_ our custom template-related scripts. The comments should also make this clear. So, we continue with the 'UiL OTS custom template' imports:

```html
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
Lines 29-31 import 'non-jsPsych' _default_ files, they import the aforementioned custom template-related javascript files. These _are_ __relative__ imports. To clarify: in case you would remove the stimuli.js file from your template experiment folder, this would result in errors if you do not also remove the import statement. 

#### In _general_: import only what you really need
You may have noticed that a standard template already has quite a few lines for standard things. This is mainly because they were designed to be 'complete experiments'. If for instance, if you would _not_ want to include any survey questions, it's best to delete the imports related to them, and of course also the parts in the index.html that relate to the survey blocks. Read on to find out about the next important section of an index.html experiment file.

## 2.2 The _script section_ of 'index.html'
#### javaScript code blocks, (sub-)trial definitions, trial procedures and other code organisation in an index.html file
After looking at what is imported in between the `<head>` tags, let's now look at what is in the next important section for using jsPsych: the part where all these files and libraries are actually used to _do_ things in the participants browser. Note, this will not be very in-depth at this point.

Global structure of the script section:

section/block | Description
--------------|-------------------------------------------------------------------------------------------------------
A             | Stimuli loading, using stimuli.js function(s), media preloading routines.
B             | Experiment logic_ variables (don't touch these, usually).
C             | Custom (template-related) Javascript _functions_ (if necessary, like with the keyboard setting procedure).
D             | Data preparation: _jsPsych-specific_ way of defining data that should be added to all trials.
E             | Trials and trial elements:_jsPsych-specific_ definition for trials/trial phases and other functional block definitions (instructions, survey blocks, consent page).
F             | Procedures: _jsPsych-specific_ _procedures_ typically use a combination of parts as defined in block E.
G             | The timeline, where the experiment's building blocks are added to form your experiment flow.
H             | The _init_-block: with this part, the experiment starts -for real- by 'executing the timeline'.

# 3. The experiment data store
Most information should be availble once you have logged in to the [Experiment Data Store](https://experiment-datastore.acc.lab.hum.uu.nl). 

# 4. Making the experiment ready for online testing
Most generally, once you have requested/defined your experiment folder, you have to copy the _Access key_ for your experiment to be the new value for the ACCESS_KEY constant in _your version_ of the `globals.js` file. So, say you have been given the code `N278123456-%^&&8888*(*7777--090900!#$%1234`, implement it like this:
```javascript
// ACCESS_KEY needs to be used for server setup (data store)
const ACCESS_KEY = 'zeeekretkeey'; 
```
And change it to:

```javascript
// ACCESS_KEY needs to be used for server setup (data store)
const ACCESS_KEY = 'N278123456-%^&&8888*(*7777--090900!#$%1234'; 
```
Note the _quotes_!

# 5. Sharing your experiment
Running your experiment _locally_ on your own PC will usually _also_ still work after editing that value the `globals.js` file, but of course, the data is not saved like on the server, you will just get a bunch of output in your browser window. Please do make sure to keep track of your edits. Once you are sure everything works, you can invite your participants!

# General best practices for jsPsych experiments 

## Audio
In the case of web server setup, it is as good idea to initialise jsPysch with ```use_webaudio = true```, in case you use audio stimuli. This is typically faster than when set to false. This seems to be be redundant now, since we can do such things using ```jspsych-uil-utils```.

## Preload media, like images, video, audio
In general, since timing is important, please make sure to [pre-load all media files](https://www.jspsych.org/overview/media-preloading/). This is because we will typically use trials with a timelineVariables setup. In the auditory lexical decision templates, you will find pre-loading routines for the audio files used in those.

## Always start an experiment with a _html-button-response_ interaction part
Browsers will often disallow auto-playing sound/video if there is no user activity related to a _mouse click_. It would be a shame to start of the experiment with errors of this type. An _instruction_ (plugin) with a mouse button response (or a multi-page instuction) will also fix this potential error.

# Pseudo-random vs true random

You can find a trial procedure using a custom function from the 'uil-utils' library. A default restriction for pseudorandomisation is configured in the templates as a constant in each ```globals.js``` file, with the string ```const MAX_SUCCEEDING_ITEMS_OF_TYPE = 2```. 

The big caveat for pseudorandomisation, especially with the current small number of items in templates (only _two_ items in the practice items): the utility function _tries_ to shuffle your items given this 'max 2-succeeding items restriction' for X (say, 10) times when your index.html initialises the experiment. If it (the function) fails to do so, --in this case, because you have too few items to make it happen-- your experiment will _not_ start (because of this underlying error, not visible in the browser).

In the lexical decision templates index.html file, find the sections in the timeline part (block G, pretty down below) where you can either use 'real' randomisation or pseudorandomisation given the criterion configured in ```globals.js```. Example taken from [vislexdec-vp](https://github.com/UiL-OTS-labs/jspsych-vislexdec-vp):

```javascript

        //////////////// timeline /////////////////////////////////

        let timeline = [];

        // it's best practice to have *mouse click* user I/O first
        timeline.push(start_screen);
        
        // survey
        timeline.push(survey_procedure);
        
        // kb layout
        timeline.push(select_keyboard_layout);
        
        // kb important keys
        timeline.push(keyboard_set_key_left_procedure);
        timeline.push(keyboard_set_key_right_procedure);
        
        // task instruction
        timeline.push(instruction_screen_practice);

        // a keyboard dominant hand configured key continue/prepare flow
        timeline.push(participant_keyboard_control_start);
        
        timeline.push(practice_procedure);
        timeline.push(well_done_screen);

        // "get ready"
        timeline.push(participant_keyboard_control_start);

        // NOTE options below! comment/uncomment for regular vs restrained randomization
        // true randomness is better for the current template's amount of items...

        timeline.push(trial_procedure_pseudorandom); // don't do this with little stimuli
        //timeline.push(trial_procedure_random);
        
        timeline.push(end_screen);
 ```
 Below the ```//NOTE options below! (...)``` comment, a trial procedure is called that uses _trial_procedure_pseudorandom_. Commented out below that one, you find a different one, called _trial_procedure_random_. To go for 'real random', comment out ```timeline.push(trial_procedure_pseudorandom);``` (change to ```//timeline.push(trial_procedure_pseudorandom);```and uncomment the other one below (change ```//timeline.push(trial_procedure_random);``` to ```timeline.push(trial_procedure_random);```.
 
 The definitions of the procedures are --in this example-- only slightly above section G:
```javascript

         let trial_procedure_pseudorandom = {
            timeline:[
                present_fixation,
                present_prime,
                present_word,
            ],
            timeline_variables: uil.randomization.randomizeStimuli(
                stimuli.table,
                MAX_SUCCEEDING_ITEMS_OF_TYPE,
                'item_type',
            ),
            randomize_order: false // this should be false if uil randomization is used...
        };

        let trial_procedure_random = {
            timeline:[
                present_fixation,
                present_prime,
                present_word,
            ],
            timeline_variables: stimuli.table,
            randomize_order: true // this should be true if you want jsPsych's randomization
        };
```




  


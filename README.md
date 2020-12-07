# jspsych-uil-template-docs
A collection of generic background information on UiL OTS 'templates' (or 'boilerplates', preference for templates here) for [jsPsych](https://www.jspsych.org) experiments (mostly linguistic experimental paradigms) and some additional tools that can be reused. Ideally, any new template links to this overview in its README.md, so that we can keep core documentation in one place.


# Background and Rationale
This is a first start to provide a broader scope to using some in-house developed templates for (time critical reaction time) paradigms and tools needed to make your own experiment. The current goals are:

- Keep documentation on a selection of code bases in _one place_.
- Separate _generic_ documentation from _specific_ documentation.
- Give some _background information_ that may help Students, Researchers & Developers & Managers plan better.

Of course, new insights will probably lead to better and probably more complex organisation.

# Context and scope of current developments
The first templates are developed for the liguistics master course [Experimental Design and Data Analysis (EDDA)](https://osiris.uu.nl/osiris_student_uuprd/OnderwijsCatalogusSelect.do?selectie=cursus&cursus=TLRMV16108&collegejaar=2020&taal=nl). Given this context, we've made the templates so that they behave quite similar to the traditional, lab-bound way that was used before, using [ZEP templates](https://www.beexy.nl/zep/wiki/doku.php?id=templates:lexical_decision). However, although JavaScript and ZEP may share some features (like coding syntax, code organisation), they are of course not the same and some concessions have been made that may be changed over time. Just a few of them are worth mentioning at this point:

- Every Lexical Decision template has a simple _questionnaire_ (or survey) included. This makes the code less 'clean', but for the education context it is now considered as necessary.
- The Lexical Decision Templates currently have a routine to set _keyboard response keys_ interactively (based upon survey/questionnaire input). This makes the code more complex, but it was deemed necessary to miltigate potential Reaction Time (RT) interaction effects due to hand preference.
- Every template currently imports a _utility library_ we've created to enable, for instance, Mobile/Tablet detection (not the type of devices we want participants to use), but also _restrained (or pseudo-) randomisation_. This utility library also makes the template code more complex and may obfuscate certain types of errors.

In short: eventually, it's a delicate balance between wanting 'lean and clean' templates, versus ones that are good enough to use for the EDDA course purposes. In time, we will probably figure out a more modular approach and optimize for both aspects.

# How and where to edit templates
The general rationale for using templates, has always been to enable students/researchers without a background in programming to get started with a certain paradigm without having to do a lot of coding, but by just editing the so called 'stimulus file' and possibly some other files with globals for item types. The extent to which we can currently offer a jspsych, web based alternative within those requirements is debatable. Hopefully, this year's EDDA course can --to some extent-- serve as a test case for how easy or difficult this is, compared to ZEP. Ideally, there would be requirements to test this, but at this point, they are not very explicit.

# How to debug and edit templates
A similar question arises related to the above problem. Web-based debugging requires quite a different approach from 'local' debugging, and many students/laymen are probably unaware of how debugging in a browser works. At which level and to what extend we will need to document and help students and researchers be independent?  

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

# Data store
<How to use an experiment in our specific html-server setup and data store application.>

```

# List of jspsych based template repositories

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

# Generic jspsych utility repository (used in most templates)
A tool that may help with things like restrained randomisation, detecting mobile phone/tablets and other reusable functionality.
- [jspsych-uil-utils](https://github.com/UiL-OTS-labs/jspsych-uil-utils)

# Miscallenous jspsych related repositories (to sift through)
Some documentation on the concessions we have/had to make related to using the world wide web instead of the lab. 
- [jspsych-concessions](https://github.com/UiL-OTS-labs/jspsych-concessions)

This contains some (python) tools to enable csv/json conversions.
- [jspsych-boilerplates](https://github.com/UiL-OTS-labs/jspsych-boilerplates)

Some simple survey examples
https://github.com/jcvanelst/jspsych-survey-tests

# Current test cases as available on experiment data store (served by ICT&Media)

__Name__                                          | __weblink__                                                  |
--------------------------------------------------|--------------------------------------------------------------|
Visual Lexical Decision                           | https://web-experiments.lab.hum.uu.nl/vislexdec/             |
Visual Lexical Decision w/ Visual Prime           | https://web-experiments.lab.hum.uu.nl/vislexdec-vp/          |
Visual Lexical Decision w/ Visual Masked Prime    | https://web-experiments.lab.hum.uu.nl/vislexdec-vp-vm/       |
Auditory Lexical Decision                         | https://web-experiments.lab.hum.uu.nl/audlexdec/             |
Auditory Lexical Decision w/ Auditory Prime       | https://web-experiments.lab.hum.uu.nl/audlexdec-ap/          |
Auditory Lexical Decision w/ Visual Prime         | https://web-experiments.lab.hum.uu.nl/audlexdec-vp/          |
Auditory Lexical Decision w/ Visual Masked Prime  | https://web-experiments.lab.hum.uu.nl/audlexdec-vp-vm/       |

# What libraries always need to be imported in a jsPscyh-based experiment's index.html 
Javascript libraries --among other things-- are imported in the index.html's so-called _head section_ (somewhere in between the ```<head>``` & ```</head>``` tags, you will find import lines that may look like this:

```<script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/jspsych.js"></script>```

In the above case, the import is in fact an example using the custom [Datastore](TODO: <New ICT&Media name/refs/link>) path as can be used with our current server path to the general jsPsych JavaScript library. If you should want to use your own, _relative path_ to a different version of jsPsych, it could look like this, for example:

```<script src="jspsych/6.1.2/jspsych.js"></script>```
or 

```<script src="./myjspsychCustomFolderName/6.1.2/jspsych.js"></script>```

Configuring your own local paths to jsPsych's core scripts like in the latter examples is generally discouraged, because it may lead to difficult problems if you are not a web developer and things go wrong. If making an exception to this solves an actual problem, lab support may be able to help you out. For instance, maybe a a newer version of jsPysch would add a crucial new feature that you want to use.

In fact, let's just have a look at one of the current templates, the Auditory Lexical Decsion with Visual Prime and what the very start of the file, just until the end of the head section looks like and walk through that step by step:


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
16.    <!-- Generic check/ask libraries (instructions & surveys) -->
17.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-instructions.js"></script>
18.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-survey-html-form.js"></script>
19.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/plugins/jspsych-survey-multi-choice.js"></script>
20.    
21.    <!-- Generic jspsych style sheet -->
22.    <link href="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/css/jspsych.css" rel="stylesheet" type="text/css"/>
23.
24.    <!-- Uil OTS libraries -->
25.    <script src="https://web-experiments.lab.hum.uu.nl/jspsych/uil-utils/dev/jspsych-uil-utils.js"></script>
26.
27.    <!-- Uil OTS scripts -->
28.    <script src="stimuli.js"></script>
29.    <script src="globals.js"></script>
30.    <script src="instructions.js"></script>
31.    
...   
...    </head>
 ```
 
In order for your experiment to use _only_ jsPsych's core library, the import is on line 8 from the previous example:

```<script src="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/jspsych.js"></script>```

Additionally, the default 'look and feel' for common jsPsych experiment layouts is bundled in a 'styling' file, a .css file, this is imported on line 22 in the above line-numbered example, if you don't import it, things will not be layouted like experiments usually 'work', so it should also always be there when you start with your own experiment: 

```<link href="https://web-experiments.lab.hum.uu.nl/jspsych/6.1.0/css/jspsych.css" rel="stylesheet" type="text/css"/>```

Let us have a look at some ```<script>```-```</script>``` imports in between lines 8 and 22 and reflect on what they do to make the jsPsych library actually do things like things that typically define (reaction time) experimental linguistics experiments: key-presses, questions, audio fragments and text presentations, amongst others.

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


# Generic overview (draft)
Lab support and teachers are in the process of creating template/boilerplate experiments for you to easily set up certain types of experiments. The idea behind this, is that within certain boundaries, it should be easy to get an experiment running without (too much) programming skills, by just editing the default stimulus files. Traditionally, we've used [ZEP](https://www.beexy.nl/zep/wiki/doku.php) in the UiL OTS labs for time critical experimentation and there are many templates to start with using ZEP. ZEP was designed in house and has been designed to accurately sync sound, visuals/text and/or other hardware (eye tracking, EEG, EMG, etc) in a 'traditional' research lab setup. By that we mean:

- A quite controlled/controllable environment in terms of hardware, software, possible distractions.
- Physically being bound to the lab.
- Relatively small samples, optimised for "Wilhelm Wundt" style traditional research.

This type of training is probably going to be problematic for a while, due to COVID-19. So after a period of research & development, we've decided to choose the custom Javascipt library aimed at experimental research using a browser, called [jsPsych](https://jspsych.org) as our alternative for lab-based work. A couple of remarks here:

- 'The web' cannot offer the accuracy and precision needed for certain paradigms.
- Variations in hardware, software, internet speed, random noise and distraction and many other aspects may cause variations at multiple levels.
- Especially when sounds _and_ images need to be synced, be sure to define means to verify or falsify presentation syncing and test well.

On the other hand:
- The _principles_ of most paradigms can still be taught and learned.
- You could potentially get a lot more data, which may to some extent compensate noise and little control.
- You can find a lot of code snippets and examples online, there is a huge user base for jsPsych and many plugins for certain paradigms can be used or adapted to certain needs.

# Mini-overview of a jsPsych experiment
It's a good idea to really read the documentation on https://www.jspsych.org. The basic things like how some 'index.html' file imports from the jspsych library, where and how plugins can be used are good to start with.

It gets a bit more complicated when you discover that there are two modes in which all can be run:

- Locally on your PC, by double clicking the html file.
- Full web server implementation (getting a link to the experiment, served by ICT&Media).

These two modes will likely confuse those who are not web developers, but the bottom line is: 

- A locally developed experiment will not guarantee that the same experiment will run in a server setup, or vice versa. 

Many browsers and versions have their own defaults for security like autoplay, allowing sounds, pop-ups, importing images from local sources, etc. It is impossible to know 100% sure if things will work in your browser in advance, so be prepared to deal with some confusion.

In this stage, we will limit things to running the templates __locally__, which has implications for the reliability and format of the data. Also: locally does __not__ mean that it can be run without an internet connection in most cases, due to the nature of loading external scripts. Browsers really are optimised for being online.

# Some best practices for jsPsych experiments 

## Audio
In the case of web server setup, it is as good idea to initialise jsPysch with ```use_webaudio = true```, in case you use audio stimuli. This is typically faster than when set to false. This seems to be be redundant now, since we can do such things using ```jspsych-uil-utils```.

## Preload media, like images, video, audio
In general, since timing is important, please make sure to [pre-load all media files](https://www.jspsych.org/overview/media-preloading/). This is because, we will typically use trials with a timelineVariables setup. 

## Generic checks 
Some generic instruction and test flows (like audio tests) will also be prepared in this specific boilerplate. This may seem an odd choice, since the current boilerplate task does not require audio. The reason to define some generic tests and checks here, is to make the process of making some other boilerplates a bit easier to branch off from the same documentation and reuse generic functionality. Things we have in mind to check all the time:

- Check if the participant is using a tablet or phone. (not intended for 'mobile devices')
- A generic survey asking about dominant hand, age, 'gender-related', etc. (not at this point?)
- Keyboard layout and user-optimised response keys

## Optional checks
- Check if the audio works (and system sound loudness setting flows).

## Always start an experiment with a html-button-response interaction part
Browsers will often disallow auto-playing sound/video if there is no user activity related to a _mouse click_. It would be a shame to start of the experiment with errors of this type. An _instruction_ (plugin) with a mouse button response (or a multi-page instuction) will also fix this potential error.

# HTML, CSS, Javascipt, jsPscyh, jsPsych default plugins

How some concepts relate to each other:

## HTML
- HTML is a markup language, not a programming language
- All HTML files have a similar structure
- With the ```<script>somescipt.js</scipt>``` tags, you can use Javascript in HTML

## Javascript
- Javascipt is a (web) _programming language_.
- You can use functions, create custom code with interaction! 
- There is no "official standard" for coding Javascipt, but it is very powerful  

## CSS
- CSS deals with mainly styling, like layouts, fonts, colors, backgrounds.
- CSS evolved from being primarily a styling language, but is also becoming a bit more like a 'programming language', in a way.

## jsPsych
- jspsych _uses_ Javascript code for a specific experimental purpose and the functions from this library need to be imported in the top op your html file before you can use them.
- You _could_ run an experiment in your browser while being offline, if you only refer to local sources that are imported in the relative path.
- If you would need or want to load scripts from an online location in your experiment, you _could_. 
  - But then, do make sure that the locally run code *does* have a working internet connection!

# You need a plain text editor
Be sure to read up on the lab website and learn about rich text vs plain text and how to be able to edit and inspect your files not using LibreOffice, Microsoft or Apple defaults. (todo)

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
1  | nonword   | brlr
2  | word      | ball
3  | nonword   | pjrt

#### Some variable type is quoted, some is not, but it may be needed to do things way:

id | condition | string 
---|-----------|------- 
1  | "nonword" | brlr
2  | "word"    | ball
3  | "nonword" | pjrt

id | condition | string 
---|-----------|------- 
1  | nonword   | "brlr"
2  | word      | "ball"
3  | nonword   | "pjrt"

#### This will drive most people crazy, but it might just work

id | condition | string 
---|-----------|------- 
1  | "nonword" | "brlr"
2  | word      | "ball"
3  | nonword   | pjrt

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
        "string": "brlr"
    },
    {
        "id": "2",
        "condition": "word",
        "string": "ball"
    },
    {
        "id": "3",
        "condition": "nonword",
        "string": "pjrt"
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
        string: "brlr"
    },
    {
        id: "2",
        condition: "word",
        string: "ball"
    },
    {
        id: "3",
        condition: "nonword",
        string: "pjrt"
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










  


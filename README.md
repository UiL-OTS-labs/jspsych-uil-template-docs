General note: ILS labs used to be called UiL OTS labs; that is why sometimes you'll see the name UiL or UiL OTS pop up in links and documentation. We are working to change all instances of UiL OTS to ILS, but that will take awhile!

# jsPsych-uil-template-docs
- This page provides generic background information on ILS 'templates' (or 'boilerplates') for [jsPsych](https://www.jspsych.org) experiments (mostly linguistic experimental paradigms) and some additional tools that can be reused. 
- Any new template links to this overview in its README.md, so that we can keep core documentation in one place.

# Background and Rationale
This documentation provides information about using some templates that we developed at the ILS labs for (time critical reaction time) paradigms and tools needed to make your own online experiment using [jsPsych](https://www.jspsych.org/). The aims for this repository are:

- Keep documentation on a selection of code bases in _one place_.
- Separate _generic_ documentation from _template-specific_ documentation.
- Give some _background information_ to help Students, Researchers, and Developers plan online experimenting.


## Standard components
At this point, __every__ ILS jsPsych template comes with the following 'default' components included: 

### 1. Consent
A consent page placeholder is included before the experiment starts. It is up to the specifics of your own goals (and organisation) what information should be given. A consent page must always implement a combination of a consent statement, a checkbox that must be checked _and_ a _button_ that needs to be clicked to give consent. See `consent.js` for (placeholder) content.

### 2. Survey questions
You can adapt the survey questions to your own needs, but it is not as easy as it may seem. Please think well about what you want to accept as 'valid' in your survey. Read up about [input (data) validation](https://en.wikipedia.org/wiki/Data_validation). For instance, you may want an e-mail address to be in the form of `someone@somewebsite.com` and not allow people to fill out `whatever` in a survey field. Input validation is important for quality of online research. Also think about data management, and make sure to formulate your survey questions so that they will provide you with answers you can and will actually use (so, be very specific in your questions). See `survey.js`.

### 3. Generic ILS utility library
This [utility library](https://github.com/UiL-OTS-labs/jspsych-uil-utils) was created to enable:

- Mobile/Tablet detection (because those are not the type of devices we want participants to use).
- Randomisation using criteria about how many stimuli of a certain type are allowed to follow each other.

## Optional and or additional components
Some templates have additional files and folders included, for example:

### 1. Plugins
Sometimes, a custom plugin is used, for instance in the [Self-paced reading](https://github.com/UiL-OTS-labs/jspsych-spr-mw) template. See the folder `plugins` and its contents.
### 2. Keyboard setting/testing procedures
The Lexical Decision Templates use a custom keyboard setting procedure. See `keyboard.js`
### 3. Audio setting/testing procedures
Some templates use _audio_, if they do, there is or will be a simple testing procedure.

# Output (data)
Specific information about the output (data) of each template experiment can be found in its README.md. In addition, there is a general primer describing jsPysch's way of "dealing with data" and some of the ILS template's defaults for data output. Absolutely make sure that you read that [primer on data output](https://github.com/UiL-OTS-labs/jspsych-output), especially if this is your first time using one of these templates!

In a nutshell a _reminder_ to summarize with regard to experiment data output:
- jsPsych experiments _always return all_ data for _each type_ of stimulus/trial/trial phase in 'trial' objects, that have _keys_ and _values_.
- Many of _our_ templates add data (subject ID & list ID as _key, value_ pairs) to all the aforementioned objects, so the (sub)trial-data always have this information available for analysis.
- In the case of a trial or trial phase where the output contains relevant variables (experimental item, Reaction Time, etc), we sometimes add a key "useful_data_flag" with a value 'true' in the experiment; note that this may or may not include "practice trials", so always keep checking your code and your output!
- The above mentioned use of _flags_ can be of use for filtering your data.

# Documentation that should minimally be in _every template_ (developer requirements)
Certain information should be in every template. The elements below should be in every repository's README.md (Markdown):
The text within ```< >``` are 'placeholder text', the ones without them should be _'as is'_.
```markdown
# <Template name>
<A human redadable intuitive description related to the template name.>

# Generic documentation
Please read the [generic documentation](https://github.com/UiL-OTS-labs/jspsych-uil-template-docs) for some context and scope.
ILS-affiliated students and researchers should follow [this how-to](https://uilots-labs.wp.hum.uu.nl/how-to/online-experimenting/). 

# Paradigm-specific template related documentation
<If there are clearly shared properties of templates (a general paradigm), like in the case of the Lexical Decision Paradigm, they may be referenced here.>

# Task Description
<Optionally, some scope information about the paradigm or shared organisation, if relevant.>

### Short description
<A short description of what _this specific template_ does and what output is given on top of [the output all the templates give](https://github.com/UiL-OTS-labs/jspsych-output).>

### Longer Description
<A longer description that reflects on, for instance a paradigm's variations.>

# Output (data)
The data of all (sub) trial phases are logged. Please read the [general primer on jsPsych's data output](https://github.com/UiL-OTS-labs/jspsych-output) if you are new to jsPsych data output.

<Specific template output variables and how to adapt your stimuli.js and/or other files regarding data output.>

# Getting started
<How to use/start the experiment.>

```
# Functional code separation in different files (modular structure)
Some of the javascript (jsPsych) code (that is used by the experiments' 'index.html') is separated into separate files/modules. After unzipping a template download, you will often find the following files/folder structure.

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
As a general rule, we design templates in such a way, that the main experiment's file (index.html) remains rather 'minimal'. That is: not too many lines of code in the main experiment's index.html, but bundle shared functionalities in separate files with functional, descriptive names.
                             
# Context and scope of current developments
The first templates were developed for the liguistics RMA course [Experimental Design and Data Analysis in 2021](https://osiris.uu.nl/osiris_student_uuprd/OnderwijsCatalogusSelect.do?selectie=cursus&cursus=TLRMV16108&collegejaar=2020&taal=nl). Given this context, we've made the templates so that they behave quite similarly to the  [ZEP templates](https://www.beexy.nl/zep/wiki/doku.php?id=templates:lexical_decision) that are used in the ILS labs for traditional, lab bound research. However, although JavaScript and ZEP may share some features (like coding syntax, code organisation), they are of course not the same.

# List of jsPsych-based template repositories 
See the ILS labs website [here](https://ils-labs.wp.hum.uu.nl/experiments/overview/#custom-collapse-0-2).

## Generic ILS utility library (used in most templates)
A tool that may help with things like restrained randomisation, detecting mobile phone/tablets and other reusable functionality.
- [jspsych-uil-utils](https://github.com/UiL-OTS-labs/jspsych-uil-utils)

## Miscallenous jspsych related repositories

### Documentation on the concessions we have/had to make
- [jspsych-concessions](https://github.com/UiL-OTS-labs/jspsych-concessions)

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

## You will become a 'web developer' 
jsPsych was developed with scientists in mind, not developers. In essence, the jsPsych library tries to let you focus on mainly writing a html file and (re-)use simple JavaScript-style code blocks for trials or trial parts. However, once you get started with jsPsych, you will become a bit of a 'web developer' anyway, in the sense that:

- You will need _tools_ for editing html files, JavaScript code blocks and stylesheets (not Word, Pages, LibreOffice, but a plain text editor).
- You will need to learn about _debugging_ and the debugging capabilities of (most) web-browsers. (In Firefox, try F12).
- You will be _confused_ when things 'don't work'.
- You will need to _accept_ that you cannot _control everything_.

### You need _at least_ a _plain text editor_
- Windows users may want to download [Notepad++](https://notepad-plus-plus.org/), or try out the free Visual Studio Code IDE (todo)
- Mac users can use BBedit, or TextEdit in plain text mode (preferences) or try out Visual Studio Code, use XCode, Sublime Text, etc.
- (Linux users will usually find their way with this step.)

## General jsPsych info and tutorials
Before you start editing one of these templates, reading up about jsPsych will usually be a good primer. We encourage anyone to get a gist of the 'simple' (but powerful!) way of doing things by following the recommendations given at jsPsych's [site](https://www.jspsych.org/) and to follow the first two tutorials. The basic things like how some `index.html` file imports from the jspsych library, where and how plugins can be used are very relevant to understand. 

## The templates in a 'jsPsych' perspective
As always, the easy things tend to be easy to read (lines of code and examples) and understand, but in order to conduct a full-fledged online experiment, you need to invest a lot more time to make things work. This is why we chose to equip this selection of templates with the aforemetioned 'standard components' (consent, survey, a shared common utilities library). Also, by default, the templates implement stimulus lists with a so-called _'timelineVariable'_ implementation.

## Modes of using jsPsych (and the templates)
There are multiple ways to test, run and configure jsPsych-based experiments:

- Locally on your (or a participant's) PC, by double-clicking the `index.html` file.
- Full web server implementation (getting a link to the experiment, served by ICT&Media).

These two modes will likely confuse those who are not web developers, but the bottom line is: 

- A locally developed experiment will _not guarantee that the same experiment will run in a server setup_, or vice versa! 

Many browsers and versions have their own defaults for security like 'autoplay', allowing sounds, pop-ups and alerts, importing images from local sources, etc. It is impossible to know 100% sure if things will work in your browser in advance, so be prepared to deal with some confusion.

## For 'real' online data collection, you will need a server-based setup
While you could -- in principle -- use jsPsych offline in the traditional lab context, it will typically not make a lot of sense. Especially if you want to store your research data for an experiment in one place, a web-server setup is the way to go. 

# From template to your own online experiment

Linguistics students and researchers _affiliated with the ILS labs_ can use the templates [from our lab webiste](https://ils-labs.wp.hum.uu.nl/experiments/overview/); expand the "Online experiments using jsPsych" section for details. Please [follow this how-to](https://ils-labs.wp.hum.uu.nl/how-to/online-experimenting/) to get to your own experiment. 

- This documentation is primarily aimed at people _affiliated with the ILS labs_ (Utrecht University: Linguistics students and researchers). The infrastructure and support for doing online experiments will be _only availble for those people_. People _not affiliated with our lab_ can of course use the templates, but will have to do without (support for, access to) the [ILS Experiment Datastore](https://experiment-datastore.lab.hum.uu.nl/experiments/).


# jspsych-vislexdec-vp
Visual [lexical decision](https://en.wikipedia.org/wiki/Lexical_decision_task) experiment with _Visual Prime_ (template)

# Connected templates

### Visual Templates
1. [vislexdec](https://github.com/UiL-OTS-labs/jspsych-vislexdec)
2. [vislexdec-vp](https://github.com/UiL-OTS-labs/jspsych-vislexdec-vp)
3. [vislexdec-vp-mp](https://github.com/UiL-OTS-labs/jspsych-vislexdec-vp-vm)

### Audio and/or visual Templates
4. [audlexdec](https://github.com/UiL-OTS-labs/jspsych-audlexdec-vp)
5. [audlexdec-vp](https://github.com/UiL-OTS-labs/jspsych-audlexdec-vp)
6. [audlexdec-vp-mp](https://github.com/UiL-OTS-labs/jspsych-audlexdec-vp-mp)

# Task Description

## Short description
The participant first sees a fixation cross, then a prime is presented, followed by the test stimulus. Particpants are instructed to respond as quickly as possible to make the decision if both strings in the pair are words --or not--, using the keyboard.

- The _prime_ is a string of letters and can be a real word or a nonword.
- The _'test stimulus'_ is a string of letters and can also be a real word or a nonword.

## Longer description
There are many (slightly) different variations of a lexical decision task. In this version, a trial consists of subsequently presenting _two_ words or nonwords. The participant needs to make a swift decision whether the _pair_ of presented sets of letters - the test stimuli - are _both_ acutal words or not. 

The naming conventions for this pair can be slightly confusing. The general convention will be to differentiate between a 'prime' and the 'test stimulus', even though in a way, the _pair_ _is_ the test stimulus, both in what defines a single trial, and in the way to prepare the stimuli.js structure (the code).

The idea behind this _primed_ variant is that there may be semantic (or visual or grammatical) associations that influence reaction time in the last decision stage. For instance, after presenting the word 'snow' as a _prime_, there might be a speedup in the reaction time (RT) to the test stimulus if it were 'white', as opposed to --for instance-- 'potato', due to <i>semantic association</i>.

It is up to the researcher to balance the stimulus design according to the categorial speedup or slowdown effects that are hypothesised, amongst others. So-called _Latin Square Designs_ and things like _Pseudo-Randomisation_ are often needed, or have at least by tradition been used as solutions to certain problems. Think of: maximizing statistical power, keeping participants unbiased and naive with regards to the purpose of the experiment, general experiment look and feel, task elicited enticingness versus boredom, data management considerations, categorial data-reduction heuristics, etc...  

The essential sub trial phases for _one_ trial for this boilerplate experiment are:

1. Fixation cross presentation (fixed time, no responses are recorded) 
2. Prime presentation (fixed time, no responses are recorded)
3. Test stimulus presentation (the last string of letters of the presented pair, lexical decision phase). 

Only in this _last phase_, as soon as the "test item" is being presented, the participant can respond with the keyboard.

The reaction time, response and correctness of the response are usually the important variables for analysis. By default, the data of all sub trial phases are logged in the data, but the output data can quite easily be filtered after data collection.

# Getting started (the easy way, working internet connection required)
For now, the easiest way to test these templates, is:

1. Download this repository by clicking the green code button above and Download zip.
2. Unzip the jspsych-vislexdec-vp-main.zip at a location of your choosing.
3. Inside the folder is a file called index.html, double click it in order to open it
   in a browser.

# Getting started (the harder way, local and/or custom setup)

You need this github repository and to download the jsPsych library version 6.1
complete the following steps. When downloading and extracting folders please
keep in mind that once working on the server, filenames are case sensitive and
"jsPsych.js" and "jspsych.js" are two distinct filenames. It might work on your
machine, but it might not work on the server hosting your experiment.

You will need to adapt your own directory structure/naming convention in the 
top ```<script>``` tags as defined in index.html, if you want your own local jsPsych setup.

1. Download this repository by clicking the green code button above and Download zip.
2. Unzip the jspsych-vislexdec-vp.zip at a location of your choosing.
3. Download jsPsych-6.1.0 (-6.1.0 is the version) from the jsPsych releases website
   https://github.com/jspsych/jsPsych/releases. You might need to scroll down a little.
4. Extract the jsPsych folder into the jspsych-vislexdec-vp folder you extracted earlier.
5. Inside the folder is a file called index.html, double click it in order to open it
   in a browser.
   

# Generic overview (draft, should be moved from here after some time)
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
It's a good idea to really read the documentation on https://www.jspsych.org. The basic things like how some 'experiment.html' file imports from the jspsych library, where and how plugins can be used are good to start with.

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










  


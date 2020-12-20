![https://github.com/npec/AWOC2020-GEE-Training/tree/main/images/npec.PNG](attachment:npec.PNG)
<hr style="border:2px solid rgb(30,70,125)"> </hr>

<span style="font-family:Papyrus; font-size:2em;">Eligio Maure</span>
> maure@npec.or.jp  
> eligiomaure@gmail.com

# Outline 
<hr style="border:2px solid rgb(30,70,125)"> </hr>
<span style="font-weight:bold; font-size:1em;"><ul><li>GEE Introductory Overview ~ 1 h 30 min</li><li>Time Series Analysis (Hands-on) ~ 1 h 10 min</li><li>Wrapping Up ~ 5 min</li><li>Q&A ~</li></ul></span>  

## Introductory Overview 
<hr style="border:2px solid rgb(30,70,125)"> </hr>  <ul><li>Google Earth Engine (GEE) - <span style='font-weight:bold'>15 min</span></li><li>GEE Code Editor - <span style='font-weight:bold'>15 min</span>
</li><li>GEE Javascript - <span style='font-weight:bold'>35 min</span></li><li>Temporal and Spatial Reducers - <span style='font-weight:bold'>25 min</span></ul></li>

## Prerequisites to Using GEE
<hr style="border:2px solid rgb(30,70,125)"> </hr>  

- Get a <span style="color:blue">**GMAIL/GOOGLE**</span> account 
- <span style="color:green">**Sign up**</span> for Earth Engine (http://bit.ly/GoogEEngine). 
    - **Registration is needed to have access to EE**
- If registered, verify your GEE access though the link below
    - https://code.earthengine.google.com/  
    

_We **assume everyone is registered and have access to GEE**_  
_Otherwise, just follow the discussion and try on your own time_

## Resources
<hr style="border:2px solid rgb(30,70,125)"> </hr>

- This presentation is available at <span style="color:red">https://github.com/npec/AWOC2020-GEE-Training</span>
- All participants that updated their <span style="color:blue"> GMAIL/GOOGLE</span> were added to the class repository of GEE scripts

_**The repository will show up in your GEE code editor**_
 - Scripts &#8594; Reader   
  &#8594; **users/nwatchs/AWOC2020** (more on this later)

<span style="font-size:1.3em; font-weight:bold">Earth Engine Developer's Page</span>  https://developers.google.com/earth-engine
![https://github.com/npec/AWOC2020-GEE-Training/tree/main/images/earth-engine-intro2.png](attachment:earth-engine-intro2.png)

* <span style="color:rgb(120, 160, 210); font-weight:bold">Guides</span> - JavaScript & Python
* <span style="color:rgb(120, 160, 210); font-weight:bold">Reference</span> - Client Libraries & Code Editor
* <span style="color:rgb(120, 160, 210); font-weight:bold">Help & Support</span>
* <span style="color:rgb(120, 160, 210); font-weight:bold">Data Catalog</span>, etc.

## Comments/Questions/Help
<hr style="border:2px solid rgb(30,70,125)"> </hr>

- Please <span style="color:brown">**mute your microphone**</span> while listening
- <span style="color:green">**Unmute whenever you have a question**</span> to ask or post in the comment section
- Please reach out with any questions to maure@npec.or.jp at any time 

## Please Note
<hr style="border:2px solid rgb(30,70,125)"> </hr>

- Although we introduce EE to the ocean colour community
- We are not going to delve into specifics of ocean colour
- Unless we are advanced GEE users, it won't be practical!  

**So, let us focus on the foundations of GEE** <br> 
  The most advanced tasks are left for the future  

**All practical examples use ocean data (chlorophyll, temperature)**


```python
%%html
<style>
table {float:left}
</style>
```


<style>
table {float:left}
</style>



# Introduction to GEE 
<hr style="border:2px solid rgb(30,70,125)"> </hr>

|<span style="font-weight:bold; font-size: 1.5em; color:brown">Questions</span>|  
|:---|
<span style="font-size: 1.2em"><ul><li>What is Google Earth Engine?</li><li>Why use Google Earth Engine? *Strengths and limitations</li></ul></span>   


|<span style="font-weight:bold; font-size: 1.5em; color:green">Learning Points</span>|  
|:---|
<span style="font-size: 1.2em"><ul><li>Understand the power of Google Earth Engine</li><li>Understand the system architecture and philosophy</li></ul></span>

## What is Google Earth Engine?
<hr style="border:2px solid rgb(30,70,125)"> </hr>

<span style="color:rgb(200, 50, 50); font-weight: bold; font-size: 1.1em"> A cloud-based platform for planetary-scale geospatial analysis</span>

![https://github.com/npec/AWOC2020-GEE-Training/tree/main/images/gee-paper.PNG](attachment:gee-paper.PNG)

## Why Google Earth Engine?
<hr style="border:2px solid rgb(30,70,125)"> </hr>

|<span style="color:brown; font-weight:bold; font-size:1.5em">An interactive environment for development at scale$~$</span>|
|:---|
<ul><li>**Fast prototyping & computation**</li><li>**Easy dissemination of research outputs through GEE Apps**</li><li>**High-impact & data-driven science**</li><li>**Free cloud processing** with built-in functions optimized for parallel computing</li></ul>|  
Many Celebrity Use Case https://earthengine.google.com/case_studies/  

[Timelapse](https://earthengine.google.com/timelapse#v=24.99902,54.99209,11.872,latLng&t=2.03&ps=50&bt=19840101&et=20181231&startDwell=0&endDwell=0)

![https://github.com/npec/AWOC2020-GEE-Training/blob/main/images/Timelapse.gif](attachment:Timelapse.gif)

<span style="font-weight: bold; font-size:1.3em;">The global distribution and trajectory of tidal flats</span>  
<span style="font-size: 0.8em">Nicholas J. Murray, Stuart R. Phinn, Michael DeWitt, Renata Ferrari, Renee Johnston, Mitchell B. Lyons, Nicholas Clinton, David Thau & Richard A. Fuller</span>

![https://github.com/npec/AWOC2020-GEE-Training/tree/main/images/tidal-case.PNG](attachment:tidal-case.PNG)

_**https://www.intertidal.app/**_

<span style="font-size:1.5em; font-weight: bold">Global Surface Water</span>
![https://github.com/npec/AWOC2020-GEE-Training/tree/main/images/water-distro-app.PNG](attachment:water-distro-app.PNG)
_**https://global-surface-water.appspot.com/map**_

|<span style="font-weight: bold; color:brown; font-size: 2em">Online public data archive$~$</span> |
|:---|
<ul><li><span style='font-size: 1.3em'>A petabyte (> 50) storage accessible through GEE APIs</span></li><li><span style='font-weight:bold; font-size: 1.3em; color:rgb(255, 110, 0)'>Unfortunately, ocean colour data repository still very poor</span></ul></li>

![https://github.com/npec/AWOC2020-GEE-Training/tree/main/images/gee-data-catalogue.PNG](attachment:gee-data-catalogue.PNG)

<span style="font-size:1.2em; font-weight:bold">However</span>...   
<span style="font-size:1.1em"> > We can upload own datasets (up to 10 GB)</span>  
<span style="font-size:1.1em">> Make dataset requests</span>  

![https://github.com/npec/AWOC2020-GEE-Training/tree/main/images/gee-upload-asset.png](attachment:gee-upload-asset.png)

<span style="font-weight:bold; font-size:1.3em">Flexible access through APIs</span>  
Rapid visualization of complex spatial analyses  
_**API &#8594; application programming interface**_
![https://github.com/npec/AWOC2020-GEE-Training/tree/main/images/GEE_Languages_2.PNG](attachment:GEE_Languages_2.PNG)

<span style="font-weight:bold; font-size:1.3em">[EE Explorer](https://explorer.earthengine.google.com/#workspace)</span> 
 <hr style="border:2px solid rgb(30,70,125)"></hr>
- Great tool for non-specialists to get started 
- Allows simple data visualization but with limited analysis capabilities
- Does not require registration!  

[Introductory materials](https://www.google.com/earth/outreach/learn/introduction-to-google-earth-engine/)
![https://github.com/npec/AWOC2020-GEE-Training/tree/main/images/earth-engine-explorar.png](attachment:earth-engine-explorar.png)

|<span style="font-weight:bold; font-size:1.5em">How GEE works</span>|
|:---|
<span style="color:brown; font-weight:bold; font-size:1.2em">Server-side</span>
Written commands can be sent as requests object to Google's cloud for compution
<span style="color:brown; font-weight:bold; font-size:1.2em">Client-side</span>
Results sent back can be visualized in the browser

![https://github.com/npec/AWOC2020-GEE-Training/tree/main/images/gee-howitworks.png](attachment:gee-howitworks.png)

<span style="color: blue; font-size:1.3em; font-weight: bold">GEO-GEE License Project: 32 Projects (22 Countries) </span>  
Aim to tackle some of the world’s greatest challenges using open Earth data   
 
<span style="color: brown; font-size:1em; font-weight: bold">NPEC is part of a GEO-GEE project</span> (lead, Prof. Joji Ishizaka, Nagoya Univ.)  
**`Global screening of potential eutrophication waters`**  
**`SGLI 250 m data for mapping of near-coastal waters`**
    
![https://github.com/npec/AWOC2020-GEE-Training/tree/main/images/geo-projects.PNG](attachment:geo-projects.PNG)

<span style='font-size: 1.2em; font-weight:bold'> Summary </span>
- <span style='color:rgb(0,150,0)'>GEE is great tool operating on petabyte imagery using Google’s cloud</span>  
- <span style='color:rgb(0,150,0)'>Allows complex analysis and visualizations with basic JavaScript</span>
- <span style='color:rgb(0,150,0)'>Eliminates most of the hurdles with satellite data analysis</span>  
 &#8594; e.g., downloading, data formats, etc (not so for ocean colour)
- <span style='color:rgb(0,150,0)'>Easy dissemination of output results through GEE Apps </span>
- <span style='color:rgb(0,150,0)'>Allows import/export of your own assets </span>  
    &#8594; raster and vector data, e.g., projected swath or *in situ* data points
- <span style='color:rgb(0,150,0); font-weight:bold'>GEE is changing the way we study and understand the Earth</span>

- <span style='color:rgb(150,0,0)'>Only works with internet connection</span>  
- <span style='color:rgb(150,0,0)'>Users have no control on how computations are run in GEE</span>
- <span style='color:rgb(150,0,0)'>Non-parallelizable operations cannot be performed effectively</span>    
- <span style='color:rgb(150,0,0)'>GEE performs poorly for long-running iterative processes </span>  
  &#8594; e.g. finite element, etc.

| <span style='font-size:1.3em; font-weight:bold'>5 min break (or questions if any)</span> |
|:--- |
<span style='font-size:2em; font-weight:bold'>GEE Code Editor</span>

# GEE Code Editor 
<hr style="border:2px solid rgb(30,70,125)"> </hr>

|<span style="font-weight:bold; font-size: 1.5em; color:brown">Questions</span>|  
|:---|
<span style="font-size: 1.2em"><ul><li>What are the key features of the Google Earth Engine online code editor?</li><li>How do I search for and import datasets?</li><li>How do I create, save and share scripts?</li></ul></span>  

|<span style="font-weight:bold; font-size: 1.5em; color:green">Learning Points</span>|  
|:---|
<span style="font-size: 1.2em"><ul><li>Get familiar with the code editor and the tools available</li></ul></span>

## <span style="font-weight:bold; color:red">Data Search & Help</span>
<hr style="border:2px solid rgb(30,70,125)"> </hr>

![https://github.com/npec/AWOC2020-GEE-Training/tree/main/images/gee-code-editor-01.png](attachment:gee-code-editor-01.png)

## <span style="font-weight:bold; color:red">Scripts, Docs & Assets</span>
<hr style="border:2px solid rgb(30,70,125)"> </hr>

![https://github.com/npec/AWOC2020-GEE-Training/tree/main/images/gee-code-editor-02.png](attachment:gee-code-editor-02.png)

## <span style="font-weight:bold; color:red">Code Editor</span>
<hr style="border:2px solid rgb(30,70,125)"> </hr>

![https://github.com/npec/AWOC2020-GEE-Training/tree/main/images/gee-code-editor-03.png](attachment:gee-code-editor-03.png)

## <span style="font-weight:bold; color:red">Inspector, Console & Tasks</span>
<hr style="border:2px solid rgb(30,70,125)"> </hr>

![https://github.com/npec/AWOC2020-GEE-Training/tree/main/images/gee-code-editor-04.png](attachment:gee-code-editor-04.png)

## <span style="font-weight:bold; color:red">The Map</span>
<hr style="border:2px solid rgb(30,70,125)"> </hr>

![https://github.com/npec/AWOC2020-GEE-Training/tree/main/images/gee-code-editor-05.png](attachment:gee-code-editor-05.png)

[code editor](https://code.earthengine.google.com/)

<span style='font-size: 1.5em; font-weight:bold'> Summary </span> 
<hr style="border:2px solid rgb(30,70,125)"> </hr>

- The Code Editor provides an easy and abstract way to 
 - accessing GEE data catalog as well as personal assets
 - conducting geospatial analysis
 - displaying and sharing the results

- Provide ways to import, export, share and manage personal assets
- **Example scripts**, **Docs** and **help** are valuable resources to explore

# Basics of EE Javascript 
<hr style="border:2px solid rgb(30,70,125)"> </hr>

|<span style="font-weight:bold; font-size: 1.5em; color:brown">Questions</span>|  
|:---|
<span style="font-size: 1.2em"><ul><li>What are the basics of EE JavaScript ?</li><li>What is client-side vs. server-side JavaScript?</li></ul></span>  

|<span style="font-weight:bold; font-size: 1.5em; color:green">Learning Points</span>|  
|:---|
<span style="font-size: 1.2em"><ul><li>Gain a basic understanding JavaScript</li><li>Make a distintion between EE objects and other JavaScript objects</ul></span>

## <span style="font-weight:bold">Javascript Syntax In General</span>
<hr style="border:2px solid rgb(30,70,125)"> </hr>


```JavaScript 

// And, the first thing you do in any programming language:
print('Hello World!')


// Line comments start with two forward slashes. Like this line.


/* Multi-line comments start with a forward slash and a star,
and end with a star and a forward slash. */
```


## <span style="font-weight:bold">Variable Declaration</span>
<hr style="border:2px solid rgb(30,70,125)"> </hr>

```JavaScript 
// variables store objects and are defined using the keyword var
var thisNumber = 1;

// string objects start and end with a single quote
var thisString = 'I am a string';

// string objects can also use double quotes
// But don't mix the two
var thatString = "I am a string";
```

## <span style="font-weight:bold">Statements</span>
<hr style="border:2px solid rgb(30,70,125)"> </hr>

```JavaScript 
// statements end with a semi-colon, or the editor will complain
var feelsIncomplete = "I feel incomplete..."
var feelsComplete = "I feel complete!";

```

[Statements](https://code.earthengine.google.com/697cace51756db2431efab37874d7572)

## <span style="font-weight:bold">How to Pass Function Parameters</span>
<hr style="border:2px solid rgb(30,70,125)"> </hr>

```JavaScript 

// use parentheses to pass parameters to functions
print('This string will print in the Console tab.');


```

## <span style="font-weight:bold">List Definition</span>
<hr style="border:2px solid rgb(30,70,125)"> </hr>

```JavaScript 

/* square brackets are used for items in a list
The zero index refers to the first item in a list*/
var myList = ['eggplant','apple','wheat']; 

print(myList[0]); // prints eggplant
print(myList[3]); // prints undefined

```

## <span style="font-weight:bold">Dictionary Definition</span>
<hr style="border:2px solid rgb(30,70,125)"> </hr>

```JavaScript 
/* Use curly brackets (or braces) to define dictionaries 
   {key:value} pairs. */
var myDict = {'food':'bread', 'color':"red", 'number':42};

// Use square brackets to access dictionary items by key
print(myDict['color']);

//Or use the dot notation to get the same result
print(myDict.color);
```

[Dictionary](https://code.earthengine.google.com/45955ed3936fc619ceb0b28ac70d3240)

## <span style="font-weight:bold">Function Expression</span>
<hr style="border:2px solid rgb(30,70,125)"> </hr>

```JavaScript 
/*function can be defined as a way to reuse 
  code and make it easier to read*/ 
var myHelloFunction = function(string) {
  return 'Hello ' + string + '!';
};
print(myHelloFunction('world'));
```

[FunctionExpression](https://code.earthengine.google.com/5e1c26164be8d41115935b1ea0000b4e)

## <span style="font-weight:bold">Client vs. Server Objects</span>
<hr style="border:2px solid rgb(30,70,125)"> </hr>

- Everything we saw so far lives in the browser (client-side)
- _**Client-side**_ useful, for example, when making EE user interfaces
- _**Server-side**_ objects are proxy objects and start with `ee`  

&#8594; _**Server-side (proxy) objects are just handles for objects on the server**_


## <span style='font-weight:bold'>Strings</span>
<hr style="border:2px solid rgb(30,70,125)"> </hr>

```JavaScript 
var clientString = 'I am a String';
print(typeof clientString);  // string
      
var serverString = ee.String('I am not a String!');
print(typeof serverString);  // object
print('Is this an EE object?', 
      serverString instanceof ee.ComputedObject);  // true
/* Observe that "serverString" is an "object", 
   more specifically, "ee.computedObject" */

```

[client-server-00](https://code.earthengine.google.com/19a8c1b12271202dfeaa544ae39749e5)

```JavaScript 
/* Client doesn't know what's in the container, 
   so we can find out by printing it */
print(serverString);  // I am not a String


/* To see what the container itself looks like, 
   call toString() on the object: */
print(serverString.toString());  
// ee.String("I am not a String!")
```

```JavaScript 
/* we can get the contents of the container 
   and assign them to a variable */

var someString = serverString.getInfo();
var strings = someString + '  Am I?';
print(strings);  // I am not a String!  Am I?

/* getInfo() is synchronous, thus it blocks code execution,
   so should avoid using it unless absolutely needed */

```

[client-server-string](https://code.earthengine.google.com/6c80bab9647d34a179ea51d225568d43)

## `getInfo` vs. `evaluate`
<hr style="border:2px solid rgb(30,70,125)"> </hr>

```JavaScript 
var something = ee.thing.getInfo(); // synchronous call

// A good way to request a value of the server object is to use
// evaluate() - this call is asynchronous
ee.Number(7).evaluate(function(n) {
    var clientNum = n + 3;
    print('Should be 10. Found ' + clientNum);
});

```

[client-server-evaluate](https://code.earthengine.google.com/483709550cda17c0bd8cec6b5d01e3f0)

## <span style='font-weight:bold'>Lists</span>
<hr style="border:2px solid rgb(30,70,125)"> </hr>
    
```JavaScript 
// This exists in the browser
var clientList = [0, 1, 2, 3, 4, 5, 6, 7];
print(clientList); 

// This is a handle for some object on the cloud
var serverList = ee.List(clientList);
print(serverList); // They look the same!

var anotherList = ee.List.sequence(0, 7);
print(anotherList); // Also the same!

```

[client-server-list](https://code.earthengine.google.com/8a0db63019cbb4649f15e27b474216ab)

## <span style='font-weight:bold'>Mutable vs. Immutable</span>
<hr style="border:2px solid rgb(30,70,125)"> </hr>

```JavaScript 
// Client-side objects are mutable
clientList.push(8);
print(clientList);

// However, the same won't work on the server list
// serverList.push(8); // Error!
var longerList = serverList.add(8);
// Use docs tab to discover methods on server objects

```

[client-server-list-01](https://code.earthengine.google.com/d6dbb89217d4c5f7e00d8a6c4978d0e8)

## <span style='font-weight:bold'>Operations With Server Objects</span>
<hr style="border:2px solid rgb(30,70,125)"> </hr>

```JavaScript 
// A constant Image
var constantImage = ee.Image(7);

// This is NOT what we want:
var junkString = constantImage + 42;
/* Note that the browser calls toString() on the object and 
  then appends '42' to it. The JSON you see contains the 
  instructions sent to the server to execute your code */
print('JunkString:', junkString);
```

[client-server-images](https://code.earthengine.google.com/e4624ed0db0270c6f4ae3140e162cf47)

```JavaScript 
// This is the right way:
var someImage = constantImage.add(42);
// Click with the inspector to observe 
Map.addLayer(someImage, {}, 'someImage')
```

[client-server-images-01](https://code.earthengine.google.com/25c92873e0cfb026307b2ba0aa49704c)

## `Mapping` (what to do instead of a `for-loop`)
<hr style="border:2px solid rgb(30,70,125)"> </hr>  

- In EE we use `map()` instead of `for-loops`
 - This is key to making EE work
- `for-loops` may still be useful for client-side (user interfaces)
- However, server-side is best served with `map`



`.map(...)` vs. `for(...)`  $~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~$        [code editor](https://code.earthengine.google.com/)
<hr style="border:2px solid rgb(30,70,125)"> </hr>    

![https://github.com/npec/AWOC2020-GEE-Training/tree/main/images/gee-map.png](attachment:gee-map.png)



<span style='font-size: 1.5em; font-weight:bold'> Summary </span> 
<hr style="border:2px solid rgb(30,70,125)"> </hr>

- In EE computations are parallel (`map` instead of `for`)  
- `.getInfo()` can cause browser lock (`.evaluate` instead)
- Mixing client and server functions can cause errors
- Cast client into server objects using the `ee.Thing` constructor   
     `e.g., ee.List([1, 2]), etc.` 
- Server-side objects are _**immutable**_. Save changes in a new object 
 - i.e., assign the changes to a new variable  
 ```JavaScript
 e.g., var newImage = oldImage.add(3)
 ``` 

|<span style='font-size:1.5em; font-weight:bold'>Additional JavaScript Resources</span>|
|:---|
<span style="font-size: 1.2em"><ul><li>1. [Earth Engine Guides](https://developers.google.com/earth-engine/guides)</li><li>2. [JavaScript in General](https://www.w3schools.com/js/default.asp)</li><li>3. [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html)</li></ul></span>  


# Spatial and Temporal Reducers 
<hr style="border:2px solid rgb(30,70,125)"> </hr>

**Reduce - Aggregate everything in a collection**  
<span style="font-style: italic; color: blue">reducer</span> - an EE operation for aggregating data or computing a statistic
 
![https://github.com/npec/AWOC2020-GEE-Training/tree/main/images/gee-reduce-space.png](attachment:gee-reduce-space.png)

### Reduce Region
<hr style="border:2px solid rgb(30,70,125)"> </hr>
Apply a reducer over an image with several bands  

[code editor](https://code.earthengine.google.com/)

![https://github.com/npec/AWOC2020-GEE-Training/tree/main/images/gee-reduce-space01.png](attachment:gee-reduce-space01.png)

# Time Series Analysis ([hands-on](https://code.earthengine.google.com/))
<hr style="border:2px solid rgb(30,70,125)"> </hr>

- Temporal and Spatial Reducers (Recap) - **10 min**
- Time Series Analysis (By Point or Region) - **25 min**
- Interactive Time Series Analysis (User Interface) - **30 min**
- Q&A



|<span style="font-weight:bold; font-size: 1.5em; color:brown">Questions</span>|  
|:---|
<span style="font-size: 1.2em"><ul><li>How to create a time series for a given location?</li><li>How to plot the time series within GEE?</li><li>Can we make the plot interactive?</li></ul></span>  

|<span style="font-weight:bold; font-size: 1.5em; color:green">Learning Points</span>|  
|:---|
<span style="font-size: 1.2em"><ul><li>Import image collection and crop the region of interest</li><li>Dynamically select lon/lat for creating time series plots</li><li>Create time series of chlorophyll and/or sea surface temperature</li></ul></span>  



# Wrapping Up
<hr style="border:2px solid rgb(30,70,125)"> </hr>

## Today we have covered

1. **Introductory Overview** to GEE
2. **GEE Code Editor**: How to navigate the code editor
3. **Basics JavaScript**: What is client-side and server-side
4. **Spatial and Temporal Reducers**: aggregate space-time data
5. **Image Regions Charts**: How to create a plot of image bands
6. **Time Series**: How to a simple time series plot
7. We also demostrated the interactive plotting

 [Code Editor](https://code.earthengine.google.com/): Where you go to write code.  
  - This is the best tools for development  
  - Also, check the `Help` inside the Code Editor, it provides links to useful pages  
  
[Data Catalogue](https://code.earthengine.google.com/datasets/): Details on the available datasets  
[Developers Guide](https://developers.google.com/earth-engine/): the closest thing to a manual 
  - Other that documentation, provides links to many other resources   

[Developers Forum](https://groups.google.com/forum/?fromgroups#!forum/google-earth-engine-developers): Where you go to post questions  

- If you plan to use GEE, it is advisable to join the [EE Forum](https://groups.google.com/g/google-earth-engine-developers)
 - When posting questions to the forum, help is faster if the link to your script is included which makes easier for others to help you troubleshoot
- Where sharing codes that include private assets, ensure that they are puclicly accessible

### Additional Learning Resources/References

- [Debugging Guide](https://developers.google.com/earth-engine/debugging)
- [Earth Engine EDU](https://developers.google.com/earth-engine/tutorials/edu)
 - Some materials have also been translated to Japanese
- [GeoHackWeek](https://geohackweek.github.io/GoogleEarthEngine)

# Breakout Session (brainstorming)
<hr style="border:2px solid rgb(30,70,125)"> </hr>

Based on what you have just learned, think about some analysis you can perform of GEE  
Try to use a few commands for simple analysis   
You draft the idea with a code, or just the schematic, its OK  
This exercise can help retain a few things learned today   

10 min

# Q&A

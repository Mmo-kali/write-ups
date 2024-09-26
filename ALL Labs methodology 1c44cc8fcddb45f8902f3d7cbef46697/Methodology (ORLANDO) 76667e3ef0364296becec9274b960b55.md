# Methodology (ORLANDO):

---

# Magic polyglot.

```
JavaScript://%250Aalert?.(1)//'/*\\'/*"/*\\"/*`/*\\`/*%26apos;)/*<!--></Title/</Style/</Script/</textArea/</iFrame/</noScript>\\74k<K/contentEditable/autoFocus/OnFocus=/*${/*/;{/**/(alert)(1)}//><Base/Href=//X55.is\\76-->

```

---

REFLECTED XSS ( Tends to happen on the search bar)

1. start with some html tags like <h1>lb155</h1> and see if they are injected into the page

If this works then its vulnerable and just use plain XSS attack.

1. if this doesn’t work then you have to look at the inspector and look for where it is reflected.

```
The first reflection tends to be inside a h1 tag. But the other refllection is
what tends to be vulnerable.

If the <> are encoded try to use various <<>> if this doesnt work. Try to URL encode them.

if this doesn't work try to see if the " ' are encoded as well if they arent then just add an evenhandler such as "onmouseover="alert(1)

if you find that most tags are not allowed. First test if the <> are being filtedred. if they are not then use intruder to go through all the allowed tags.

remember that you can use custom tags too.

use resize and autofocus to get xss. These are in the cheat.

always try <img> <body> <svg> from the get go. if you see <svg> tags you can use it for xss.

if <svg> and <animatetransform>  are together then use it.

if you search canonical in the sourceCode.You inject in the URL. ?lb155
use something like
accesskey='X'onclick='alert(1)'>

if you see ` ` this means template literal. you can include ${} with this you can use javascript without exiting the string.  ${alert()}

if you cant exit the string then try to close it with the tag above.

```

STORED XSS (Tends to happen on the comment section)

1. same as reflected XSS intially start by simply injecting the tags and if it works then just do a simple XSS payload.

```
POST a comment, and see if the website is appended to that of the main website URL. Also check if it allows you to inject an invalid URL in the website. if it tdoes then it may be vulnerable.Look at where its relfected if its href then. javascript:alert(1)

```

DOM XSS

1. start by adding a canary. lb155 for example (USE DOM INVADER TOO)
2. Look for scripts in the page source first then look at the inspection. If you see

```
 [Window.location.search](<http://Window.location.search>) then  that is anything after the ? in the URL. So look at where it is injecting it to and get out of the context

 innerHTML then it means you can pass it valid HTML. Use <img> tag.

 You find jquery and $ which means that there is jquery. Look at the context if youre inside of **href** then use something like javascript:alert(1)

if the $ and jquery are talking about hashchange or its listening for a hashchange then it means the # at the end of a URL. window.location.hash means anything after the # including it. Since its looking for a hashchange then you must load the page and then add the hash change.
<iframe src="labURL#" onload="this.src+='<img src=1 onerror=print()'">
The this.src+= is appending the source to the previous source

if you see document.write it might have to do with xss.

If you see angularJS or ng-app you can test it out by using.
{{ 1+1 }}  to see if it evaluates.
then find a payload in payloadallthings. or the XSS cheat.

 if you find an a javascript file and then a function call go to the js file and search for the function. if it has eval it means its most likely vulnerable.
 Remember to look for the function call in burp and use it to escape or you could use DOM invader.

```

1. If you dont understand the script put it into chatgpt and ask it whats it doing.
2. Exit out of them.

Simple payload that works if nothing is encoded. or  sanitized.

```
<script>alert(1)</script>

```
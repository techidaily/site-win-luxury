---
title: Master Your Documents with EmEditor, the Powerful Open-Source Text Editor
date: 2024-10-19T02:00:06.481Z
updated: 2024-10-22T22:08:05.725Z
tags:
  - product
categories:
  - emeditor
thumbnail: https://thmb.techidaily.com/d9a0fed70b3544c875727acbd189babb9991061b2738772aa77659169a12a4b8.jpg
---

## Master Your Documents with EmEditor, the Powerful Open-Source Text Editor

July 30, 2014 at 11:36 am [#18710](https://tools.techidaily.com/emeditor/products/) 

[![](https://secure.gravatar.com/avatar/f29c043a3cc5c5dac8db4e62939893e9?s=80&d=identicon&r=g)Stefan](https://www.emeditor.com/forums/users/Stefan/ "View Stefan's profile")

Participant

Sorry, update again.

  
 Better logic:  
 if last line have whitespace only, just remove these blanks and done.  
 Else, if last line is not empty, but not whitespace only, add a new line.  
 (This way we not end up with too “visible blank” lines)

  
 I also added cursor handling to went back from EOF to origin cursor place.  
 (Not needed for this thread purpose as event script, but if script is used on demand)

Not asked for, but just done for the fun:  

```
//JavaScript Macro for EmEditor, v0.02 by Stefan
//Purpose: Ensure that last line is a blank one, by adding one if need.

//// Don't show the cursor move////
//EmEditor Help - EmEditor Macro Reference - Window Object
//prevents changes in EmEditor from being redrawn:
Redraw = false;

////Store cursor position////
//EmEditor Help - EmEditor Macro Reference - Selection Object
//Returns the column number of the cursor position.
xPos = document.selection.GetActivePointX(eePosLogical);
//Returns the line number of the cursor position:
yPos = document.selection.GetActivePointY(eePosLogical);

////Check status of last line////
//EmEditor Help - EmEditor Macro Reference - Document Object
//Retrieves the number of the lines in the document:
nLines = document.GetLines();
//Retrieves the text on the specified line:
str = document.GetLine(nLines);
//Moves the cursor to the end of the document:
document.selection.EndOfDocument();
//If last line only contains indenting white space, just remove the whitespace//
if(str.match(/^\s+$/) != null){
	//Selects a line at the cursor:
	document.selection.SelectLine();
	//Deletes the selected text:
	document.selection.Delete();
}else if (str.length != 0){
//If last line is NOT empty, but not whitespace only, add one blank line//
	document.selection.NewLine();	

////Restore cursor position////
//Sets the cursor position:
bExtendSelection = false;
document.selection.SetActivePoint(eePosLogical, xPos, yPos, bExtendSelection);

//<EOF>
```

<ins class="adsbygoogle"
     style="display:block"
     data-ad-format="autorelaxed"
     data-ad-client="ca-pub-7571918770474297"
     data-ad-slot="1223367746"></ins>

<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-7571918770474297"
     data-ad-slot="8358498916"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>

<span class="atpl-alsoreadstyle">Also read:</span>
<div><ul>
<li><a href="https://facebook-video-footage.techidaily.com/new-2024-approved-editors-assistant-top-5-portable-devices-for-vfx-artists/"><u>[New] 2024 Approved Editor's Assistant Top 5 Portable Devices for VFX Artists</u></a></li>
<li><a href="https://extra-skills.techidaily.com/updated-real-reviews-real-results-in-branding/"><u>[Updated] Real Reviews, Real Results in Branding</u></a></li>
<li><a href="https://tech-haven.techidaily.com/chat-with-gpt-powered-assistant-on-android-now-available-in-latest-app-release/"><u>Chat With GPT-Powered Assistant on Android - Now Available in Latest App Release</u></a></li>
<li><a href="https://win-luxury.techidaily.com/como-desconectar-onedrive-de-tu-sistema-operativo-windows-11-un-guia-detallada/"><u>Cómo Desconectar OneDrive De Tu Sistema Operativo Windows 11: Un Guía Detallada</u></a></li>
<li><a href="https://win-luxury.techidaily.com/customize-line-spacing-with-vertical-align-feature-in-emeditor-text-editor/"><u>Customize Line Spacing with Vertical Align Feature in EmEditor Text Editor</u></a></li>
<li><a href="https://extra-hints.techidaily.com/expert-analysis-of-samsungs-2023-photo-enhancement-suite/"><u>Expert Analysis of Samsung’s 2023 Photo Enhancement Suite</u></a></li>
<li><a href="https://pokemon-go-android.techidaily.com/how-to-fix-pokemon-go-route-not-working-on-honor-70-lite-5g-drfone-by-drfone-virtual-android/"><u>How to Fix Pokemon Go Route Not Working On Honor 70 Lite 5G? | Dr.fone</u></a></li>
<li><a href="https://android-location.techidaily.com/in-2024-getting-the-pokemon-go-gps-signal-not-found-11-error-in-tecno-phantom-v-flip-drfone-by-drfone-virtual/"><u>In 2024, Getting the Pokemon Go GPS Signal Not Found 11 Error in Tecno Phantom V Flip | Dr.fone</u></a></li>
<li><a href="https://win-luxury.techidaily.com/quick-and-simple-setup-for-concurrent-synology-nas-devices-linking/"><u>Quick and Simple Setup for Concurrent Synology NAS Devices Linking</u></a></li>
<li><a href="https://win-luxury.techidaily.com/step-by-step-tutorial-on-restoring-downloading-or-removing-lost-videos-from-your-nest-device/"><u>Step-by-Step Tutorial on Restoring, Downloading, or Removing Lost Videos From Your Nest Device</u></a></li>
<li><a href="https://facebook-video-content.techidaily.com/turn-fb-hd-videos-into-high-quality-mp4-free-online-method-unveiled-for-2024/"><u>Turn FB HD Videos Into High-Quality MP4 – Free Online Method Unveiled for 2024</u></a></li>
</ul></div>

<!-- affiliate ads begin -->
<span id="1424529">
					<video width="864" height="1536" style="cursor:pointer"
           poster="//a.impactradius-go.com/display-clicktoplayimage/1424529.png"
           onclick="if(!this.playClicked){this.play();this.setAttribute('controls',true);this.playClicked=true;}">
	   <source src="//a.impactradius-go.com/display-ad/16446-1424529">
	   <img src="//a.impactradius-go.com/display-clicktoplayimage/1424529.png" style="border: none; height: 100%; width: 100%; object-fit: contain">
	</video>
	<div style="width:540px;text-align:center"><a href="javascript:window.open(decodeURIComponent('https%3A%2F%2Flaganoo.pxf.io%2Fc%2F5597632%2F1424529%2F16446'), '_blank');void(0);">Click here</a></div>
</span>
<img height="0" width="0" src="https://imp.pxf.io/i/5597632/1424529/16446" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->


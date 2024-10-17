---
title: Master Your Documents with EmEditor, the Powerful Open-Source Text Editor
date: 2024-10-10T16:26:29.315Z
updated: 2024-10-17T16:15:54.650Z
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
<li><a href="https://youtube-tips.techidaily.com/n-2024-snappy-film-maker/"><u>[New] In 2024, Snappy Film Maker</u></a></li>
<li><a href="https://instagram-video-files.techidaily.com/2024-approved-capture-attention-with-perfectly-cropped-instagram-ready-videos/"><u>2024 Approved Capture Attention with Perfectly Cropped, Instagram-Ready Videos</u></a></li>
<li><a href="https://win-luxury.techidaily.com/comment-numeriser-avec-succes-vos-donnees-sur-un-hdd-externe-a-laide-dun-cable-ethernet-methode-la-plus-facile-a-adoption/"><u>Comment Numériser Avec Succès Vos Données Sur Un HDD Externe À L'aide D'un Câble Ethernet : Méthode La Plus Facile À Adoption</u></a></li>
<li><a href="https://fake-location.techidaily.com/complete-tutorial-to-use-gps-joystick-to-fake-gps-location-on-infinix-note-30i-drfone-by-drfone-virtual-android/"><u>Complete Tutorial to Use GPS Joystick to Fake GPS Location On Infinix Note 30i | Dr.fone</u></a></li>
<li><a href="https://win-luxury.techidaily.com/die-besten-portierbaren-tools-zum-umzug-von-samsung-daten-expertenanleitung-und-vergleiche/"><u>Die Besten Portierbaren Tools Zum Umzug Von Samsung Daten: Expertenanleitung Und Vergleiche</u></a></li>
<li><a href="https://win-luxury.techidaily.com/double-nas-capability-synology-tra-due-router-with-integrated-network-sharing-servers/"><u>Double NAS Capability Synology Tra Due Router with Integrated Network Sharing Servers</u></a></li>
<li><a href="https://easy-unlock-android.techidaily.com/how-to-remove-screen-lock-pin-on-oppo-f23-5g-like-a-pro-5-easy-ways-by-drfone-android/"><u>How To Remove Screen Lock PIN On Oppo F23 5G Like A Pro 5 Easy Ways</u></a></li>
<li><a href="https://sim-unlock.techidaily.com/in-2024-best-free-apple-iphone-14-pro-imei-checker-by-drfone-ios/"><u>In 2024, Best Free Apple iPhone 14 Pro IMEI Checker</u></a></li>
<li><a href="https://android-frp.techidaily.com/lava-yuva-2-pro-adb-format-tool-for-pc-vs-other-unlocking-tools-which-one-is-the-best-by-drfone-android/"><u>Lava Yuva 2 Pro ADB Format Tool for PC vs. Other Unlocking Tools Which One is the Best?</u></a></li>
<li><a href="https://discover-docs.techidaily.com/movavi-aiuta-a-convertire-i-tuoi-file-mkv-in-formato-wma-gratuitamente-su-internet/"><u>Movavi Aiuta a Convertire I Tuoi File MKV in Formato WMA Gratuitamente Su Internet</u></a></li>
<li><a href="https://win-luxury.techidaily.com/step-by-step-tutorial-installing-windows-11-on-usb-3-methods-revealed/"><u>Step-by-Step Tutorial: Installing Windows 11 on USB - 3 Methods Revealed</u></a></li>
<li><a href="https://techidaily.com/this-is-how-you-can-recover-deleted-pictures-from-honor-90-lite-by-fonelab-android-recover-pictures/"><u>This is how you can recover deleted pictures from Honor 90 Lite.</u></a></li>
</ul></div>

<!-- affiliate ads begin -->
<a href="https://aligracehair.sjv.io/c/5597632/1975841/19272" target="_top" id="1975841">
  <img src="//a.impactradius-go.com/display-ad/19272-1975841" border="0" alt="https://techidaily.com" width="728" height="90"/>
</a>
<img height="0" width="0" src="https://aligracehair.sjv.io/i/5597632/1975841/19272" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->


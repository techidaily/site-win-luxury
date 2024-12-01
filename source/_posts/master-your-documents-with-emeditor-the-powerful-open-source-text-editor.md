---
title: Master Your Documents with EmEditor, the Powerful Open-Source Text Editor
date: 2024-11-26T00:55:21.857Z
updated: 2024-11-30T19:59:35.895Z
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
<li><a href="https://screen-sharing-recording.techidaily.com/new-2024-approved-avoid-common-pitfalls-in-ppt-recording/"><u>[New] 2024 Approved Avoid Common Pitfalls in PPT Recording</u></a></li>
<li><a href="https://screen-mirroring-recording.techidaily.com/updated-top-tips-for-efficient-film-recording-on-pc-and-mobile-for-2024/"><u>[Updated] Top Tips for Efficient Film Recording on PC & Mobile for 2024</u></a></li>
<li><a href="https://win-premium.techidaily.com/comment-corriger-les-pannes-de-registre-sur-windows-11-guide-dexperts/"><u>Comment Corriger Les Pannes De Registre Sur Windows 11 : Guide D'Experts</u></a></li>
<li><a href="https://win-howtos.techidaily.com/disabling-unnecessary-processes-in-windows-10/"><u>Disabling Unnecessary Processes in Windows 10</u></a></li>
<li><a href="https://youtube-videos.techidaily.com/entry-level-landing-low-cost-profitable-youtube-platforms/"><u>Entry Level Landing Low-Cost, Profitable YouTube Platforms</u></a></li>
<li><a href="https://win-luxury.techidaily.com/fixing-the-unresponsive-select-all-feature-in-emeditor-a-troubleshooting-guide/"><u>Fixing the Unresponsive Select-All Feature in EmEditor: A Troubleshooting Guide</u></a></li>
<li><a href="https://win-luxury.techidaily.com/guide-retrieving-and-saving-pictures-on-your-ipad-via-icloud/"><u>Guide: Retrieving and Saving Pictures on Your iPad via iCloud</u></a></li>
<li><a href="https://tech-recovery.techidaily.com/how-to-easily-navigate-and-use-googles-measure-application-for-android-devices/"><u>How to Easily Navigate and Use Google's Measure Application for Android Devices</u></a></li>
<li><a href="https://win-luxury.techidaily.com/microsoft-2012-r22022/"><u>Microsoft サーバーを2012 R2から2022年へ完全対応アップグレード手順</u></a></li>
<li><a href="https://extra-approaches.techidaily.com/perfecting-your-linkedin-summary-statement-for-2024/"><u>Perfecting Your LinkedIn Summary Statement for 2024</u></a></li>
<li><a href="https://win-luxury.techidaily.com/resolving-hp-envys-unresponsive-power-key-problem-for-seamless-functionality/"><u>Resolving HP Envy's Unresponsive Power Key Problem for Seamless Functionality</u></a></li>
<li><a href="https://win-luxury.techidaily.com/restaurar-archivos-borrados-sin-complicaciones-con-winfr-para-sistemas-operativos-de-windows-version-facil/"><u>Restaurar Archivos Borrados Sin Complicaciones Con Winfr Para Sistemas Operativos De Windows: Versión Fácil</u></a></li>
<li><a href="https://win-luxury.techidaily.com/steps-to-restore-accidentally-erased-documents-on-windows-operating-systems-xp-10-11/"><u>Steps to Restore Accidentally Erased Documents on Windows Operating Systems (XP, 10, 11)</u></a></li>
<li><a href="https://win-luxury.techidaily.com/the-presence-of-chromium-can-improve-the-alloys-ability-to-withstand-stress-corrosion-cracking-and-reduce-sensitization-during-welding-which-could-otherwise338/"><u>The Presence of Chromium Can Improve the Alloy's Ability to Withstand Stress Corrosion Cracking and Reduce Sensitization During Welding, Which Could Otherwise Lead to Localized Areas of Weakness.</u></a></li>
<li><a href="https://common-error.techidaily.com/troubleshooting-fixes-why-your-pcs-touchpad-scroll-function-fails-in-windows-10/"><u>Troubleshooting Fixes: Why Your PC's Touchpad Scroll Function Fails in Windows 10</u></a></li>
<li><a href="https://techidaily.com/undelete-lost-data-from-itel-p55t-by-fonelab-android-recover-data/"><u>Undelete lost data from Itel P55T</u></a></li>
<li><a href="https://win-luxury.techidaily.com/verschieben-des-betriebssystems-auf-eine-neue-festplatte-professionelle-anleitung/"><u>Verschieben Des Betriebssystems Auf Eine Neue Festplatte – Professionelle Anleitung</u></a></li>
</ul></div>

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/pGHmqD53gc8?si=ymgHIB6Aa7_MoUUf" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->


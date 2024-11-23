---
title: Master Your Documents with EmEditor, the Powerful Open-Source Text Editor
date: 2024-11-15T22:30:22.457Z
updated: 2024-11-23T04:31:40.548Z
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
<li><a href="https://facebook-video-content.techidaily.com/new-in-2024-unveiling-tricky-feed-functions-more-vids-please/"><u>[New] In 2024, Unveiling Tricky Feed Functions More Vids Please</u></a></li>
<li><a href="https://fox-links.techidaily.com/new-video-excellence-via-apple-music-add-on/"><u>[New] Video Excellence via Apple Music Add-On</u></a></li>
<li><a href="https://youtube-zero.techidaily.com/approved-the-tug-of-war-youtube-licensing-versus-cc-principles/"><u>2024 Approved The Tug-of-War Youtube Licensing Versus CC Principles</u></a></li>
<li><a href="https://desktop-recording.techidaily.com/2024-approved-voice-recorder-mac-5-best-voice-recorders-for-mac-devices/"><u>2024 Approved Voice Recorder Mac - 5 Best Voice Recorders for Mac Devices</u></a></li>
<li><a href="https://win-luxury.techidaily.com/1728501053695-windows-7/"><u>如何在Windows 7中使用优秀软件自由克隆硬盘，避免重装的麻烦</u></a></li>
<li><a href="https://win-luxury.techidaily.com/comprehensive-tutorial-on-crafting-and-applying-a-recovery-disk-for-windows-11-systems/"><u>Comprehensive Tutorial on Crafting & Applying a Recovery Disk for Windows 11 Systems</u></a></li>
<li><a href="https://win-luxury.techidaily.com/copia-di-sicurezza-facile-e-completa-per-il-tuo-server-windows-server-2012-versione-disco-nuovo/"><u>Copia Di Sicurezza Facile E Completa per Il Tuo Server Windows Server 2012 Versione Disco NUOVO</u></a></li>
<li><a href="https://some-knowledge.techidaily.com/die-welt-der-4k-ultra-hd-videos-entschlusselt-ihr-umfassender-leitfaden/"><u>Die Welt Der 4K Ultra HD Videos Entschlüsselt: Ihr Umfassender Leitfaden</u></a></li>
<li><a href="https://graphic-issues.techidaily.com/fix-laptop-screen-wont-turn-on-issue/"><u>Fix Laptop Screen Won't Turn On Issue</u></a></li>
<li><a href="https://win-luxury.techidaily.com/gmail/"><u>Gmail簡易修復：如何迅速找回丢失的电子邮件</u></a></li>
<li><a href="https://unlock-android.techidaily.com/in-2024-full-tutorial-to-bypass-your-xiaomi-redmi-note-12-4g-face-lock-by-drfone-android/"><u>In 2024, Full Tutorial to Bypass Your Xiaomi Redmi Note 12 4G Face Lock?</u></a></li>
<li><a href="https://win-luxury.techidaily.com/professionelle-software-zum-kopieren-von-datentragern-unter-windows-server-2012/"><u>Professionelle Software Zum Kopieren Von Datenträgern Unter Windows Server 2012</u></a></li>
<li><a href="https://remote-screen-capture.techidaily.com/recording-success-the-ultimate-guide-for-facetime-conversations-for-2024/"><u>Recording Success The Ultimate Guide for FaceTime Conversations for 2024</u></a></li>
<li><a href="https://win-luxury.techidaily.com/seamless-steps-moving-your-windows-server-2022-iso-image-onto-a-usb-drive/"><u>Seamless Steps: Moving Your Windows Server 2022 ISO Image Onto a USB Drive</u></a></li>
<li><a href="https://win-luxury.techidaily.com/ssd-vs-hdd-fur-die-datensicherung-welches-externe-laufwerk-eignet-sich-besser/"><u>SSD vs HDD Für Die Datensicherung: Welches Externe Laufwerk Eignet Sich Besser?</u></a></li>
<li><a href="https://technical-tips.techidaily.com/unlocking-the-secrets-expert-reviews-on-sturdy-waterproof-phones-housings-for-this-year/"><u>Unlocking the Secrets: Expert Reviews on Sturdy Waterproof Phones Housings for This Year</u></a></li>
<li><a href="https://win-luxury.techidaily.com/wie-entfernt-man-das-wasserzeichen-fur-nicht-erfullte-anforderungen-auf-dem-betriebssystem-windows-11/"><u>Wie Entfernt Man Das Wasserzeichen Für Nicht Erfüllte Anforderungen Auf Dem Betriebssystem Windows 11?</u></a></li>
</ul></div>

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/AcAYRX0cwwA?si=DxqWU39vqksZbe1s&autoplay=1" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->


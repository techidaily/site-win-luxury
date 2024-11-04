---
title: Master Your Documents with EmEditor, the Powerful Open-Source Text Editor
date: 2024-11-02T21:31:50.956Z
updated: 2024-11-03T22:04:13.983Z
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
<li><a href="https://on-screen-recording.techidaily.com/new-achieving-perfect-time-lapses-with-ios-devices-for-2024/"><u>[New] Achieving Perfect Time-Lapses with iOS Devices for 2024</u></a></li>
<li><a href="https://article-helps.techidaily.com/updated-in-2024-gastronomic-glamour-top-7-ingredients-for-stunning-cooking-videos/"><u>[Updated] In 2024, Gastronomic Glamour Top 7 Ingredients for Stunning Cooking Videos</u></a></li>
<li><a href="https://win-luxury.techidaily.com/1728476602066-windows-11usb/"><u>透過修復工具來振興Windows 11版本：USB介面方法教學</u></a></li>
<li><a href="https://win-luxury.techidaily.com/comment-activer-et-gerer-le-raid-1-sur-windows-serveur-avec-un-outil-specialise/"><u>Comment Activer Et Gérer Le RAID 1 Sur Windows Serveur Avec Un Outil Spécialisé</u></a></li>
<li><a href="https://win-luxury.techidaily.com/comment-sauvegarder-en-toute-securite-vos-donnees-sur-une-carte-sd-avec-windows-guide-complet/"><u>Comment Sauvegarder en Toute Sécurité Vos Données Sur Une Carte SD Avec Windows: Guide Complet</u></a></li>
<li><a href="https://vp-tips.techidaily.com/complete-guide-to-sound-included-screen-capture-techniques-for-your-mac-computer/"><u>Complete Guide to Sound Included Screen Capture Techniques for Your Mac Computer</u></a></li>
<li><a href="https://win-luxury.techidaily.com/descubre-como-generar-e-inscribir-tu-propio-archivo-iso-usando-la-herramienta-aomei-backupper/"><u>Descubre Cómo Generar E Inscribir Tu Propio Archivo ISO Usando La Herramienta AOMEI Backupper</u></a></li>
<li><a href="https://win-luxury.techidaily.com/discover-hidden-files-on-windows-11-unlocking-secrets-with-four-methods/"><u>Discover Hidden Files on Windows 11: Unlocking Secrets with Four Methods</u></a></li>
<li><a href="https://blog-min.techidaily.com/how-to-remove-google-frp-lock-on-honor-90-by-drfone-android-unlock-remove-google-frp/"><u>How to remove Google FRP Lock on Honor 90</u></a></li>
<li><a href="https://bypass-frp.techidaily.com/in-2024-the-complete-guide-to-vivo-v30-lite-5g-frp-bypass-everything-you-need-to-know-by-drfone-android/"><u>In 2024, The Complete Guide to Vivo V30 Lite 5G FRP Bypass Everything You Need to Know</u></a></li>
<li><a href="https://win-luxury.techidaily.com/lideal-des-solutions-de-secours-pour-particuliers-trouvez-la/"><u>L'Idéal Des Solutions De Secours Pour Particuliers : Trouvez-La !</u></a></li>
<li><a href="https://extra-skills.techidaily.com/laughter-lab-steps-to-simple-sharp-memes-for-2024/"><u>Laughter Lab Steps to Simple, Sharp Memes for 2024</u></a></li>
<li><a href="https://article-helps.techidaily.com/macos-11-big-sur-compatibility-guide/"><u>MacOS 11 Big Sur Compatibility Guide</u></a></li>
<li><a href="https://tech-recovery.techidaily.com/mastering-the-art-of-gmail-alias-creating-a-new-online-persona/"><u>Mastering the Art of Gmail Alias: Creating a New Online Persona</u></a></li>
<li><a href="https://win-luxury.techidaily.com/praktischer-walkthrough-zur-installation-von-windows-server-2022-eine-schritt-fur-schritt-anleitung-erklart/"><u>Praktischer Walkthrough Zur Installation Von Windows Server 2022 - Eine Schritt-Für-Schritt-Anleitung Erklärt</u></a></li>
<li><a href="https://win-luxury.techidaily.com/rescuing-lost-snaps-a-guide-on-managing-and-purging-ios-deleted-photo-gallery/"><u>Rescuing Lost Snaps: A Guide on Managing and Purging iOS 'Deleted' Photo Gallery</u></a></li>
<li><a href="https://some-knowledge.techidaily.com/revive-access-to-your-account-a-quick-fix-for-forgotten-instagram-passwords/"><u>Revive Access to Your Account: A Quick Fix for Forgotten Instagram Passwords</u></a></li>
<li><a href="https://win-luxury.techidaily.com/step-by-step-guide-accessing-old-conversations-across-various-iphone-applications/"><u>Step-by-Step Guide: Accessing Old Conversations Across Various iPhone Applications</u></a></li>
<li><a href="https://facebook-record-videos.techidaily.com/the-early-birds-guide-to-youtube-skip-these-8-potential-pitfalls-for-2024/"><u>The Early Bird's Guide to YouTube Skip These 8 Potential Pitfalls for 2024</u></a></li>
</ul></div>

<!-- affiliate ads begin -->
<a href="https://appsumo.8odi.net/c/5597632/2075462/7443" target="_top" id="2075462">
  <img src="//a.impactradius-go.com/display-ad/7443-2075462" border="0" alt="https://techidaily.com" width="728" height="90"/>
</a>
<img height="0" width="0" src="https://appsumo.8odi.net/i/5597632/2075462/7443" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->


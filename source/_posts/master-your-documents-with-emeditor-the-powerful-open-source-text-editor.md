---
title: Master Your Documents with EmEditor, the Powerful Open-Source Text Editor
date: 2024-10-23T17:29:03.707Z
updated: 2024-10-29T00:39:06.800Z
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
<li><a href="https://instagram-video-files.techidaily.com/updated-insta-photo-carousel-magic/"><u>[Updated] Insta-Photo Carousel Magic</u></a></li>
<li><a href="https://facebook-video-share.techidaily.com/updated-pioneering-sustainability-transforming-metropolitan-environments/"><u>[Updated] Pioneering Sustainability Transforming Metropolitan Environments</u></a></li>
<li><a href="https://win-luxury.techidaily.com/7-systems/"><u>7 Systems</u></a></li>
<li><a href="https://win-luxury.techidaily.com/windows-11d/"><u>再び利用できるようにしましょう！Windows 11下の消えたDドライブの修復方法四連</u></a></li>
<li><a href="https://techidaily.com/all-things-you-need-to-know-about-wipe-datafactory-reset-for-tecno-spark-go-2023-drfone-by-drfone-reset-android-reset-android/"><u>All Things You Need to Know about Wipe Data/Factory Reset For Tecno Spark Go (2023) | Dr.fone</u></a></li>
<li><a href="https://win-luxury.techidaily.com/comment-recuperer-des-fichiers-chiffres-par-un-virus-sur-une-cle-usb/"><u>Comment Récupérer Des Fichiers Chiffrés Par Un Virus Sur Une Clé USB ?</u></a></li>
<li><a href="https://win-luxury.techidaily.com/como-crear-una-copia-de-seguridad-gratuita-para-la-unidad-d-en-windows-7-o-10/"><u>Cómo Crear Una Copia De Seguridad Gratuita Para La Unidad D en Windows 7 O 10</u></a></li>
<li><a href="https://buynow-tips.techidaily.com/ensuring-quality-streams-finding-the-best-spot-for-your-ps4-camera/"><u>Ensuring Quality Streams: Finding the Best Spot for Your PS4 Camera</u></a></li>
<li><a href="https://easy-unlock-android.techidaily.com/how-to-change-nokia-c32-lock-screen-password-by-drfone-android/"><u>How To Change Nokia C32 Lock Screen Password?</u></a></li>
<li><a href="https://android-location.techidaily.com/in-2024-10-fake-gps-location-apps-on-android-of-your-xiaomi-14-ultra-drfone-by-drfone-virtual/"><u>In 2024, 10 Fake GPS Location Apps on Android Of your Xiaomi 14 Ultra | Dr.fone</u></a></li>
<li><a href="https://instagram-video-files.techidaily.com/in-2024-rotate-for-results-instagram-video-alchemy/"><u>In 2024, Rotate for Results Instagram Video Alchemy</u></a></li>
<li><a href="https://win-luxury.techidaily.com/mastering-privacy-controls-protect-your-pictures-in-the-deleted-items-folder-on-iphone-ios-16-and-ios-ummary-17/"><u>Mastering Privacy Controls: Protect Your Pictures in the 'Deleted Items' Folder on iPhone (iOS 16 & iOS Ummary 17)</u></a></li>
<li><a href="https://hardware-reviews.techidaily.com/unveiling-gigabytes-high-end-ice-sports-design-golden-socketed-intel-z790-aorus-xtreme-x-motherboard-featuring-colossal-m2-cooling/"><u>Unveiling Gigabyte's High-End Ice Sports Design: Golden Socketed Intel Z790 Aorus Xtreme X Motherboard Featuring Colossal M.2 Cooling</u></a></li>
<li><a href="https://win-luxury.techidaily.com/1728469510750-windows-10/"><u>Windows 10でネットワークドライブ同期がうまくいかない場合、修正策と代わりのアプローチ</u></a></li>
</ul></div>

<!-- affiliate ads begin -->
<a href="https://appsumo.8odi.net/c/5597632/2144308/7443" target="_top" id="2144308">
  <img src="//a.impactradius-go.com/display-ad/7443-2144308" border="0" alt="https://techidaily.com" width="600" height="90"/>
</a>
<img height="0" width="0" src="https://appsumo.8odi.net/i/5597632/2144308/7443" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->


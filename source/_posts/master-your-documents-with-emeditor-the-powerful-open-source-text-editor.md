---
title: Master Your Documents with EmEditor, the Powerful Open-Source Text Editor
date: 2024-10-08T20:08:10.204Z
updated: 2024-10-10T21:17:05.190Z
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
<li><a href="https://youtube-blog.techidaily.com/iscovering-income-monetization-through-youtube-sponsored-videos/"><u>[New] Discovering Income Monetization Through YouTube Sponsored Videos?</u></a></li>
<li><a href="https://remote-screen-capture.techidaily.com/2024-approved-quick-guide-to-recording-presentations-using-webcam/"><u>2024 Approved Quick Guide to Recording Presentations Using Webcam</u></a></li>
<li><a href="https://android-location-track.techidaily.com/how-do-i-stop-someone-from-tracking-my-vivo-y100i-drfone-by-drfone-virtual-android/"><u>How Do I Stop Someone From Tracking My Vivo Y100i? | Dr.fone</u></a></li>
<li><a href="https://blog-min.techidaily.com/how-to-recover-lost-data-from-iphone-14-pro-drfone-by-drfone-ios-data-recovery-ios-data-recovery/"><u>How To Recover Lost Data from iPhone 14 Pro? | Dr.fone</u></a></li>
<li><a href="https://review-topics.techidaily.com/how-to-upgrade-iphone-12-mini-without-data-loss-drfone-by-drfone-ios-system-repair-ios-system-repair/"><u>How to Upgrade iPhone 12 mini without Data Loss? | Dr.fone</u></a></li>
<li><a href="https://review-topics.techidaily.com/in-2024-complete-tutorial-to-use-vpna-to-fake-gps-location-on-apple-iphone-15-drfone-by-drfone-virtual-ios/"><u>In 2024, Complete Tutorial to Use VPNa to Fake GPS Location On Apple iPhone 15 | Dr.fone</u></a></li>
<li><a href="https://on-screen-recording.techidaily.com/inaugural-vision-preservation-review-and-alternate-suggestions-for-2024/"><u>Inaugural Vision Preservation Review & Alternate Suggestions for 2024</u></a></li>
<li><a href="https://youtube-clips.techidaily.com/navigate-and-dominate-with-youtube-studios-advanced-editing-features/"><u>Navigate and Dominate with YouTube Studio's Advanced Editing Features</u></a></li>
<li><a href="https://win-luxury.techidaily.com/resolving-the-grey-screen-error-while-editing-pages-on-flipprogram-expert-solutions/"><u>Resolving the Grey Screen Error While Editing Pages on FlipProgram - Expert Solutions</u></a></li>
<li><a href="https://win-dash.techidaily.com/1722964231314-seamless-driver-update-for-the-amd-ryzen-5-2500u-get-started-now/"><u>Seamless Driver Update for the AMD Ryzen 5 2500U: Get Started Now!</u></a></li>
<li><a href="https://win-luxury.techidaily.com/speed-up-your-reading-mastering-quick-flip-techniques-with-flipbuilder/"><u>Speed Up Your Reading: Mastering Quick Flip Techniques with FlipBuilder</u></a></li>
<li><a href="https://win-luxury.techidaily.com/top-rated-photo-design-software-can-you-trust-flipbuilder/"><u>Top Rated Photo Design Software: Can You Trust FlipBuilder?</u></a></li>
<li><a href="https://win-luxury.techidaily.com/troubleshooting-broken-hyperlinks-in-your-page-turner-ebooks-after-flipbuilder-conversion-tutorial/"><u>Troubleshooting Broken Hyperlinks in Your Page-Turner Ebooks After FlipBuilder Conversion Tutorial</u></a></li>
<li><a href="https://win-luxury.techidaily.com/uncovering-targeted-keywords-on-your-website-through-flipbook-analysis-techniques/"><u>Uncovering Targeted Keywords on Your Website Through FlipBook Analysis Techniques</u></a></li>
</ul></div>

<!-- affiliate ads begin -->
<a href="https://appsumo.8odi.net/c/5597632/2105870/7443" target="_top" id="2105870">
  <img src="//a.impactradius-go.com/display-ad/7443-2105870" border="0" alt="https://techidaily.com" width="728" height="90"/>
</a>
<img height="0" width="0" src="https://appsumo.8odi.net/i/5597632/2105870/7443" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->


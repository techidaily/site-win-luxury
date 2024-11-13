---
title: Master Your Documents with EmEditor, the Powerful Open-Source Text Editor
date: 2024-11-12T01:27:41.525Z
updated: 2024-11-13T01:06:43.689Z
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
<li><a href="https://fox-hovers.techidaily.com/new-2024-approved-benq-bl2711u-a-journey-through-professional-4k-display-tech/"><u>[New] 2024 Approved BenQ BL2711U - A Journey Through Professional 4K Display Tech</u></a></li>
<li><a href="https://fox-links.techidaily.com/new-in-2024-enhanced-virtual-storefronts-analysis/"><u>[New] In 2024, Enhanced Virtual Storefronts Analysis</u></a></li>
<li><a href="https://fox-links.techidaily.com/new-in-2024-visual-vanguard-cutting-edge-cinematographic-insights-year-of-24/"><u>[New] In 2024, Visual Vanguard Cutting-Edge Cinematographic Insights - Year of '24</u></a></li>
<li><a href="https://facebook-record-videos.techidaily.com/updated-prime-streamer-gear-essential-livestream-tools-unveiled/"><u>[Updated] Prime Streamer Gear Essential Livestream Tools Unveiled</u></a></li>
<li><a href="https://extra-guidance.techidaily.com/updated-sns-hdr-pro-review-is-it-worth-using-and-what-other-hdr-software-to-u/"><u>[Updated] SNS HDR Pro Review Is It Worth Using and What Other HDR Software to U</u></a></li>
<li><a href="https://tech-recovery.techidaily.com/best-7-kid-friendly-internet-games-to-keep-young-minds-busy/"><u>Best 7 Kid-Friendly Internet Games to Keep Young Minds Busy</u></a></li>
<li><a href="https://win-luxury.techidaily.com/1728506023921-bitlocker/"><u>BitLockerで暗号化されたハードドライブの複製 - 一番シンプルな方法</u></a></li>
<li><a href="https://win-luxury.techidaily.com/come-trovare-e-riesumare-una-cartella-sparita-in-windows-10-o-11-guida-dettagliata/"><u>Come Trovare E Riesumare Una Cartella Sparita in Windows 10 O 11: Guida Dettagliata</u></a></li>
<li><a href="https://win-luxury.techidaily.com/guida-allidentificazione-e-alla-corretta-configurazione-del-disco-sconosciuto-della-serie-wd-per-un-funzionamento-ottimale/"><u>Guida All'Identificazione E Alla Corretta Configurazione Del Disco Sconosciuto Della Serie WD per Un Funzionamento Ottimale</u></a></li>
<li><a href="https://apple-account.techidaily.com/how-to-delete-icloud-account-on-iphone-14-without-password-by-drfone-ios/"><u>How to Delete iCloud Account On iPhone 14 without Password?</u></a></li>
<li><a href="https://win-luxury.techidaily.com/how-to-reset-your-win111087-computer-before-selling-it-detailed-explanation/"><u>How to Reset Your Win11/10/8/7 Computer Before Selling It - Detailed Explanation</u></a></li>
<li><a href="https://win-luxury.techidaily.com/safe-techniques-for-data-retrieval-from-cfast-cards/"><u>Safe Techniques for Data Retrieval From CFast Cards</u></a></li>
<li><a href="https://win-luxury.techidaily.com/schnelle-moglichkeiten-die-formatierung-ruckgangig-zu-machen-entdecken-sie-3-effektive-strategien/"><u>Schnelle Möglichkeiten, Die Formatierung Rückgängig Zu Machen - Entdecken Sie 3 Effektive Strategien!</u></a></li>
<li><a href="https://youtube-zero.techidaily.com/mlining-your-youtube-editing-with-imovie-tools/"><u>Streamlining Your YouTube Editing with iMovie Tools</u></a></li>
<li><a href="https://audio-shaping.techidaily.com/updated-in-2024-slow-motion-music-methods-keeping-rhythmic-patterns-consistent-in-volume-and-hertz/"><u>Updated In 2024, Slow-Motion Music Methods Keeping Rhythmic Patterns Consistent in Volume and Hertz</u></a></li>
<li><a href="https://win-luxury.techidaily.com/windows-10-ntfs/"><u>Windows 10で直面する「停止コード: NTFSファイルシステム」エラーを解決する手軽なトリプル戦略</u></a></li>
<li><a href="https://win-luxury.techidaily.com/windows-11-pccddvd4/"><u>Windows 11 PCでCD/DVD起動に失敗する:効果的な解決方法を4点</u></a></li>
</ul></div>

<!-- affiliate ads begin -->
<a href="https://appsumo.8odi.net/c/5597632/2082532/7443" target="_top" id="2082532">
  <img src="//a.impactradius-go.com/display-ad/7443-2082532" border="0" alt="https://techidaily.com" width="728" height="90"/>
</a>
<img height="0" width="0" src="https://appsumo.8odi.net/i/5597632/2082532/7443" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->


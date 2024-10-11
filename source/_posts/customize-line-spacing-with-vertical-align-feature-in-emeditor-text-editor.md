---
title: Customize Line Spacing with Vertical Align Feature in EmEditor Text Editor
date: 2024-10-06T02:39:46.766Z
updated: 2024-10-10T17:06:00.405Z
tags:
  - product
categories:
  - emeditor
thumbnail: https://thmb.techidaily.com/c45c79cad80f175d94c593fb8ff026b4aafae59d206eadb54e9f9c923883caa5.jpg
---

## Customize Line Spacing with Vertical Align Feature in EmEditor Text Editor

Viewing 1 post (of 1 total)

* Author  
Posts
* May 21, 2012 at 3:08 pm [#10375](https://tools.techidaily.com/emeditor/products/)  
[![](https://secure.gravatar.com/avatar/f29c043a3cc5c5dac8db4e62939893e9?s=80&d=identicon&r=g)Stefan](https://www.emeditor.com/forums/users/Stefan/ "View Stefan's profile")  
Participant  
Attention:  
 this script HAD contain an Bug:  
 IF an Line doesn’t had contain the delimiter  
 THEN this line was excluded from the output!  
 This was fixed at 13\. July 2012 in the code below.  
 Also there was added some improvements:  
 – prompt for the sign to be used as alignment. e.g. use one space or one dot.  
 – prompt for sing(s) to insert before this new alignment (i.e. at the place where the delimiter was found)  
 – prompt for sign(s) to insert right in front of the found delimiter  
 ————————-  
 For example you can align at an “M” sign by inserting spaces:  
O          Matches NUL character.  
	n      Matches a new line character  
	f      Matches a form feed character  
	r      Matches carriage return character  
	t      Matches a tab character  
	v      Matches a vertical tab character  
	[b]      Matches a backspace.  
	xxx      Matches the ASCII character expressed by the octal number xxx.  
	xdd      Matches the ASCII character expressed by the hex number dd.  
	uxxxx      Matches the ASCII character expressed by the UNICODE xxxx.  
O          Matches NUL character.  
	n          Matches a new line character  
	f          Matches a form feed character  
	r          Matches carriage return character  
	t          Matches a tab character  
	v          Matches a vertical tab character  
	[b]        Matches a backspace.  
	xxx        Matches the ASCII character expressed by the octal number xxx.  
	xdd        Matches the ASCII character expressed by the hex number dd.  
	uxxxx      Matches the ASCII character expressed by the UNICODE xxxx.  
 Or f.ex. at an semicolon by inserting dots  
 and two extra spaces in front and after the alignment:  
FPGA.rbf;247942;8/5/2011;none;7/12/2012  
	PDAManager.exe;136016;8/5/2011;1.0.0.1;7/12/2012  
	uImage;1126214;8/5/2011;none;7/12/2012  
	uRamdisk;6761355;8/5/2011;none;7/12/2012  
FPGA.rbf  ......  ;247942;8/5/2011;none;7/12/2012  
	PDAManager.exe    ;136016;8/5/2011;1.0.0.1;7/12/2012  
	uImage  ........  ;1126214;8/5/2011;none;7/12/2012  
	uRamdisk  ......  ;6761355;8/5/2011;none;7/12/2012  
 Do this two more times, with start at column 20 and then 40,  
 align with spaces, and also insert one extra space “in  
 front of the whole alignment”, you can get something like this:  
FPGA.rbf  ......  ;247942  ;8/5/2011;none    ;7/12/2012  
	PDAManager.exe    ;136016  ;8/5/2011;1.0.0.1 ;7/12/2012  
	uImage  ........  ;1126214 ;8/5/2011;none    ;7/12/2012  
	uRamdisk  ......  ;6761355 ;8/5/2011;none    ;7/12/2012  
 (again: sometime i will add code to automatically align at all found delimiters at once.  
 If i get the free time once…)  
 ————————-  
 Vertical align all selected lines at an given sign macro.  
 If you have an list with different word length at the beginning  
 and want to align the delimiter sign (e.g. “=” or “:”)  
 on all lines to the same column position,  
 then you may want to try this JavaScript macro.  
![](http://forentmp.lima-city.de/EmEditor_AlignLinesAtAnGivenSign.gif)  
 After that you may use other features to modify the text further.  
 For example:  
 – make an vertical zero-width selection to insert more text  
![](http://forentmp.lima-city.de/EmEditor_AlignLinesAtAnGivenSign_Usage.gif)  
 The code so far:  
 (Updated 19.06.2012: added “StartPos”, now you can align at other pos then at the first delimiter pos only.  
 OK, not well coded right now, i want to do that better sometimes (with an foreach-delim-IN-DelimS),  
 but it works as an interim solution right now already:  
 – just start this script the first time with StartPos=0.  
 – next enter StartPos=x, where ‘x’ is an position behind the first delimiter. Just take an look at the ruler for this.)  
    
	//http://www.emeditor.com/modules/newbb/viewtopic.php?topic_id=2044&forum=19  
	    
	// ===  Description/Purpose:  
	// vertical align lines at an given sign,  
	// e.g. at "=" or at ":", or "" or "." or "M", or...  
	    
	//Version 0.02, 13. July 2012  
	    
	    
	//Please note that i use Windows Line enders rn  
	    
	    
	//Settings:  
	o = document.selection;  
	    
	// Note: this script works on an text selection!  
	// So select some text before executing it.  
	if(o.IsEmpty == true){alert("This script works on an selection only.nnScript quits here."); quit();}  
	Redraw    = false;  
	Delim     = prompt("Enter sign to vertical align all lines at:", "=");  
	if (Delim == ""){quit();}  
	    
	//Not nice coded, but by entering the start pos you can align at several different positions.  
	//Or just skip an delimiter at the beginning and align only the next one.  
	StartPos  = prompt("Align  ""+Delim+""  only if found after this column: ", "0");  
	if (StartPos == ""){quit();}  
	    
	//Additional:  
	sInsert = prompt("Enter ONE sign to use as alignment (default is one dot):",".");  
	if (sInsert == ""){sInsert = " ";}  
	    
	sBefore = prompt("Enter sign(s) to insert in front of the whole alignment:", "");  
	sAfter  = prompt("Enter sign(s) to insert additional right before the found delim ""+Delim+"" :","");  
	    
	    
	//Work on this lines:  
	LineBeg = o.GetTopPointY(eePosLogical);  
	LineEnd = o.GetBottomPointY(eePosLogical);  
	    
	//Get the lines and the col pos of the Delim into an array:  
	var aLinesArr = new Array();  
	var aDelimPos = new Array();  
	    
	//  
	for (var L=LineBeg, i=0; L<=LineEnd; L++){  
		sCuLi = document.GetLine(L);  
	 	aLinesArr[i] = sCuLi;  
		nDePos = sCuLi.indexOf(Delim, StartPos) +1;  
	 	aDelimPos[i] = nDePos;  
	 	i++;  

	//Sort the MaxColumn Array  
	// to find the longest right point of an Delim:  
	aDelimMax = aDelimPos.slice();  
	aDelimMax.sort(function(a,b){return a - b}).reverse();  
	nMaxPos = aDelimMax[0];  
	    
	//Modify the lines inside the array and write to an new Array:  
	var aOutArray = new Array();  
	for(L=0,E=aLinesArr.length;L<E;L++){  
		sLine = aLinesArr[L];  
		nPos  = aDelimPos[L];  
		if ((nPos > 0)&&(nPos <= nMaxPos)){  
			sOut = sLine.substring(0,nPos -1);  
			sOut += sBefore;  
			sOut += Array(nMaxPos - nPos +1).join(sInsert);  
			sOut += sAfter;  
			sOut += sLine.slice(nPos -1);  
		}else{  
			sOut = sLine;  

		aOutArray[L] = sOut;  

	    
	//Output the new Array:  
	o.text = aOutArray.join("rn");  
	Done by Stefan with the kind help of Google.  
 I use this to align CSV files or to align code at an equal sign.  
 Or to align copy & pasted text from an web page.
* Author  
Posts

Viewing 1 post (of 1 total)

* You must be logged in to reply to this topic.

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
<li><a href="https://facebook-video-content.techidaily.com/new-in-2024-profiling-success-a-step-by-step-guide/"><u>[New] In 2024, Profiling Success A Step-by-Step Guide</u></a></li>
<li><a href="https://desktop-recording.techidaily.com/updated-2024-approved-invisible-listeners-guide-6-clandestine-recording-apps-androidios/"><u>[Updated] 2024 Approved Invisible Listeners Guide 6 Clandestine Recording Apps (Android/iOS)</u></a></li>
<li><a href="https://win-luxury.techidaily.com/h265-hevc/"><u>最高の H.265 HEVC ビデオエディター推薦リスト</u></a></li>
<li><a href="https://digital-screen-recording.techidaily.com/capturing-every-moment-unveiling-5-exceptional-streamer-webcams-for-2024/"><u>Capturing Every Moment Unveiling 5 Exceptional Streamer Webcams for 2024</u></a></li>
<li><a href="https://tech-hub.techidaily.com/crafting-custom-sounds-in-a-daw-using-chatgpt-a-comprehensive-guide/"><u>Crafting Custom Sounds in a DAW Using ChatGPT: A Comprehensive Guide</u></a></li>
<li><a href="https://mondly-stories.techidaily.com/echoes-from-olympus-the-lingual-journey-of-greeks/"><u>Echoes From Olympus: The Lingual Journey of Greeks</u></a></li>
<li><a href="https://win-luxury.techidaily.com/guide-steps-to-successfully-downloading-content-from-jw-player-platforms/"><u>Guide: Steps to Successfully Downloading Content From JW Player Platforms</u></a></li>
<li><a href="https://win-luxury.techidaily.com/hassle-free-method-batch-convert-your-au-recordings-to-high-quality-wav-files-instantly/"><u>Hassle-Free Method: Batch Convert Your AU Recordings to High-Quality WAV Files Instantly</u></a></li>
<li><a href="https://win-luxury.techidaily.com/hevch265vlc/"><u>HEVC(H.265)をVLCメディアプレーヤー上で再生しにくい場合の解決策</u></a></li>
<li><a href="https://android-pokemon-go.techidaily.com/in-2024-all-you-need-to-know-about-mega-greninja-for-oppo-a78-5g-drfone-by-drfone-virtual-android/"><u>In 2024, All You Need To Know About Mega Greninja For Oppo A78 5G | Dr.fone</u></a></li>
<li><a href="https://android-pokemon-go.techidaily.com/in-2024-ipogo-will-be-the-new-ispoofer-on-xiaomi-14-ultra-drfone-by-drfone-virtual-android/"><u>In 2024, iPogo will be the new iSpoofer On Xiaomi 14 Ultra? | Dr.fone</u></a></li>
<li><a href="https://ios-unlock.techidaily.com/in-2024-passfab-iphone-13-backup-unlocker-top-4-alternatives-by-drfone-ios/"><u>In 2024, PassFab iPhone 13 Backup Unlocker Top 4 Alternatives</u></a></li>
<li><a href="https://win-luxury.techidaily.com/ipad-compatible-video-types-explained-a-guide-to-seamless-file-conversions/"><u>IPad Compatible Video Types Explained: A Guide to Seamless File Conversions</u></a></li>
<li><a href="https://win-luxury.techidaily.com/legitimate-wonderfox-dvd-ripping-solution-secure-your-copy-without-the-crack/"><u>Legitimate WonderFox DVD Ripping Solution – Secure Your Copy Without the Crack</u></a></li>
<li><a href="https://win-luxury.techidaily.com/master-the-art-of-opening-and-streaming-vob-movies-directly-from-your-windows-1011-device-tips-and-tricks-for-a-seamless-experience/"><u>Master the Art of Opening and Streaming VOB Movies Directly From Your Windows 10/11 Device: Tips & Tricks for a Seamless Experience</u></a></li>
<li><a href="https://win-luxury.techidaily.com/opening-swf-files-a-comprehensive-guide-for-pc-users/"><u>Opening SWF Files: A Comprehensive Guide for PC Users</u></a></li>
<li><a href="https://win11.techidaily.com/overcoming-hard-drive-not-installed-error-in-windows-11/"><u>Overcoming 'Hard Drive Not Installed' Error in Windows 11</u></a></li>
<li><a href="https://win-luxury.techidaily.com/seamless-guide-converting-and-ripping-dvds-into-divx-format/"><u>Seamless Guide: Converting & Ripping DVDs Into DivX Format</u></a></li>
<li><a href="https://extra-tips.techidaily.com/top-5-best-value-camcorders-for-sports-and-stunts/"><u>Top 5 Best Value Camcorders for Sports and Stunts</u></a></li>
</ul></div>

<!-- affiliate ads begin -->
<span id="1993645">
					<video width="576" height="240" style="cursor:pointer"
           poster="//a.impactradius-go.com/display-clicktoplayimage/1993645.png"
           onclick="if(!this.playClicked){this.play();this.setAttribute('controls',true);this.playClicked=true;}">
	   <source src="//a.impactradius-go.com/display-ad/22993-1993645">
	   <img src="//a.impactradius-go.com/display-clicktoplayimage/1993645.png" style="border: none; height: 100%; width: 100%; object-fit: contain">
	</video>
	<div style="width:360px;text-align:center"><a href="javascript:window.open(decodeURIComponent('https%3A%2F%2Fhomestyler.sjv.io%2Fc%2F5597632%2F1993645%2F22993'), '_blank');void(0);">Click here</a></div>
</span>
<img height="0" width="0" src="https://imp.pxf.io/i/5597632/1993645/22993" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->


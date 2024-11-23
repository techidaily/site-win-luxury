---
title: Customize Line Spacing with Vertical Align Feature in EmEditor Text Editor
date: 2024-11-18T01:40:28.343Z
updated: 2024-11-22T17:56:46.192Z
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
<li><a href="https://fox-glue.techidaily.com/new-in-2024-inside-track-to-superior-srt-upgrades/"><u>[New] In 2024, Inside Track to Superior SRT Upgrades</u></a></li>
<li><a href="https://extra-skills.techidaily.com/new-optimal-steadicam-choices-enhancing-professional-grade-dslr-footage/"><u>[New] Optimal Steadicam Choices Enhancing Professional-Grade DSLR Footage</u></a></li>
<li><a href="https://some-guidance.techidaily.com/new-the-ultimate-guide-to-picsarts-latest-features-rev-2024/"><u>[New] The Ultimate Guide to PicsArt's Latest Features, Rev. 2024</u></a></li>
<li><a href="https://article-files.techidaily.com/updated-in-2024-master-your-media-best-6-video-apps-for-macos-big-sur-users/"><u>[Updated] In 2024, Master Your Media Best 6 Video Apps for macOS Big Sur Users</u></a></li>
<li><a href="https://win-luxury.techidaily.com/1-effortless-iphone-synchronization-two-methods-beyond-using-itunes/"><u>1. Effortless iPhone Synchronization: Two Methods Beyond Using iTunes</u></a></li>
<li><a href="https://some-knowledge.techidaily.com/2024-approved-from-basic-to-advanced-your-guide-to-system-advancements/"><u>2024 Approved From Basic to Advanced Your Guide to System Advancements</u></a></li>
<li><a href="https://win-luxury.techidaily.com/er-two-effective-approaches/"><u>Er: Two Effective Approaches</u></a></li>
<li><a href="https://win-luxury.techidaily.com/fehlerbehebung-fur-windows-migrationshilfe-losungsansatze-fur-haufig-auftretende-probleme/"><u>Fehlerbehebung Für Windows-Migrationshilfe: Lösungsansätze Für Häufig Auftretende Probleme</u></a></li>
<li><a href="https://win-howtos.techidaily.com/how-to-fix-nier-automata-crashes-in-pc-gaming-a-comprehensive-guide/"><u>How to Fix Nier: Automata Crashes in PC Gaming – A Comprehensive Guide</u></a></li>
<li><a href="https://fox-blue.techidaily.com/in-2024-groundwork-for-animate-infographic-creation/"><u>In 2024, Groundwork for Animate Infographic Creation</u></a></li>
<li><a href="https://android-unlock.techidaily.com/in-2024-pattern-locks-are-unsafe-secure-your-gionee-f3-pro-phone-now-with-these-tips-by-drfone-android/"><u>In 2024, Pattern Locks Are Unsafe Secure Your Gionee F3 Pro Phone Now with These Tips</u></a></li>
<li><a href="https://win-luxury.techidaily.com/klons-de-hardvaste-platte-van-windows-server-2012-r2-2-goede-methoden/"><u>Klons De Hardvaste Platte Van Windows Server 2012 R2 - 2 Goede Methoden</u></a></li>
<li><a href="https://win-luxury.techidaily.com/procreate-ipad-transferieren-and-tipps/"><u>Procreate, iPad, Transferieren, and Tipps.</u></a></li>
<li><a href="https://extra-tips.techidaily.com/professional-looking-shots-at-home-top-5-must-try-tips/"><u>Professional-Looking Shots at Home – Top 5 Must-Try Tips</u></a></li>
<li><a href="https://win-luxury.techidaily.com/schritt-fur-schritt-leitfaden-zur-einrichtung-und-verwendung-von-hyper-vs-erweiterter-sitzung-in-microsoft-windows/"><u>Schritt-Für-Schritt-Leitfaden Zur Einrichtung Und Verwendung Von Hyper-V's Erweiterter Sitzung in Microsoft Windows</u></a></li>
<li><a href="https://win-luxury.techidaily.com/the-complete-handbook-of-retrieving-lost-data-from-discs-advanced-strategies-and-steps-for-cddvd-recovery/"><u>The Complete Handbook of Retrieving Lost Data From Discs: Advanced Strategies and Steps for CD/DVD Recovery</u></a></li>
<li><a href="https://win-luxury.techidaily.com/wiederherstellung-der-hauptpartition-die-versehentlich-geloscht-wurde-auf-windows-11/"><u>Wiederherstellung Der Hauptpartition, Die Versehentlich Gelöscht Wurde, Auf Windows 11</u></a></li>
</ul></div>

<!-- affiliate ads begin -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/BmegThMdrJE?si=rILo1FJb9DgnPljV&autoplay=1" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<!-- affiliate ads end -->


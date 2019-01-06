---
layout: post
title: Remove Acrobat X Context Menu Entries and Outlook PDF Maker Plug-in
date: 2012-08-17 07:15
categories: 
tags: [acrobat, adobe, Uncategorized]
---

To remove the context menu entries:<br><span>regsvr32 /u "C:Program Files (x86)AdobeAcrobat 10.0Acrobat ElementsContextMenu.dll"</span><br><br>
Also run this for 64-bit Windows:<br><span>regsvr32 /u "C:Program Files (x86)AdobeAcrobat 10.0Acrobat ElementsContextMenu64.dll"</span><br><br>
To remove Outlook PDF Maker:<br><span>regsvr32 /u "C:Program Files (x86)AdobeAcrobat 10.0PDFMakerMailOutlookPDFMOutlook.dll"</span>

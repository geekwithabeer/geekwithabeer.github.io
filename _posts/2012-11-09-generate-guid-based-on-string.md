---
layout: post
title: Generate GUID Based on String
date: 2012-11-09 06:12
categories: 
tags: [C#, guid, Uncategorized]
---

<span><span><span>new</span></span></span><span><span> </span></span><span><span><span>Guid</span></span></span><span><span>(System.Security.Cryptography.</span></span><span><span><span>MD5</span></span></span><span><span>.Create().ComputeHash(System.Text.</span></span><span><span><span>Encoding</span></span></span><span><span>.Default.GetBytes(input)));</span></span>

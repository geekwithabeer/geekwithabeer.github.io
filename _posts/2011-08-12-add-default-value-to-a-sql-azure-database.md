---
layout: post
title: Add Default Value to A SQL Azure Database
date: 2011-08-12 17:20
categories: 
tags: [azure, sql, Uncategorized]
---

ALTER TABLE [Table_Name] ADD CONSTRAINT [Constraint_Name] DEFAULT NEWID() FOR [COLUMN_NAME]

---
layout: post
title: PowerShell batch rename with a list
date: 2019/1/11
categories: 
tags: [powershell]
---

1. Run the following command in PowerShell:

    ```powershell
    gci | Select-Object -Property Name | Export-Csv .\rename.csv
    ```

1. Open _rename.csv_ file and delete the first row. Create a second column called _NewName_ and list the new names of files in the column. The final _rename.csv_ should look like the following:

    ```
    Name,NewName
    "File-1.txt", "File-One.txt"
    "File-2.txt", "File-Two.txt"
    ```
    
1. Run the following command in PowerShell:

    ```powershell
    foreach ($f in Import-Csv .\rename.csv) { Rename-Item -Path $f.Name -NewName $f.NewName }
    ```

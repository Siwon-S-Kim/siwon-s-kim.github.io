---
title: 'Importing scores csv file on ETL'
date: 2024-04-29
permalink: /posts/2024/04/blog-post-1/
tags:
  - computer
  - SNU ETL (Canvas LMS)
  - text encoding
---
This is article for TAs in SNU, or anyone using electronic learning system, 'Canvas LMS'.
Currently Canvas LMS has problem on uploading `.csv` files created with Excel, for updating
grades. This is just problem of text encoding. ETL imports and exports `.csv` file with encoding
`utf-8` but when we save `.csv` file with Excel, it saves with encoding: `ANSI`.
For those who needs deeper understanding look here:
[About encoding](https://theonemanitdepartment.wordpress.com/2014/12/15/the-absolute-minimum-everyone-working-with-data-absolutely-positively-must-know-about-file-types-encoding-delimiters-and-data-types-no-excuses/)

## How to import `.csv` scores on ETL worked on Excel-like software.
1. First row of csv file must be `Student`,`ID`,`SIS Login ID`,`Section` and scores to upload: 
   e.g. `midterm_question_1`, `midterm_question_2`,`total_score`.
3. After that, next rows are data of student corresponding to first row.
4. Filling all information, save csv file and open csv file with any text editor that can convert text encoding, e.g., text pad.
5. Convert file into `utf8`.
6. Upload .csv file and select columns you want to upload.
   
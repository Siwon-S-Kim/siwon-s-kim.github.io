---
title: 'Importing scores csv file on ETL'
date: 2024-04-29
permalink: /posts/2024/04/blog-post-1/
tags:
  - computer
  - SNU ETL (Canvas LMS)
  - text encoding
---

With new ETL, many would have suffered from uploading `.csv` file to ETL. Especially when if one worked student's scores on Excel. Long story short, this is problem of text encoding. ETL imports and exports `.csv` file with encoding `UTF-8 with BOM` (This is different from UTF-8 encoding, may not be relevant to topic though). When we save `.csv` file with Excel, it saves with encoding: ANSI and converting it with encoding utf8 or utf8 with BOM with text pad `save as` will solve problem. For those who needs deeper understanding look here: [About encoding](https://theonemanitdepartment.wordpress.com/2014/12/15/the-absolute-minimum-everyone-working-with-data-absolutely-positively-must-know-about-file-types-encoding-delimiters-and-data-types-no-excuses/)

## How to import `.csv` scores on ETL worked on Excel-like software.
### Delete everything unnecessary, and save with `.txt` with encoding "utf-8 with BOM".
1. get `.csv` from ETL
2. open it with Excel.
3. Delete every information that is not relevant to this upload: e.g. previous scores, total scores. For our case it is as follows:
   1. Delete 2nd and 3rd row, which corresponds to "Manual posting", Read only, possible points. i.e. delete every information except for first row(the header) and students.
   2. Delete every column after Section (any columns after the ones that holding student information)
4. Add scores for this upload. Column name at first row of the column and scores.
5. Save it as `.`.csv``. Ignore Excel's warning "some feature might not be saved".
6. Open it with text pad (메모장)
7. Do, save-as with file type :`.txt` and with encoding: UTF-8 with BOM
8. upload to ETL.
   
## Remark
- Any solution that does not change encoding of imported file would work. For example, if we edit imported `.csv` file with text editors, like notepad, notepad ++, Vim and vscode, it won't have problem. But this is almost same thing as entering scores in ETL website, and we need cleaning of our imported `.csv` file anyway(if we don't clean unnecessary columns, ETL ask you to select whether to ignore it or use it all by hand). 

- If one wants to use python pandas module for their work and one need utf-8 with BOM, then try saving `.csv` file with `encoding='utf_8_sig'` will do.

- But UTF-8 would work too on this case.
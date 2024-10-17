---
type: assignment
date: 2024-10-16T20:30:00-5:00
date_a1: 2024-10-16T20:30:00-5:00
date_c1: 2024-10-16T20:30:00-5:00
title: 'Assignment - 6 (K-nn, Decision Trees, & Random Forests)'
hide_from_announcments: false
due_event: 
    type: due
    date: 2024-10-24T23:69:00-6:00
    date_a1: 2024-10-24T23:59:00-5:00
    date_c1: 2024-10-24T23:59:00-5:00
    description: 'Assignment6 due'
---

# Assignment 06

Assignment 6 released on K-nn, Decision Trees, & Random Forests.
Here is the [notebook](https://github.com/tools4ds/ds701_fa2024_assignments/blob/main/assignments/assignment06/assignment6.ipynb).

### Special Note for Colab Users

If you are doing this homework on Colab, you will have to take these 3 extra steps:

1. Copy this [zipped test folder](https://github.com/tools4ds/ds701_fa2024_assignments/blob/main/assignments/assignment06/hw6-tests.rar)
   to your Colab local storage<br>
2. In colab run the following commands, <br>
   !pip install rarfile<br>
   !apt-get install unrar<br>
3. Copy the below code and run it in a cell after the pip installations:<br>
   import rarfile<br>
   import os<br>
   rar_file = 'hw6_tests.rar'<br>
   with rarfile.RarFile(rar_file) as rf:<br>
   &nbsp;&nbsp;&nbsp;&nbsp;rf.extractall('test')<br>
6. Add another code cell with `!pip install otter-grader`

The last grader.export cell will give you an error, however all other cells should run. Download your notebook from Colab and submit the .ipynb directly to Gradescope.

Good luck! Please reach out on Piazza with any questions or issues.

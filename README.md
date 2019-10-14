# Project 1e: Average Grade Calculator

You have been asked to write a script that pulls in student grades from multiple assignments and provides an average for each student. Each file will contain the student ID and a grade representing a single assignment. The output should simply show a single report of each student and their average grade.

The script, `gradecalc.py`, should: 

0. Create a dictionary to hold a student and a list of grades
1. Ask the user for a file name (if the user presses enter, break to step 6)
2. Open the requested file 
3. Iterate over each line in the file (each line will contain a student and a grade) 
4. For each line, create or append to a list of grades using the student id as the key in the grades dictionary
5. Repeat step 1
6. When done, iterate over each of the keys in your dictionary
7. For each key, retrieve the list of grades, average them, and then print out a line of the final report

Each line in the file will be in the format `student_id,grade`. When outputing the final report (i.e., line 7), you should print the id left-aligned within 20 spaces followed by the average right-aligned within 10 spaces with 1 decimal point. Total for each line should be 30 characters. Here's an example run with partial results: 
```
Enter file (blank to stop): grades-1.txt
Enter file (blank to stop): grades-2.txt
Enter file (blank to stop): grades-3.txt
Enter file (blank to stop):

alan.alda                 76.7
benny.barker              82.7
chloe.carter             100.0
...
```

## REQUIRED IMPLEMENTATION NOTES 

1. You MUST abstract your most useful logic by creating a function named `addgrade` that takes both the dictionary (your `grades` dictionary) and a string (a single line of text read from a grade file). The function should then add the grade to the dictionary as described in steps 3 & 4. Your main code will CALL this method inside of the line to perform steps 3 & 4 ONLY. The remainder of the logic should simply be part of the "main" script. So to reiterate, the following function MUST be in your code: 
``` 
        def addgrade(grades,line): 
            ...
``` 
2. Hint on step 4: you will want to "ask" the grades dictionary if the student id is `in` the dictionary. If so, you want to `append()` the grade and if not, you want to create a new list with that grade as the first item. Remember that if your student id is stored in a variable called `id` and the list is in the dictionary, it can be accessed using standard dictionary syntax like `grades[id]`. So assuming you have a new grade to add, you can append to the list of grades directly like this: `grades[id].append(newgrade)`. And remember that it is easy to create a list with a single value like this: `[123]`. So setting the value is likewise straightforward: `grades[id] = [newgrade]`

3. You MUST modify __all three__ of the grades files to add YOU and provide yourself with a grade for each assignment.

4. You MUST run your script against all three of the example grades files (after adding yourself) and redirect the output to `averages.txt`. In other words, you should run `python gradecalc.py > averages.txt` and enter the names of all three of the sample files into your prompts. Include `averages.txt` in your final submission. 

## LOGISTICS 

Same basic deal as with the homeworks. 

1. From your AIST2120 folder, run `git clone [URL]` to make a local copy of this assignment. 
2. DO THE WORK (create and complete any and all needed files)
3. TEST YOUR WORK A WHOLE LOT 
4. TEST IT SOME MORE LIKE YOU MEAN IT THIS TIME 
5. When done, run `git add .` 
6. Then run `git commit –m "type a clever message here"` 
7. Finally run `git push` to push your changes back up to GitHub 
8. Breathe a sigh of relief 

## OPTIONAL CHALLENGES 

1. Create a second version of the script, gradcalc2.py. This version should import the addgrade function from gradecalc (`from gradcalc import addgrade`). Import the os module, and instead of asking for file names, use the os.listdir() method to iterate over ALL of the files in the current folder. If the filename begins with "grades" and ends with ".txt", then you should automatically process it. Use the existing `addgrade()` function to avoid having to copy/paste so much from your original gradecalc.py script.

2. Improve the logic of `addgrade` so that it will append 1 __OR MORE__ grades. In other words, if the text file contains the id and three grades per line, add each to the list.

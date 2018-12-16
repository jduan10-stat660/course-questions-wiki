
## Week 3 Quiz Questions and Answers

In order to prepare your Week 3 Quiz submission, please edit ***this*** document to provide substantive questions for each Quiz Problem and SAS Recipe listed below, as well as answers to at least three questions raised.

All edits should conform to GitHub Markdown specifications (https://guides.github.com/features/mastering-markdown/) and should be committed to a branch named "week-3" in your fork of this repo. Then, after all edits have been made/committed, your Week 3 Quiz should be submitted by initiating a pull request using

- the master branch of the stat660/course_questions_wiki repo as the base fork and

- the week-3 branch of your version of the repo as the head fork.

The instructor will then review the pull request and make comments should further revision be needed. Then, after the contents of the pull request have been finalized without any merge conflicts, the instructor will merge the pull request.



********************************************************************************



[Course Textbook Chapter 5, Problem 1]
- Question (mphan12-stat660): Why is the label option turned on, yet the columns are still column names rather than label names in the table?
- Answer(jduan10-stat660): We need to write LABEL statement in the data step.
- Question (yli110-stat660): In the proc print procedure, what is the difference between ID statement and VAR statement?
- Answer (yli110-stat660): VAR lists the variables of the data set to be printed with obs (row number) at the far left, whereas ID lists the variables showing on the far left instead of obs.
- Question (whu8-stat660): Is observation number a default column in SAS?
- Question (jduan10-stat660): What happens if the variable in ID statement also appears in VAR statement?
- Answer (jduan10-stat660):  The output contains two columns for that variable.
- Question (llopez37-stat660) Are there options outside of just label and id?
- Question (anguyen152-stat660): What if the variables' names are "date" ,"on", "changed", "flight" ? Should the answer "d" be correct then ?



[Course Textbook Chapter 5, Problem 3]
- Question (mphan12-stat660): What is another way of select RANCH, SPLIT, or TWOSTORY?
- Answer (mphan12-stat660): Where style = 'RANCH' or style = 'SPLIT' or style = 'TWOSTORY'
- Question (yli110-stat660): What does IN operator do in the WHERE statement?
- Answer (yli110-stat660): In the WHERE statement, the IN operator enables yout to select variables based on several values.
- Question (whu8-stat660): What’s the difference between "in" and "="?
- Answer (whu8-stat660): They are used in different cases, '=' is used for a single value while 'in' is used for multiple values.
- Question (jduan10-stat660): How many WHERE statement can be written in a PROC PRINT step?
- Question (llopez37-stat660) How long can the where statement string be?
- Question (anguyen152-stat660): Why are quotation marks needed here ?
- Answer (anguyen152-stat660):Because character values must be enclosed in quotation marks and must be in the same case as in the data set.



[Course Textbook Chapter 5, Problem 4]
- Question (mphan12-stat660): How is the data set saved if out=calc instead of out= work.calc?
- Answer (mphan12-stat660): The calc data set will still be created in the temporary directory work.
- Question (yli110-stat660): What does the OUT= option do in the PROC SORT step?
- Answer (yli110-stat660): In PROC SORT step, the OUT= option specifies the outputed sorted data set. Without OUT= option, the original data set will be sorted.
- Question (whu8-stat660): Is semicolon needed between 'data' and 'out' statements? 
- Answer (whu8-stat660): Semicolon is not allowed between 'data' and 'out' statements.
- Question (jduan10-stat660): Does PROC SORT generate printed output?
- Answer (jduan10-stat660): No, PROC SORT doesn’t generate printed output.
- Question (llopez37-stat660) Is it possible to have the out statement save in a different library?
- Question (anguyen152-stat660): Can we sort a dataset by 2 or more variables ?



[Course Textbook Chapter 5, Problem 7]
- Question (mphan12-stat660): What correction must be made to have this script run without error?
- Answer (mphan12-stat660): The code should read: 
- - proc sort data=clinic.diabetes;
 - - - by age;
- - run;
- - proc print data=clinic.diabetes;
 - - - var age height weight pulse;
 - - - where sex='F';
- - run;
- Question (yli110-stat660): What happens if there's no BY statement in a PROC SORT step?
- Answer (jduan10-stat660): The dataset can not be sorted sucessfully because the criteria are missing.
- Question (whu8-stat660):Is 'by' statement necessary when using sort function?
- Answer (whu8-stat660): Yes. 
- Question (jduan10-stat660): How to remove the Obs column?
- Question (llopez37-stat660) what other format options are there? 
- Question (anguyen152-stat660): Doesn't SAS work step by step ? If step 1 fails, it still runs step 2 ?



[Course Textbook Chapter 5, Problem 9]
- Question (mphan12-stat660): What should you consider when writing mathematical expression?
- Answer (mphan12-stat660): Order of operation matters, apply PEMDAS rule in SAS. 
- Question (yli110-stat660): How to select rows based on several conditions?
- Question (whu8-stat660):If there are mulitiple "and","or",what would be the sequence of process?
- Answer (whu8-stat660): SAS will process the command by input sequence.
- Question (jduan10-stat660): How to test for multiple values of the same variable with WHERE statement?
- Question (llopez37-stat660) Is it possible for the string of and statements to cause issues with one another? 
- Answer (llopez37-stat660) Yes it goes by input order so if one conflicts there will be an error
- Question (anguyen152-stat660): Can we use "=" and "eq" in the same statement ?
- Answer (anguyen152-stat660): Yes. They both represent the same meaning



[Course Textbook Chapter 5, Problem 10]
- Question (mphan12-stat660): What does PROC PRINT display by default?
- Answer (mphan12-stat660): PROC PRINT displays all observations and variables in the data set, a column for observation numbers on the far left, and variables in the order in which they occur in the data set.
- Question (yli110-stat660): In the PROC PRINT step, how do you select columns and how do you select rows to be printed?
- Question (whu8-stat660):Will the second 'proc print' overwrite the result before?
- Question (jduan10-stat660): How to control which observations are printed?
- Answer (jduan10-stat660): We can add a WHERE statement to the PROC PRINT step.
- Question (llopez37-stat660) Can you sort through proc print? 
- Answer (llopez37-stat660) no, can only choose to print out which data set.
- Question (anguyen152-stat660): What's the PAGEBY statement used for (under PROC PRINT) ?
- Answer (anguyen152-stat660): Control page ejects that occur before a page is full



[Week 3 SAS Recipe: recipe_to_check_for_duplicates]
- Question (mphan12-stat660): How do you get the pairs of duplicate?
- Answer (mphan12-stat660): You can get duplicate pair by using the dupout statement:
- - proc sort nodupkey
- - -  data=FRPM1516_raw
- - -  out=_null_
- - -  dupout= _dup_    ;
- - - by County_Code District_Code School_Code    ;
- - run;
- Question (yli110-stat660): What are the definitions of duplicates in a SAS data set?
- Question (whu8-stat660):Is 'nodupkey' a global statement? 
- Answer (whu8-stat660): It's not a global statement.
- Question (jduan10-stat660): What's the code “nodupkey” for and what else can the out= option be set to other than “_null_”?
- Question (llopez37-stat660) Will it know if some duplicates are important and not just redundent?
- Question (anguyen152-stat660): Will the log window inform me if the dataset has duplicates or not ?



[Week 3 SAS Recipe: recipe_for_sorting_data]
- Question (mphan12-stat660): What does the descending option do?
- Answer (mphan12-stat660): Sorts by largest to smallest, or z to a on the variables in the by statement.
- Question (yli110-stat660): What happens if you don't specify OUT= option in a PROC SORT step? Is it good practice to do so? Why or why not?
- Question (whu8-stat660):What’s the default sort order in SAS?
- Answer (whu8-stat660): Ascending.
- Question (jduan10-stat660): How to sort the dataset by alphabetical order? 
- Question (jduan10-stat660): How to sort the dataset by alphabetical order?
- Question (llopez37-stat660) How granular can you get with the descending and ascending options? 
- Question (anguyen152-stat660): What is the “out=” command for?
- Answer (anguyen152-stat660): It prevents us from overriding the original data.



[Week 3 SAS Recipe: recipe_for_printing_values]
- Question (mphan12-stat660): What does ID statement do? 
- Answer (mphan12-stat660): ID statement specifies one or more variables to print instead of the observation number at the beginning of each row of the report.
- Question (yli110-stat660): Instead of PROC PRINT, what is the best way to look at a SAS data set interactively?
- Question (whu8-stat660):What are the two methods to check a data set information in SAS?
- Answer (whu8-stat660): 'Porc print' statement and explore function.
- Question (jduan10-stat660): Does the order of the list in “ID” statement matters?
- Answer (jduan10-stat660):  Yes, the id names are in order.
- Question (llopez37-stat660) Just as ID sorts which variables to print can we also add a new variable through ID?
- Answer (llopez37-stat660) No there is a method of adding variables and then printing it through ID
- Question (anguyen152-stat660): Can we obmit the ID statement ?



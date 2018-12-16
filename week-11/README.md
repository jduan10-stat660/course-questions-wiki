
## Week 11 Quiz Questions and Answers

In order to prepare your Week 11 Quiz submission, please edit ***this*** document to provide substantive questions for each Quiz Problem and SAS Recipe listed below, as well as answers to at least three questions raised.

All edits should conform to GitHub Markdown specifications (https://guides.github.com/features/mastering-markdown/) and should be committed to a branch named "week-11" in your fork of this repo. Then, after all edits have been made/committed, your Week 11 Quiz should be submitted by initiating a pull request using

- the master branch of the stat660/course_questions_wiki repo as the base fork and

- the week-11 branch of your version of the repo as the head fork.

The instructor will then review the pull request and make comments should further revision be needed. Then, after the contents of the pull request have been finalized without any merge conflicts, the instructor will merge the pull request.



********************************************************************************



[Course Textbook Chapter 15, Problem 1]
- Question (mphan12-stat660): How are DO loops useful?
- Answer (mphan12-stat660): DO loops process a group of statements repeatedly rather than once. This can greatly reduce the number of statements required for a repetitive calculation. DO loop enables you to achieve the same results with fewer statements.
- Question (whu8-stat660):Can DO loops be used in PROC steps?
- Answer (whu8-stat660):No.
- Question (anguyen152-stat660) : When to use DO loops ? 
- Answer (anguyen152-stat660) : When we need to iterate over parameters in an algorithm or indices in an array.
- Question (jduan10-stat660): Can we change the index variable within the DO Group?
- Answer (jduan10-stat660): No, we can’t.
* Question (yli110-stat660): Can DO loops be used with PROC step?
* Answer (yli110-stat660): No, DO loops are DATA step statements, and cannot be conjuaged with PROC steps.
- Question (llopez37-stat660) Is there a way to combine these steps like we do with nested do loops?
- Answer (llopez37-stat660) It seems like you cannot do this 



[Course Textbook Chapter 15, Problem 2]
- Question (mphan12-stat660): What are the possible expression of specification of index-variable?
- Answer (mphan12-stat660):Possible expressions are '='/'until'/'while' condition expressions.
- Question (whu8-stat660):What determins the number of iterations?
- Answer (whu8-stat660):The DO statement's stop valued determins the number of iterations.
- Question (anguyen152-stat660) : Why dont we need the "BY" increment statement sometimes in our DO loops ? 
- Answer (jduan10-stat660): BY increment specifies a positive or negative number (or an expression that yields a number) to control the incrementing of index-variable. 
- Question (jduan10-stat660): Does DO Loop step read data from external sources?
- Answer (jduan10-stat660): DO Loop step does not read data from an external source.
* Question (yli110-stat660): How is the number of iterations determined in the DO statement?
- Question (llopez37-stat660) It only tries to execute a plus one step but it does not count is that the case here? 
- Answer (llopez37-stat660) yes this is what google has explained that it attempts it but fails



[Course Textbook Chapter 15, Problem 3]
- Question (mphan12-stat660): How do you decrement a DO loop's index variable?
- Answer (mphan12-stat660): You can decrement a DO loop's index variable by specifying a negative value for the BY clause. For example, the specification in this iterative DO statement decreases the index variable by -1, resulting in values of 5, 4, 3, 2, and 1. 
- Question (whu8-stat660):What are the possible expression of specification of index-variable?
- Answer (whu8-stat660):It could be a value ranges or 'until'/'while' condition expression.
- Question (anguyen152-stat660) : Will the year values(1-15) will be included in the final dataset ? 
- Question (jduan10-stat660): What can we do to stop a loop?
- Answer (jduan10-stat660): Change the value of index variable or use LEAVE statement.
* Question (yli110-stat660): How do you avoid infinite loops in DO loops?
- Question (llopez37-stat660) could we replace the 10% with the by statement? 



[Course Textbook Chapter 15, Problem 4]
- Question (mphan12-stat660): What is the difference between the stored index value and stopped value of index?
- Question (whu8-stat660):Is the stored index value always the same as the stopped value of index?
- Question (anguyen152-stat660) : Why "do year=1990 to 2004;" but the stored value of year is 2005 ? 
- Answer (anguyen152-stat660) : At the end of the 15th iteration of the DO loop, the value for Year is incremented to 2005. Because this value exceeds the stop value, the DO loop ends. At the bottom of the DATA step, the current values are written to the data set.
- Question (jduan10-stat660): What value does the sum statement store?
- Answer (jduan10-stat660): The SUM statement stores the total value of the variables.
* Question (yli110-stat660): How does DO loop stopy?
* Answer (yli110-stat660): When the index variable has a value that exceeds the stop value in do loop, the loop will stop. However the index variable will be stored as it's latest number.
- Question (llopez37-stat660) would the output by year always be plus one? 
- Answer (llopez37-stat660) it seems that this is the case with compound type outputs



[Course Textbook Chapter 15, Problem 5]
- Question (mphan12-stat660): Can DO loops be written in PROC statements?
- Answer (mphan12-stat660): No, DO loops are DATA step statements therefore must between written between the DATA and RUN statements.
- Question (whu8-stat660):What's the difference bewtween last index stored value and last output index value?
- Question (anguyen152-stat660) : What's the function of the OUTPUT statement in this case ? 
- Answer (anguyen152-stat660) : The OUTPUT statement overrides the automatic output at the end of the DATA step. On the last iteration of the DO loop, the value of Year, 2004, is written to the data set.
- Question (jduan10-stat660): What will happen if I add output outside the Do loop?
* Question (yli110-stat660): How does the OUTPUT in DO loop change the stored value of the index variable?
* Answer (yli110-stat660): Without the OUTPUT statement, index variable exceeds the stop value, and the loop writes out the observation with which the index has already exceeds the stop value. With OUTPUT statement, on the other hand, writes observations out at end of each iteration, thus the last observation will include the index variable with the stop value.
- Question (llopez37-stat660) why is this one not outputting 2005?



[Course Textbook Chapter 15, Problem 6]
- Question (mphan12-stat660): When the does the DO statements stop?
- Answer (mphan12-stat660): When the logic becomes FALSE.
- Question (whu8-stat660):Is the number of observations based on the number of times the OUTPUT statement executes?
- Answer (whu8-stat660):Correct.
- Question (anguyen152-stat660) : How many observations will the data set Work.Earn contain without the OUTPUT statement ? 
- Question (jduan10-stat660): How to separate items in the do loop series?
- Answer (jduan10-stat660): Use comma to separate.
* Question (yli110-stat660): How does SAS determine the number of observations written out in the OUTPUT statement in DO loop?
- Question (llopez37-stat660) If this was a question based on year would it be 21 instead of 20?



[Course Textbook Chapter 15, Problem 7]
- Question (mphan12-stat660): What is Nesting DO loops?
- Answer (mphan12-stat660): Iterative DO statements can be executed within a DO loop. Putting a DO loop within a DO loop is called nesting.  In order for nested DO loops to execute correctly, you must assign a unique index-variable name in each iterative DO statement and END each DO loop with an END statment.
- Question (whu8-stat660):What's the use of nested Do loops?
- Question (anguyen152-stat660) :When will nested DO loops work ?
- Question (jduan10-stat660): What is the difference between DO WHILE and DO UNTIL?
* Question (yli110-stat660): When do you use nested DO loops?
- Question (llopez37-stat660) Would this be the only way to go about it or is this just the best method? 



[Course Textbook Chapter 15, Problem 8]
- Question (mphan12-stat660): How does the DO UNTIL statement executes?
- Answer (mphan12-stat660):The DO UNTIL statement executes a DO loop until the expression becomes true.  The DO UNTIL statements enable you to execute statements conditionally and that the iterative DO statement enables you to execute statements a set number of times, unconditionally.
- Question (whu8-stat660):Where is the do until condition evaluated in the loop?
- Answer (whu8-stat660):It's evaluated at the bottom of the loop,so the enclosed statement are always executed at least once.
- Question (anguyen152-stat660) : Does "DO WHILE" statement have its condition being evaluated at the bottom of the loop like the "DO UNTIL" statement ? 
- Answer (anguyen152-stat660) : No. DO WHILE loop is evaluated at the top of the loop, you specify the condition that must exist in order to execute the enclosed statements.
- Question (jduan10-stat660): Is there index variable in DO UNTIL?
* Question (yli110-stat660): What is the difference between DO UNTIL and DO WHILE?
- Question (llopez37-stat660) This is why it doesnt add a plus one to the 1 through 20 then correct? 



[Course Textbook Chapter 15, Problem 9]
- Question (mphan12-stat660): How does the DO WHILE statement execute?
- Answer (mphan12-stat660):  The DO WHILE statement executes DO loops conditionally. You can use the DO WHILE statement to execute a DO loop while the expression is true.
- Question (whu8-stat660):What's the difference between DO UNTIL and DO WHILE conditon?
- Answer (whu8-stat660):The DO UNTIL condition is evaluated at the bottom of the loop while the DO WHILE loop is evaluated at the top of the loop.
- Question (anguyen152-stat660) : What does "gt" in this statement "do until(Capital gt 500000)" mean ?
- Answer (anguyen152-stat660) : "gt" means "greater than"
- Question (jduan10-stat660): When does DO WHILE step stop?
* Question (yli110-stat660): How do you manipulate DO UNTIL and DO WHILE for them to produce the same results?
- Question (llopez37-stat660) is le less than or equal to? 



[Course Textbook Chapter 15, Problem 10]
- Question (mphan12-stat660): What is the difference between DO WHILE and DO UNTIL statements? 
- Answer (mphan12-stat660): The difference between the DO UNTIL and DO WHILE statements is that the DO WHILE expression is evaluated at the top of the DO loop. If the expression is false the first time it is evaluated, the DO loop never executes. 
- Question (whu8-stat660):Can we only put a equal sign in the DO UNTIL and DO WHILE condition?
- Answer (whu8-stat660):I don't think so.
- Question (anguyen152-stat660) : Does SAS have "DO WHEN" and "DO OVER" loops ?
- Answer (anguyen152-stat660) : No. Using "DO WHILE" and "DO UNTIL" instead
- Question (jduan10-stat660): Can we use do loop within another do loop?
* Question (yli110-stat660): What the difference of DO UNITL and DO WHILE in terms of the number of executions of the loop?
- Question (llopez37-stat660) how does the while versus until statement differ? 



[Week 11 SAS Recipe: ddl-and-dml-sql-queries]
- Question (mphan12-stat660): What is DDL and DML?
- Answer (mphan12-stat660): Data-definition-language (DDL) task, such as defining, obtaining, or modifying column information for a table.  And data-manipulation-language (DML) task, such as obtaining, creating, or modifying the rows of data in a table.
- Question (whu8-stat660):What is DDL and DML?
- Answer (whu8-stat660):DDL is the data-definition language, meaning they define, obtain, or modify column information in a table or delete a table entirely. DML is the data-manipulation language,meaning they obtain, create, modify or delete rows of data in a table.
- Question (anguyen152-stat660) : What if we want to change the values of a specific row in the iris dataset ? 
- Question (jduan10-stat660): How can we process date type columns in SQL?
* Question (yli110-stat660): What is the difference between DDL and DML?
- Question (llopez37-stat660) is this purely for aesthetics and ingesting the formats?



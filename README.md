# Case Study: Income Tax Collector


## Summary

Most of the chapters in this book include a case study that illustrates the software development process. This approach may seem overly elaborate for small programs, but it scales up well when programs become larger. The first case study develops a program that calculates income tax.

Each year, nearly everyone with an income faces the unpleasant task of computing his or her income tax return. If only it could be done as easily as suggested in this case study! We start with the customer request phase.

## Request

The customer requests a program that computes a person’s income tax.

## Instructions

This Case Study will walk you through the analysis, design, implementation, and testing of the program under study.

Click Next Step to get started!

## Grading

You will not be graded on this lab.

Analysis

Analysis often requires the programmer to learn some things about the problem domain, in this case, the relevant tax law. For the sake of simplicity, let’s assume the following tax laws:

All taxpayers are charged a flat tax rate of 20%.
All taxpayers are allowed a $10,000 standard deduction.
For each dependent, a taxpayer is allowed an additional $3,000 deduction.
Gross income must be entered to the nearest penny.
The income tax is expressed as a decimal number.
Another part of analysis determines what information the user will have to provide. In this case, the user inputs are gross income and number of dependents. The program calculates the income tax based on the inputs and the tax law and then displays the income tax. Figure 2-4 shows the proposed terminal-based interface.

The figure shows the user interface for the income tax calculator. Line 1: Enter the gross income, colon, 150000.00. Line 2: enter the number of dependents, colon, 3. Line 3: the income tax is $26200.0.
Figure 2-4 The user interface for the income tax calculator

Characters in italics indicate user inputs. The program prints the rest. The inclusion of an interface at this point is a good idea because it allows the customer and the programmer to discuss the intended program’s behavior in a context understandable to both.

Design

During analysis, we specify what a program is going to do. In the next phase, design, we describe how the program is going to do it. This usually involves writing an algorithm. In Chapter 1, we showed how to write algorithms in ordinary English. In fact, algorithms are more often written in a somewhat stylized version of English called pseudocode. Here is the pseudocode for our income tax program:

1. Input the gross income and number of dependents
2. Compute the taxable income using the formula
3. Taxable income = gross income - 10000 - (3000 * number of dependents)
4. Compute the income tax using the formula Tax = taxable income * 0.20
5. Print the tax
Although there are no precise rules governing the syntax of pseudocode, in your pseudocode you should strive to describe the essential elements of the program in a clear and concise manner. Note that this pseudocode closely resembles Python code, so the transition to the coding step should be straightforward.


Implementation (Coding)

Given the preceding pseudocode, an experienced programmer would now find it easy to write the corresponding Python program.

For a beginner, on the other hand, writing the code can be the most difficult part of the process. Although the program that follows is simple by most standards, do not expect to understand every bit of it at first.

Testing

Our income tax program can run as a script from an IDLE window. If there are no syntax errors, we will be able to enter a set of inputs and view the results. However, a single run without syntax errors and with correct outputs provides just a slight indication of a program’s correctness. Only thorough testing can build confidence that a program is working correctly. Testing is a deliberate process that requires some planning and discipline on the programmer’s part. It would be much easier to turn the program in after the first successful run to meet a deadline or to move on to the next assignment. But your grade, your job, or people’s lives might be affected by the slipshod testing of software.

Testing can be performed easily from an IDLE window. The programmer just loads the program repeatedly into the shell and enters different sets of inputs. The real challenge is coming up with sets of inputs that can reveal an error. An error at this point, also called a logic error or a design error, is an unexpected output. A correct program produces the expected output for any legitimate input. The tax calculator’s analysis does not provide a specification of what inputs are legitimate, but common sense indicates that they would be numbers greater than or equal to 0. Some of these inputs will produce outputs that are less than 0, but we will assume for now that these outputs are expected. Even though the range of the input numbers on a computer is finite, testing all of the possible combinations of inputs would be impractical. The challenge is to find a smaller set of inputs, called a test suite, from which we can conclude that the program will likely be correct for all inputs.

In the tax program, we try inputs of 0, 1, and 2 for the number of dependents. If the program works correctly with these, we can assume that it will work correctly with larger values. The test inputs for the gross income are a number equal to the standard deduction and a number twice that amount (10000 and 20000, respectively). These two values will show the cases of a minimum expected tax (0) and expected taxes that are less than or greater than 0. The program is run with each possible combination of the two inputs. Table 2-1 shows the possible combinations of inputs and the expected outputs in the test suite.

The table for the test suite for tax calculator program with three columns. The table has six rows with data values. The column headers are Number of Dependents, Gross Income and Expected Tax. The data values of first row, associated to their related headers are Number of Dependents - 0 ; Gross Income - 10000 ; Expected Tax - 0. The data values of second row, associated to their related headers are Number of Dependents - 1 ; Gross Income - 10000 ; Expected Tax - minus 600. The data values of third row, associated to their related headers are Number of Dependents - 2 ; Gross Income - 10000 ; Expected Tax - minus 1200. The data values of fourth row, associated to their related headers are Number of Dependents - 0 ; Gross Income - 20000 ; Expected Tax - 2000. The data values of fifth row, associated to their related headers are Number of Dependents - 1 ; Gross Income - 20000 ; Expected Tax - 1400.  The data values of sixth row, associated to their related headers are Number of Dependents - 2 ; Gross Income - 20000 ; Expected Tax - 800.
Table 2-1 The test suite for the tax calculator program

If there is a logic error in the code, it will almost certainly be caught using these data. Note that the negative outputs are not considered errors. We will see how to prevent such computations in the next chapter.

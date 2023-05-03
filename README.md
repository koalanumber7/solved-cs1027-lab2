Download Link: https://assignmentchef.com/product/solved-cs1027-lab2
<br>
<h1></h1>

<ul>

 <li>Create a sub-class of an existing class</li>

 <li>Identify cases of overriding methods and overloading methods</li>

 <li>Understand the purpose of the “super” keyword in inherited methods</li>

 <li>Observe and experiment with polymorphism and dynamic binding</li>

 <li>Use “instanceof” and casting to resolve invalid statements with polymorphism</li>

</ul>




<h1>Pre-Lab</h1>




<ul>

 <li>Create a new Java project called Lab2</li>

 <li>Download the files: <a href="https://www.csd.uwo.ca/courses/CS1027a/labs/lab02/BankAccount.java">java</a><a href="https://www.csd.uwo.ca/courses/CS1027a/labs/lab02/BankAccount.java">,</a> <a href="https://www.csd.uwo.ca/courses/CS1027a/labs/lab02/CheckingAccount.java">CheckingAccount.java</a><a href="https://www.csd.uwo.ca/courses/CS1027a/labs/lab02/CheckingAccount.java">,</a> <a href="https://www.csd.uwo.ca/courses/CS1027a/labs/lab02/TestBankAccounts.java">TestBankAccounts.java</a><a href="https://www.csd.uwo.ca/courses/CS1027a/labs/lab02/TestBankAccounts.java">,</a> <a href="https://www.csd.uwo.ca/courses/CS1027a/labs/lab02/BankMachine.java">BankMachine.java</a><a href="https://www.csd.uwo.ca/courses/CS1027a/labs/lab02/BankMachine.java">,</a> and <a href="https://www.csd.uwo.ca/courses/CS1027a/labs/lab02/AnswersLab2.txt">AnswersLab</a><a href="https://www.csd.uwo.ca/courses/CS1027a/labs/lab02/AnswersLab2.txt">2</a><a href="https://www.csd.uwo.ca/courses/CS1027a/labs/lab02/AnswersLab2.txt">.txt</a></li>

 <li>Save these downloaded files into the Lab2 src folder</li>

</ul>




<h1>Exercise 1 – Creating a sub-class</h1>




<ol>

 <li>Create a new SavingsAccount class in your project, which extends the class BankAccount.</li>

 <li>Besides the instance variables and methods inherited from class BankAccount, this class must contain one instance variable of type double called interestRate. We might need to create several objects of the new class SavingsAccount, each one with its own balance and interest rate. Should instance variable interestRate be declared as static? Write your answer in AnswersLab2.txt.</li>

 <li>This class must also contain the following methods:

  <ol>

   <li>constructor with two parameters of type double. The method signature is thus: public SavingsAccount(double initialAmount, double rate).</li>

  </ol></li>

</ol>

This constructor must initialize the interestRate instance variable with the value of rate and it must also initialize the instance variable balance of class BankAccount with the value of initialAmount (if you do not know how to do this, please review the lecture notes on inheritance. If you still need additional help, please see class CheckingAccount to see how to do this).

<ol>

 <li>public getter method called getInterestRate() that returns the value of interestRate.</li>

 <li>public method calculateInterest(), which calculates one month’s interest and adds this amount to the balance; the interest is computed by multiplying interestRate and the balance. How can you get the balance from BankAccount?</li>

</ol>

How do you add the interest to the balance of BankAccount? (If you are unsure about how to do this, please read class BankAccount.)

<ol>

 <li>public method toString(), which returns a string representation of the instance variables; this string must be of the form “SavingsAccount: balance $123, interest rate 0.12”.</li>

</ol>

<ol start="4">

 <li>Add <a href="https://www.csd.uwo.ca/courses/CS1027a/labs/lab02/main.txt">this test harness</a> (copy and paste it) to your SavingsAccount class.</li>

 <li>Run the program and write the output in AnswersLab2.txt.</li>

</ol>




<h1>Exercise 2 – Experimenting with inheritance</h1>




<ol>

 <li>Open TestBankAccounts.java. This class has a main method that creates several bank account objects of the three types: BankAccount, CheckingAccount, and SavingsAccount.</li>

 <li>In each step of this exercise, you will be adding statements to the main method and running it after each addition. Answer the questions at each step and write your answers in AnswersLab2.txt. If there is a compilation error, make sure you comment out the offending statement before advancing to the next step of this exercise.</li>

 <li>Which method(s) of the class CheckingAccount demonstrate overriding? Which demonstrate overloading?</li>

 <li>In the main method, add the statement bacc0 = chacc1; which makes the BankAccount variable bacc0 reference the CheckingAccount object referenced by chacc1. Is this legal? Why?</li>

 <li>Add the statement chacc1 = bacc1;. Is this legal? Why not? If not, comment it out.</li>

 <li>Add the statement BankAccount bacc2 = new CheckingAccount(200.0); then add the statement chacc1 = bacc2;. Fix this last statement using casting so that it compiles and runs.</li>

 <li>Add statements to invoke method deductFees(), without parameters, on all variables bacc1, chacc1, and sacc1. On which type of objects was this legal? Why?</li>

 <li>Try to fix the above compilation errors through casting:</li>

</ol>

((CheckingAccount)variable).deductFees(). Which compilation error(s) could be fixed this way? Which one(s) could not be fixed this way? Why?

<ol start="9">

 <li>If there are compilation errors (cannot be more than 1), comment out the line causing the error. Then run the program. Did the program run? If the program crashed, why did it crash?</li>

 <li>If the program crashed, comment out the statement that caused the program to crash.</li>

</ol>

Add the statement chacc1.deposit(100.0); Your program should compile and run.

<ol start="11">

 <li>Now make the following change to CheckingAccount.java: in the code for the deposit method, change deposit(amount); to deposit(amount); Compile and run. What was the runtime error?</li>

 <li>To understand why the program crashed, add a breakpoint in class TestBankAccounts at the line deposit(100.0); (review Lab 2 if you do not remember how to do this).</li>

 <li>Run the program using the debugger. The execution of the program will stop at the line where you added the breakpoint. Repeatedly press F5 to see how the execution of the program proceeds. How many times is the method deposit() invoked?</li>

 <li>Terminate the program by clicking on the red square in the tool bar at the top of Eclipse’s window.</li>

</ol>




<h1>Exercise 3 – Experimenting with polymorphism</h1>




<ol>

 <li>Open BankMachine.java and read over the code in its main()</li>

 <li>The program produces two compilation errors, one when invoking method getTransactionCount() and the other when invoking getInterestRate().</li>

</ol>

Explain why the compiler issues these two errors. Write your answer in AnswersLab2.txt.

<ol start="3">

 <li>In the statement String accountInfo = newAcc.toString(); just by looking at the code can you tell whether the method toString() being invoked is from SavingsAccount or from CheckingAccount? Explain your answer and write it in AnswersLab2.txt.</li>

 <li>Modify the code so that getTransactionCount() is invoked only if newAcc references an object of the class CheckingAccount, and newAcc.getInterestRate() is invoked only if newAcc references an object of the class SavingsAccount.</li>

 <li>Run the program and verify that it works correctly for both account types (run the program and type either ‘c’ or ‘s’ so the program prints a message indicting that an account has been created and it also prints information about the account including either the interest rate or the number of transactions).</li>

</ol>



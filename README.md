Download Link: https://assignmentchef.com/product/solved-cs-211-assignment-3-bomb-lab
<br>



<h1>1             Introduction</h1>

The purpose of Programming Assignment 3 (PA3) is for you to become familiar with x86IA32 Instruction Set Architecture (ISA). The nefarious Dr. Evil has planted a slew of binary bombs on our machines. A binary bomb is a program that consists of a sequence of phases. Each phase expects you to type a particular string on stdin. If you type the correct string, then the phase is defused and the bomb proceeds to the next phase. Otherwise, the bomb explodes by printing BOOM!!! and then terminating. The bomb is defused when every phase has been defused. There are too many bombs for us to deal with, so we are giving everyone a bomb to defuse. Your mission, which you have no choice but to accept, is to defuse your bomb before the due date. Good luck, and welcome to the bomb squad!

<h1>2             Instruction</h1>

The bombs were constructed specifically for <strong>32-bit </strong>machines and <strong>Linux </strong>operating system. You must do this assignment <strong>only on the iLab machines</strong>. You will not defuse the bomb otherwise and will not get credit.

Open an Internet Browser and go to the URL: <a href="http://assembly.cs.rutgers.edu:17200/">http://assembly.cs.rutgers.edu:17200</a>

This address is only visible when you are connected in the <strong>Rutgers Network</strong>. Fill the form up with your NetID and your email address to get your bomb package. The file that you will get is in the format bombN.tar, where N is your bomb ID, i.e. ID. If you havent downloaded it in the iLab machines, copy the file to there and untar your bomb into your home directory. You are not allowed to download <strong>no more than two bombs</strong>. Copy the bomb that you downloaded into your iLab account and work with it.

<h2>$ tar -xvf bombID.tar</h2>

It will create a directory bombID that should contain the following files:

<ol>

 <li>bomb: The executable binary bomb</li>

 <li>c: Source file with the bombs main routine</li>

 <li>README: File with the bomb ID and extra information</li>

</ol>

Your job is to defuse the bomb. You can use many tools to help you with this; please look at the tools section for some tips and ideas. The best way is to use a debugger to step through the disassembled binary. The bomb has <strong>9 phases</strong>. The phases get progressively harder to defuse, but the expertise you gain as you move from phase to phase should offset this difficulty. Nonetheless, the latter phases are not easy, so please dont wait until the last minute to start. The bomb ignores blank input lines. If you run your bomb with a command line argument, for example, <strong>$ ./bomb mysolution.txt</strong>

then it will read the input lines from mysolution.txt until it reaches EOF (end of file), and then switch over to stdin (standard input from the terminal). In a moment of weakness, Dr. Evil added this feature so you dont have to keep retyping the solutions to phases you have already defused. To avoid accidentally detonating the bomb, you will need to learn how to single-step through the assembly code and how to set breakpoints. You will also need to learn how to inspect both the registers and the memory states. One of the nice side-effects of doing the lab is that you will get very good at using a debugger. This is a crucial skill that will pay big dividends the rest of your career.

<strong>IMPORTANT</strong>: Every time that the bomb explodes, you will lose <strong>0.5 </strong>points. It is important that you use breakpoints and avoid those unnecessary explosions.

<h1>3             Checking your Work</h1>

We provided a webpage where you can check your work. Here you can access the scoreboard to verify how many points you have, up to which phase you have defused the bomb, and so on. Again, you have to be on the Rutgers network to access the above link.

<a href="http://assembly.cs.rutgers.edu:17200/scoreboard">http://assembly.cs.rutgers.edu:17200/scoreboard</a>

<h1>4             Tools</h1>

There are many ways of defusing your bomb. You can examine it in great detail without ever running the program, and figure out exactly what it does. This is a useful technique, but it not always easy to do. You can also run it under a debugger, watch what it does step by step, and use this information to defuse it. This is probably the fastest way of defusing it. We do make one request, please do not use brute force! You could write a program that will try every possible key to find the right one, but the number of possibilities is so large that you wont be able to try them all in time. There are many tools which are designed to help you figure out both how programs work, and what is wrong when they dont work. Here is a list of some of the tools you may find useful in analyzing your bomb, and hints on how to use them.

<ul>

 <li><strong>gdb: </strong>The GNU debugger is a command line debugger tool available on virtually every platform. You can trace through a program line by line, examine memory and registers, look at both the source code and assembly code (we are not giving you the source code for most of your bomb), set breakpoints, set memory watch points, and write scripts. Here are some tips for using gdb.

  <ul>

   <li>To keep the bomb from blowing up every time you type in a wrong input, youllwant to learn how to set breakpoints.</li>

   <li>For other documentation, type help at the gdb command prompt, or type mangdb, or info gdb at a Unix prompt. Some people also like to run gdb under gdb-mode in emacs.</li>

   <li><a href="http://csapp.cs.cmu.edu/public/students.html">The CS:APP Student Site</a> has a very handy gdb summary (there is also a more extensive tutorial)</li>

  </ul></li>

 <li><strong>objdump -t bomb: </strong>This will print out the bombs symbol table. The symbol table includes the names of all functions and global variables in the bomb, the names of all the functions the bomb calls, and their addresses. You may learn something by looking at the function names.</li>

 <li><strong>objdump -d bomb: </strong>Use this to disassemble all of the code in the bomb. You can also just look at individual functions. Reading the assembler code can tell you how the bomb works. Although objdump -d gives you a lot of information, it doesnt tell you the whole story.</li>

 <li><strong>strings -t x bomb: </strong>This utility will display the printable strings in your bomb and their offset within the bomb. Dont forget, the commands apropos and man are your friends.</li>

</ul>

k. Keep in mind that your final and midterm will test you based on the skills learned in this assignment.
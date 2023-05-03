Download Link: https://assignmentchef.com/product/solved-cs061-lab4-more-arrays
<br>
In today’s lab you will play around with arrays and loops a bit more, get some more practice with LDR, do some doubling down, and further explore the mysteries of console output.

<ul>

 <li><strong>Our Targets for This Week </strong></li>

</ul>

<ol>

 <li>Lab 3 review –  Exercise 01</li>

 <li>What a character! Exercise 02 3.       Bits and pieces  –   Exercises 03 – 04</li>

 <li>I rock!</li>

</ol>

<strong>3.1    Lab 3 review </strong>

You will be building on the skills you learned last week: prompts, sentinel-controlled loops, and arrays, so let’s start with a variation on last week’s array – this time storing the results of a calculation, rather than user input.

<strong><em>Remember to always open the Text Window of your simpl LC-3 emulator! </em></strong>

<h1>Exercise 01</h1>

Use .BLKW to set up an array of 10 values, starting at memory location x4000, as in lab 3.

Now <em>programmatically</em>​           ​ populate the array with the numbers 0 through 9 <em>(</em>​<u>​<em>note</em></u><u>​</u><em> – NOT the characters ‘0’ through ‘9’!)</em>​ – i.e. hard-code just the first value (0), then calculate the rest one at a time, storing them in the array as you go. ​<em>Remember the proper way of setting a register to 0! </em>

After you’ve stored them all, grab the ​<em><u>seventh</u></em>​ value (i.e. 6) and store it in R2.

<em>Clearly, you can’t access this location via a label, so you’ll need it’s actual address.  </em>

<em>How will you obtain that? And how will you use that address to get the value stored there? </em>

As always, step through your program and examine the values as they are stored in the array, and examine the final value stored in R2, to make sure your program works as expected.

<strong>3.2    What a character!  </strong>

<h1>Exercise 02</h1>

You’ll notice that Exercise 01 didn’t ask you to output to console the array you built.

Why not?

Because as you know by now, numbers are not digits!

So now go and add an output loop, making it output the ​<em>characters</em>​ corresponding to the ​<em>numbers</em> stored in your array, just as you learned to do in assignments 2 &amp; 3.

<strong>3.3    Bits and pieces …  </strong>

<h1>Exercise 03</h1>

Let’s try another modification of our well-used array program from Exercise 01:

This time, instead of calculating and storing the numbers from 0 to 9 in the array, calculate and store the first ten Finally, grab the seventh value (2<u>​<em>powers of 2</em></u><u>​</u>, starting with 2​6​) from the array, and store it in R​0​ = 1 in array index 0. 2.

In order to do this, you will have to figure out how to calculate powers of 2.

Some hints:

<ul>

 <li>Mathematically speaking: How do I obtain 2​<sup>n+1​</sup> if I have 2​<sup>n​</sup>?</li>

 <li>What LC-3 operation could I use to multiply a number by 2?</li>

</ul>




As always, place a breakpoint in your program, and step through it, examining the values as they are being stored in the array, and examine the final value stored in R2,  to make sure your program works as expected.

You already understand that you can’t simply output the values in the array to the console “as is”, so we have to manipulate them somehow to turn them into characters.

But this time all but the first four are <em><u>multi-digit numbers</u></em>​    <u>​</u> when represented as decimal values, so our trick from the last exercise won’t work – it can only convert the numbers from 0 to 9 into the single-digit ascii characters ‘0’ through ‘9’.

This is going to take some more effort to solve, so we’ll spread it out over a couple of labs &amp; assignments.

<h1>Exercise 04</h1>

The first step will be to output the 1’s and 0’s of a stored value as <em><u>16</u></em>​<em><u> ascii characters</u></em><u>​</u>:

But wait! … You already did this in your last assignment!

<ol start="2">

 <li>Make a copy of your assn 3 code and modify it so that it prints out the contents of register 2.</li>

 <li>Now copy your ex3 code into lab05_ex4.asm, and add in your new output code: drop it in after you load the 7​<sup>th​</sup> array value to R2.</li>

</ol>

At this point your program should print out 2^6 in binary format: <strong>b0000 0000 0100 0000 </strong>

So now we know how to print any number in binary format <em>(</em>​ <em>put the value in R2 and paste the binary print code)</em>​; and we also know how to write code that can build and traverse an array. It is time to combine our knowledge to print out all elements in the array!!

<ul>

 <li>You have an array that holds the powers of 2 from 2^0 to 2^9.</li>

</ul>

You have code that prints a (binary) value in R2 in a nicely formatted sequence of ascii 1’s and

0’s

So now modify your program so that it traverses the array of powers of 2 and prints out all 10 values:

<strong>b0000 0000 0000 0001 b0000 0000 0000 0010 b0000 0000 0000 0100 </strong><u>…</u><strong>. </strong>

<u>…</u><strong>. b0000 0001 0000 0000 b0000 0010 0000 0000 </strong>

<strong> </strong>

Keep your code clean and well organized, for example in pseudo-code it should look something like this:

<ol>

 <li>03: Prepare the binary array with successive powers of 2</li>

</ol>




<ol>

 <li>04: Load starting address of array into a base register (say R6) for each element in array load the value to R2</li>

</ol>

print the value in R2 (use ‘the code’)

end of program (HALT)

// program data<strong>                          </strong>
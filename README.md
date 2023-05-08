Download Link: https://assignmentchef.com/product/solved-programs-verify_hetero-c-to-verify-a-heterosquare
<br>
A heterosquare is a square matrix of size <em>n</em> x <em>n</em> with positive numbers from 1… n<sup>2</sup> arranged such that the numbers in any line (horizontal, vertical, and both main diagonals) sum to <em>different</em>values. You can read more about it in this <a href="https://en.wikipedia.org/wiki/Heterosquare">reference (Links to an external site.)Links to an external site.</a>.

For this assignment you will be writing a programs <strong>verify_hetero.c</strong>  to verify a heterosquare.

The program <strong>verify_hetero.c </strong>will be run as follows:

./verify_hetero &lt;filename&gt;

Where &lt;filename&gt; is the name of the file that contains the square that needs to be verified. The format of the file will be as follows:

<ul>

 <li>The first line will be a positive integer <em>n</em>for the number of rows/columns of the square. So the dimensions of the square are <em>n </em>x <em>n</em>.</li>

 <li>Every line after that represents a row in the magic square, starting with the first row. There will be <em>n</em>such lines where each line has <em>n</em> numbers(columns) separated by commas.</li>

</ul>

So for instance, a file containing a heterosquare of size 3 will have this format:

39,8,72,1,63,4,5




The program should read and parse the input file to construct a square using the struct provided in the skeleton code. You will need to dynamically allocate memory for the 2D array.

To verify the square is indeed a heterosquare you need to total up the lines for each row, each column, and the two main diagonals (top-left to bottom-right, and top-right to bottom-left) and store those line totals in an array. Next, pass the array to the insertion sort function discussed in the next paragraph. Finally, check if the sorted array contains any duplicate values, and if so, it’s not a heterosquare. <strong>The program should print <u>true</u> if the input file is a heterosquare, and <u>false</u> otherwise </strong>(keywords like right/wrong, valid/not valid, etc. should not be used).

The program implements insertion sort to put the line totals (integers) in ascending order, which will be used for verification of the heterosquare. Insertion sort performs in-place sorting on an array of integers. Using the array of unsorted integers, it iterates through that array growing the sorted list as each <u>un</u>sorted item is inserted into the sorted part of the array. Initially, the first integer in the array (at index 0) is in the sorted part and the rest of the integers are in the <u>un</u>sorted part. The integer at index 1 is then inserted into the sorted part by finding its where it belongs in the sorted list, shifting any larger values in the sorted list each one to the right to make room, and then assigning the integer being sorted to its element. This approach is repeated for all remaining integers in the unsorted part.

The sample run below shows the expected behavior of the program:

$ ./verify_heteroUsage: ./verify_hetero &lt;filename&gt;$ cat hetero-4.txt41,2,3,45,6,7,89,10,11,1213,14,16,15$ ./verify_hetero hetero-4.txttrue$ cat not-hetero-3.txt34,3,89,1,52,7,6$ ./verify_hetero not-hetero-3.txtfalseThe following assumptions can be made regarding the input file:

<ul>

 <li>The input file contains distinct integers from 1 to n<sup>2</sup></li>

 <li>The maximum number of characters possible in each line of input file is 100</li>

</ul>



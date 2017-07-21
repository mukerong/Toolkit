<hr />

<h2>Table of Contents</h2>

<ul>
<li><a href="#2-3">Python 2 or Python 3</a></li>
<li><a href="#basic">Basic Terminology</a></li>
<li><a href="#strings">Strings</a>

<ul>
<li><a href="#string-definition">Definition</a></li>
<li><a href="#string-operations">Operations </a></li>
<li><a href="#string-indexing">Indexing &amp; Slicing</a></li>
<li><a href="#string-functions">Functions</a></li>
<li><a href="#string-methods">Methods</a></li>
<li><a href="#string-formatting">Formatting</a></li>
</ul></li>
<li><a href="#numeric">Numeric Data</a>

<ul>
<li><a href="#numeric-types-conversion">Types &amp; Conversion</a></li>
<li><a href="#numeric-operators">Operators</a></li>
<li><a href="#numeric-function">Functions</a></li>
</ul></li>
<li><a href="#list">List</a>

<ul>
<li><a href="#list-definition">Definition &amp; Creation</a></li>
<li><a href="#list-indexing">Indexing &amp; Slicing</a></li>
<li><a href="#list-operators">Operators</a></li>
<li><a href="#list-functions">Functions</a></li>
<li><a href="#list-methods">Methods</a></li>
<li><a href="#list-comprehension">List Comprehension</a></li>
</ul></li>
<li><a href="#tuple">Tuple</a>

<ul>
<li><a href="#tuple-definition">Definition &amp; Creation</a></li>
<li><a href="#tuple-indexing">Indexing &amp; Slicing</a></li>
<li><a href="#tuple-operators">Operators</a></li>
<li><a href="#tuple-functions">Functions</a></li>
<li><a href="#tuple-methods">Methods</a></li>
</ul></li>
<li><a href="#dictionary">Dictionary</a>

<ul>
<li><a href="#dictionary-definition">Definition &amp; Creation</a></li>
<li><a href="#dictionary-indexing">Indexing &amp; Slicing</a></li>
<li><a href="#dictionary-operators">Operators</a></li>
<li><a href="#dictionary-functions">Functions</a></li>
<li><a href="#dictionary-methods">Methods</a></li>
</ul></li>
<li><a href="#file">Files</a>

<ul>
<li><a href="#file-open">Open</a></li>
<li><a href="#file-methods">Methods</a></li>
</ul></li>
<li><a href="#pipe">Pipes</a></li>
<li><a href="#condition">Conditions</a></li>
<li><a href="#if">if</a></li>
<li><a href="#while">while</a></li>
<li><a href="#for">for</a></li>
<li><a href="#function">Functions</a>

<ul>
<li><a href="#function-definition">Definition &amp; Creation</a></li>
<li><a href="#function-arguments">Arguments</a></li>
<li><a href="#lambda">map() &amp; lambda</a></li>
</ul></li>
<li><a href="#modules">Modules</a>

<ul>
<li><a href="#re">re</a></li>
<li><a href="#numpy">numpy</a></li>
<li><a href="#pandas">pandas</a></li>
</ul></li>
<li><a href="#exception-handling">Exception Handling</a></li>
<li><a href="#resources">Resources</a></li>
</ul>

<hr />

<p>Python is a kind of snake as well as a high-level programming language for general-purpose programming. Its code is very simple and clear. It is becoming the No.1 programming language in data industry.</p>

<hr />

<h3 id="2-3">Python 2 vs. Python 3</h3>

<p>By the time I started to learn Python, Python 3 has been used widely, so I use Python 3 directly. There are some differences between Python 2 and 3, but the basic syntax is the same. I will highlight the difference in my notes. </p>

<hr />

<h3 id="basic">Basic Terminology</h3>

<ul>
<li>Program - instructions that specifies how to perform a computation

<ul>
<li>input, output, math, conditional execution, repetition</li>
</ul></li>
<li>Bugs - programming errors

<ul>
<li>Syntax errors - Similar to grammar error in natural language</li>
<li>Runtime errors - Also called exceptions. They will not appear until program started running</li>
<li>Semantic errors - The program can run but does not do what it meant to</li>
</ul></li>
<li>Values - The basic thing a program works with. They have various types.

<ul>
<li>Use type() function to check the type of a value or a variable

<ul>
<li>e.g. type(3.2), type(&#8216;abc&#8217;)</li>
</ul></li>
</ul></li>
<li>Variables - They are names that refer to a value. Use <code>=</code> to assign value

<ul>
<li>Variables are case sensitive, so <code>a</code> is not equal to <code>A</code></li>
<li>For best practice, python variables are normally all lowercase</li>
<li>e.g. x = 5, pi = 3.14</li>
</ul></li>
<li>Build-in Keyword - When choose name for variables, Python will return error if the names are build-in keywords.

<ul>
<li>and, as, assert, break, class, continue, def, del, elif, else, except, exec, finally, for, from, global, if, import, in, is, lambda, not, or, pass, print, raise, return, try, while, with, yield</li>
<li>Note: In Python 3, exec is not a keyword, but nonlocal is.</li>
</ul></li>
<li>Operators - special symbols that represent computation

<ul>
<li>+, -, *, /, %, //</li>
<li>In Python 2, / will perform floor division when both of the operands are integers. In Python 3, / will return float and // will performs floor division.</li>
</ul></li>
<li>Expression - combination of values, variables and operators.

<ul>
<li>expression always has a value</li>
</ul></li>
<li>Statement - A unit of code that interpreter executes</li>
<li>Class - a logical grouping of data, functions and methods</li>
<li>Function - a piece of code that is called by name, can optionally return value and assign to a variable</li>
<li>Method - a piece of code that is called by name, is associated with an objective specifically</li>
<li>Indentation - whitespace or blocks

<ul>
<li>Python uses indentation to signal the beginning and ending of a statement</li>
<li>normally 4 spaces</li>
</ul></li>
<li>None - Python use <em>None</em> to show null value

<ul>
<li>to check whether a variable is None, use <em>is None</em></li>
</ul></li>
<li>Comments - Notes in programs that will not be executed.

<ul>
<li>One line comments use <em># This is comments</em></li>
<li>Multiple line comments use <em>&#8216;&#8217;&#8216;This is comments&#8217;&#8216;&#8217;</em></li>
</ul></li>
</ul>

<hr />

<h3 id="strings">Strings</h3>

<h4 id="string-definition">Definition</h4>

<p>A string is a collection of characters. Strings can be created with either single quotes (&#8216;) or double quotes (&quot;). There is no differences. If the text is more than one line, you need to use triple quotes (&#8217;&#8216;&#8217; or &#8220;&#8221;&quot;).</p>

<h4 id="string-operations">Operations</h4>

<p>Add</p>

<pre><code class="Python">&gt;&gt;&gt; a = 'apple'
&gt;&gt;&gt; b = 'banana'
&gt;&gt;&gt; a + b
'applebanana'
</code></pre>

<p>Concatenate</p>

<pre><code class="Python">&gt;&gt;&gt; fruit = 'apple ' 'banana ' 'orange '
&gt;&gt;&gt; fruit
'apple banana orange '
</code></pre>

<p>Repetition</p>

<pre><code class="Python">&gt;&gt;&gt; 'a' * 5
'aaaaa'
</code></pre>

<h4 id="string-indexing">Indexing &amp; Slicing</h4>

<p>Python supports strings indexing and slicing. Indexing means each character has its own index. Slicing means to extract a contiguous piece of a string. Python uses zero index, which means the first index starts from 0 instead of 1. Strings are immutable, which means they cannot be changed through indexing. </p>

<pre><code class="Python">&gt;&gt;&gt; a = 'apple'
&gt;&gt;&gt; a[0]
'a'
</code></pre>

<p>Use negative number can get the character from the end of the string.</p>

<pre><code class="Python">&gt;&gt;&gt; a = 'apple'
&gt;&gt;&gt; a[-1]
'e'
</code></pre>

<p>To get part of the string, you can use colon (:) to connect the index. The character with ending index will not be selected. </p>

<pre><code class="Python">&gt;&gt;&gt; a = 'apple'
&gt;&gt;&gt; a[0:2]
'ap'
</code></pre>

<p>You can omit the first or second index. Python will select from the beginning or ending of the string, respectively.</p>

<pre><code class="Python">&gt;&gt;&gt; a = 'apple'
&gt;&gt;&gt; a[:3]
'app'
&gt;&gt;&gt; a[4:]
'e'
&gt;&gt;&gt; a[:]
'apple'
</code></pre>

<h4 id="string-functions">Functions</h4>

<p>Functions can run on it own, like type(). Methods need to be run with an objective, like string.upper(). </p>

<p>Common String Functions</p>

<ul>
<li>len() - return the number of characters</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; len('apple')
5
</code></pre>

<h4 id="string-methods">Methods</h4>

<ul>
<li>string.split(maxsplit) - create a list from characters in a string

<ul>
<li>maxsplit argument - defines how many times you want to split the string</li>
</ul></li>
</ul>

<pre><code class="Python"> &gt;&gt;&gt; str = 'I am learning Python'
 &gt;&gt;&gt; str.split(' ') # split using spaces
 ['I', 'am', 'learning', 'Python']
</code></pre>

<pre><code class="Python"> &gt;&gt;&gt; str = 'I am learning Python'
 &gt;&gt;&gt; str.split(' ', maxsplit = 1)
 ['I', 'am learning Python']
</code></pre>

<ul>
<li>deliminator.join(string) - opposite of split() method. create a string from a list</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; meat = ['chicken', 'pork', 'beef']
&gt;&gt;&gt; '&amp;'.join(meat) # join them together with &amp;
'chicken&amp;pork&amp;beef'
</code></pre>

<ul>
<li>string.upper() &amp; string.lower()</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; a = 'apple'
&gt;&gt;&gt; b = a.upper()
&gt;&gt;&gt; b
'APPLE'
&gt;&gt;&gt; b.lower()
'apple'
</code></pre>

<ul>
<li>string.isalnum, string.isalpha, string.isdigit, string.islower, string.isspace, string.istitle, string.isupper

<ul>
<li>No arguments. Return 1 if True</li>
</ul></li>
<li><a href="https://www.tutorialspoint.com/python/string_strip.htm">string.strip()</a></li>
</ul>

<h4 id="string-formatting">Formatting</h4>

<p>In Python, you can use print() function (Python 3) and print command (Python 2) - quickly show the output.</p>

<pre><code class="Python">&gt;&gt;&gt; print('string')
string
&gt;&gt;&gt; print (1 + 2)
3
</code></pre>

<p>You can also format the string you want to print using the percentage operator (%) in both Python 2 and Python 3, or {} in Python 3 only.</p>

<pre><code class="Python">&gt;&gt;&gt; '%s, %s' % ('one', 'two')
'one, two'
&gt;&gt;&gt; '{}'.format(2)
2
&gt;&gt;&gt; '{1} {0}'.format(1, 2) # only available in Python 3
'2 1'
</code></pre>

<p>The &#8216;s&#8217; after % is the types of the data you are print. &#8216;s&#8217; stands for string. Below are some other key character in old formatting. These are only useful in the old formatting. For more details about the new formatting in Python 3, you can use <a href="https://docs.python.org/3.1/library/string.html#string-formatting">this document</a>.</p>

<ul>
<li>d/i - decimal integer</li>
<li>u - unsigned integer</li>
<li>o - octal integer</li>
<li>h/H - hexadecimal integer</li>
<li>f - floating point number</li>
<li>e/E - floating point number with exponential notation</li>
<li>g/G - floating point number with &#8216;optimal&#8217; notation</li>
<li>s - string</li>
<li>c - single character</li>
</ul>

<p>To make the formatting easier to read, you can use <a href="#dictionary">dictionary</a>. </p>

<pre><code class="Python">&gt;&gt;&gt; dict = {'one': 1, 'two': 2}
&gt;&gt;&gt; '% (one)d is smaller than % (two)d' % dict
'1 is smaller than 2'.
&gt;&gt;&gt; '{one} is smaller than {two}'.format(**dict)
'1 is smaller than 2'
</code></pre>

<hr />

<h3 id="numeric">Numeric Data</h3>

<h4 id="numeric-types-conversion">Types &amp; Conversion</h4>

<ul>
<li>Integers

<ul>
<li>range from &#8211;2 billion to 2 billion</li>
<li>int() # no rounding</li>
</ul></li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; int(3.9)
3
</code></pre>

<ul>
<li>Long Integers

<ul>
<li>need to use long integers if the number is out of integer range</li>
<li>need to use letter &#8216;L&#8217; to make number long integers (e.g. 27L)</li>
<li>will slow down the program</li>
<li>long() # only in Python 2</li>
</ul></li>
<li>Float

<ul>
<li>at most 15 to 16 digits, use long integers if needed</li>
<li>To use exponential notation: 1e3 (aka. 1000)</li>
<li>float()</li>
</ul></li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; float(3)
3.0
</code></pre>

<ul>
<li>Complex

<ul>
<li>use complex function to enter complex number (e.g. complex(1.2, 7)) or use &#8216;j&#8217; (e.g. 1.2 + 7j)</li>
<li>complex()</li>
</ul></li>
</ul>

<h4 id="numeric-operators">Operators</h4>

<ul>
<li>+</li>
<li>-</li>
<li>*</li>
<li>/ # Python 2: the result will be integer only all operands are integer</li>
<li>** # exponentiation</li>
<li>%</li>
<li>// # floor division, only in Python 3</li>
<li>&gt;&gt; # right bit shift</li>
<li>&lt;&lt; # left bit shift</li>
</ul>

<h4 id="numeric-function">Function</h4>

<ul>
<li>abs()</li>
<li>round()</li>
<li>divmod()</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; divmod(9, 4)
(2, 1)
</code></pre>

<ul>
<li>pow()

<ul>
<li>alternative way to use exponentiation</li>
</ul></li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; pow (3, 2)
9
</code></pre>

<ul>
<li>coerce() - convert the two different numeric data type into the same

<ul>
<li>will follow the hierarchy to change number in the lower hierarchy to higher</li>
<li>integer &lt; long integer &lt; float &lt; complex</li>
</ul></li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; coerce (1, 2L)
(1L, 2L)
</code></pre>

<ul>
<li>str() - change numeric data to string</li>
</ul>

<p>There are not many build-in functions available. Use <em>math</em> module for more functions. This is the <a href="https://docs.python.org/3.5/library/math.html">documentation</a>.</p>

<pre><code class="Python">import math
&gt;&gt;&gt; math.pi
3.141592653589793
&gt;&gt;&gt; math.sqrt(4)
2.0
</code></pre>

<hr />

<h3 id="list">List</h3>

<h4 id="list-definition">Definition &amp; Creation</h4>

<p>Python can save a group of objectives together. This is called a list. A list will be hold by square brackets ([]). A list can hold numeric, string and list data together.</p>

<p>To create a list, simply use [], or use list() function.</p>

<pre><code class="Python">&gt;&gt;&gt; fruit = ['apple', 'banana', 'orange']
&gt;&gt;&gt; meat = list(['pork', 'beef', 'chicken'])
&gt;&gt;&gt; mix = [123, ['Python', 'SQL'], 'iPhone']
</code></pre>

<h4 id="list-indexing">Indexing &amp; Slicing</h4>

<p>Similar to string, you can use indexing and slicing. Unlike string, lists are mutable, which means you can update the value within lists.</p>

<pre><code class="Python">&gt;&gt;&gt; mylist = [1, 2, 3, 4, 5, 6]
&gt;&gt;&gt; mylist[1] = 10
&gt;&gt;&gt; mylist 
[1, 10, 3, 4, 5, 6]
</code></pre>

<p>Note that the original list is updated. Python does not create a copy of original list. </p>

<p>You can update several elements at the same time. Just need to use [].</p>

<pre><code class="Python">&gt;&gt;&gt; mylist = [1, 2, 3, 4, 5]
&gt;&gt;&gt; mylist[3:5] = [100, 101]
&gt;&gt;&gt; mylist
[1, 2, 3, 100, 101, 6]
</code></pre>

<p>If the assigned elements is less or more than sliced elements, lists will shrink or expand, respectively.</p>

<pre><code class="Python">&gt;&gt;&gt; newlist = [1, 2, 3]
&gt;&gt;&gt; newlist[0:2] = [4] # list will shrink
&gt;&gt;&gt; newlist 
[4, 3]
</code></pre>

<p>You can insert another list into existing as well.</p>

<pre><code class="Python">&gt;&gt;&gt; newlist = [1, 2, 3] 
&gt;&gt;&gt; newlist[2] = [2, 2, 2] # insert a new list
&gt;&gt;&gt; newlist
[1, [2, 2, 2], 3]
</code></pre>

<p>If you want to make a copy of the original lists, there is one thing to keep in mind. When you use = to copy a list, if the original list changes, the coped one will be changed as well.</p>

<pre><code class="Python">&gt;&gt;&gt; x = [1, 2, 3]
&gt;&gt;&gt; y = x
&gt;&gt;&gt; y
[1, 2, 3]
&gt;&gt;&gt; x[1] = 1000
&gt;&gt;&gt; x
[1, 1000, 3]
&gt;&gt;&gt; y
[1, 1000, 3]
</code></pre>

<p>The reasons of this are beyond the scope of this article. If you want to avoid this situation, you can use slicing to copy a list or import <em>copy</em> module.</p>

<pre><code class="Python">&gt;&gt;&gt; x = [1, 2, 3]
&gt;&gt;&gt; y = x[:]
&gt;&gt;&gt; x[1] = 1000
&gt;&gt;&gt; x
[1, 1000, 3]
&gt;&gt;&gt; y 
[1, 2, 3]
</code></pre>

<p>or</p>

<pre><code class="Python">&gt;&gt;&gt; import copy
&gt;&gt;&gt; x = [1, 2, 3]
&gt;&gt;&gt; y = copy.copy(x)
&gt;&gt;&gt; x[0] = 10
&gt;&gt;&gt; x
[10, 2, 3]
&gt;&gt;&gt; y 
[1, 2, 3]
</code></pre>

<p>To remove certain characters within a list, you can use<em>del</em> statement with indexing or slicing.</p>

<pre><code class="Python">&gt;&gt;&gt; mylist = [1, 2, 3, 4]
&gt;&gt;&gt; del mylist[1]
&gt;&gt;&gt; mylist
[1, 3, 4]
&gt;&gt;&gt; del mylist[:2]
&gt;&gt;&gt; mylist
[4]
</code></pre>

<h4 id="list-operators">Operators</h4>

<p>You can use <em>+</em> to combine two lists.</p>

<pre><code class="Python">&gt;&gt;&gt; a = [1, 2, 3]
&gt;&gt;&gt; b = [4, 5, 6]
&gt;&gt;&gt; a + b
[1, 2, 3, 4, 5, 6]
</code></pre>

<p>You can use * to repeat a list.</p>

<pre><code class="Python">&gt;&gt;&gt; a = [1, 2]
&gt;&gt;&gt; a * 2
[1, 2, 1, 2]
&gt;&gt;&gt; [a] * 2
[[1, 2], [1, 2]]
</code></pre>

<p><em>in</em> operator - return True if an element is within a list, return False otherwise</p>

<pre><code class="Python">&gt;&gt;&gt; mylist = [1, 2, 3, 4]
&gt;&gt;&gt; 1 in mylist
True
&gt;&gt;&gt; 10 in mylist
False
</code></pre>

<h4 id="list-functions">Functions</h4>

<ul>
<li>len() - return the length of a list</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; mylist = [1, 2, 3, 4]
&gt;&gt;&gt; len(mylist)
4
</code></pre>

<ul>
<li>min() - return the smallest element in a list</li>
<li>max() - return the largest element in a list</li>
<li>list() - convert a tuple into a list or build a list</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; mytuple = (1, 2, 3)
&gt;&gt;&gt; list(mytuple)
[1, 2, 3]
</code></pre>

<h4 id="list-methods">Methods</h4>

<p>The list methods will modify the lists itself. The return value from list methods should not be assigned to any object.</p>

<ul>
<li>list.append(element) - add a single/list element to the end of an existing list</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; a = [1, 2, 3]
&gt;&gt;&gt; a.append(4)
&gt;&gt;&gt; a
[1, 2, 3, 4]
&gt;&gt;&gt; b = [7, 8]
&gt;&gt;&gt; a.append(b)
[1, 2, 3, 4, [7, 8]]
</code></pre>

<ul>
<li>list.extend(list) - add a list of elements to the end of an existing list</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; a = [1, 2, 3]
&gt;&gt;&gt; b = [7, 8]
&gt;&gt;&gt; a.extend(b)
[1, 2, 3, 7, 8]
</code></pre>

<ul>
<li>list.insert(index, element) - add an element to a list at a location other than the end</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; a = [1, 2, 3]
&gt;&gt;&gt; a.insert(1, 10)
&gt;&gt;&gt; a
[1, 10, 2, 3]
</code></pre>

<ul>
<li>list.remove(value) - remove the value at the first occurrence in a list</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; a = [1, 2, 3]
&gt;&gt;&gt; a.remove(2)
&gt;&gt;&gt; a
[1, 3]
</code></pre>

<ul>
<li>list.pop(index) - return the element based on the index provided and remove it from a list</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; a = [1, 2, 3]
&gt;&gt;&gt; a.pop(1)
2
&gt;&gt;&gt; a
[1, 3]
</code></pre>

<ul>
<li>list.sort() - sort the elements within a list based on numerical order and alphabetical order</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; a = [3, 2, 1]
&gt;&gt;&gt; a.sort()
&gt;&gt;&gt; a
[1, 2, 3]
</code></pre>

<ul>
<li>list.count(value) - count how many times a value appears in a list</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; a = [1, 1, 1, 2, 3,]
&gt;&gt;&gt; a.count(1)
3
</code></pre>

<ul>
<li>list.index(value) - return the index of the first occurrence of the given value in a list</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; a = [1, 2, 3, 4]
&gt;&gt;&gt; a.index(2)
1
</code></pre>

<h4 id="list-comprehension">List Comprehension</h4>

<p>You can combine <a href="#for">for loop</a> and <a href="#if">if statement</a> with lists to create a list based on an existing sequence.</p>

<pre><code class="Python">&gt;&gt;&gt; old = [1, 2, 3, 4, 5]
&gt;&gt;&gt; new = [i**2 for i in old]
&gt;&gt;&gt; new
[1, 4, 9, 16, 25]
</code></pre>

<p>List comprehension is very simple, The above example is equivalent to this:</p>

<pre><code class="Python">&gt;&gt;&gt; old = [1, 2, 3, 4, 5]
&gt;&gt;&gt; new = []
&gt;&gt;&gt; for i in old:
...         new.append(i**2)
...
&gt;&gt;&gt; new
[1, 4, 9, 16, 25]
</code></pre>

<p>You can also use <em>if</em> statement in list comprehension:</p>

<pre><code class="Python">&gt;&gt;&gt; old = [1, 2, 3, 4, 5]
&gt;&gt;&gt; new = [i for i in old if i % 2 == 1]
&gt;&gt;&gt; new
[1, 3, 5]
</code></pre>

<p>List comprehension also allows more than 1 <em>for</em> loops:</p>

<pre><code class="Python">&gt;&gt;&gt; a = [(i, j) for i in range(2) for j in range(3)] # no comma in between
&gt;&gt;&gt; a
[(0, 0), (0, 1), (0, 2), (1, 0), (1, 1), (1, 2)]
</code></pre>

<hr />

<h3 id="tuple">Tuple</h3>

<h4 id="tuple-definition">Definition &amp; Creation</h4>

<p>Tuple is very similar to list, except that it is <em>immutable</em>. Once a tuple is created, it cannot be modified. Tuples are useful because of the following reasons:</p>

<ul>
<li>faster than lists</li>
<li>protect the data since it is immutable</li>
<li>there are some situations where tuples are required

<ul>
<li>e.g. keys on dictionaries</li>
</ul></li>
</ul>

<p>Tuples are created by listing several values. You can use () to surround the values, but it is optional. () is only required when you create an empty or one element tuple. If you want to create a tuple with only 1 element, add a comma (,) after it.</p>

<pre><code class="Python">&gt;&gt;&gt; mytuple = 1, 2, 3
&gt;&gt;&gt; type(mytuple)
&lt;class 'tuple'&gt;
&gt;&gt;&gt; mytuple + (7, )
(1, 2, 3, 7)
</code></pre>

<p>You can also use tuple() function to transfer a list into a tuple.</p>

<pre><code class="Python">&gt;&gt;&gt; mylist = [1, 2, 3]
&gt;&gt;&gt; tuple(mylist)
(1, 2, 3)
</code></pre>

<h4 id="tuple-indexing">Indexing &amp; Slicing</h4>

<p>Same with <a href="#list-indexing">list indexing and slicing</a>.</p>

<h4 id="tuple-operators">Operators</h4>

<p>Same with <a href="#list-operators">list operators</a>.</p>

<h4 id="tuple-functions">Functions</h4>

<p>Tuple functions are very similar to lists.</p>

<ul>
<li>len() - return the length of a list</li>
<li>min() - return the smallest element in a list</li>
<li>max() - return the largest element in a list</li>
<li>tuple() - convert a list into tuple</li>
</ul>

<h4 id="tuple-methods">Methods</h4>

<p>Since tuples are immutable, tuples do not have as many methods as lists. </p>

<ul>
<li>tuple.count(value) - count how many times a value appears in a tuple</li>
<li>tuple.index(value) - return the index of the first occurrence of the given value in a tuple</li>
</ul>

<hr />

<h3 id="dictionary">Dictionary</h3>

<h4 id="dictionary-definition">Definition &amp; Creation</h4>

<p>Dictionary is like a map. You have the <em>key</em> to pair with the <em>value</em> It is similar to list, but, instead of being indexed by integers, it can be indexed by any immutable object, such as tuples. It will be easier to get information through dictionary.</p>

<p>To create a dictionary, we can use {}, use colon(:) to connect between keys and values. Please note that <em>keys</em> must be unique, and immutable, which mean they cannot be lists. </p>

<pre><code class="Python">&gt;&gt;&gt; mydict = {key1: value1, key2: value2}
</code></pre>

<h4 id="dictionary-indexing">Indexing &amp; Slicing</h4>

<p>Dictionary can use indexing through its <em>keys</em>.</p>

<pre><code class="Python">&gt;&gt;&gt; dict = {'a': 'apple', 'b': 'banana'}
&gt;&gt;&gt; dict['a']
'apple'
</code></pre>

<p>Dictionary is mutable like lists. You can use indexing to update the values.</p>

<pre><code class="Python">&gt;&gt;&gt; dict = {'a': 'apple', 'b': 'banana'}
&gt;&gt;&gt; dict['a'] = 'burger'
&gt;&gt;&gt; dict
{'a': 'burger', 'b': 'banana'}
</code></pre>

<p>You can also add new pairs to a dictionary.</p>

<pre><code class="Python">&gt;&gt;&gt; dict = {'a': 'apple', 'b': 'banana'}
&gt;&gt;&gt; dict['c'] = 'cat'
&gt;&gt;&gt; dict
dict = {'a': 'apple', 'b': 'banana', 'c': 'cat'}
</code></pre>

<p>Dictionary doesn&#8217;t have slicing, like lists. </p>

<h4 id="dictionary-operators">Operators</h4>

<ul>
<li>in operators - access the keys within a dictionary, cannot access value</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; dict = {'a': 'apple', 'b': 'banana'}
&gt;&gt;&gt; 'a' in dict
True
&gt;&gt;&gt; 'apple' in dict
False
</code></pre>

<ul>
<li>del statement - eliminate a key/value pair</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; dict = {'a': 'apple', 'b': 'banana'}
&gt;&gt;&gt; del dict
&gt;&gt;&gt; dict
&lt;class 'dict'&gt;
</code></pre>

<h4 id="dictionary-functions">Functions</h4>

<ul>
<li>len() - return the number of elements, the number of key/value pairs, in a dictionary</li>
</ul>

<h4 id="dictionary-methods">Methods</h4>

<ul>
<li>dict.keys() - return list of dictionary&#8217;s keys</li>
<li>dict.values() - return list of dictionary&#8217;s values</li>
<li>dict.items() - return a list of dictionary&#8217;s (key, value) tuple pairs</li>
<li>dict.clear - remove all elements of a dictionary</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; dict = {'a': 'apple', 'b': 'banana'}
&gt;&gt;&gt; dict
{}
</code></pre>

<ul>
<li>dict.get(key, default = None) - return the value paired with the key argument if the key exists, return None or other value if key is not in dictionary</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; dict = {'a': 'apple', 'b': 'banana'}
&gt;&gt;&gt; dict.get('a')
'apple'
&gt;&gt;&gt; dict.get('c')
&gt;&gt;&gt; dict.get('c', &quot;doesn't exist&quot;)
&quot;doesn't exist&quot;
</code></pre>

<ul>
<li>dict.copy() - copy the current dictionary

<ul>
<li>change of the old dictionary will not affect copied one</li>
</ul></li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; dict = {'a': 'apple', 'b': 'banana'}
&gt;&gt;&gt; dict2 = dict.copy()
&gt;&gt;&gt; dict2
{'a': 'apple', 'b': 'banana'}
&gt;&gt;&gt; dict['a'] = 'dog'
&gt;&gt;&gt; dict
{'a': 'cat', 'b': 'banana'}
&gt;&gt;&gt; dict2
{'a': 'apple', 'b': 'banana'}
</code></pre>

<ul>
<li>dict.update(dict) - merge all the key/value pairs with another dictionary</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; dict = {'a': 'apple', 'b': 'banana'}
&gt;&gt;&gt; dict2 = {'a': 'dog', 'b': 'banana', 'c': 'cat'}
&gt;&gt;&gt; dict.update(dict2)
&gt;&gt;&gt; dict
{'a': dog', 'b': 'banana', 'c': 'cat'}
</code></pre>

<hr />

<h3 id="file">File</h3>

<h4 id="file-open">Open</h4>

<p>Python can access files through a file object, which is created by open() function. After creating the file object, there are lots of method reading and writing the files.</p>

<p>There are three arguments within open() function. If you want to learn the logical behind, and learn the differences between them, you can refer to <a href="http://stackoverflow.com/questions/1466000/python-open-built-in-function-difference-between-modes-a-a-w-w-and-r">stack overflow</a>.</p>

<ul>
<li>file name, required</li>
<li>actions to do, default is read, optional

<ul>
<li>r - open file for reading; file must exist</li>
<li>w - open file for writing; file will be created if not existing</li>
<li>a - open file for appending; file will be created if not existing</li>
<li>r+ - open file for reading and writing; content are not destroyed</li>
<li>w+ - open file for reading and writing; contents are destroyed</li>
<li>a+ - open file for reading and writing; contents are not destroyed</li>
</ul></li>
<li>how to file should be buffered; normally don&#8217;t need

<ul>
<li>0 - no buffering</li>
<li>1 - line buffering</li>
<li>other positive value - siave of the bufer</li>
</ul></li>
</ul>

<h4 id="file-methods">Methods</h4>

<ul>
<li>file.read() - read the whole file, return a string contains all the data</li>
<li>file.readline() - read a single line from a file</li>
<li>file.readlines() - read the whole file, and return a list consisting of all of the lines in the file</li>
<li>file.write() - write a single argument into a file</li>
<li>file.writelines() - write a list argument into a file</li>
<li>file.close() - close a file after finishing reading and writing</li>
</ul>

<hr />

<h3 id="pipe">Pipes</h3>

<p>Pipe means reading output from a command or sending output to a command. For example, you may use Python to get data from website, and send to Excel for analysis. Python has <em>os</em> module, and popen() function in this module to achieve pipe.</p>

<pre><code class="Python">&gt;&gt;&gt; import os
&gt;&gt;&gt; from os import popen
</code></pre>

<p>Pipes and os module will be explained in another article later.</p>

<hr />

<h3 id="condition">Conditions</h3>

<p>Relational operators</p>

<ul>
<li>x == y - equal</li>
<li>x != y - not equal</li>
<li>x &gt; y - greater than</li>
<li>x &lt; y - less than</li>
<li>x &gt;= y - greater than or equal</li>
<li>x &lt; = y - less than or equal</li>
<li>in - within a sequence</li>
<li>not in - not in a sequence</li>
<li>is - equivalent</li>
<li>not is - not equivalent</li>
<li>is None - null value</li>
<li>is not None - not null value</li>
</ul>

<p>Logical operator</p>

<ul>
<li>and - overall statement is true if all statements are true</li>
<li>or - overall statement is true if one statement is true</li>
<li>not - negated</li>
</ul>

<hr />

<h3 id="if">if statement</h3>

<p>Python use <em>if</em> statement to perform basic conditional execution. </p>

<pre><code class="Python">&gt;&gt;&gt; if expression:
...         statement
...     elif expression: # short for else if
...         statement
...     else:
...         statement
</code></pre>

<p>Note: &#8220;:&#8221; after if, and four indents </p>

<p>You can use function and <em>if</em> statement to do iteration as well, but normally you can achieve this more easily with <a href="#for"><em>for</em> loop</a> or <a href="#while"><em>while</em> loop</a>.</p>

<p>Example: </p>

<pre><code class="python">def countdown(n): 
    if n &lt; 0:
        print(Done!)
    else:
        print(n)
        countdown(n-1)
</code></pre>

<hr />

<h3 id="for">for loops</h3>

<p><em>for</em> loops can iterate over all the values in a sequence (strings, lists, tuples, dictionaries and files). </p>

<pre><code class="python">for name_whatever_you_want in sequence:
    statements
</code></pre>

<p>When you want to iterate several sequences at once, you can combine <em>for</em> loops with range() function. range() function returns a sequence of integers from 0 to one less than the provided arguments, which can represent index of a sequence.</p>

<pre><code class="python">&gt;&gt;&gt; x = [1, 2, 3, 4]
&gt;&gt;&gt; y = [5, 6, 7, 8]
&gt;&gt;&gt; for i in range(len(x)):
...         print(x[i], y[i])
1 5
2 6
3 7
4 8
</code></pre>

<hr />

<h3 id="while">while loops</h3>

<p>When the repetitive computation is not based on a sequence, while loops will be very helpful. </p>

<pre><code class="python">while expression:
    statements
</code></pre>

<p>To jump out of the loop, use break statement:</p>

<pre><code class="python">while condition_is_true:
    break
</code></pre>

<hr />

<h3 id="function">Function</h3>

<h4 id="function-definition">Definition &amp; Creation</h4>

<p>Function is a named sequence of statements that performs a computation. Users can use built-in functions as well as user-defined functions. </p>

<p>You have seen many build-in functions through this article. You can find a comprehensive build-in functions in <a href="https://docs.python.org/3/library/functions.html">the formal documentation</a>.</p>

<p>You can define your own functions as well. Functions are very powerful because it allows you to reuse code you have written, and it logically isolate different tasks. </p>

<p>Variables and parameters within a function are local, which means they only exist inside the function. This is called scoping, which follows <a href="http://stackoverflow.com/questions/291978/short-description-of-python-scoping-rules">LEGB rules</a>.</p>

<p>To create a new function, you need to use <em>def</em> statement. </p>

<pre><code class="python">def function_name(parameter1, parameter2,...):
''' This is the documentation of this function.'''
    body area
    (return XXX)
</code></pre>

<h4 id="function-arguments">Arguments</h4>

<p>The elements within the () when defining a function is called parameters of functions or arguments. Each arguments have their names. When creating a function, you can assign a default value for arguments so that you do not need to provide values for these arguments when calling a function. Just note that if you want to provide a default values to arguments, these arguments need to be put after other arguments. If you provide value when calling the function, the default value will be override. </p>

<p>When assigning value to arguments, you can specify arguments&#8217; name. In this way, you do not need to care about the order or the arguments. If you do not specify the name, the arguments need to be on exact same order with defining.</p>

<pre><code class="Python">&gt;&gt;&gt; def count_letter (string, letter = 'a'):
...     '''This function will count how many times a letter showing in a string.
...     If no letter is provided, the default will be letter &quot;a&quot;. '''  
...         count = 0
...         for element in string:
...         if element == letter:
...             count += 1 # equivalent to count = count +1
...         return count
...
&gt;&gt;&gt; print(count_letter('apple'))
1
&gt;&gt;&gt; print(count_letter(letter = 'p', string = 'apple')
2
</code></pre>

<p>It is also possible that you do not know how many arguments you may need. Python uses asterisk (*) to help with this. </p>

<pre><code class="Python">&gt;&gt;&gt; def max_length(*string)
...     '''You can compare as many strings as you want. The function will return 
...     the maximum length of those strings'''
...         max = 0
...         for letter in string:
...             if len(letter) &gt; max:
...                 max = len(letter)
...         return max
...
&gt;&gt;&gt; print(max_length('apple', 'banana', 'tax_return', 'iPhone')
10
</code></pre>

<p>Python also provide a way to use unlimited pairs of keys and values, which is achieved using two asterisk (**).</p>

<pre><code class="Python">&gt;&gt;&gt; def print_dict(**dict):
...     '''Print the key and value pairs of a dictionary'''
...         for k, v in dict.items()
...             print(k, v)
...
&gt;&gt;&gt; print_dict(x = 1, y = 2, z = 3)
x 1
y 2
z 3
</code></pre>

<h4 id="lambda">map() &amp; lambda</h4>

<p>map() function can apply a list of objects to a function. It is an alternative way to use <em>for</em> loop when you need to perform the same task on every object.</p>

<pre><code class="Python">&gt;&gt;&gt; num = ['1', '2', '3']
&gt;&gt;&gt; letter = ['a', 'b', 'c']
&gt;&gt;&gt; combine = []
&gt;&gt;&gt; for i in range(len(num)):
...         combine.append(': '.join((num[i], letter[i])))
...
&gt;&gt;&gt; combine
['1: a', '2: b', '3: c']
</code></pre>

<p>This is kind of complicated way to combine two lists. You can use function and map() function to achieve the same goal much more simply.</p>

<pre><code class="Python">&gt;&gt;&gt; def combine_list(list1, list2):
...         return ': '.join([list1, list2])
...
&gt;&gt;&gt; num = ['1', '2', '3']
&gt;&gt;&gt; letter = ['a', 'b', 'c']
&gt;&gt;&gt; list(map(combine_list, num, letter))
['1: a', '2: b', '3: c']
</code></pre>

<p>Python provides lambda operators to quickly write a function, without worrying about the formatting of defining a function. It looks like list comprehension. </p>

<pre><code class="Python">&gt;&gt;&gt; num = ['1', '2', '3']
&gt;&gt;&gt; letter = ['a', 'b', 'c']
&gt;&gt;&gt; list(map(lambda list1, list2: ': '.join([list1, list2]), num, letter))
['1: a', '2: b', '3: c']
</code></pre>

<p>Lambda also works very effectively with filter() function.</p>

<pre><code class="Python">&gt;&gt;&gt; num = [1, 3, -2, -10, 5]
&gt;&gt;&gt; list(filter(lambda x: x &lt; 0, num))
[-2, -10]
</code></pre>

<hr />

<h3 id="modules">Modules</h3>

<p>You have already seen some modules like <em>math</em> and <em>copy</em>. The core Python language is very small and simple. To make it more powerful, and have more capability, it is necessary to use modules. Modules are collections of Python programs. There are many modules available to use. The three most popular and powerful modules in data industry are <a href="http://www.numpy.org">numpy</a>, <a href="http://pandas.pydata.org">pandas</a>, and <a href="http://matplotlib.org">matplotlib</a>. There will be in-depth articles later. </p>

<h4 id="re">re module</h4>

<p>You can find the introduction about regular expression in my blog - <a href="https://rachelfu.github.io/page2/">mukerong</a>. <em>re</em> module provides a way to incorporate regex into Python.</p>

<ul>
<li>re.compile() - compile a regex pattern into a regex object, which can be used for re.match() and re.search()</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; import re
&gt;&gt;&gt; regex = re.compile('hello')
&gt;&gt;&gt; type(regex)
&lt;class '_sre.SRE_Pattern'&gt;
</code></pre>

<ul>
<li>re.match() - look for a regex at the beginning of a string; return None if nothing found</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; regex = re.compile('hello')
&gt;&gt;&gt; regex.match('hello world') is None
False
</code></pre>

<p>You can also omit re.compile(), and use re.match() directly.</p>

<pre><code class="Python">&gt;&gt;&gt; re.match('hello', 'hello world') is None
False
</code></pre>

<ul>
<li>re.search() - look for a regex anywhere in a string; return None if nothing found

<ul>
<li>You can find the difference between search and match <a href="http://stackoverflow.com/questions/180986/what-is-the-difference-between-pythons-re-search-and-re-match">here</a></li>
</ul></li>
<li>re.split() - split string by the pattern</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; re.split('\d+', 'as3bcsd5')
['as', 'bcsd', '']
</code></pre>

<ul>
<li>re.findall() - return all non-overlapping matching patterns</li>
</ul>

<pre><code class="Python">&gt;&gt;&gt; re.findall('\d+', 'as3bcsd5')
['3', '5']
</code></pre>

<h4 id="numpy">numpy</h4>

<p>There will a comprehensive explanation about numpy soon.</p>

<h4 id="pandas">pandas</h4>

<p>There will a comprehensive explanation about pandas soon.</p>

<h4 id="matplotlib">matplotlib</h4>

<p>There will a comprehensive explanation about matplotlib soon.</p>

<hr />

<h3 id="exception-handling">Exception Handling</h3>

<p>No matter how careful you are, errors are inevitable due to some situation. Python provides a method of handling errors. </p>

<pre><code class="Python">&gt;&gt;&gt; x = 1
&gt;&gt;&gt; y = 0
&gt;&gt;&gt; print(x/y)
Traceback (most recent call last):
  File &quot;&lt;stdin&gt;&quot;, line 1, in &lt;module&gt;
ZeroDivisionError: division by zero
&gt;&gt;&gt; try:
...         print(x/y)
...     except: # you can specify error type here
...         print('y cannot be zero')
...
y cannot be zero
</code></pre>

<p>This is just a simple example. You will get more used to it after using Python more!</p>

<hr />

<h3 id="resources">Resources</h3>

<p>You have learnt the Python basics by reading this article. Hope you like it. To further explore Python, you can look at the following resources:</p>

<ul>
<li><a href="https://www.python.org">Python.org</a> - Official website and documentations</li>
<li><a href="https://www.continuum.io/downloads">Anaconda</a> - Install Python and all packages</li>
<li><a href="http://jupyter.org">Jupyter Notebook</a> - Platform to write Python; very popular in data industry</li>
<li><a href="https://learnpythonthehardway.org">Learn Python the Hard Way</a> - Help beginner to learn Python</li>
<li><a href="https://stackoverflow.com">Stack Overflow</a> - No matter what questions you have, you can find n answer</li>
</ul>

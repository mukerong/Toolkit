<h1>Regular Expression Basics</h1>

<p>You may remember the two wildcard, &#8216;?&#8217; and &#8216;*&#8217; in Excel. Regular Expression (aka. Regex) provides more ways to help searching the pattern you are looking for. It can significantly improve the productivity. I hope this article can help you understand the basics of regex. </p>

<hr />

<h2>Table of Contents</h2>

<ul>
<li><a href="#definition-of-regex">Definition</a></li>
<li><a href="#literal-characters">Literal Characters</a></li>
<li><a href="#metacharacters">Special Characters</a>

<ul>
<li><a href="#begin">^</a></li>
<li><a href="#end">$</a></li>
<li><a href="#dot">.</a></li>
<li><a href="#or">|</a></li>
<li><a href="#repeat1">? &amp; * &amp; +</a></li>
<li><a href="#escape">\</a></li>
<li><a href="#others">Others</a></li>
</ul></li>
<li><a href="#character-set">Character Classes</a>

<ul>
<li><a href="#bracket">[]</a></li>
<li><a href="#negated">[^]</a></li>
<li><a href="#digit">\d &amp; \D</a></li>
<li><a href="#word">\w &amp; \W</a></li>
<li><a href="#space">\s &amp; \S</a></li>
</ul></li>
<li><a href="#anchors">Anchors</a>

<ul>
<li><a href="#begin-end">^ &amp; $</a></li>
<li><a href="#boundry">\b &amp; \B</a></li>
</ul></li>
<li><a href="#repeat">Repeat</a>

<ul>
<li><a href="#repeat2">? &amp; * &amp; +</a></li>
<li><a href="#repeat3">{m} &amp; {m,} &amp; {m, n}</a></li>
</ul></li>
<li><a href="#grouping">Grouping</a></li>
<li><a href="#backreferences">Backreferences</a></li>
<li><a href="#forwardreferences">ForwardReferences</a></li>
<li><a href="#lookahead">Lookahead</a></li>
<li><a href="#lookbehind">Lookbehind</a></li>
<li><a href="#application">Application</a></li>
<li><a href="#regex-resources">Resources</a></li>
</ul>

<hr />

<h3 id="definition-of-regex">Definition</h3>

<p>Based on the Definition on <a href="https://en.wikipedia.org/wiki/Regular_expression">Wiki</a>, </p>

<blockquote>
<p>A regular expression is a sequence of characters that define a search pattern in theoretical computer science and formal language.</p>
</blockquote>

<p>So what does it exactly mean? Based on my understanding, regular expression is a very simple language that can help with search and find function. For example, if you want to find a movie called &#8220;zootopia&#8221; saved in your computer, but all you forget the name, and all you can remember is &#8220;zoo something with &#8216;ia&#8217; at then end &#8221;. What you are going to do? You may start to search &#8220;zoo&#8221; in your computer, but you may have hundreds or thousands of files saved with &#8220;zoo&#8221; in the name. Are there any better way to find it?</p>

<p>Luckily, regular expression (Regex) is here to help. It can help you search whatever pattern you want to use. In the example above, you can simply use <code>^zoo\w*ia$</code> to match the pattern and find the movie you want. Don&#8217;t worry if you do not understand what the thing I just wrote mean. It was nonsense to me several week ago. I will show you in the following ones to help you understand the awesome regex.</p>

<h3 id="literal-characters">Literal Characters</h3>

<p>Literal characters include both letters (abc&#8230;) and digits (123&#8230;). They are the easiest and simplest pattern in regex. You can use them as you use in Excel search box. </p>

<p>For example, when you want to search for &#8216;a&#8217; just type &#8216;a&#8217;. When you want to search &#8216;facebook&#8217; in your website bookmark, you can simple type &#8216;medium&#8217; and &#8216;https://<strong>facebook</strong>.com&#8217; can be found.</p>

<h3 id="metacharacters">Special Characters (a.k.a. metacharacters)</h3>

<h4 id="begin"><code>^</code></h4>

<p>To make a character the beginning of a pattern. i.e. <code>^zoo</code> to search &#8216;zootopia&#8217;. It also means negated if placed after <code>[</code>. </p>

<p>More details under <a href="#begin-end">^ &amp; $</a></p>

<h4 id="end"><code>$</code></h4>

<p>To make a character the ending of a pattern. i.e.: <code>pia$</code> to search &#8216;zootopia&#8217;. </p>

<p>More details under <a href="#begin-end">^ &amp; $</a></p>

<h4 id="dot"><code>.</code></h4>

<p>In short, <code>.</code> can be used for matching anything except newline. </p>

<p>What does this mean? Well, if you forget whether it is &#8216;microeconomics&#8217; or &#8216;macroeconomics&#8217; you are looking for, you can type <code>m.croeconomics</code>, so you can find both. Dot(.) means any single letter, digit or special character you want to search. But remember, it can only substitute for one character. If you type <code>1.2.3.4</code>, you may find <strong>1+2&#8211;3+4</strong> or may find <strong>1a2b3c4</strong>. If you want to match for more than one character, you can type <code>1..34</code>.</p>

<p>If you want to search a dot(.) instead of everything, you can use <code>\.</code> Here, <code>\</code> is an escape sign to show computer that you want to match dot(.) instead of using dot as a pattern character. </p>

<h4 id="or"><code>|</code></h4>

<p>In short, <code>|</code> means &#8216;Or&#8217;. </p>

<p>For example, <code>(Rachel | Amanda) likes regex</code> can match either &#8216;Rachel likes regex&#8217; or &#8216;Amanda likes regex&#8217;, but not both. </p>

<p>You may use <code>I</code> a lot since Regex is case sensitive unless you told it not to. Therefore, &#8216;a&#8217; is not the same as &#8216;A&#8217;. <code>You can use</code>|<code>to do alternative matching when you are not sure whether a letter is lowercase or uppercase. For example,</code>(R | r)egular` can match &#8216;Regular&#8217; or &#8216;regular&#8217;. </p>

<h4 id="repeat1"><code>?</code> &amp; <code>*</code> &amp; <code>+</code></h4>

<p>In short, <code>?</code> can match 0 or 1 repetition; <code>*</code> is used to match 0 or more repetitions, and <code>+</code> is used to match 1 or more repetitions.</p>

<p>More details under <a href="#repeat2">? &amp; * &amp; +</a></p>

<h4 id="escape"><code>\</code></h4>

<p>It normally means &#8216;escape&#8217;. If you want to search for the characters that listed above, you need to add a <code>\</code> before them to search. For example, to search period &#8216;.&#8217;, instead of using <code>.</code>, you need to type <code>\.</code>. </p>

<h4 id="others"><code>(</code>, <code>)</code>, <code>[</code>, <code>{</code></h4>

<p>These are just special characters, but no very useful meanings. </p>

<h3 id="character-set">Character Classes (a.k.a. Character Sets)</h3>

<h4 id="bracket"><code>[]</code></h4>

<p>In short, <code>[]</code> is used to match one out of several characters. <code>[ab]c</code> will match &#8216;ac&#8217; or &#8216;bc&#8217;.</p>

<p>When you want to search for a song with vowel as a start, <code>\w</code> or dot can make things even harder. To match one out of several characters, you can placed them inside a square brackets []. For example, <code>[aeiou] is a vowel</code> can find &#8216;a is a vowel&#8217;, &#8216;e&#8217; is a vowel&#8217; and etc. Just remember, [] will find only one character out of all the characters within it, not all of them.</p>

<p>[] is very useful, but listing all the word or number one by one may also be exhausted. You can use dash(-) to accelerate this process. [a-z] means a, b, c&#8230;z. [7&#8211;9] means 7, 8, 9. [A-D] means A, B, C, D. Easy? One thing to keep in mind, Regex is case sensitive, which means a is different from A. In the example above, if you want to search for vowel and do not care whether it is capital letter or not, you can use <code>[aeiouAEIOU]</code>.</p>

<h4 id="negated"><code>[^]</code></h4>

<p>In short, <code>[^]</code> means negated character classes. <code>[^0-8]</code> can match &#8216;9&#8217;.</p>

<p>You can search for certain characters with <code>[]</code>. How about you want to find characters except some characters? For example, you want to search music name that not starts from a vowel. Well, you can add a &#8216;^&#8217; within a square brackets like [^aeiou]. Within a square brackets, <code>^</code> does not mean &#8216;start&#8217; anymore, it means &#8216;opposite&#8217; or &#8216;negated&#8217;. <code>[^aeiou]</code> can help find all the letter other than &#8216;aeios&#8217;.</p>

<h4 id="digit"><code>\d</code> &amp; <code>\D</code></h4>

<p>In short, <code>\d</code> means all digital number. It equals to [0&#8211;9]. <code>\D</code> means all non-digital number. It equals to [^0&#8211;9].</p>

<p>Dot is useful when searching all literal characters, but can you just match numbers when I search for phone number instead of everything? You bet. you can use <code>\d</code> to help. </p>

<p>When you want to search phone number &#8216;800&#8211;800-&#8217; but forget the last four digits, you can type <code>800-800-\d\d\d\d</code> to find the number you need. It will show something like &#8216;800&#8211;800&#8211;1234&#8217;. How about the opposite way? You have your final essay needs to be submit, but you have version essay_v1, essay_v2, &#8230; essay_v10000 saved in your computer, and you just want to find essay_vFinal, what should you do? Well, you cannot use dot since it will list you everything. Or, if you remember, you can search vFinal. What about you were too excited when you finished the final version, and misspell final to something else?<code>\D</code> will help you here. <code>\D</code> is exactly the opposite of <code>\d</code>, which means it will match everything other than digits. <code>essay_v\D</code> can help you find &#8216;essay_vp&#8217;, &#8216;essay_vF&#8217; or &#8216;essay_v@&#8217;. </p>

<p><code>\D</code> and <code>\d</code> can only match one character at a time like dot. You can type <code>\d\d\d\d</code> to match multiple, or I will show you, in the following articles&#8217; about how to match multiple characters at a time.</p>

<h4 id="word"><code>\w</code> &amp; <code>\W</code></h4>

<p>In short, <code>\w</code> means all word character including both alphanumeric and underscore. It equals to [0&#8211;9A-Za-z_]. <code>\W</code> means all non-word character. It equals to [^0&#8211;9A-Za-z_].</p>

<p><code>\d</code> is cool when search for phone number, but what about word character. Dot can help find everything, but how about some special characters that you do not want to search. <code>\w</code> can help with all the issues. <code>\w</code> can match all word characters, which includes both alphanumeric characters (a-z, A-Z, and 0&#8211;9) and underscores (_). The method to use <code>\w</code> is the same with <code>/d</code>. &#8216;\W&#8217; is exactly the opposite of <code>\w</code>, which means it will match any character other than alphanumeric characters and underscore. When you want to search for special character, it will help a lot.</p>

<h4 id="space"><code>\s</code> &amp; <code>\S</code></h4>

<p>In short, <code>\s</code> matches all whitespace character, including spaces, tabs, and line breaks. <code>\S</code> matches any character that is not a whitespace character. </p>

<p>Another often used patterns with backslash are <code>\s</code> and <code>\S</code>. <code>\s</code> can matches any whitespace character, which includes <code>\r</code>, <code>\n</code>, <code>\t</code>, <code>\f</code>. You do not need to memorize these four. All you need to remember is when you are looking for whitespace like &#8216;A B&#8217;, <code>\s</code> can help you find it. No matter whether you are looking for a single whitespace, or a new line, or a space created by hitting tab. <code>\S</code>, as you may already know, can match all non-whitespace character. Therefore, <code>\S</code> is more general than <code>\w</code>, since alphanumeric characters, underscores and special characters are all non-whitespace character. </p>

<h3 id="anchors">Anchors</h3>

<p>Anchors do not match any characters. They match a position for the characters. </p>

<h4 id="begin-end"><code>^</code> &amp; <code>$</code></h4>

<p><code>^</code> matches the position before the first character.
<code>$</code> matches the position after the laster character.</p>

<p>These two characters are probably my favorite in regular expression. In short, <code>^</code> means beginning and <code>$</code> means ending. You can use them separately or combined. For the &#8216;zootopia&#8217; example, if just using <code>zoo\w+ia</code>, you may find something like &#8216;asdfja<strong>zoo</strong>a;sdjfaskd<strong>ia</strong>a;skjf;kj;fja&#8217;, which is clearly not what you are looking for. Since you know the word starts from &#8216;zoo&#8217; and end at &#8216;ia&#8217;, you can use <code>^zoo\w+ia$</code>. In this way, computer knows you are looking for some word starts from &#8216;z&#8217; and end at &#8216;a&#8217;. Then, how about starts from &#8216;zoo&#8217;, and end at &#8216;ia&#8217;? This will be another topic called group, which will be shown later.</p>

<h4 id="boundry"><code>\b</code> &amp; <code>\B</code></h4>

<p>In short, <code>\b</code> means word boundaries. It Includs:</p>

<ul>
<li>Before the first character if the first character is a word character</li>
<li>After the last character if the last character is a word character</li>
<li>Between two characters if one is word character and the other is not</li>
</ul>

<p><code>\B</code> is the negated version of <code>\b</code>. </p>

<p><code>\b</code> can find a word boundary, such as whitespace, punctuation and the start/end of a string. There are three different kinds of word boundaries. By word, I mean a-z, A-Z and 0&#8211;9, which is <code>\w</code> in regex. </p>

<ul>
<li>Before a character:

<ul>
<li>If the first character is a word character, the boundary is the one before the first character.</li>
<li>When you put something like <code>\bword\b</code>, it can help you find the whole words. For example: <code>\bword\b</code> can find &#8216;a <strong>word</strong>&#8217;.</li>
</ul></li>
<li>Between two characters:

<ul>
<li>When one is a word character and the other is not.</li>
<li>For example: <code>\b1\b</code> can find &#8216;Regex-<strong>1</strong>&#8217;</li>
</ul></li>
<li>After a character:

<ul>
<li>When the last character is a word character.</li>
<li>For example: <code>Welcome\b</code> can find &#8216;<strong>Welcome</strong>!&#8217;</li>
</ul></li>
</ul>

<p>You may wonder what is the different between <code>\b</code> and <code>\s</code>. It seems that both can find whitespace, why we need two? Well, <code>\b</code> is like &#8216;^&#8217; and &#8216;$&#8217;, which means it will match a position. The match is zero-length. It can only work with other characters together. It will be helpful when you want to find the word characters with boundaries. Meanwhile <code>\w</code> can be very helpful when you want to find the actual whitespace. </p>

<h3 id="repeat">Repeat</h3>

<h4 id="repeat2"><code>?</code> &amp; <code>*</code> &amp; <code>+</code></h4>

<p>In short, <code>?</code> can match 0 or 1 repetition; <code>*</code> is used to match 0 or more repetitions, and <code>+</code> is used to match 1 or more repetitions.</p>

<p>All the patterns are cool, but it will be a disaster if you do not know how many of them you are looking for. Do you remember the previous example of &#8216;zootopia&#8217;? When you know &#8216;zoo&#8217; and &#8216;ia&#8217; but forget the rest of it? You may want to use <code>.</code> or <code>\w</code> to help you find it, but you do not know how many letters are between &#8216;zoo&#8217; and &#8216;ia&#8217;. What should you do, try them one by one until you find it? Fortunately, there is a better way to do it. </p>

<p>Regex provides <code>?</code>, <code>*</code> and <code>+</code>. <code>?</code> can match 0 or 1 repetition; <code>*</code> can match zero or more repetitions and <code>+</code> can match one ore more repetitions. For example, <code>a?b</code> can match &#8216;ab&#8217; or &#8216;aab&#8217;. <code>a*b</code> can find &#8216;b&#8217; or &#8216;aaaaaaaab&#8217;. <code>a+b</code> can find &#8216;ab&#8217; or &#8216;aaaaaab&#8217;. </p>

<p>For the example of &#8216;zootopia&#8217;, if you know there are letters between &#8216;zoo&#8217; and &#8216;ia&#8217; but do not know how many are there, you can use <code>zoo\w+ia</code>. If you are not sure whether there are letters in between, you can use <code>zoo\w*ia</code>. Short and sweet, right?</p>

<h4 id="repeat3"><code>{m}</code> &amp; <code>{m,}</code> &amp; <code>{m, n}</code></h4>

<p>In short, <code>{m}</code> matches m repetition. <code>{m, n}</code> matches m to n repetition. <code>{m, }</code> matches m or more repetition.</p>

<p><code>?</code>, <code>*</code> and <code>+</code> are very helpful with zero/one or more repetitions, but there are high probabilities that you need to more than that. For example, finding certain amount of repetitions, more than 10 repetitions or repetition between 1 and 100. In these cases, <code>{}</code> will be very helpful. </p>

<ul>
<li>{m} can match x repetitions

<ul>
<li><code>a{5}</code> can match &#8216;aaaaa&#8217;</li>
</ul></li>
<li>{m,} can match x or more repetitions.

<ul>
<li><code>a{5,}</code> can match &#8216;aaaaa&#8217; or more than 5 a.</li>
</ul></li>
<li>{m,n} can match repetitions between x and y (both inclusive)

<ul>
<li><code>a{2,3}</code> can match &#8216;aa&#8217; or &#8216;aaa&#8217;.</li>
</ul></li>
</ul>

<h3 id="grouping">Grouping</h3>

<ul>
<li><code>(group)</code>: capture part of the regex together</li>
<li><code>(?:group)</code>: will group together but will not be recognized in backreferences</li>
</ul>

<p>Talking about repetitions, all the examples above are about repetition of single characters. Is it possible to repeat certain words? Absolutely. Parenthesis() can group part of the regex together; in which case, you can repeat that part after grouping. For example, <code>Regular expression is (not)? awesome</code> can match either &#8216;Regular expression is awesome&#8217; or &#8216;Regular expression is not awesome&#8217;. (We know it is!!!)</p>

<h3 id="backreferences">Backreferences</h3>

<ul>
<li><code>(regex1)regex2\1</code></li>
</ul>

<p>As mentioned earlier, parentheses ( ) in regex capture group, which can be used by backreferences. Backreferences match the same text as previously matched by a capturing group. For example: <code>(1)23\1</code> will match &#8216;1231&#8217;, and <code>12(3)\1</code> will match &#8216;1233&#8217;. The number behind &#8216;' means group number. The group number is determined by the number of the parentheses. The simplest example to show like this: &#8217;(\d)(\d)(\d)(\d)\4\3\2\1&#8217; can match &#8216;12344321&#8217;. Backreferences will always repeat the pattern they referred to. so when you want to repeat a pattern, a backreferences will always be helpful!</p>

<p>However, there is one thing need to be aware of: capturing group that match nothing does not equal to capturing group that did not participate in the match at all. </p>

<ul>
<li>One the one hand, <code>(a?)b\1</code> can match &#8216;b&#8217;, where <code>a</code> does not happen, so the () captures nothing. <code>\1</code> will match nothing as well. There is nothing after &#8216;b&#8217; so &#8216;b&#8217; can be matched.</li>
<li>One the other hand, <code>(a)?b\1</code> cannot match &#8216;b&#8217;. Why? Since <code>(a)</code> does not happen instead of <code>a</code>, this capturing group does not participate in the match at all. Since there is <code>?</code> after (a), it will be OK. However, \1 will not participate in the match, and there is no option sign &#8216;?&#8217;, which will cause the failure. Due to the failure, &#8216;b&#8217; will not be matched.</li>
</ul>

<p>If you have too many parentheses to capture group, and you do not some of the group to be capturing group, just put <code>?:</code> after the first parenthese, which will look like <code>(?:aaa)</code>, which will create a non-capturing group.</p>

<p>One useful example of backreferences is to check for doubled words or numbers. <code>\b([\w+]\s+\1\b</code> can capture stuff like &#8216;123 123&#8217;, which can help find duplicates. </p>

<h3 id="forwardreferences">ForwardReferences</h3>

<p>Forwardreferences just like backreferences. Backreferences will refer to group captured earlier while forwardreferences will refer to group captured later. Forwardreferences for example, can be something like <code>\123(45)</code> can match &#8216;452345&#8217;. </p>

<p>In practice, forwardreferences are not very helpful, and will not be used often. Therefore, not all the languages support forwardreferences, including Python. </p>

<h3 id="lookahead">Lookahead</h3>

<ul>
<li><code>regex1(?=regex2)</code>: match regex1 following by regex2</li>
<li><code>regex2(?!regex2)</code>: match regex1 not following by regex2</li>
</ul>

<p>All the examples we talked about before are related to the characters or words you are looking for directly, which means, when you want to search for &#8216;dog&#8217; in &#8216;I love dogs&#8217;, you just search &#8216;dog&#8217;. </p>

<p>But how about this? Within the word &#8216;chocolate&#8217;, there are three &#8217;c&#8217;s, but you want to get the &#8216;c&#8217; before the letter &#8216;o&#8217; only, not the other &#8216;c&#8217;. There are certainly ways to do so. There is a regex pattern looks like <code>regex1(?=regex2)</code>. In the chocolate example, it looks like <code>c(?=o)</code>: &#8216;cho<strong>c</strong>olate&#8217;. This pattern means regex will find &#8216;c&#8217; followed by an &#8216;o&#8217;. Regex engine will only show the regex1 that you are looking for, not the following regex2. </p>

<p>What about the opposite way? There is a pattern that can match characters not following by another characters as well. In the above example, you are looking for &#8216;c&#8217; not following by an &#8216;o&#8217;. The pattern will look like <code>regex1(?!regex2)</code>. <code>c(?!o)</code> can find &#8216;<strong>c</strong>hocolate&#8217;. </p>

<p>This two patterns are called lookahead. </p>

<h3 id="lookbehind">Lookbehind</h3>

<ul>
<li><code>(?&lt;=regex2)regex1</code>: match regex1 behind regex2</li>
<li><code>(?&lt;!regex2)regex1</code>: match regex1 not behind regex2</li>
</ul>

<p>If there are &#8216;lookahead&#8217;, there will be &#8216;lookbehind&#8217;. Here is a practical example: you are doing a research on Facebook to learn whether gmail or hotmail is more popular. You may want to grab all the registered email and get the email address. You cannot count them one by one for sure since it will take forever. What will you do? Lookbehind of regex can help since all email address contains &#8216;@&#8217;. </p>

<p>The lookbehind pattern looks like this: <code>(?&lt;=regex2)regex1</code>. It means looking for and return regex1 following by regex2. In the email example, it looks like this: <code>(?&lt;=@)(gmail | hotmail)</code>. Regex engine will return either &#8216;gmail&#8217; or &#8216;hotmail&#8217; following by @, and you can get all the data you need very easily.</p>

<p>If you are looking for regex1 not following by regex2, like lookahead, just change &#8216;=&#8217; to &#8216;!&#8217;. As a result, the pattern becomes <code>(?&lt;!regex2)regex1</code>π. </p>

<h3 id="application">Application</h3>

<p>The explanation above covers most of the patterns in regex. Can&#8217;t wait to try it? Here are some ways to apply regex:</p>

<ul>
<li>Install in Excel. You can find the instruction and example <a href="http://stackoverflow.com/questions/22542834/how-to-use-regular-expressions-regex-in-microsoft-excel-both-in-cell-and-loops">here</a></li>
<li>MySQL REGEP</li>
<li>Python re operations.</li>
</ul>

<h3 id="regex-resources">Resources</h3>

<p>I want to provide some documentations and website that can help you understand and practice regex. There are many other resources you can use, such as Codecademy, but the following three are extremely useful for me.</p>

<ul>
<li><a href="http://www.regular-expressions.info/reference.html">Regex Documentation</a> provides the comprehensive documentation you can refer to help you understand all aspects of regex.</li>
<li><a href="http://www.regexr.com">RegExr</a> is an awesome website that summarize the most important information about regex. It has cheatsheet you can refer to, and have samples that can help you decide whether your regex is correct.</li>
<li><a href="https://www.hackerrank.com">Hackerrank</a> has very good practice for people check how their knowledge. It also has lots of other languages practice, such as SQL and Python.</li>
</ul>

<p>These are all the basics of Regular Expression. Hope you enjoy learning it. :)</p>

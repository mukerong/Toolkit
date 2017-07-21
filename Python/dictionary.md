<h3>Dictionary</h3>

<h4>dict.keys()</h4>

<ul>
<li>return a list of all keys</li>
<li>dict_keys type</li>
<li>use list() to transfer to a list</li>
</ul>

<h4>dict.values()</h4>

<ul>
<li>return a list of all values</li>
<li>dict_values type</li>
<li>use list() to transfer to a list</li>
</ul>

<h4>dict.items()</h4>

<p>return a list of tuples of keys and values</p>

<pre><code class="Python">for key, value in dict.items():
    pass
</code></pre>

<h4>dict.get()</h4>

<h4>defaultdict</h4>

<p>Here is <a href="https://www.accelebrate.com/blog/using-defaultdict-python/">some examples</a></p>

<pre><code class="Python">from collections import defaultdict
mydict = defaultdict(function)
</code></pre>

<h4>append multiple values for one key</h4>

<p><a href="http://stackoverflow.com/questions/3199171/append-multiple-values-for-one-key-in-python-dictionary">Reference</a></p>

<pre><code class="Python">dict[key].append()
</code></pre>

<h4>Loop issues</h4>

<p>When looping a dictionary and appending to a list, you will see that all the dictionary has the same values. This is because, when you create keys and values for a dictionary in a loop, the values assigned to the keys are stored as a reference. Therefore, if in the same loop you give a key another value, it will update the reference to the value for this loop and all preceding loops.</p>

<p>There are two ways to deal with this:</p>

<ol>
<li>Append a copy of the dictionary each loop</li>
</ol>

<pre><code class="Python">list.append(dictionary.copy())
</code></pre>

<ol>
<li>Initialize the dictionary for each loop</li>
</ol>

<pre><code class="Python">for element in root:
    element_dict = {}
    for item in list:
        element_dict[item] = something
        desired_list.append(element_dict)
</code></pre>

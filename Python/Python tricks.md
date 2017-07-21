<h1>Python Tricks</h1>

<hr />

<h2>Table of Contents</h2>

<ul>
<li><a href="#unique-value">Find Unique Value</a></li>
<li><a href="#change-key">Change Dictionary Key</a></li>
</ul>

<hr />

<h3 id="unique-value">Find Unique Value</h3>

<pre><code class="Python">unique = set()
for row in file:
    unique.add(row[key])
</code></pre>

<h3 id="change-key">Change Dictionary Key</h3>

<pre><code class="Python">dict[new_key] = dict.pop(old_key)
</code></pre>

<p>or</p>

<pre><code class="Python">dict[new_key] = dict[old_key]
del[dict[old_key]]
</code></pre>

<h3>Check NaN in DataFrame</h3>

<p><a href="https://stackoverflow.com/questions/29530232/python-pandas-check-if-any-value-is-nan-in-dataframe">Stackoverflow Reference</a></p>

<pre><code class="Python">df.isnull().any()

df.isnull().any().any()

df.isnull().values.any() # Fastest

df.isnull().values.sum()

df.isnull.sum().sum()
</code></pre>

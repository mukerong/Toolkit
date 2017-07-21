<h3>Find Unique Value</h3>

<pre><code class="Python">unique = set()
for row in file:
    unique.add(row[key])
</code></pre>

<h3>Change Dictionary Key</h3>

<pre><code class="Python">dict[new_key] = dict.pop(old_key)
</code></pre>

<p>or</p>

<pre><code class="Python">dict[new_key] = dict[old_key]
del[dict[old_key]]
</code></pre>

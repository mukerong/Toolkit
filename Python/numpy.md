<h3>Numpy</h3>

<h4>install</h4>

<pre><code class="Python">install numpy as np
</code></pre>

<h4>array</h4>

<ul>
<li>each element needs to be the same type</li>
<li>vectorized operation</li>
</ul>

<h4>in-place vs not in-place</h4>

<ul>
<li>in-place will modify the original array

<ul>
<li>+=</li>
<li>slice</li>
</ul></li>
<li>not in-place will create a copy of original array

<ul>
<li>= X + X</li>
</ul></li>
</ul>

<h4>attributes</h4>

<ul>
<li>arr.dtype - return the type of arrays</li>
</ul>

<h4>logical</h4>

<ul>
<li>&amp;</li>
<li>|</li>
<li>~</li>
<li>bitwise operations, use <a href="https://docs.scipy.org/doc/numpy/reference/generated/numpy.logical_and.html">np.logical_and()</a>, <a href="https://docs.scipy.org/doc/numpy/reference/generated/numpy.logical_or.html">np.logical_or</a> and <a href="https://docs.scipy.org/doc/numpy/reference/generated/numpy.logical_not.html">np.logical_not</a> for non-boolean arrays</li>
</ul>

<h4>functions &amp; methods</h4>

<ul>
<li><a href="https://docs.scipy.org/doc/numpy/reference/generated/numpy.argmax.html">arr.argmax() or np.argmax(arr)</a> - return the position of the maximum value</li>
<li>arr.max() or np.max(arr)</li>
<li>arr.min() or np.min(arr)</li>
<li>arr.mean() or np.mean(arr)</li>
<li>arr.std() or np.std(arr)

<ul>
<li>return population std by default, different from pd.std()</li>
</ul></li>
<li>arr.sum() or np.sum(arr)</li>
<li><a href="https://docs.scipy.org/doc/numpy/reference/generated/numpy.corrcoef.html">np.corrcoef()</a> - return Pearson&#8217;s r

<ul>
<li>will return a matrix, use index to get the desired one</li>
</ul></li>
<li><a href="https://docs.scipy.org/doc/numpy/reference/generated/numpy.where.html">np.where</a>

<ul>
<li><a href="https://discussions.udacity.com/t/apply-and-applymap-confusion/241704/6">Use it with DataFrame</a></li>
</ul></li>
</ul>

<h3>Pandas</h3>

<h4>install</h4>

<pre><code class="Python">install pandas as pd
</code></pre>

<h4>Pandas methods &amp; functions</h4>

<ul>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.read_csv.html">pd.read csv()</a></li>
</ul>

<pre><code class="Python">pd.read_csv('')
</code></pre>

<ul>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.html">pd.Series(value, index)</a></li>
</ul>

<pre><code class="Python">pd.Series([1,2,3,4], index = ['a', 'b', 'c', 'd'])

a 1
b 2
c 3
d 4
</code></pre>

<ul>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.html">pd.DataFrame()</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.qcut.html">pd.qcut()</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.cut.html">pd.cut</a>

<ul>
<li><a href="https://discussions.udacity.com/t/titanic-age-data-use-of-pd-cut-causes-a-warning/172477">Udacity Questions</a></li>
</ul></li>
</ul>

<h4>Series functions &amp; methods</h4>

<ul>
<li>can use the array methods</li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.std.html">Series.std</a> - return sample std by default, different from np.std, which returns population std by default</li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.unique.html">Series.unique()</a> - return the unique values</li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.describe.html">Series.describe()</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.loc.html">Series.loc[&#8216;index_name&#8217;]</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.iloc.html">Series.iloc[&#8216;position&#8217;]</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.argmax.html">Series.argmax()</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/version/0.18.1/generated/pandas.Series.idxmax.html">Series.idxmax()</a> - same with argmax</li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.dropna.html">Series.dropna()</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.fillna.html">Series.fillna</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.add.html">Series.add()</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.apply.html">Series.apply(function_name)</a> - return a new Series

<ul>
<li>don&#8217;t put <code>()</code> after function</li>
</ul></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.map.html">Series.map()</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.nlargest.html">Series.nlargest()</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.sort_values.html">Series.sort_values()</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.append.html">Series.append()</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.rename.html">Series.rename()</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.value_counts.html">Series.value_counts</a></li>
</ul>

<h4>DataFrame attributes</h4>

<ul>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.values.html">df.values</a> - return a 2D np.array containing only the values

<ul>
<li>useful when calculate mean for all values</li>
</ul></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.html">df.columns</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.html">df.index</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.html">df.dtype</a></li>
</ul>

<h4>DataFrame functions &amp; methods</h4>

<ul>
<li>To loop the column:</li>
</ul>

<pre><code class="Python">for col in list(df.columns):
</code></pre>

<p>or</p>

<pre><code class="Python">for col in df:
</code></pre>

<ul>
<li>(axis = 0) == (axis =&#8217;index&#8217;)</li>
<li>(axis = 1) == (axis = &#8216;column&#8217;)</li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.mean.html">df.mean()</a> - return means for each column</li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.loc.html">df.loc[]</a> - by index</li>
<li><a href="http://pandas.pydata.org/pandas-docs/version/0.17.0/generated/pandas.DataFrame.iloc.html">df.iloc[]</a> - by position</li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.idxmax.html">df.idxmax(axis = )</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.head.html">df.head(n = )</a> - return the first n rows</li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.describe.html">df.describe()</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.std.html">df.std()</a> - return sample std by default

<ul>
<li>when calculating Pearson&#8217;s r, use un-corrected std, ddof = 0</li>
</ul></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.stack.html">df.stack()</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.shift.html">df.shift()</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.apply.html#pandas.DataFrame.apply">df.apply(function)</a> - make calculation for each column/row, return a column/row or one single value

<ul>
<li><a href="http://stackoverflow.com/questions/12182744/python-pandas-apply-a-function-with-arguments-to-a-series">if function has more than one params</a></li>
</ul></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.applymap.html">df.applymap(function)</a> - make calculation for each element</li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.add.html">df.add()</a>

<ul>
<li><a href="https://discussions.udacity.com/t/quiz-15-vectorized-operations/242845">Questions I had before</a></li>
</ul></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.sub.html">df.sub()</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.div.html">df.div()</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.groupby.html">df.groupby()</a>

<ul>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/groupby.html">More details</a></li>
<li>attributes: .groups</li>
</ul></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.merge.html">df.merge()</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.drop.html">df.drop()</a>

<ul>
<li>axis = 1 for column</li>
<li>axis = 0 for row</li>
</ul></li>
<li><a href="http://stackoverflow.com/questions/13411544/delete-column-from-pandas-dataframe">del df[&#8216;column_name&#8217;]</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.isnull.html">df.isnull()</a>

<ul>
<li><a href="http://stackoverflow.com/questions/29530232/python-pandas-check-if-any-value-is-nan-in-dataframe">quick check if there are any NaN in df</a></li>
</ul></li>
<li><a href="http://pandas.pydata.org/pandas-docs/version/0.18.1/generated/pandas.DataFrame.dropna.html">df.dropna</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.unstack.html">df.unstack</a></li>
</ul>

<h4>Plot</h4>

<ul>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.plot.html">Series.plot()</a> - index is x-axis, value is y-axis</li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.hist.html">Series.hist()</a></li>
<li><a href="http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.plot.html">df.plot()</a></li>
</ul>

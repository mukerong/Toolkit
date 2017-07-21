<h3>matplotlib.pyplot</h3>

<h4>install</h4>

<pre><code class="Python">%matplotlib inline
import matplotlib.pyplot as plt
import seaborn as sns # automatically make plt look better
</code></pre>

<h4>Set up</h4>

<p>To control where to put each plot:</p>

<pre><code class="Python">fig = plt.figure()
axes1 = fig.add_axes([left, bottom, width, height]) # range from 0 to 1
axes2 = fig.add_axes([left, bottom, width, height]) # range from 0 to 1
axes1.plot()
axes2.plot()
</code></pre>

<p>Use Matplotlib layout manager:</p>

<pre><code class="Python">fig, axes = plt.subplots(nrows = , ncols = )
axes.plot
</code></pre>

<h4><a href="https://matplotlib.org/api/figure_api.html">figure</a></h4>

<ul>
<li>size</li>
</ul>

<pre><code class="Python">fig = plt.figure(figsize = (X, X))
</code></pre>

<p>or</p>

<pre><code class="Python">fig, axes = plt.subplots(figsize = (X, X))
</code></pre>

<ul>
<li>save</li>
</ul>

<pre><code class="Python">fig.savefig('filename.png', dpi = )
</code></pre>

<ul>
<li>axis position</li>
</ul>

<pre><code class="Python">fig.subplots_adjust(left = , right = , bottom = , top = )
</code></pre>

<h4><a href="https://matplotlib.org/api/axes_api.html">axes</a></h4>

<ul>
<li>label</li>
</ul>

<pre><code class="Python">axes.set_xlabel('x axes label')
axes.set_ylabel('y axes label')
</code></pre>

<ul>
<li>title</li>
</ul>

<pre><code class="Python">axes.set_title('title of plot')
</code></pre>

<ul>
<li>legends</li>
</ul>

<pre><code class="Python">ax.legend(['legend1', 'legend2', 'legend3'])
</code></pre>

<p>or</p>

<pre><code class="Python">ax.plot(label = 'legend1')
ax.plot(label = 'legend2')
ax.legend()
</code></pre>

<p>location</p>

<pre><code class="Python">ax.legend(loc = 0) # let matplotlib decide the optimal location
ax.legend(loc = 1) # upper right corner
ax.legend(loc = 2) # upper left corner
ax.legend(loc = 3) # lower left corner
ax.legend(loc = 4) # lower right corner
</code></pre>

<ul>
<li><a href="http://stackoverflow.com/questions/22287827/add-text-to-pandas-dataframe-plot">add text</a>

<ul>
<li>ax.text()</li>
<li>ax.annotate()</li>
</ul></li>
<li><p>line color</p></li>
</ul>

<pre><code class="Python">ax.plot(color = 'red')
ax.plot(color = '#1155dd')
ax.plot('b.-') # blue line with dots
ax.plot('g--') # green dashed line
</code></pre>

<ul>
<li>line width</li>
</ul>

<pre><code class="Python">ax.plot(linewidth = |lw = )
</code></pre>

<ul>
<li>line style: &#8216;-&#8217;, &#8216;&#8211;&#8217;, &#8216;-.&#8217;, &#8216;:&#8217;, &#8216;steps&#8217;</li>
</ul>

<pre><code class="Python">ax.plot(linestyle = '-'|ls = )
</code></pre>

<p>custom dash</p>

<pre><code class="Python">line, = ax.plot()
line.set_dashes([]) # format: line length, space length...
</code></pre>

<ul>
<li>line marker: &#8216;+&#8217;, &#8216;o&#8217;, &#8216;*&#8217;, &#8216;s&#8217;, &#8216;,&#8217;, &#8216;.&#8217;, &#8216;1&#8217;, &#8216;2&#8217;, &#8230;</li>
</ul>

<pre><code class="Python">ax.plot(marker = , markersize = , markerfacecolor = )
</code></pre>

<ul>
<li>plot range</li>
</ul>

<pre><code class="Python">ax.set_xlim([ , ])
ax.set_ylim([ , ])
</code></pre>

<ul>
<li>logarithmic scale</li>
</ul>

<pre><code class="Python">ax.plot()
ax.set_yscale('log')
</code></pre>

<ul>
<li>ticks</li>
</ul>

<pre><code class="Python">ax.set_xticks([1, 2, 3, 4, 5])
ax.set_xticklabels([r'$\alpha$', r'$\beta$', ...])
</code></pre>

<ul>
<li>axis number and label spacing</li>
</ul>

<pre><code># distance between x and y axis and the numbers on the axes
matplotlib.rcParams['xtick.major.pad'] = 5
matplotlib.rcParams['ytick.major.pad'] = 5

# padding between axis label and axis numbers
ax.xaxis.labelpad = 5
ax.yaxis.labelpad = 5
</code></pre>

<ul>
<li>axis position</li>
</ul>

<pre><code class="Python">fig.subplots_adjust(left = , right = , bottom = , top = )
</code></pre>

<ul>
<li>grid</li>
</ul>

<pre><code class="Python">ax.grid(True)
ax.grid(color = , alpha = , linestyle = , linewidth = )
</code></pre>

<ul>
<li><a href="https://matplotlib.org/api/spines_api.html">spines</a></li>
</ul>

<pre><code class="Python">ax.spines['top'].set_color()
ax.spines['bottom'].set_linewidth()
ax.spines['right'].set_color('none') # turn off axis spines
ax.yaxis.tick_left()
</code></pre>

<ul>
<li>twin axes</li>
</ul>

<pre><code class="Python">for label in ax1.get_yticklabels():
    label.set_color('blue')

ax2 = ax1.twinx()
for label in ax2.get_yticklabels():
    label.set_color()
</code></pre>

<ul>
<li><a href="https://matplotlib.org/devdocs/api/_as_gen/matplotlib.axes.Axes.axhline.html">draw horizontal line</a></li>
</ul>

<pre><code class="Python">ax.axhline(y = , xmin = , xmax = )
</code></pre>

<ul>
<li><a href="https://matplotlib.org/api/ticker_api.html">scientific notation</a></li>
</ul>

<pre><code class="Python">from matplotlib import ticker
formatter = ticker.ScalarFormatter(useMathText = True)
formatter.set_scientific(True)
formatter.set_powerlimits((-1, 1))
ax.yaxis.set_major_formatter(formatter)
</code></pre>

<h4>format text</h4>

<ul>
<li>LaTeX</li>
</ul>

<pre><code class="Python">ax.plot(label = r'$\alpha$')
ax.set_xlabel(r'$\mu$', fontsize = )
</code></pre>

<ul>
<li>configuration parameters</li>
</ul>

<pre><code class="Python">matplotlib.rcParams.update({'font.size': , 'font.family': , 'text.usetex': })
</code></pre>

<h4>direct plot</h4>

<ul>
<li>label</li>
</ul>

<pre><code class="Python">plt.xlabel('label for x axis')
plt.ylabel('label for y axis')
</code></pre>

<ul>
<li>title</li>
</ul>

<pre><code class="Python">plt.title('title of plot')
</code></pre>

<h4>histogram</h4>

<pre><code class="Python">plt.hist(data, bins = XX)
</code></pre>

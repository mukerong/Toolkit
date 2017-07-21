<h3>Read file to Python</h3>

<h4>CSV</h4>

<ul>
<li>Documentation

<ul>
<li><a href="https://docs.python.org/2/library/csv.html">CSV Documentation</a></li>
<li><a href="https://www.codementor.io/sheena/python-generators-and-iterators-du1082iua">Iterator Tutorial</a></li>
</ul></li>
<li><p>Python</p></li>
</ul>

<pre><code class="Python">with open(datafile, 'rb') as f:
    header = f.readline().split(',')
    for line in f:
        fields = line.split(',')
        entry = {}
        
        for i, v in enumerate(fields):
            entry[head[i].strip()] = v.strip()
        
        data.append(entry)
</code></pre>

<ul>
<li>csv</li>
</ul>

<pre><code class="Python">import csv

data = []
with open(datafile, 'rb') as f:
    r = csv.DictReader(f)
    for line in r:
        data.append(line)
</code></pre>

<ul>
<li>unicodecsv</li>
</ul>

<pre><code class="Python">import unicodecsv

file = []
f = open('file_name.csv', 'rb') # 'rb' is required
reader = unicodecsv.DictReader(f) # read as a dictionary

for row in reader: # iterator can only be used once
    file.append(row)
    
f.close()
</code></pre>

<p>To avoid f.close(), and make the file close automatically:</p>

<pre><code class="Python">import unicodecsv

file = []
with open('file_name.csv', 'rb') as f: 
    reader = unicodecsv.DictReader(f) # read as a dictionary

    for row in reader: # iterator can only be used once
        file.append(row)
</code></pre>

<p>To use without iterator:</p>

<pre><code class="Python">import unicodecsv

with open('file_name.csv', 'rb') as f: 
    reader = unicodecsv.DictReader(f) # read as a dictionary
    file = list(reader)
</code></pre>

<h4>Excel</h4>

<ul>
<li>xlrd # for read excel file</li>
</ul>

<pre><code class="Python">import xlrd

workbook = xlrd.open_workbook(datafile)
sheet = workbook.sheet_by_index(0) 
data = [[sheet.cell_value(r, col)] for col in range(sheet.ncols) 
             for r in range(sheet.nrows)]
             
             
# method

sheet.nrows
sheet.cell_type(row, col)
sheet.cell_value(row, col)
sheet.col_values(col, start_rowx = , end_rowx = )
xlrd.xldate_as_tuple(time, 0)
</code></pre>

<ul>
<li>xlwd # for create excel file</li>
</ul>

<h4>JSON</h4>

<pre><code class="Python">import json
import requests
import codecs
</code></pre>

<h4>XML</h4>

<ul>
<li><a href="https://docs.python.org/3/library/xml.etree.elementtree.html">XML Documentation</a></li>
<li><a href="https://docs.python.org/2/library/xml.etree.elementtree.html#module-xml.etree.ElementTree">Python 2 Documentation</a></li>
<li><a href="https://docs.python.org/2/library/xml.etree.elementtree.html">Python 3 Documentation</a></li>
</ul>

<pre><code class="Python">import xml.etree.ElementTree as ET
import pprint
</code></pre>

<pre><code class="Python">tree = ET.parse('name.xml')
root = tree.getroot()
</code></pre>

<h4>Web Scrapping</h4>

<ul>
<li><a href="https://www.crummy.com/software/BeautifulSoup/bs4/doc/">Documentation</a></li>
</ul>

<pre><code class="Python">from bs4 import BeautifulSoup
soup = BeautifulSoup(html, 'lxml')
codes = soup.find()
value = codes[value]
</code></pre>

<ul>
<li>Procedure

<ol>
<li>Build list</li>
<li>Make HTTp request to download all data</li>
<li>Parse the datafile</li>
</ol></li>
<li>Best Practice

<ol>
<li>Look at how a browser makes request</li>
<li>Emulate in code</li>
<li>If stuff blows up, look at your HTTP traffic</li>
<li>Return to 1 until it works</li>
</ol></li>
</ul>

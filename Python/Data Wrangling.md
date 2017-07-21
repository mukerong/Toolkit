<h1>Data Wrangling</h1>

<hr />

<h2>Table of Content</h2>

<ul>
<li><a href="#csv">csv Module</a>

<ul>
<li><a href="#csv_documentation">Documentation</a></li>
<li><a href="#csv_functions">Common Functions &amp; Classes</a></li>
<li><a href="#csv_application">Application</a></li>
</ul></li>


<hr />

<h3 id="csv">csv Module</h3>


<h4 id="csv_documentation">Documentation</h4>

<ul>
<li><a href="https://docs.python.org/2/library/csv.html">Python2</a></li>
<li><a href="https://docs.python.org/3/library/csv.html">Python3</a>
</br></li>
</ul>

<h4 id="csv_functions">Common Functions</h4>


<h5>csv.reader() - Return a reader object</h5>

<p><code>csv</code> module will import all the data as strings.</p>

<pre><code class="Python">import csv
with open('XXX.csv', 'r', newline = ' ') as csvfile:
    reader = csv.reader(csvfile, delimiter = ',')
    for row in reader:
        print(row)
</code></pre>

<p>Please note that once you leave the <code>with</code> block, the file is closed.</p>

<p>or</p>

<pre><code class="Python">import csv
f = oepn('XXX.csv', 'r')
reader = csv.reader(f)
for row in reader:
    print(row)

f.close()
</code></pre>

<p>Please note that file needs to be closed explicitly, or it will remain open. </p>

<h5>csv.writer() - Return a writer object</h5>

<pre><code class="Python">f = open('XXX.csv', 'r')
reader = csv.reader(f)

with open('XXX.csv', 'w', newline = '') as csvfile: 
    writer = csv.writer(csvfile, delimiter = ',')
    for row in reader:
        writer.writerow(row)
        
f.close()
</code></pre>

<p><code>newline = ''</code> is required to make the function work.</p>

<h5>csv.DictReader() - class, map the information to an OrderedDict</h5>

<p><code>csv</code> module will import all the data as strings.</p>

<pre><code class="Python">with open('XXX.csv', 'r', fieldnames = sequence) as csvfile:
    reader = csv.DictReader(csvfile)
    header = reader.fieldnames
    for row in reader:
        print(row['column1']) 
</code></pre>

<p>If <em>fieldnames</em> is omitted, the value in the first row is used as the fieldnames. </p>

<h5>csv.DictWriter() - class, map the dictionaries onto output rows</h5>

<pre><code class="Python">f = open('XXX.csv', 'r')
reader = csv.DictReader(f)
header = reader.fieldnames
with open('XXX.csv', 'w') as csvfile:
    writer = csv.DictWriter(csvfile, delimiter = ',', fieldnames = header)
    writer.writehead()
    for row in reader:
        writer.writerow(row)
        
f.close()  
</code></pre>

<p><em>fieldnames</em> is required. </p>

<h4 id="csv_application">Application</h4>

<h5>Use criteria to select data and move to new file</h5>

<pre><code class="Python">import csv

input_file = 'XXX.csv'
criteria1_file = 'XXX.csv'
criteria2_file = 'XXX.csv'

with open(input_file, 'r') as f:
    reader = csv.DictReader(f)
    header = reader.fieldnames
    
    g = open(criteria1_file, 'w')
    writerg = csv.DictWriter(g, delimiter = ',', fieldnames = header)
    writerg.writeheader()
    
    b = open(criteria2_file, 'w')
    writerb = csv.DictWriter(b, delimiter = ',', fieldnames = header)
    writerb.writeheader()
    
    for row in reader:
        if criteria1:
            writerg.writerow(row)
        elif criteria2:
            writerb.writerow(row)
    
    g.close()
    b.close()
</code></pre>

<h5>Append information to a new file</h5>

<pre><code class="Python">import csv

input_file = 'XXX.csv'
criteria1_file = 'XXX.csv'
criteria2_file = 'XXX.csv'

with open(input_file, 'r') as f:
    reader = csv.DictReader(f)
    header = reader.fieldnames
    counterg = 0
    counterb = 0
    
    for row in reader:
        if criteria1:
            with open(criteria1_file, 'a+') as g:
                writerg = csv.DictWriter(g, delimiter = ',', fieldnames = header)
                if counterg == 0:
                    writerg.writeheader()
                    counterg += 1
                writerg.writerow(row)
        elif criteria2:
            with open(criteria2_file, 'a+') as b:
                writerb = csv.DictWriter(b, delimiter = ',', fieldnames = header)
                if counterb == 0:
                    writerb.writeheader()
                    counterb += 1
                writerb.writerow(row)
</code></pre>

<p>Please note you will have to delete the file if you run the code multiple times since it will keep adding information to the same file.</p>

<h5>Use List to append information</h5>

<pre><code class="Python">import csv

input_file = 'XXX.csv'
criteria1_file = 'XXX.csv'
criteria2_file = 'XXX.csv'

with open(input_file, 'r') as f:
    reader = csv.DictReader(f)
    header = reader.fieldnames
    list1 = []
    list2 = []
    for row in reader:
        if criteria1:
            list1.append(row)
        elif criteria2:
            list2.append(row)
            
with open(criteria1_file, 'w') as g:
    writer = csv.DictWriter(g, delimiter = ',', fieldnames = header)
    writer.writeheader()
    writer.writerows(list1)

with open(criteria2_file, 'w') as b:
    writer = csv.DictWriter(b, delimiter = ',', fieldnames = header)
    writer.writeheader()
    for row in list2:
        writer.writerow(row)
</code></pre>

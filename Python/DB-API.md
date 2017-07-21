<h3>DB-API</h3>

<h4>sqlite3</h4>

<p>To fetch the results:</p>

<pre><code class="Python">import sqlite3
conn = sqlite3.connect('name')
cursor = conn.cursor()
cursor.execute('query')
results = cursor.fetchall()
print(results)
conn.close()
</code></pre>

<p>To insert a row:</p>

<pre><code class="Python">db = sqlite3.connect('database')
c = db.cursor()
c.execute('query')
db.commit()
</code></pre>

<p>Export data to CSV:</p>

<pre><code class="sql">sqlite&gt; .mode csv
sqlite&gt; .output file_name.csv
sqlite&gt; select * from table_name;
sqlite&gt; .exit
</code></pre>

<p>Import CSV into table:</p>

<pre><code class="sql">$ sqlite3 new.db -- If you'd like your csv's in a new database
sqlite&gt; CREATE TABLE table_name() -- build your schema
sqlite&gt; .mode csv
sqlite&gt; .import file_name.csv table_name
</code></pre>

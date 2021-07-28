```python
import csv
import pandas as pd
```


```python
kwlist = list()
kwcount = list()

with open("C:\\Users\\thach\\OneDrive\\Desktop\\Python Notebooks\\JD.txt") as f:
    reader = csv.reader(f, delimiter =' ')
    kw = [i for row in reader for i in row]
    for i in range(0, len(kw)):
        kw[i] = kw[i].lower()
        if len(kw[i]) > 1 and kw[i][-1] in [',', '.', ';']:
            kw[i] = kw[i][:-1]
```


```python
for i in kw:
    if 4 < len(i) < 20:
        if i not in kwlist: 
            kwlist.append(i)
            kwcount.append(0)
        if i in kwlist:
            kwcount[kwlist.index(i)] += 1
```


```python
d = {'Keyword': kwlist, 'Kw Count': kwcount}
df = pd.DataFrame(d)
df.sort_values(by = 'Kw Count', ascending = False).head(30)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Keyword</th>
      <th>Kw Count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>supply</td>
      <td>95</td>
    </tr>
    <tr>
      <th>1</th>
      <td>chain</td>
      <td>87</td>
    </tr>
    <tr>
      <th>46</th>
      <td>experience</td>
      <td>58</td>
    </tr>
    <tr>
      <th>211</th>
      <td>skills</td>
      <td>45</td>
    </tr>
    <tr>
      <th>15</th>
      <td>business</td>
      <td>43</td>
    </tr>
    <tr>
      <th>5</th>
      <td>inventory</td>
      <td>34</td>
    </tr>
    <tr>
      <th>47</th>
      <td>planning</td>
      <td>30</td>
    </tr>
    <tr>
      <th>2</th>
      <td>analyst</td>
      <td>28</td>
    </tr>
    <tr>
      <th>210</th>
      <td>strong</td>
      <td>27</td>
    </tr>
    <tr>
      <th>35</th>
      <td>ability</td>
      <td>27</td>
    </tr>
    <tr>
      <th>49</th>
      <td>analysis</td>
      <td>25</td>
    </tr>
    <tr>
      <th>39</th>
      <td>analytical</td>
      <td>25</td>
    </tr>
    <tr>
      <th>159</th>
      <td>support</td>
      <td>25</td>
    </tr>
    <tr>
      <th>236</th>
      <td>required</td>
      <td>23</td>
    </tr>
    <tr>
      <th>48</th>
      <td>management</td>
      <td>23</td>
    </tr>
    <tr>
      <th>133</th>
      <td>customer</td>
      <td>22</td>
    </tr>
    <tr>
      <th>23</th>
      <td>company</td>
      <td>22</td>
    </tr>
    <tr>
      <th>67</th>
      <td>production</td>
      <td>22</td>
    </tr>
    <tr>
      <th>196</th>
      <td>process</td>
      <td>21</td>
    </tr>
    <tr>
      <th>81</th>
      <td>degree</td>
      <td>21</td>
    </tr>
    <tr>
      <th>203</th>
      <td>related</td>
      <td>20</td>
    </tr>
    <tr>
      <th>50</th>
      <td>preferred</td>
      <td>20</td>
    </tr>
    <tr>
      <th>121</th>
      <td>logistics</td>
      <td>19</td>
    </tr>
    <tr>
      <th>134</th>
      <td>service</td>
      <td>19</td>
    </tr>
    <tr>
      <th>44</th>
      <td>position</td>
      <td>19</td>
    </tr>
    <tr>
      <th>207</th>
      <td>years</td>
      <td>19</td>
    </tr>
    <tr>
      <th>395</th>
      <td>solutions</td>
      <td>18</td>
    </tr>
    <tr>
      <th>125</th>
      <td>improvement</td>
      <td>18</td>
    </tr>
    <tr>
      <th>124</th>
      <td>develop</td>
      <td>18</td>
    </tr>
    <tr>
      <th>177</th>
      <td>manufacturing</td>
      <td>17</td>
    </tr>
  </tbody>
</table>
</div>



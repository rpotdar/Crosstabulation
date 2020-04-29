```python
import pandas as pd
```


```python
df = pd.read_csv(r"https://raw.githubusercontent.com/KeithGalli/Pandas-Data-Science-Tasks/master/SalesAnalysis/Sales_Data/Sales_April_2019.csv")
```


```python
df
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
      <th>Order ID</th>
      <th>Product</th>
      <th>Quantity Ordered</th>
      <th>Price Each</th>
      <th>Order Date</th>
      <th>Purchase Address</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>176558</td>
      <td>USB-C Charging Cable</td>
      <td>2</td>
      <td>11.95</td>
      <td>04/19/19 08:46</td>
      <td>917 1st St, Dallas, TX 75001</td>
    </tr>
    <tr>
      <td>1</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>2</td>
      <td>176559</td>
      <td>Bose SoundSport Headphones</td>
      <td>1</td>
      <td>99.99</td>
      <td>04/07/19 22:30</td>
      <td>682 Chestnut St, Boston, MA 02215</td>
    </tr>
    <tr>
      <td>3</td>
      <td>176560</td>
      <td>Google Phone</td>
      <td>1</td>
      <td>600</td>
      <td>04/12/19 14:38</td>
      <td>669 Spruce St, Los Angeles, CA 90001</td>
    </tr>
    <tr>
      <td>4</td>
      <td>176560</td>
      <td>Wired Headphones</td>
      <td>1</td>
      <td>11.99</td>
      <td>04/12/19 14:38</td>
      <td>669 Spruce St, Los Angeles, CA 90001</td>
    </tr>
    <tr>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <td>18378</td>
      <td>194090</td>
      <td>Google Phone</td>
      <td>1</td>
      <td>600</td>
      <td>04/08/19 17:11</td>
      <td>177 Jackson St, Los Angeles, CA 90001</td>
    </tr>
    <tr>
      <td>18379</td>
      <td>194091</td>
      <td>AA Batteries (4-pack)</td>
      <td>1</td>
      <td>3.84</td>
      <td>04/15/19 16:02</td>
      <td>311 Forest St, Austin, TX 73301</td>
    </tr>
    <tr>
      <td>18380</td>
      <td>194092</td>
      <td>AAA Batteries (4-pack)</td>
      <td>2</td>
      <td>2.99</td>
      <td>04/28/19 14:36</td>
      <td>347 Sunset St, San Francisco, CA 94016</td>
    </tr>
    <tr>
      <td>18381</td>
      <td>194093</td>
      <td>AA Batteries (4-pack)</td>
      <td>1</td>
      <td>3.84</td>
      <td>04/14/19 15:09</td>
      <td>835 Lake St, Portland, OR 97035</td>
    </tr>
    <tr>
      <td>18382</td>
      <td>194094</td>
      <td>Lightning Charging Cable</td>
      <td>1</td>
      <td>14.95</td>
      <td>04/18/19 11:08</td>
      <td>354 North St, Boston, MA 02215</td>
    </tr>
  </tbody>
</table>
<p>18383 rows × 6 columns</p>
</div>




```python
import os
```


```python
files = [file for file in os,listdir(r"https://github.com/KeithGalli/Pandas-Data-Science-Tasks/tree/master/SalesAnalysis/Sales_Data")]
for file in files:
    print(file)
```


      File "<ipython-input-11-57e498f770bc>", line 1
        files = [file for file in os,listdir(r"https://github.com/KeithGalli/Pandas-Data-Science-Tasks/tree/master/SalesAnalysis/Sales_Data")]
                                    ^
    SyntaxError: invalid syntax
    



```python
files = [file for file in os,listdir(r"https://github.com/KeithGalli/Pandas-Data-Science-Tasks/tree/master/SalesAnalysis/Sales_Data")]
for file in files:
    print(file)
```


      File "<ipython-input-13-15a46f918822>", line 1
        files = [file for file in os,listdir(r"https://github.com/KeithGalli/Pandas-Data-Science-Tasks/tree/master/SalesAnalysis/Sales_Data")]
                                    ^
    SyntaxError: invalid syntax
    



```python
import glob

csvfiles = glob.glob("/path/to/foder/*.csv")
```


```python
print(csvfiles)
```

    []
    


```python
import glob

csvfiles = glob.glob(r"https://github.com/KeithGalli/Pandas-Data-Science-Tasks/tree/master/SalesAnalysis/Sales_Data")
```


```python
csvfiles
```




    []




```python
print(csvfiles)
```

    []
    


```python
print(csvfiles)
```

    []
    


```python
import os, glob
import pandas as pd


```


```python
path = "C:/Users/renuka/Downloads/Pandas-Data-Science-Tasks-master/SalesAnalysis/Sales_Data/"
```


```python
path
```




    'C:/Users/renuka/Downloads/Pandas-Data-Science-Tasks-master/SalesAnalysis/Sales_Data/'




```python
path
```




    'C:/Users/renuka/Downloads/Pandas-Data-Science-Tasks-master/SalesAnalysis/Sales_Data/'




```python
all_files = glob.glob(os.path.join(path,"*.csv"))
```


```python
df_merged = (pd.read_csv(f, sep=',') for f in all_files)
df_merged   = pd.concat(all_files, ignore_index=True)
df_merged.to_csv( "merged.csv")
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-16-53711be61db5> in <module>
          1 df_merged = (pd.read_csv(f, sep=',') for f in all_files)
    ----> 2 df_merged   = pd.concat(all_files, ignore_index=True)
          3 df_merged.to_csv( "merged.csv")
    

    ~\Anaconda3\lib\site-packages\pandas\core\reshape\concat.py in concat(objs, axis, join, join_axes, ignore_index, keys, levels, names, verify_integrity, sort, copy)
        253         verify_integrity=verify_integrity,
        254         copy=copy,
    --> 255         sort=sort,
        256     )
        257 
    

    ~\Anaconda3\lib\site-packages\pandas\core\reshape\concat.py in __init__(self, objs, axis, join, join_axes, keys, levels, names, ignore_index, verify_integrity, copy, sort)
        330                     " only Series and DataFrame objs are valid".format(type(obj))
        331                 )
    --> 332                 raise TypeError(msg)
        333 
        334             # consolidate
    

    TypeError: cannot concatenate object of type '<class 'str'>'; only Series and DataFrame objs are valid



```python
import os, glob
import pandas as pd
# Declare path where all csv files are stored
path = "C:/Users/renuka/Downloads/Pandas-Data-Science-Tasks-master/SalesAnalysis/Sales_Data/"
# Create an array that contains the path to each csv file in directory
all_files = glob.glob(os.path.join(path, "*.csv"))
# df_merged = (pd.read_csv(f, sep=',') for f in all_files)
# df_merged   = pd.concat(all_files, ignore_index=True)

# df_merged.to_csv( "merged.csv")
```


```python
# empty list to store dataframes
li = []

# read each csv file, convert to dataframe using read_csv
# then append dataframe to li
for filename in all_files:
    df = pd.read_csv(filename, index_col=None, header=0)
    li.append(df)
 
# concatenate  multipledataframes along column because axis=0
frame = spd.concat(li, axis=0, ignore_index=True)
```


```python
frame
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
      <th>Order ID</th>
      <th>Product</th>
      <th>Quantity Ordered</th>
      <th>Price Each</th>
      <th>Order Date</th>
      <th>Purchase Address</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>176558</td>
      <td>USB-C Charging Cable</td>
      <td>2</td>
      <td>11.95</td>
      <td>04/19/19 08:46</td>
      <td>917 1st St, Dallas, TX 75001</td>
    </tr>
    <tr>
      <td>1</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <td>2</td>
      <td>176559</td>
      <td>Bose SoundSport Headphones</td>
      <td>1</td>
      <td>99.99</td>
      <td>04/07/19 22:30</td>
      <td>682 Chestnut St, Boston, MA 02215</td>
    </tr>
    <tr>
      <td>3</td>
      <td>176560</td>
      <td>Google Phone</td>
      <td>1</td>
      <td>600</td>
      <td>04/12/19 14:38</td>
      <td>669 Spruce St, Los Angeles, CA 90001</td>
    </tr>
    <tr>
      <td>4</td>
      <td>176560</td>
      <td>Wired Headphones</td>
      <td>1</td>
      <td>11.99</td>
      <td>04/12/19 14:38</td>
      <td>669 Spruce St, Los Angeles, CA 90001</td>
    </tr>
    <tr>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <td>186845</td>
      <td>259353</td>
      <td>AAA Batteries (4-pack)</td>
      <td>3</td>
      <td>2.99</td>
      <td>09/17/19 20:56</td>
      <td>840 Highland St, Los Angeles, CA 90001</td>
    </tr>
    <tr>
      <td>186846</td>
      <td>259354</td>
      <td>iPhone</td>
      <td>1</td>
      <td>700</td>
      <td>09/01/19 16:00</td>
      <td>216 Dogwood St, San Francisco, CA 94016</td>
    </tr>
    <tr>
      <td>186847</td>
      <td>259355</td>
      <td>iPhone</td>
      <td>1</td>
      <td>700</td>
      <td>09/23/19 07:39</td>
      <td>220 12th St, San Francisco, CA 94016</td>
    </tr>
    <tr>
      <td>186848</td>
      <td>259356</td>
      <td>34in Ultrawide Monitor</td>
      <td>1</td>
      <td>379.99</td>
      <td>09/19/19 17:30</td>
      <td>511 Forest St, San Francisco, CA 94016</td>
    </tr>
    <tr>
      <td>186849</td>
      <td>259357</td>
      <td>USB-C Charging Cable</td>
      <td>1</td>
      <td>11.95</td>
      <td>09/30/19 00:18</td>
      <td>250 Meadow St, San Francisco, CA 94016</td>
    </tr>
  </tbody>
</table>
<p>186850 rows × 6 columns</p>
</div>



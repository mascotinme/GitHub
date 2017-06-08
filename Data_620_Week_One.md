
Name: MUSA T. GANIYU
    
    
Course:MSDA IS 620
    
    
School: CUNY SCHOOL OF PROFESSIONAL STUDIES
    
    
Date:06/08/2017
    



```python
import graphlab
```


```python
from graphlab import SGraph, Vertex, Edge
```


```python
from graphlab import SFrame
data2 = SFrame.read_csv("C:\Users\mayowa\Documents\GitHub\MSDA-620\Week_1_Data_Set_2.csv")
sg = SGraph()

sg = sg.add_edges(data2, src_field='src', dst_field='dst')
print sg
```

    This non-commercial license of GraphLab Create for academic use is assigned to musa.ganiyu@spsmail.cuny.edu and will expire on June 05, 2018.
    

    [INFO] graphlab.cython.cy_server: GraphLab Create v2.1 started. Logging: C:\Users\mayowa\AppData\Local\Temp\graphlab_server_1496930405.log.0
    


<pre>Read 18 lines. Lines per second: 580.233</pre>



<pre>Finished parsing file C:\Users\mayowa\Documents\GitHub\MSDA-620\Week_1_Data_Set_2.csv</pre>



<pre>Parsing completed. Parsed 18 lines in 0.031022 secs.</pre>


    ------------------------------------------------------
    Inferred types from first 100 line(s) of file as 
    column_type_hints=[str,str,str]
    If parsing fails due to incorrect types, you can correct
    the inferred type list above and pass it to read_csv in
    the column_type_hints argument
    ------------------------------------------------------
    


<pre>Finished parsing file C:\Users\mayowa\Documents\GitHub\MSDA-620\Week_1_Data_Set_2.csv</pre>



<pre>Parsing completed. Parsed 18 lines in 0.03002 secs.</pre>


    SGraph({'num_edges': 18L, 'num_vertices': 10L})
    


```python
data2.head(5)
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;"><table frame="box" rules="cols">
    <tr>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">src</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">dst</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">link</th>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">The Secret</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">The Secret</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Satire</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">What I Thought I Knew</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">The Secret</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Romance</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">What I Thought I Knew</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">The Secret</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Mystery</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Buried Secrets</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">The Girl On The Train</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Horror</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">The Girl On The Train</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">The Perfect Girl</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Self_help</td>
    </tr>
</table>
[5 rows x 3 columns]<br/>
</div>




```python

data1 = SFrame.read_csv('C:\Users\mayowa\Documents\GitHub\MSDA-620\Week_1_Data_Set.csv')

sg = SGraph(vertices=data1, edges=data2, vid_field='Books',
           src_field='src', dst_field='dst')
```


<pre>Finished parsing file C:\Users\mayowa\Documents\GitHub\MSDA-620\Week_1_Data_Set.csv</pre>



<pre>Parsing completed. Parsed 9 lines in 0.030021 secs.</pre>


    ------------------------------------------------------
    Inferred types from first 100 line(s) of file as 
    column_type_hints=[str,str,long,long]
    If parsing fails due to incorrect types, you can correct
    the inferred type list above and pass it to read_csv in
    the column_type_hints argument
    ------------------------------------------------------
    


<pre>Finished parsing file C:\Users\mayowa\Documents\GitHub\MSDA-620\Week_1_Data_Set.csv</pre>



<pre>Parsing completed. Parsed 9 lines in 0.034023 secs.</pre>



```python
data1.head(5)
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;"><table frame="box" rules="cols">
    <tr>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">Books</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">Soft_hard</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">Recomm</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">Not_Recomm</th>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">The Secret</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">S</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">The Girl On The Train</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">S</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Deceived</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">H</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Buried Secrets</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">S</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Angels Walking</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">H</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0</td>
    </tr>
</table>
[5 rows x 4 columns]<br/>
</div>




```python
sg.save('my_book')
new_graph = graphlab.load_sgraph('my_book')
```


```python
graphlab.canvas.set_target('ipynb')
```


```python
sg.show(vlabel='id', highlight=['Behind Closed Doors', 'What I Thought I Knew'], arrows=True)
```



Thanks for your time


```python

```


```python

```

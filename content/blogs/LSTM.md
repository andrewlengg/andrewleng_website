```python
import pandas as pd
import os
os.chdir('/Users/andrewleng/Desktop/MGT4187')
df = pd.read_csv("articles.csv", dtype={'article_id': 'str'})

df.head()
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
      <th>article_id</th>
      <th>product_code</th>
      <th>prod_name</th>
      <th>product_type_no</th>
      <th>product_type_name</th>
      <th>product_group_name</th>
      <th>graphical_appearance_no</th>
      <th>graphical_appearance_name</th>
      <th>colour_group_code</th>
      <th>colour_group_name</th>
      <th>...</th>
      <th>department_name</th>
      <th>index_code</th>
      <th>index_name</th>
      <th>index_group_no</th>
      <th>index_group_name</th>
      <th>section_no</th>
      <th>section_name</th>
      <th>garment_group_no</th>
      <th>garment_group_name</th>
      <th>detail_desc</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0108775015</td>
      <td>108775</td>
      <td>Strap top</td>
      <td>253</td>
      <td>Vest top</td>
      <td>Garment Upper body</td>
      <td>1010016</td>
      <td>Solid</td>
      <td>9</td>
      <td>Black</td>
      <td>...</td>
      <td>Jersey Basic</td>
      <td>A</td>
      <td>Ladieswear</td>
      <td>1</td>
      <td>Ladieswear</td>
      <td>16</td>
      <td>Womens Everyday Basics</td>
      <td>1002</td>
      <td>Jersey Basic</td>
      <td>Jersey top with narrow shoulder straps.</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0108775044</td>
      <td>108775</td>
      <td>Strap top</td>
      <td>253</td>
      <td>Vest top</td>
      <td>Garment Upper body</td>
      <td>1010016</td>
      <td>Solid</td>
      <td>10</td>
      <td>White</td>
      <td>...</td>
      <td>Jersey Basic</td>
      <td>A</td>
      <td>Ladieswear</td>
      <td>1</td>
      <td>Ladieswear</td>
      <td>16</td>
      <td>Womens Everyday Basics</td>
      <td>1002</td>
      <td>Jersey Basic</td>
      <td>Jersey top with narrow shoulder straps.</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0108775051</td>
      <td>108775</td>
      <td>Strap top (1)</td>
      <td>253</td>
      <td>Vest top</td>
      <td>Garment Upper body</td>
      <td>1010017</td>
      <td>Stripe</td>
      <td>11</td>
      <td>Off White</td>
      <td>...</td>
      <td>Jersey Basic</td>
      <td>A</td>
      <td>Ladieswear</td>
      <td>1</td>
      <td>Ladieswear</td>
      <td>16</td>
      <td>Womens Everyday Basics</td>
      <td>1002</td>
      <td>Jersey Basic</td>
      <td>Jersey top with narrow shoulder straps.</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0110065001</td>
      <td>110065</td>
      <td>OP T-shirt (Idro)</td>
      <td>306</td>
      <td>Bra</td>
      <td>Underwear</td>
      <td>1010016</td>
      <td>Solid</td>
      <td>9</td>
      <td>Black</td>
      <td>...</td>
      <td>Clean Lingerie</td>
      <td>B</td>
      <td>Lingeries/Tights</td>
      <td>1</td>
      <td>Ladieswear</td>
      <td>61</td>
      <td>Womens Lingerie</td>
      <td>1017</td>
      <td>Under-, Nightwear</td>
      <td>Microfibre T-shirt bra with underwired, moulde...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0110065002</td>
      <td>110065</td>
      <td>OP T-shirt (Idro)</td>
      <td>306</td>
      <td>Bra</td>
      <td>Underwear</td>
      <td>1010016</td>
      <td>Solid</td>
      <td>10</td>
      <td>White</td>
      <td>...</td>
      <td>Clean Lingerie</td>
      <td>B</td>
      <td>Lingeries/Tights</td>
      <td>1</td>
      <td>Ladieswear</td>
      <td>61</td>
      <td>Womens Lingerie</td>
      <td>1017</td>
      <td>Under-, Nightwear</td>
      <td>Microfibre T-shirt bra with underwired, moulde...</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 25 columns</p>
</div>




```python
reduced = pd.read_csv('reduced.csv', dtype={'customer_id': 'str'})
```


```python
for col in df.columns:
    print(col)
    print(len(pd.unique(df[col])))
```

    article_id
    105542
    product_code
    47224
    prod_name
    45875
    product_type_no
    132
    product_type_name
    131
    product_group_name
    19
    graphical_appearance_no
    30
    graphical_appearance_name
    30
    colour_group_code
    50
    colour_group_name
    50
    perceived_colour_value_id
    8
    perceived_colour_value_name
    8
    perceived_colour_master_id
    20
    perceived_colour_master_name
    20
    department_no
    299
    department_name
    250
    index_code
    10
    index_name
    10
    index_group_no
    5
    index_group_name
    5
    section_no
    57
    section_name
    56
    garment_group_no
    21
    garment_group_name
    21
    detail_desc
    43405



```python
df = df.drop(columns = ['product_type_name', 'graphical_appearance_name', 'colour_group_name', 'perceived_colour_value_name',
                        'perceived_colour_master_name', 'index_name', 'index_group_name', 'section_name', 
                        'garment_group_name', 'prod_name', 'department_name', 'detail_desc'])
df.head()
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
      <th>article_id</th>
      <th>product_code</th>
      <th>product_type_no</th>
      <th>product_group_name</th>
      <th>graphical_appearance_no</th>
      <th>colour_group_code</th>
      <th>perceived_colour_value_id</th>
      <th>perceived_colour_master_id</th>
      <th>department_no</th>
      <th>index_code</th>
      <th>index_group_no</th>
      <th>section_no</th>
      <th>garment_group_no</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0108775015</td>
      <td>108775</td>
      <td>253</td>
      <td>Garment Upper body</td>
      <td>1010016</td>
      <td>9</td>
      <td>4</td>
      <td>5</td>
      <td>1676</td>
      <td>A</td>
      <td>1</td>
      <td>16</td>
      <td>1002</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0108775044</td>
      <td>108775</td>
      <td>253</td>
      <td>Garment Upper body</td>
      <td>1010016</td>
      <td>10</td>
      <td>3</td>
      <td>9</td>
      <td>1676</td>
      <td>A</td>
      <td>1</td>
      <td>16</td>
      <td>1002</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0108775051</td>
      <td>108775</td>
      <td>253</td>
      <td>Garment Upper body</td>
      <td>1010017</td>
      <td>11</td>
      <td>1</td>
      <td>9</td>
      <td>1676</td>
      <td>A</td>
      <td>1</td>
      <td>16</td>
      <td>1002</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0110065001</td>
      <td>110065</td>
      <td>306</td>
      <td>Underwear</td>
      <td>1010016</td>
      <td>9</td>
      <td>4</td>
      <td>5</td>
      <td>1339</td>
      <td>B</td>
      <td>1</td>
      <td>61</td>
      <td>1017</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0110065002</td>
      <td>110065</td>
      <td>306</td>
      <td>Underwear</td>
      <td>1010016</td>
      <td>10</td>
      <td>3</td>
      <td>9</td>
      <td>1339</td>
      <td>B</td>
      <td>1</td>
      <td>61</td>
      <td>1017</td>
    </tr>
  </tbody>
</table>
</div>




```python
temp = df.rename(
    columns={'article_id': 'item_id:token', 'product_code': 'product_code:token', 'product_type_no': 'product_type_no:float',
             'product_group_name': 'product_group_name:token_seq', 'graphical_appearance_no': 'graphical_appearance_no:token', 
             'colour_group_code': 'colour_group_code:token', 'perceived_colour_value_id': 'perceived_colour_value_id:token', 
             'perceived_colour_master_id': 'perceived_colour_master_id:token', 'department_no': 'department_no:token', 
             'index_code': 'index_code:token', 'index_group_no': 'index_group_no:token', 'section_no': 'section_no:token', 
             'garment_group_no': 'garment_group_no:token'})
temp.head()
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
      <th>item_id:token</th>
      <th>product_code:token</th>
      <th>product_type_no:float</th>
      <th>product_group_name:token_seq</th>
      <th>graphical_appearance_no:token</th>
      <th>colour_group_code:token</th>
      <th>perceived_colour_value_id:token</th>
      <th>perceived_colour_master_id:token</th>
      <th>department_no:token</th>
      <th>index_code:token</th>
      <th>index_group_no:token</th>
      <th>section_no:token</th>
      <th>garment_group_no:token</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0108775015</td>
      <td>108775</td>
      <td>253</td>
      <td>Garment Upper body</td>
      <td>1010016</td>
      <td>9</td>
      <td>4</td>
      <td>5</td>
      <td>1676</td>
      <td>A</td>
      <td>1</td>
      <td>16</td>
      <td>1002</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0108775044</td>
      <td>108775</td>
      <td>253</td>
      <td>Garment Upper body</td>
      <td>1010016</td>
      <td>10</td>
      <td>3</td>
      <td>9</td>
      <td>1676</td>
      <td>A</td>
      <td>1</td>
      <td>16</td>
      <td>1002</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0108775051</td>
      <td>108775</td>
      <td>253</td>
      <td>Garment Upper body</td>
      <td>1010017</td>
      <td>11</td>
      <td>1</td>
      <td>9</td>
      <td>1676</td>
      <td>A</td>
      <td>1</td>
      <td>16</td>
      <td>1002</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0110065001</td>
      <td>110065</td>
      <td>306</td>
      <td>Underwear</td>
      <td>1010016</td>
      <td>9</td>
      <td>4</td>
      <td>5</td>
      <td>1339</td>
      <td>B</td>
      <td>1</td>
      <td>61</td>
      <td>1017</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0110065002</td>
      <td>110065</td>
      <td>306</td>
      <td>Underwear</td>
      <td>1010016</td>
      <td>10</td>
      <td>3</td>
      <td>9</td>
      <td>1339</td>
      <td>B</td>
      <td>1</td>
      <td>61</td>
      <td>1017</td>
    </tr>
  </tbody>
</table>
</div>




```python
import os
os.chdir('/Users/andrewleng/Desktop/MGT4187/recbox_data_1')
temp.to_csv('recbox_data.item', index=False, sep='\t')
```


```python
df = pd.read_csv("/Users/andrewleng/Desktop/MGT4187/transactions_train.csv", dtype={'article_id': 'str'})
```


```python
df['t_dat'] = pd.to_datetime(df['t_dat'], format="%Y-%m-%d")
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
      <th>t_dat</th>
      <th>customer_id</th>
      <th>article_id</th>
      <th>price</th>
      <th>sales_channel_id</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2018-09-20</td>
      <td>000058a12d5b43e67d225668fa1f8d618c13dc232df0ca...</td>
      <td>0663713001</td>
      <td>0.050831</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2018-09-20</td>
      <td>000058a12d5b43e67d225668fa1f8d618c13dc232df0ca...</td>
      <td>0541518023</td>
      <td>0.030492</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2018-09-20</td>
      <td>00007d2de826758b65a93dd24ce629ed66842531df6699...</td>
      <td>0505221004</td>
      <td>0.015237</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2018-09-20</td>
      <td>00007d2de826758b65a93dd24ce629ed66842531df6699...</td>
      <td>0685687003</td>
      <td>0.016932</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2018-09-20</td>
      <td>00007d2de826758b65a93dd24ce629ed66842531df6699...</td>
      <td>0685687004</td>
      <td>0.016932</td>
      <td>2</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>31788319</th>
      <td>2020-09-22</td>
      <td>fff2282977442e327b45d8c89afde25617d00124d0f999...</td>
      <td>0929511001</td>
      <td>0.059305</td>
      <td>2</td>
    </tr>
    <tr>
      <th>31788320</th>
      <td>2020-09-22</td>
      <td>fff2282977442e327b45d8c89afde25617d00124d0f999...</td>
      <td>0891322004</td>
      <td>0.042356</td>
      <td>2</td>
    </tr>
    <tr>
      <th>31788321</th>
      <td>2020-09-22</td>
      <td>fff380805474b287b05cb2a7507b9a013482f7dd0bce0e...</td>
      <td>0918325001</td>
      <td>0.043203</td>
      <td>1</td>
    </tr>
    <tr>
      <th>31788322</th>
      <td>2020-09-22</td>
      <td>fff4d3a8b1f3b60af93e78c30a7cb4cf75edaf2590d3e5...</td>
      <td>0833459002</td>
      <td>0.006763</td>
      <td>1</td>
    </tr>
    <tr>
      <th>31788323</th>
      <td>2020-09-22</td>
      <td>fffef3b6b73545df065b521e19f64bf6fe93bfd450ab20...</td>
      <td>0898573003</td>
      <td>0.033881</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
<p>31788324 rows × 5 columns</p>
</div>




```python
import numpy as np
df['timestamp'] = df.t_dat.values.astype(np.int64) // 10 ** 9
df.head()
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
      <th>t_dat</th>
      <th>customer_id</th>
      <th>article_id</th>
      <th>price</th>
      <th>sales_channel_id</th>
      <th>timestamp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2018-09-20</td>
      <td>000058a12d5b43e67d225668fa1f8d618c13dc232df0ca...</td>
      <td>0663713001</td>
      <td>0.050831</td>
      <td>2</td>
      <td>1537401600</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2018-09-20</td>
      <td>000058a12d5b43e67d225668fa1f8d618c13dc232df0ca...</td>
      <td>0541518023</td>
      <td>0.030492</td>
      <td>2</td>
      <td>1537401600</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2018-09-20</td>
      <td>00007d2de826758b65a93dd24ce629ed66842531df6699...</td>
      <td>0505221004</td>
      <td>0.015237</td>
      <td>2</td>
      <td>1537401600</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2018-09-20</td>
      <td>00007d2de826758b65a93dd24ce629ed66842531df6699...</td>
      <td>0685687003</td>
      <td>0.016932</td>
      <td>2</td>
      <td>1537401600</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2018-09-20</td>
      <td>00007d2de826758b65a93dd24ce629ed66842531df6699...</td>
      <td>0685687004</td>
      <td>0.016932</td>
      <td>2</td>
      <td>1537401600</td>
    </tr>
  </tbody>
</table>
</div>




```python
temp = df[df['customer_id'].isin(reduced['customer_id'])][['customer_id', 'article_id', 'timestamp']].rename(
    columns={'customer_id': 'user_id:token', 'article_id': 'item_id:token', 'timestamp': 'timestamp:float'})
temp
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
      <th>user_id:token</th>
      <th>item_id:token</th>
      <th>timestamp:float</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>144</th>
      <td>00be0a263381af38132d31225e8fb12fbc527c654b4464...</td>
      <td>0644522001</td>
      <td>1537401600</td>
    </tr>
    <tr>
      <th>206</th>
      <td>012bbedf2efe728a7407a5dc842a852f8e09e9ae972711...</td>
      <td>0651456003</td>
      <td>1537401600</td>
    </tr>
    <tr>
      <th>207</th>
      <td>012bbedf2efe728a7407a5dc842a852f8e09e9ae972711...</td>
      <td>0651456003</td>
      <td>1537401600</td>
    </tr>
    <tr>
      <th>208</th>
      <td>012bbedf2efe728a7407a5dc842a852f8e09e9ae972711...</td>
      <td>0651456003</td>
      <td>1537401600</td>
    </tr>
    <tr>
      <th>218</th>
      <td>0137b87739a796f65396d8483173f66318039d19a2583f...</td>
      <td>0577992001</td>
      <td>1537401600</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>31788215</th>
      <td>fed66fd2a9c2f7af755813db23e7fdce433c9706960b2b...</td>
      <td>0873279005</td>
      <td>1600732800</td>
    </tr>
    <tr>
      <th>31788226</th>
      <td>feeea34bc8517c692eed5c4e203d421497f06dc16f79c3...</td>
      <td>0924243001</td>
      <td>1600732800</td>
    </tr>
    <tr>
      <th>31788227</th>
      <td>feeea34bc8517c692eed5c4e203d421497f06dc16f79c3...</td>
      <td>0924243002</td>
      <td>1600732800</td>
    </tr>
    <tr>
      <th>31788278</th>
      <td>ff6bc0a652d313d04a8c5852c7e740b9e351b3f9420e2e...</td>
      <td>0866714016</td>
      <td>1600732800</td>
    </tr>
    <tr>
      <th>31788279</th>
      <td>ff6bc0a652d313d04a8c5852c7e740b9e351b3f9420e2e...</td>
      <td>0922625005</td>
      <td>1600732800</td>
    </tr>
  </tbody>
</table>
<p>1337996 rows × 3 columns</p>
</div>




```python
temp.to_csv('recbox_data_1.inter', index=False, sep='\t')
```


```python
import logging
from logging import getLogger
from recbole.config import Config
from recbole.data import create_dataset, data_preparation
from recbole.model.sequential_recommender import GRU4Rec
from recbole.trainer import Trainer
from recbole.utils import init_seed, init_logger
```


```python
parameter_dict = {
    'data_path': '/Users/andrewleng/Desktop/MGT4187',
    'USER_ID_FIELD': 'user_id',
    'ITEM_ID_FIELD': 'item_id',
    'TIME_FIELD': 'timestamp',
    'user_inter_num_interval': "[40,inf)",
    'item_inter_num_interval': "[40,inf)",
    'load_col': {'inter': ['user_id', 'item_id', 'timestamp'],
                 'item': ['item_id', 'product_code', 'product_type_no', 'product_group_name', 'graphical_appearance_no',
                      'colour_group_code', 'perceived_colour_value_id', 'perceived_colour_master_id',
                      'department_no', 'index_code', 'index_group_no', 'section_no', 'garment_group_no']
             },
    'selected_features': ['product_code', 'product_type_no', 'product_group_name', 'graphical_appearance_no',
                          'colour_group_code', 'perceived_colour_value_id', 'perceived_colour_master_id',
                          'department_no', 'index_code', 'index_group_no', 'section_no', 'garment_group_no'],
    'neg_sampling': None,
    'epochs': 30,
    'eval_args': {
        'split': {'RS': [9, 0, 1]},
        'group_by': 'user',
        'order': 'TO',
        'mode': 'full'}
}

config = Config(model='GRU4Rec', dataset='recbox_data_1', config_dict=parameter_dict)

# init random seed
init_seed(config['seed'], config['reproducibility'])

# logger initialization
init_logger(config)
logger = getLogger()
# Create handlers
c_handler = logging.StreamHandler()
c_handler.setLevel(logging.INFO)
logger.addHandler(c_handler)

# write config info into log
logger.info(config)
```

    22 Apr 05:36    INFO  
    General Hyper Parameters:
    gpu_id = 0
    use_gpu = True
    seed = 2020
    state = INFO
    reproducibility = True
    data_path = /Users/andrewleng/Desktop/MGT4187/recbox_data_1
    checkpoint_dir = saved
    show_progress = True
    save_dataset = False
    dataset_save_path = None
    save_dataloaders = False
    dataloaders_save_path = None
    log_wandb = False
    
    Training Hyper Parameters:
    epochs = 30
    train_batch_size = 2048
    learner = adam
    learning_rate = 0.001
    neg_sampling = None
    eval_step = 1
    stopping_step = 10
    clip_grad_norm = None
    weight_decay = 0.0
    loss_decimal_place = 4
    
    Evaluation Hyper Parameters:
    eval_args = {'split': {'RS': [9, 0, 1]}, 'group_by': 'user', 'order': 'TO', 'mode': 'full'}
    repeatable = True
    metrics = ['Recall', 'MRR', 'NDCG', 'Hit', 'Precision']
    topk = [10]
    valid_metric = MRR@10
    valid_metric_bigger = True
    eval_batch_size = 4096
    metric_decimal_place = 4
    
    Dataset Hyper Parameters:
    field_separator = 	
    seq_separator =  
    USER_ID_FIELD = user_id
    ITEM_ID_FIELD = item_id
    RATING_FIELD = rating
    TIME_FIELD = timestamp
    seq_len = None
    LABEL_FIELD = label
    threshold = None
    NEG_PREFIX = neg_
    load_col = {'inter': ['user_id', 'item_id', 'timestamp'], 'item': ['item_id', 'product_code', 'product_type_no', 'product_group_name', 'graphical_appearance_no', 'colour_group_code', 'perceived_colour_value_id', 'perceived_colour_master_id', 'department_no', 'index_code', 'index_group_no', 'section_no', 'garment_group_no']}
    unload_col = None
    unused_col = None
    additional_feat_suffix = None
    rm_dup_inter = None
    val_interval = None
    filter_inter_by_user_or_item = True
    user_inter_num_interval = [40,inf)
    item_inter_num_interval = [40,inf)
    alias_of_user_id = None
    alias_of_item_id = None
    alias_of_entity_id = None
    alias_of_relation_id = None
    preload_weight = None
    normalize_field = None
    normalize_all = None
    ITEM_LIST_LENGTH_FIELD = item_length
    LIST_SUFFIX = _list
    MAX_ITEM_LIST_LENGTH = 50
    POSITION_FIELD = position_id
    HEAD_ENTITY_ID_FIELD = head_id
    TAIL_ENTITY_ID_FIELD = tail_id
    RELATION_ID_FIELD = relation_id
    ENTITY_ID_FIELD = entity_id
    benchmark_filename = None
    
    Other Hyper Parameters: 
    wandb_project = recbole
    require_pow = False
    embedding_size = 64
    hidden_size = 128
    num_layers = 1
    dropout_prob = 0.3
    loss_type = CE
    MODEL_TYPE = ModelType.SEQUENTIAL
    selected_features = ['product_code', 'product_type_no', 'product_group_name', 'graphical_appearance_no', 'colour_group_code', 'perceived_colour_value_id', 'perceived_colour_master_id', 'department_no', 'index_code', 'index_group_no', 'section_no', 'garment_group_no']
    MODEL_INPUT_TYPE = InputType.POINTWISE
    eval_type = EvaluatorType.RANKING
    device = cpu
    train_neg_sample_args = {'strategy': 'none'}
    eval_neg_sample_args = {'strategy': 'full', 'distribution': 'uniform'}
    
    
    
    General Hyper Parameters:
    gpu_id = 0
    use_gpu = True
    seed = 2020
    state = INFO
    reproducibility = True
    data_path = /Users/andrewleng/Desktop/MGT4187/recbox_data_1
    checkpoint_dir = saved
    show_progress = True
    save_dataset = False
    dataset_save_path = None
    save_dataloaders = False
    dataloaders_save_path = None
    log_wandb = False
    
    Training Hyper Parameters:
    epochs = 30
    train_batch_size = 2048
    learner = adam
    learning_rate = 0.001
    neg_sampling = None
    eval_step = 1
    stopping_step = 10
    clip_grad_norm = None
    weight_decay = 0.0
    loss_decimal_place = 4
    
    Evaluation Hyper Parameters:
    eval_args = {'split': {'RS': [9, 0, 1]}, 'group_by': 'user', 'order': 'TO', 'mode': 'full'}
    repeatable = True
    metrics = ['Recall', 'MRR', 'NDCG', 'Hit', 'Precision']
    topk = [10]
    valid_metric = MRR@10
    valid_metric_bigger = True
    eval_batch_size = 4096
    metric_decimal_place = 4
    
    Dataset Hyper Parameters:
    field_separator = 	
    seq_separator =  
    USER_ID_FIELD = user_id
    ITEM_ID_FIELD = item_id
    RATING_FIELD = rating
    TIME_FIELD = timestamp
    seq_len = None
    LABEL_FIELD = label
    threshold = None
    NEG_PREFIX = neg_
    load_col = {'inter': ['user_id', 'item_id', 'timestamp'], 'item': ['item_id', 'product_code', 'product_type_no', 'product_group_name', 'graphical_appearance_no', 'colour_group_code', 'perceived_colour_value_id', 'perceived_colour_master_id', 'department_no', 'index_code', 'index_group_no', 'section_no', 'garment_group_no']}
    unload_col = None
    unused_col = None
    additional_feat_suffix = None
    rm_dup_inter = None
    val_interval = None
    filter_inter_by_user_or_item = True
    user_inter_num_interval = [40,inf)
    item_inter_num_interval = [40,inf)
    alias_of_user_id = None
    alias_of_item_id = None
    alias_of_entity_id = None
    alias_of_relation_id = None
    preload_weight = None
    normalize_field = None
    normalize_all = None
    ITEM_LIST_LENGTH_FIELD = item_length
    LIST_SUFFIX = _list
    MAX_ITEM_LIST_LENGTH = 50
    POSITION_FIELD = position_id
    HEAD_ENTITY_ID_FIELD = head_id
    TAIL_ENTITY_ID_FIELD = tail_id
    RELATION_ID_FIELD = relation_id
    ENTITY_ID_FIELD = entity_id
    benchmark_filename = None
    
    Other Hyper Parameters: 
    wandb_project = recbole
    require_pow = False
    embedding_size = 64
    hidden_size = 128
    num_layers = 1
    dropout_prob = 0.3
    loss_type = CE
    MODEL_TYPE = ModelType.SEQUENTIAL
    selected_features = ['product_code', 'product_type_no', 'product_group_name', 'graphical_appearance_no', 'colour_group_code', 'perceived_colour_value_id', 'perceived_colour_master_id', 'department_no', 'index_code', 'index_group_no', 'section_no', 'garment_group_no']
    MODEL_INPUT_TYPE = InputType.POINTWISE
    eval_type = EvaluatorType.RANKING
    device = cpu
    train_neg_sample_args = {'strategy': 'none'}
    eval_neg_sample_args = {'strategy': 'full', 'distribution': 'uniform'}
    
    
    
    General Hyper Parameters:
    gpu_id = 0
    use_gpu = True
    seed = 2020
    state = INFO
    reproducibility = True
    data_path = /Users/andrewleng/Desktop/MGT4187/recbox_data_1
    checkpoint_dir = saved
    show_progress = True
    save_dataset = False
    dataset_save_path = None
    save_dataloaders = False
    dataloaders_save_path = None
    log_wandb = False
    
    Training Hyper Parameters:
    epochs = 30
    train_batch_size = 2048
    learner = adam
    learning_rate = 0.001
    neg_sampling = None
    eval_step = 1
    stopping_step = 10
    clip_grad_norm = None
    weight_decay = 0.0
    loss_decimal_place = 4
    
    Evaluation Hyper Parameters:
    eval_args = {'split': {'RS': [9, 0, 1]}, 'group_by': 'user', 'order': 'TO', 'mode': 'full'}
    repeatable = True
    metrics = ['Recall', 'MRR', 'NDCG', 'Hit', 'Precision']
    topk = [10]
    valid_metric = MRR@10
    valid_metric_bigger = True
    eval_batch_size = 4096
    metric_decimal_place = 4
    
    Dataset Hyper Parameters:
    field_separator = 	
    seq_separator =  
    USER_ID_FIELD = user_id
    ITEM_ID_FIELD = item_id
    RATING_FIELD = rating
    TIME_FIELD = timestamp
    seq_len = None
    LABEL_FIELD = label
    threshold = None
    NEG_PREFIX = neg_
    load_col = {'inter': ['user_id', 'item_id', 'timestamp'], 'item': ['item_id', 'product_code', 'product_type_no', 'product_group_name', 'graphical_appearance_no', 'colour_group_code', 'perceived_colour_value_id', 'perceived_colour_master_id', 'department_no', 'index_code', 'index_group_no', 'section_no', 'garment_group_no']}
    unload_col = None
    unused_col = None
    additional_feat_suffix = None
    rm_dup_inter = None
    val_interval = None
    filter_inter_by_user_or_item = True
    user_inter_num_interval = [40,inf)
    item_inter_num_interval = [40,inf)
    alias_of_user_id = None
    alias_of_item_id = None
    alias_of_entity_id = None
    alias_of_relation_id = None
    preload_weight = None
    normalize_field = None
    normalize_all = None
    ITEM_LIST_LENGTH_FIELD = item_length
    LIST_SUFFIX = _list
    MAX_ITEM_LIST_LENGTH = 50
    POSITION_FIELD = position_id
    HEAD_ENTITY_ID_FIELD = head_id
    TAIL_ENTITY_ID_FIELD = tail_id
    RELATION_ID_FIELD = relation_id
    ENTITY_ID_FIELD = entity_id
    benchmark_filename = None
    
    Other Hyper Parameters: 
    wandb_project = recbole
    require_pow = False
    embedding_size = 64
    hidden_size = 128
    num_layers = 1
    dropout_prob = 0.3
    loss_type = CE
    MODEL_TYPE = ModelType.SEQUENTIAL
    selected_features = ['product_code', 'product_type_no', 'product_group_name', 'graphical_appearance_no', 'colour_group_code', 'perceived_colour_value_id', 'perceived_colour_master_id', 'department_no', 'index_code', 'index_group_no', 'section_no', 'garment_group_no']
    MODEL_INPUT_TYPE = InputType.POINTWISE
    eval_type = EvaluatorType.RANKING
    device = cpu
    train_neg_sample_args = {'strategy': 'none'}
    eval_neg_sample_args = {'strategy': 'full', 'distribution': 'uniform'}
    
    



```python
dataset = create_dataset(config)
logger.info(dataset)
```

    22 Apr 05:37    INFO  recbox_data_1
    The number of users: 5834
    Average actions of users: 79.84056231784673
    The number of items: 5780
    Average actions of items: 80.5866066793563
    The number of inters: 465710
    The sparsity of the dataset: 98.61891216386935%
    Remain Fields: ['user_id', 'item_id', 'timestamp']
    recbox_data_1
    The number of users: 5834
    Average actions of users: 79.84056231784673
    The number of items: 5780
    Average actions of items: 80.5866066793563
    The number of inters: 465710
    The sparsity of the dataset: 98.61891216386935%
    Remain Fields: ['user_id', 'item_id', 'timestamp']
    recbox_data_1
    The number of users: 5834
    Average actions of users: 79.84056231784673
    The number of items: 5780
    Average actions of items: 80.5866066793563
    The number of inters: 465710
    The sparsity of the dataset: 98.61891216386935%
    Remain Fields: ['user_id', 'item_id', 'timestamp']



```python
# dataset splitting
train_data, valid_data, test_data = data_preparation(config, dataset)
```

    22 Apr 05:37    INFO  [Training]: train_batch_size = [2048] negative sampling: [None]
    [Training]: train_batch_size = [2048] negative sampling: [None]
    [Training]: train_batch_size = [2048] negative sampling: [None]
    22 Apr 05:37    INFO  [Evaluation]: eval_batch_size = [4096] eval_args: [{'split': {'RS': [9, 0, 1]}, 'group_by': 'user', 'order': 'TO', 'mode': 'full'}]
    [Evaluation]: eval_batch_size = [4096] eval_args: [{'split': {'RS': [9, 0, 1]}, 'group_by': 'user', 'order': 'TO', 'mode': 'full'}]
    [Evaluation]: eval_batch_size = [4096] eval_args: [{'split': {'RS': [9, 0, 1]}, 'group_by': 'user', 'order': 'TO', 'mode': 'full'}]



```python
train_data.dataset
```




    [1;35mrecbox_data_1[0m
    [1;34mThe number of users[0m: 5834
    [1;34mAverage actions of users[0m: 71.39499399965712
    [1;34mThe number of items[0m: 5780
    [1;34mAverage actions of items[0m: 72.1245237270523
    [1;34mThe number of inters[0m: 416447
    [1;34mThe sparsity of the dataset[0m: 98.76500421701681%
    [1;34mRemain Fields[0m: ['user_id', 'item_id', 'timestamp', 'item_id_list', 'timestamp_list', 'item_length']




```python
test_data.dataset
```




    [1;35mrecbox_data_1[0m
    [1;34mThe number of users[0m: 5834
    [1;34mAverage actions of users[0m: 7.44556831818961
    [1;34mThe number of items[0m: 5780
    [1;34mAverage actions of items[0m: 12.68770084721005
    [1;34mThe number of inters[0m: 43430
    [1;34mThe sparsity of the dataset[0m: 99.87120601936151%
    [1;34mRemain Fields[0m: ['user_id', 'item_id', 'timestamp', 'item_id_list', 'timestamp_list', 'item_length']




```python
# model loading and initialization
model = GRU4Rec(config, train_data.dataset).to(config['device'])
logger.info(model)

# trainer loading and initialization
trainer = Trainer(config, model)

# model training
best_valid_score, best_valid_result = trainer.fit(train_data)
```

    18 Apr 20:41    INFO  GRU4Rec(
      (item_embedding): Embedding(5780, 64, padding_idx=0)
      (emb_dropout): Dropout(p=0.3, inplace=False)
      (gru_layers): GRU(64, 128, bias=False, batch_first=True)
      (dense): Linear(in_features=128, out_features=64, bias=True)
      (loss_fct): CrossEntropyLoss()
    )
    Trainable parameters: 451904
    GRU4Rec(
      (item_embedding): Embedding(5780, 64, padding_idx=0)
      (emb_dropout): Dropout(p=0.3, inplace=False)
      (gru_layers): GRU(64, 128, bias=False, batch_first=True)
      (dense): Linear(in_features=128, out_features=64, bias=True)
      (loss_fct): CrossEntropyLoss()
    )
    Trainable parameters: 451904
    18 Apr 20:47    INFO  epoch 0 training [time: 407.84s, train loss: 1707.0271]
    epoch 0 training [time: 407.84s, train loss: 1707.0271]
    18 Apr 20:47    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 20:54    INFO  epoch 1 training [time: 398.48s, train loss: 1607.3541]
    epoch 1 training [time: 398.48s, train loss: 1607.3541]
    18 Apr 20:54    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 21:01    INFO  epoch 2 training [time: 390.24s, train loss: 1556.4927]
    epoch 2 training [time: 390.24s, train loss: 1556.4927]
    18 Apr 21:01    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 21:07    INFO  epoch 3 training [time: 390.64s, train loss: 1525.6584]
    epoch 3 training [time: 390.64s, train loss: 1525.6584]
    18 Apr 21:07    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 21:14    INFO  epoch 4 training [time: 399.50s, train loss: 1499.1653]
    epoch 4 training [time: 399.50s, train loss: 1499.1653]
    18 Apr 21:14    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 21:20    INFO  epoch 5 training [time: 392.71s, train loss: 1474.7752]
    epoch 5 training [time: 392.71s, train loss: 1474.7752]
    18 Apr 21:20    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 21:27    INFO  epoch 6 training [time: 392.80s, train loss: 1454.4012]
    epoch 6 training [time: 392.80s, train loss: 1454.4012]
    18 Apr 21:27    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 21:33    INFO  epoch 7 training [time: 391.60s, train loss: 1437.0852]
    epoch 7 training [time: 391.60s, train loss: 1437.0852]
    18 Apr 21:33    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 21:40    INFO  epoch 8 training [time: 388.24s, train loss: 1421.4530]
    epoch 8 training [time: 388.24s, train loss: 1421.4530]
    18 Apr 21:40    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 21:46    INFO  epoch 9 training [time: 388.85s, train loss: 1407.2323]
    epoch 9 training [time: 388.85s, train loss: 1407.2323]
    18 Apr 21:46    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 21:53    INFO  epoch 10 training [time: 389.37s, train loss: 1394.4328]
    epoch 10 training [time: 389.37s, train loss: 1394.4328]
    18 Apr 21:53    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 21:59    INFO  epoch 11 training [time: 389.62s, train loss: 1382.2895]
    epoch 11 training [time: 389.62s, train loss: 1382.2895]
    18 Apr 21:59    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 22:06    INFO  epoch 12 training [time: 386.35s, train loss: 1370.9878]
    epoch 12 training [time: 386.35s, train loss: 1370.9878]
    18 Apr 22:06    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 22:12    INFO  epoch 13 training [time: 384.76s, train loss: 1360.1986]
    epoch 13 training [time: 384.76s, train loss: 1360.1986]
    18 Apr 22:12    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 22:19    INFO  epoch 14 training [time: 385.36s, train loss: 1349.8523]
    epoch 14 training [time: 385.36s, train loss: 1349.8523]
    18 Apr 22:19    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 22:25    INFO  epoch 15 training [time: 385.92s, train loss: 1340.8944]
    epoch 15 training [time: 385.92s, train loss: 1340.8944]
    18 Apr 22:25    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 22:31    INFO  epoch 16 training [time: 386.12s, train loss: 1332.2864]
    epoch 16 training [time: 386.12s, train loss: 1332.2864]
    18 Apr 22:31    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 22:38    INFO  epoch 17 training [time: 385.38s, train loss: 1324.5974]
    epoch 17 training [time: 385.38s, train loss: 1324.5974]
    18 Apr 22:38    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 22:44    INFO  epoch 18 training [time: 385.83s, train loss: 1317.7935]
    epoch 18 training [time: 385.83s, train loss: 1317.7935]
    18 Apr 22:44    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 22:51    INFO  epoch 19 training [time: 387.14s, train loss: 1311.3753]
    epoch 19 training [time: 387.14s, train loss: 1311.3753]
    18 Apr 22:51    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 22:57    INFO  epoch 20 training [time: 384.41s, train loss: 1305.0150]
    epoch 20 training [time: 384.41s, train loss: 1305.0150]
    18 Apr 22:57    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 23:04    INFO  epoch 21 training [time: 385.02s, train loss: 1299.6498]
    epoch 21 training [time: 385.02s, train loss: 1299.6498]
    18 Apr 23:04    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 23:10    INFO  epoch 22 training [time: 384.42s, train loss: 1294.0794]
    epoch 22 training [time: 384.42s, train loss: 1294.0794]
    18 Apr 23:10    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 23:16    INFO  epoch 23 training [time: 386.03s, train loss: 1288.8088]
    epoch 23 training [time: 386.03s, train loss: 1288.8088]
    18 Apr 23:16    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 23:23    INFO  epoch 24 training [time: 384.75s, train loss: 1283.9739]
    epoch 24 training [time: 384.75s, train loss: 1283.9739]
    18 Apr 23:23    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 23:29    INFO  epoch 25 training [time: 384.71s, train loss: 1279.3002]
    epoch 25 training [time: 384.71s, train loss: 1279.3002]
    18 Apr 23:29    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 23:36    INFO  epoch 26 training [time: 385.98s, train loss: 1274.7418]
    epoch 26 training [time: 385.98s, train loss: 1274.7418]
    18 Apr 23:36    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 23:42    INFO  epoch 27 training [time: 385.82s, train loss: 1270.7022]
    epoch 27 training [time: 385.82s, train loss: 1270.7022]
    18 Apr 23:42    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 23:49    INFO  epoch 28 training [time: 384.58s, train loss: 1266.9011]
    epoch 28 training [time: 384.58s, train loss: 1266.9011]
    18 Apr 23:49    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    18 Apr 23:55    INFO  epoch 29 training [time: 385.40s, train loss: 1263.0150]
    epoch 29 training [time: 385.40s, train loss: 1263.0150]
    18 Apr 23:55    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 00:01    INFO  epoch 30 training [time: 389.58s, train loss: 1259.5748]
    epoch 30 training [time: 389.58s, train loss: 1259.5748]
    19 Apr 00:01    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 00:08    INFO  epoch 31 training [time: 387.13s, train loss: 1256.4172]
    epoch 31 training [time: 387.13s, train loss: 1256.4172]
    19 Apr 00:08    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 00:14    INFO  epoch 32 training [time: 386.75s, train loss: 1253.2787]
    epoch 32 training [time: 386.75s, train loss: 1253.2787]
    19 Apr 00:14    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 00:21    INFO  epoch 33 training [time: 386.56s, train loss: 1250.3000]
    epoch 33 training [time: 386.56s, train loss: 1250.3000]
    19 Apr 00:21    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 00:27    INFO  epoch 34 training [time: 391.03s, train loss: 1247.6400]
    epoch 34 training [time: 391.03s, train loss: 1247.6400]
    19 Apr 00:27    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 00:34    INFO  epoch 35 training [time: 391.51s, train loss: 1244.7825]
    epoch 35 training [time: 391.51s, train loss: 1244.7825]
    19 Apr 00:34    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 00:40    INFO  epoch 36 training [time: 385.80s, train loss: 1242.1370]
    epoch 36 training [time: 385.80s, train loss: 1242.1370]
    19 Apr 00:40    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 00:47    INFO  epoch 37 training [time: 387.66s, train loss: 1239.6370]
    epoch 37 training [time: 387.66s, train loss: 1239.6370]
    19 Apr 00:47    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 00:53    INFO  epoch 38 training [time: 390.58s, train loss: 1237.1563]
    epoch 38 training [time: 390.58s, train loss: 1237.1563]
    19 Apr 00:53    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 01:00    INFO  epoch 39 training [time: 386.43s, train loss: 1234.7463]
    epoch 39 training [time: 386.43s, train loss: 1234.7463]
    19 Apr 01:00    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 01:06    INFO  epoch 40 training [time: 387.52s, train loss: 1232.6239]
    epoch 40 training [time: 387.52s, train loss: 1232.6239]
    19 Apr 01:06    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 01:13    INFO  epoch 41 training [time: 386.27s, train loss: 1230.4688]
    epoch 41 training [time: 386.27s, train loss: 1230.4688]
    19 Apr 01:13    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 01:19    INFO  epoch 42 training [time: 386.71s, train loss: 1228.8331]
    epoch 42 training [time: 386.71s, train loss: 1228.8331]
    19 Apr 01:19    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 01:25    INFO  epoch 43 training [time: 385.90s, train loss: 1226.6865]
    epoch 43 training [time: 385.90s, train loss: 1226.6865]
    19 Apr 01:25    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 01:32    INFO  epoch 44 training [time: 385.63s, train loss: 1224.9972]
    epoch 44 training [time: 385.63s, train loss: 1224.9972]
    19 Apr 01:32    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 01:38    INFO  epoch 45 training [time: 385.27s, train loss: 1223.5569]
    epoch 45 training [time: 385.27s, train loss: 1223.5569]
    19 Apr 01:38    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 01:45    INFO  epoch 46 training [time: 385.88s, train loss: 1221.5319]
    epoch 46 training [time: 385.88s, train loss: 1221.5319]
    19 Apr 01:45    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 01:51    INFO  epoch 47 training [time: 385.91s, train loss: 1220.4111]
    epoch 47 training [time: 385.91s, train loss: 1220.4111]
    19 Apr 01:51    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 01:58    INFO  epoch 48 training [time: 385.36s, train loss: 1218.5557]
    epoch 48 training [time: 385.36s, train loss: 1218.5557]
    19 Apr 01:58    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 02:04    INFO  epoch 49 training [time: 385.74s, train loss: 1217.2128]
    epoch 49 training [time: 385.74s, train loss: 1217.2128]
    19 Apr 02:04    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 02:10    INFO  epoch 50 training [time: 385.08s, train loss: 1215.7525]
    epoch 50 training [time: 385.08s, train loss: 1215.7525]
    19 Apr 02:10    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 02:17    INFO  epoch 51 training [time: 385.49s, train loss: 1214.8657]
    epoch 51 training [time: 385.49s, train loss: 1214.8657]
    19 Apr 02:17    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 02:23    INFO  epoch 52 training [time: 385.21s, train loss: 1213.1685]
    epoch 52 training [time: 385.21s, train loss: 1213.1685]
    19 Apr 02:23    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 02:30    INFO  epoch 53 training [time: 385.20s, train loss: 1212.4714]
    epoch 53 training [time: 385.20s, train loss: 1212.4714]
    19 Apr 02:30    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 02:36    INFO  epoch 54 training [time: 385.92s, train loss: 1211.2250]
    epoch 54 training [time: 385.92s, train loss: 1211.2250]
    19 Apr 02:36    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 02:43    INFO  epoch 55 training [time: 385.01s, train loss: 1210.2704]
    epoch 55 training [time: 385.01s, train loss: 1210.2704]
    19 Apr 02:43    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 02:49    INFO  epoch 56 training [time: 388.88s, train loss: 1209.2185]
    epoch 56 training [time: 388.88s, train loss: 1209.2185]
    19 Apr 02:49    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 02:55    INFO  epoch 57 training [time: 385.11s, train loss: 1208.3433]
    epoch 57 training [time: 385.11s, train loss: 1208.3433]
    19 Apr 02:55    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 03:02    INFO  epoch 58 training [time: 385.25s, train loss: 1207.4065]
    epoch 58 training [time: 385.25s, train loss: 1207.4065]
    19 Apr 03:02    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 03:08    INFO  epoch 59 training [time: 390.55s, train loss: 1206.5465]
    epoch 59 training [time: 390.55s, train loss: 1206.5465]
    19 Apr 03:08    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 03:15    INFO  epoch 60 training [time: 390.53s, train loss: 1205.4049]
    epoch 60 training [time: 390.53s, train loss: 1205.4049]
    19 Apr 03:15    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 03:21    INFO  epoch 61 training [time: 389.60s, train loss: 1204.3194]
    epoch 61 training [time: 389.60s, train loss: 1204.3194]
    19 Apr 03:21    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 03:28    INFO  epoch 62 training [time: 388.59s, train loss: 1203.2898]
    epoch 62 training [time: 388.59s, train loss: 1203.2898]
    19 Apr 03:28    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 03:34    INFO  epoch 63 training [time: 389.15s, train loss: 1203.2432]
    epoch 63 training [time: 389.15s, train loss: 1203.2432]
    19 Apr 03:34    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 03:41    INFO  epoch 64 training [time: 388.77s, train loss: 1202.2894]
    epoch 64 training [time: 388.77s, train loss: 1202.2894]
    19 Apr 03:41    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 03:47    INFO  epoch 65 training [time: 388.42s, train loss: 1201.2379]
    epoch 65 training [time: 388.42s, train loss: 1201.2379]
    19 Apr 03:47    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 03:54    INFO  epoch 66 training [time: 387.67s, train loss: 1200.8582]
    epoch 66 training [time: 387.67s, train loss: 1200.8582]
    19 Apr 03:54    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 04:00    INFO  epoch 67 training [time: 388.38s, train loss: 1199.7428]
    epoch 67 training [time: 388.38s, train loss: 1199.7428]
    19 Apr 04:00    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 04:07    INFO  epoch 68 training [time: 388.08s, train loss: 1199.3497]
    epoch 68 training [time: 388.08s, train loss: 1199.3497]
    19 Apr 04:07    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    19 Apr 04:13    INFO  epoch 69 training [time: 387.57s, train loss: 1198.7420]
    epoch 69 training [time: 387.57s, train loss: 1198.7420]
    19 Apr 04:13    INFO  Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth
    Saving current: saved/GRU4Rec-Apr-18-2022_20-41-08.pth



```python
from recbole.utils.case_study import full_sort_topk
external_user_ids = dataset.id2token(
    dataset.uid_field, list(range(dataset.user_num)))[1:]#fist element in array is 'PAD'(default of Recbole) ->remove it 
```


```python
dataset.user_num
```




    5834




```python
topk_items = []
for internal_user_id in list(range(dataset.user_num))[1:]:
    _, topk_iid_list = full_sort_topk([internal_user_id], model, test_data, k=10, device=config['device'])
    last_topk_iid_list = topk_iid_list[-1]
    external_item_list = dataset.id2token(dataset.iid_field, last_topk_iid_list.cpu()).tolist()
    topk_items.append(external_item_list)
print(len(topk_items))
```

    5833



```python
external_item_str = [' '.join(x) for x in topk_items]
result = pd.DataFrame(external_user_ids, columns=['customer_id'])
result['prediction'] = external_item_str
result.head()
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
      <th>customer_id</th>
      <th>prediction</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0667219847ad2c164e5a8939746cc57c3ac86a747a5752...</td>
      <td>0852746001 0717490057 0547780001 0717490008 05...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>06756e39fcf7b51b98cd087e765de8e501c8c19f369933...</td>
      <td>0863000004 0817353003 0874465001 0906635001 08...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>06884807549bd7463a0f21e97beacbd0bd28c01dfde80d...</td>
      <td>0698286004 0559601019 0717370001 0559601010 06...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0960d621697ca8d22e8d1e943894cd19878b01bbca6407...</td>
      <td>0759871025 0759871002 0408875001 0733749001 08...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0d85c62c90b562c25347bfc7b85d0e42cfdbe66ab2c23f...</td>
      <td>0866731003 0852174003 0866731002 0866731001 08...</td>
    </tr>
  </tbody>
</table>
</div>




```python
evaluate = temp[temp['user_id:token'].isin(result['customer_id'])]
```


```python
evaluate.shape
```




    (912466, 3)




```python
df1 = pd.read_csv("articles.csv", dtype={'article_id': 'str'})
```


```python
def common_code(a, b):
    a_set = set(a)
    b_set = set(b)
    if (a_set & b_set):
        return True 
    else:
        return False
```


```python
hit = 0
for i in result['customer_id']:
    ID=i
    actual = evaluate[evaluate['user_id:token']==ID]['item_id:token'].tolist()
    actualcode = df1[df1['article_id'].isin(actual)]['product_code'].tolist()
    predicted = result[result['customer_id']==ID]['prediction'].str.split(' ').tolist()[0]
    predictedcode = df1[df1['article_id'].isin(predicted)]['product_code'].tolist()
    if common_code(actualcode,predictedcode):
        hit+=1
```


```python
predictedcode
```




    [111586,
     111593,
     158340,
     228257,
     417951,
     436261,
     480093,
     611415,
     889379,
     901924]




```python
df1[df1['article_id'].isin(predicted)]['product_code'].nunique()
```




    10




```python
hit
```




    5504




```python
hit/result.shape[0]
```




    0.9435967769586834




```python
for i in actual:
    if i in predicted:
        print(True)
```


```python
evaluate[evaluate.customer_id==ID]['article_id']
```




    19423    695322001
    Name: article_id, dtype: int64



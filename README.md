# Whats-App-Chat-Analyzer

### 1. Importing Libraries and Reading Data
```python
import re        # imported for regular expression because we need it if we want to convert text file into dataframe
import pandas as pd
```


```python
f = open("WhatsApp Chat with Tayaba Malik Student.txt", encoding = 'utf-8')    # opened the file using file handling
```


```python
data = f.read()    # read the content of the file in form of string and stored it in data
```


```python
print((data))
```
    # A limited amount of chat has been shown
    2/9/21, 7:26 pm - Messages and calls are end-to-end encrypted. No one outside of this chat, not even WhatsApp, can read or listen to them. Tap to learn more.
    2/9/21, 7:26 pm - ~K: Kainat here
    2/9/21, 7:26 pm - Tayaba Malik Student: Yes teacher
    2/9/21, 7:26 pm - Tayaba Malik Student: Assalam-o-Alaikum...
    2/9/21, 7:26 pm - Tayaba Malik Student: Tayyaba  here....
    2/9/21, 7:27 pm - ~K: W. Aslam
    Do download and install ur software
    2/9/21, 7:28 pm - ~K: And if any of the issue arises do let me know
    2/9/21, 7:28 pm - Tayaba Malik Student: Oky  teacher...
    2/9/21, 7:28 pm - Tayaba Malik Student: W m na installation  p lagya hua h... jab s academy  s ahi abhi tak ni hua half hua h...
    2/9/21, 7:29 pm - Tayaba Malik Student: M picture  bjti...
    2/9/21, 7:29 pm - ~K: Dikhay mjy picture
    2/9/21, 7:29 pm - Tayaba Malik Student: Ok
    2/9/21, 7:30 pm - Tayaba Malik Student: <Media omitted>
    2/9/21, 7:30 pm - ~K: Chalo thats fine now atleast is downloading
    2/9/21, 7:31 pm - Tayaba Malik Student: Yes...
    2/9/21, 7:31 pm - ~K: Ho jay jb complete to Intall kr lijiay ga.. Agr koi issue ata hai to btay phir mjy
    2/9/21, 7:31 pm - Tayaba Malik Student: Jab h ga I make practice  j aj parha...
    2/9/21, 7:31 pm - Tayaba Malik Student: Ok thanku
    2/9/21, 7:32 pm - ~K: G g sure



```python

### 2. Data Formating and Cleaning 
# till line 14 we are doing some data preprocessing
pattern = r'\d{1,2}/\d{1,2}/\d{2,4},?\s\d{1,2}:\d{2}\s[APMapm]{2}\s-\s'     # Created a regular expression for 1st column which is dateTime
```


```python
messages = re.split(pattern, data)[1:]   #extracted index 1 elements of list base on pattern
(messages)
```




    ['Messages and calls are end-to-end encrypted. No one outside of this chat, not even WhatsApp, can read or listen to them. Tap to learn more.\n',
     '~K: Kainat here\n',
     'Tayaba Malik Student: Yes teacher\n',
     'Tayaba Malik Student: Assalam-o-Alaikum...\n',
     'Tayaba Malik Student: Tayyaba  here....\n',
     '~K: W. Aslam\nDo download and install ur software\n',
     '~K: And if any of the issue arises do let me know\n',
     'Tayaba Malik Student: Oky  teacher...\n',
     'Tayaba Malik Student: W m na installation  p lagya hua h... jab s academy  s ahi abhi tak ni hua half hua h...\n',
     'Tayaba Malik Student: M picture  bjti...\n',
     '~K: Dikhay mjy picture\n',
     'Tayaba Malik Student: Ok\n',
     'Tayaba Malik Student: <Media omitted>\n',
     '~K: Chalo thats fine now atleast is downloading\n',
     'Tayaba Malik Student: Yes...\n',
     '~K: Ho jay jb complete to Intall kr lijiay ga.. Agr koi issue ata hai to btay phir mjy\n',
     'Tayaba Malik Student: Jab h ga I make practice  j aj parha...\n',
     'Tayaba Malik Student: Ok thanku\n',
     '~K: G g sure\n',

```python
dates = re.findall(pattern, data)
dates
```




    ['2/9/21, 7:26\u202fpm - ',
     '2/9/21, 7:26\u202fpm - ',
     '2/9/21, 7:26\u202fpm - ',
     '2/9/21, 7:26\u202fpm - ',
     '2/9/21, 7:26\u202fpm - ',
     '2/9/21, 7:27\u202fpm - ',
     '2/9/21, 7:28\u202fpm - ',
     '2/9/21, 7:28\u202fpm - ',
     '2/9/21, 7:28\u202fpm - ',
     '2/9/21, 7:29\u202fpm - ',
     '2/9/21, 7:29\u202fpm - ',
     '2/9/21, 7:29\u202fpm - ',
     '2/9/21, 7:30\u202fpm - ',
     '2/9/21, 7:30\u202fpm - ',
     '2/9/21, 7:31\u202fpm - ',
     '2/9/21, 7:31\u202fpm - ',
     '2/9/21, 7:31\u202fpm - ',
     '2/9/21, 7:31\u202fpm - ',
     '2/9/21, 7:32\u202fpm - ',
     '19/9/21, 7:42\u202fpm - ',
     '19/9/21, 7:43\u202fpm - ',
     '19/9/21, 7:43\u202fpm - ',
     '19/9/21, 7:59\u202fpm - ',
     '19/9/21, 8:02\u202fpm - ',
     '19/9/21, 8:03\u202fpm - ',
     '19/9/21, 8:04\u202fpm - ',
     '19/9/21, 8:05\u202fpm - ',
     '19/9/21, 8:08\u202fpm - ',
     '19/9/21, 8:09\u202fpm - ',
     '19/9/21, 8:23\u202fpm - ',


```python
df = pd.DataFrame({'user_message':messages,'message_date':dates})
# convert message_date to DateTime type
df['message_date'] = pd.to_datetime(df['message_date'], format = '%d/%m/%y, %I:%M %p - ')
df.rename(columns={'message_date':'date'}, inplace=True)
df.head()
```


<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>user_message</th>
      <th>date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Messages and calls are end-to-end encrypted. N...</td>
      <td>2021-09-02 19:26:00</td>
    </tr>
    <tr>
      <th>1</th>
      <td>~K: Kainat here\n</td>
      <td>2021-09-02 19:26:00</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Tayaba Malik Student: Yes teacher\n</td>
      <td>2021-09-02 19:26:00</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Tayaba Malik Student: Assalam-o-Alaikum...\n</td>
      <td>2021-09-02 19:26:00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Tayaba Malik Student: Tayyaba  here....\n</td>
      <td>2021-09-02 19:26:00</td>
    </tr>
  </tbody>
</table>
</div>




```python
### 3. Separating users and messages
# separate users and message
users = []
messages = []
for message in df['user_message']:
    entry = re.split('([\w\W]+?):\s', message)
    if entry[1:]: # user name
        users.append(entry[1])
        messages.append(entry[2])
    else:   # if : is not found in the message
        users.append('group_notification')
        messages.append(entry[0])
df['user'] = users
df['message'] = messages
df.drop(columns=['user_message'], inplace=True)
df.head()
```



<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>date</th>
      <th>user</th>
      <th>message</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2021-09-02 19:26:00</td>
      <td>group_notification</td>
      <td>Messages and calls are end-to-end encrypted. N...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2021-09-02 19:26:00</td>
      <td>~K</td>
      <td>Kainat here\n</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2021-09-02 19:26:00</td>
      <td>Tayaba Malik Student</td>
      <td>Yes teacher\n</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2021-09-02 19:26:00</td>
      <td>Tayaba Malik Student</td>
      <td>Assalam-o-Alaikum...\n</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2021-09-02 19:26:00</td>
      <td>Tayaba Malik Student</td>
      <td>Tayyaba  here....\n</td>
    </tr>
  </tbody>
</table>
</div>




```python
df['year'] = df['date'].dt.year
df.head()
```




<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>date</th>
      <th>user</th>
      <th>message</th>
      <th>year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2021-09-02 19:26:00</td>
      <td>group_notification</td>
      <td>Messages and calls are end-to-end encrypted. N...</td>
      <td>2021</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2021-09-02 19:26:00</td>
      <td>~K</td>
      <td>Kainat here\n</td>
      <td>2021</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2021-09-02 19:26:00</td>
      <td>Tayaba Malik Student</td>
      <td>Yes teacher\n</td>
      <td>2021</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2021-09-02 19:26:00</td>
      <td>Tayaba Malik Student</td>
      <td>Assalam-o-Alaikum...\n</td>
      <td>2021</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2021-09-02 19:26:00</td>
      <td>Tayaba Malik Student</td>
      <td>Tayyaba  here....\n</td>
      <td>2021</td>
    </tr>
  </tbody>
</table>




```python
df['month'] = df['date'].dt.month_name()
```


```python
 df['day']= df['date'].dt.day
```


```python
df.head()
```




<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>date</th>
      <th>user</th>
      <th>message</th>
      <th>year</th>
      <th>month</th>
      <th>day</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2021-09-02 19:26:00</td>
      <td>group_notification</td>
      <td>Messages and calls are end-to-end encrypted. N...</td>
      <td>2021</td>
      <td>September</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2021-09-02 19:26:00</td>
      <td>~K</td>
      <td>Kainat here\n</td>
      <td>2021</td>
      <td>September</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2021-09-02 19:26:00</td>
      <td>Tayaba Malik Student</td>
      <td>Yes teacher\n</td>
      <td>2021</td>
      <td>September</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2021-09-02 19:26:00</td>
      <td>Tayaba Malik Student</td>
      <td>Assalam-o-Alaikum...\n</td>
      <td>2021</td>
      <td>September</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2021-09-02 19:26:00</td>
      <td>Tayaba Malik Student</td>
      <td>Tayyaba  here....\n</td>
      <td>2021</td>
      <td>September</td>
      <td>2</td>
    </tr>
  </tbody>
</table>




```python
df['hour'] = df['date'].dt.hour
df['minute'] = df['date'].dt.minute
df.head()
```

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>date</th>
      <th>user</th>
      <th>message</th>
      <th>year</th>
      <th>month</th>
      <th>day</th>
      <th>hour</th>
      <th>minute</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2021-09-02 19:26:00</td>
      <td>group_notification</td>
      <td>Messages and calls are end-to-end encrypted. N...</td>
      <td>2021</td>
      <td>September</td>
      <td>2</td>
      <td>19</td>
      <td>26</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2021-09-02 19:26:00</td>
      <td>~K</td>
      <td>Kainat here\n</td>
      <td>2021</td>
      <td>September</td>
      <td>2</td>
      <td>19</td>
      <td>26</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2021-09-02 19:26:00</td>
      <td>Tayaba Malik Student</td>
      <td>Yes teacher\n</td>
      <td>2021</td>
      <td>September</td>
      <td>2</td>
      <td>19</td>
      <td>26</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2021-09-02 19:26:00</td>
      <td>Tayaba Malik Student</td>
      <td>Assalam-o-Alaikum...\n</td>
      <td>2021</td>
      <td>September</td>
      <td>2</td>
      <td>19</td>
      <td>26</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2021-09-02 19:26:00</td>
      <td>Tayaba Malik Student</td>
      <td>Tayyaba  here....\n</td>
      <td>2021</td>
      <td>September</td>
      <td>2</td>
      <td>19</td>
      <td>26</td>
    </tr>
  </tbody>
</table>




```python
df[df['user'] == 'Zara CR'].shape[0]
```




    0




```python

```

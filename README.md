# Whats-App-Chat-Analyzer

## Jupyter Notebook code:
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

### 2. Data Formating and Cleaning 
```python

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


### 3. Separating users and messages

```python

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
## Website for code was done on Pycharm across 3 files

## Main.py

     ```python
        import matplotlib.pyplot as plt
        import streamlit as st
        from preprocessor import preprocess
        import helper
        import seaborn as sns
        
        st.sidebar.title("WhatsApp Chat Analyser")
        uploaded_file = st.sidebar.file_uploader("Choose a file")

        if uploaded_file is not None:
            bytes_data = uploaded_file.getvalue()
            data = bytes_data.decode("utf-8")
            #st.text(data)
            df = preprocess(data)
        
            user_list = df['user'].unique().tolist()
            user_list.remove("group_notification")
            user_list.sort()
            user_list.insert(0,"Overall")
            selected_user= st.sidebar.selectbox("Show analysis wrt", user_list)

            if st.sidebar.button("Show Analysis"):
                # Stats Area
                num_messages, words, num_media_messages, num_links = helper.fetch_stats(selected_user, df)
                st.title("Total Statistics")
                col1, col2, col3, col4 = st.columns(4)
                with col1:
                    st.header("Total Messages")
                    st.title(num_messages)
                with col2:
                    st.header("Total Words")
                    st.title(words)
                with col3:
                    st.header("Media Messages")
                    st.title(num_media_messages)
                with col4:
                    st.header("Links Shared")
                    st.title(num_links)
        
                # monthly Timeline
                st.title("Monthly Timeline")
                timeline = helper.monthly_timeline(selected_user,df)
                fig,ax = plt.subplots()
                ax.plot(timeline['time'], timeline['message'], color = 'green')
                plt.xticks(rotation = 'vertical')
                st.pyplot(fig)
        
                # Daily timeline
                st.title("Daily Timeline")
                daily_timeline = helper.daily_timeline(selected_user, df)
                fig, ax = plt.subplots()
                ax.plot(daily_timeline['only_date'], daily_timeline['message'], color='black')
                plt.xticks(rotation='vertical')
                st.pyplot(fig)
        
                # Activity Map
                st.title("Activity Map")
                col1,col2 = st.columns(2)
        
                with col1:
                    st.header("Most busy day")
                    busy_day = helper.week_activity_map(selected_user,df)
                    fig,ax = plt.subplots()
                    ax.bar(busy_day.index, busy_day.values)
                    plt.xticks(rotation='vertical')
                    st.pyplot(fig)
                with col2:
                    st.header("Most busy month")
                    busy_month = helper.month_activity_map(selected_user, df)
                    fig, ax = plt.subplots()
                    ax.bar(busy_month.index, busy_month.values, color='orange')
                    plt.xticks(rotation='vertical')
                    st.pyplot(fig)
        
                st.title("Weekly Activity Map")
                user_heatmap = helper.activity_heatmap(selected_user,df)
                fig, ax = plt.subplots()
                ax = sns.heatmap(user_heatmap)
                st.pyplot(fig)
        
        
                # fetch busiest user in the group(Group level)
                if selected_user == 'Overall':
                    st.title("Most Busy User")
                    x, new_df = helper.most_busy_users(df)
                    fig, ax = plt.subplots()
        
                    col1, col2 = st.columns(2)
        
                    with col1:
                        ax.bar(x.index, x.values)
                        plt.xticks(rotation = 'vertical')
                        st.pyplot(fig)
                    with col2:
                        st.dataframe(new_df)
        
                # WordCloud
                st.title("Wordcloud")
                df_wc = helper.create_wordcloud(selected_user,df)
                fig, ax = plt.subplots()
                ax.imshow(df_wc)
                st.pyplot(fig)
        
                # Most Common Words
                most_common_df = helper.most_common_words(selected_user,df)
                fig, ax = plt.subplots()
                ax.barh(most_common_df[0], most_common_df[1])
                plt.xticks(rotation='vertical')
        
                st.title("Most Common Words")
                st.pyplot(fig)
        
                # emoji analysis
                emoji_df = helper.emoji_helper(selected_user,df)
                st.title("Most Common Emojis")
                col1, col2 = st.columns(2)
        
                with col1:
                    st.dataframe(emoji_df)
                with col2:
                    fig,ax = plt.subplots()
                    ax.pie(emoji_df[1].head(),labels=emoji_df[0].head(),autopct="%0.2f")
                    st.pyplot(fig) 
     ```python

## Helper.py


     ```python
        import streamlit
        from urlextract import URLExtract
        import matplotlib.pyplot as plt
        from wordcloud import WordCloud
        from collections import Counter
        import pandas as pd
        import emoji
        extract = URLExtract()
        
        def fetch_stats(selected_user,df):
            if selected_user != 'Overall':
                df = df[df['user'] == selected_user]
            # 1. fetch number of messages
            num_messages = df.shape[0]
            # 2. fetch number of words
            words = []
            for message in df['message']:
                words.extend(message.split())
            # 3. fetch number of media messages
            num_media_messages = df[df['message'] == '<Media omitted>\n'].shape[0]
        
            # 4. fetch number of links shared
            links =[]
            for message in df['message']:
                links.extend(extract.find_urls(message))
            return num_messages, len(words), num_media_messages, len(links)
        
        def most_busy_users(df):
            x = df['user'].value_counts().head()
            df = round((df['user'].value_counts() / df.shape[0])*100,2 ).reset_index().rename({'index':'name','count':'percentage'})
            return x, df
        
        def create_wordcloud(selected_user,df):
            if selected_user != 'Overall':
                df = df[df['user'] == selected_user]
            temp = df[df['user'] != 'group_notification']
            temp = temp[temp['message'] != '<Media omitted>\n']
            wc = WordCloud(width=500,height=500,min_font_size=10, background_color='white')
            df_wc = wc.generate(temp['message'].str.cat(sep = " "))
            return df_wc
        
        def most_common_words(selected_user,df):
            f = open('stop_hinglish.txt','r')
            stop_words = f.read()
            if selected_user != 'Overall':
                df = df[df['user'] == selected_user]
            temp = df[df['user'] != 'group_notification']
            temp = temp[temp['message'] != '<Media omitted>\n']
        
            words=[]
            for message in temp['message']:
                for word in message.lower().split():
                    if word not in stop_words:
                        words.append(word)
            most_common_df = pd.DataFrame(Counter(words).most_common(20))
            return most_common_df
        
        def emoji_helper(selected_user,df):
            if selected_user != 'Overall':
                df = df[df['user'] == selected_user]
        
            emojis=[]
            for message in df['message']:
                emojis.extend([c for c in message if c in emoji.EMOJI_DATA])
        
            emoji_df = pd.DataFrame(Counter(emojis).most_common(len(Counter(emojis))))
            return emoji_df
        
        def monthly_timeline(selected_user,df):
            if selected_user != 'Overall':
                df = df[df['user'] == selected_user]
            timeline = df.groupby(['year','month_num','month']).count()['message'].reset_index()
        
            time=[]
            for i in range(timeline.shape[0]):
                time.append(timeline['month'][i] + "-" + str(timeline['year'][i]))
            timeline['time'] = time
            return timeline
        
        def daily_timeline(selected_user,df):
            if selected_user != 'Overall':
                df = df[df['user'] == selected_user]
            daily_timeline = df.groupby('only_date').count()['message'].reset_index()
            return daily_timeline
        
        def week_activity_map(selected_user,df):
            if selected_user != 'Overall':
                df = df[df['user'] == selected_user]
            return df['day_name'].value_counts()
        
        def month_activity_map(selected_user,df):
            if selected_user != 'Overall':
                df = df[df['user'] == selected_user]
            return df['month'].value_counts()
        
        def activity_heatmap(selected_user,df):
            if selected_user != 'Overall':
                df = df[df['user'] == selected_user]
            activity_heatmap = df.pivot_table(index='day_name', columns='period', values='message', aggfunc='count').fillna(0)
            return activity_heatmap
        
    ```python


## preprocessor.py
    ```python
        import re
        import pandas as pd
        def preprocess(data):
            pattern = r'\d{1,2}/\d{1,2}/\d{2,4},?\s\d{1,2}:\d{2}\s[APMapm]{2}\s-\s'  # Created a regular expression for 1st column which is dateTime
            messages = re.split(pattern, data)[1:]  # extracted index 1 elements of list base on pattern
            dates = re.findall(pattern, data)
        
            df = pd.DataFrame({'user_message': messages, 'message_date': dates})
            # convert message_date to DateTime type
            df['message_date'] = pd.to_datetime(df['message_date'], format='%d/%m/%y, %I:%M %p - ')
            df.rename(columns={'message_date': 'date'}, inplace=True)
        
            # separate users and message
            users = []
            messages = []
            for message in df['user_message']:
                entry = re.split('([\w\W]+?):\s', message)
                if entry[1:]:  # user name
                    users.append(entry[1])
                    messages.append(entry[2])
                else:  # if : is not found in the message
                    users.append('group_notification')
                    messages.append(entry[0])
            df['user'] = users
            df['message'] = messages
            df.drop(columns=['user_message'], inplace=True)
            df['only_date'] = df['date'].dt.date
            df['day_name'] = df['date'].dt.day_name()
            df['year'] = df['date'].dt.year
            df['month'] = df['date'].dt.month_name()
            df['month_num'] = df['date'].dt.month
            df['day'] = df['date'].dt.day
            df['hour'] = df['date'].dt.hour
            df['minute'] = df['date'].dt.minute
        
            period = []
            for hour in df[['day_name','hour']]['hour']:
                if hour == 23:
                    period.append(str(hour) + "-" + str('00'))
                elif hour == 0:
                    period.append(str('00') + "-" + str(hour + 1))
                else:
                    period.append(str(hour) + "-" + str(hour + 1))
        
            df['period'] = period
            return df
        ```python
        
        
        


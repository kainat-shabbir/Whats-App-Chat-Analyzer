# Whats-App-Chat-Analyzer

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
    19/9/21, 7:42 pm - Tayaba Malik Student: <Media omitted>
    19/9/21, 7:43 pm - Tayaba Malik Student: Assalam-o-Alaikum  teacher  time table...
    19/9/21, 7:43 pm - Tayaba Malik Student: 1 wla mera h... is week m
    19/9/21, 7:59 pm - ~K: W. Aslam... SE 3rd A apka hai?
    19/9/21, 8:02 pm - Tayaba Malik Student: G
    19/9/21, 8:03 pm - ~K: To Jin days main 12 40 last class hai apki... Ap ghar kab tk wapis aa jay ge?
    19/9/21, 8:04 pm - Tayaba Malik Student: Pta ni... teacher  yh ab gari waly s us din btata h..  k w kab lany ay g...
    19/9/21, 8:05 pm - Tayaba Malik Student: Lakin 4 s phly aha jau gi
    19/9/21, 8:08 pm - ~K: Ap ny khud kya socha hai... Kis kis din aa sky ge ap?
    19/9/21, 8:09 pm - ~K: Q k Mery khyal sy to Monday ko chor k baki days main flexibility hai any ki
    19/9/21, 8:23 pm - Tayaba Malik Student: Teacher m jis din ghar 4 bajy aha gi... m aha jau gi...
    19/9/21, 8:23 pm - Tayaba Malik Student: Jis din late h gi phir  off...
    19/9/21, 8:37 pm - ~K: Chalain thk Hai jaisy easy lagy apko kr laina
    19/9/21, 8:40 pm - Tayaba Malik Student: G teacher
    19/9/21, 8:41 pm - Tayaba Malik Student: Thanku
    26/9/21, 1:43 pm - Tayaba Malik Student: Assalam-o-Alaikum  teacher
    26/9/21, 1:43 pm - Tayaba Malik Student: <Media omitted>
    26/9/21, 2:18 pm - ~K: W. Aslam
    26/9/21, 2:19 pm - ~K: So u have no class on Sat?
    26/9/21, 3:22 pm - Tayaba Malik Student: G teacher  agar  koi arrange  na ki..
    26/9/21, 3:35 pm - ~K: so currently thursday and saturday are seems to be easy, which other days you think are gonna be easier for you?
    26/9/21, 3:36 pm - Tayaba Malik Student: G
    26/9/21, 3:36 pm - Tayaba Malik Student: Kal on Monday...
    26/9/21, 3:37 pm - Tayaba Malik Student: And  Friday
    26/9/21, 3:38 pm - ~K: Ok that sounds good. now then you should try to be there on these 4 days
    26/9/21, 4:55 pm - Tayaba Malik Student: Yes.. inshallah
    1/10/21, 2:00 pm - Tayaba Malik Student: Assalam-o-Alaikum  teacher  aj m ahu gi... m ghar  aha gi ...
    7/10/21, 7:01 pm - Tayaba Malik Student: Assalam-o-Alaikum... teacher  email...
    7/10/21, 7:01 pm - Tayaba Malik Student: tayaba1389@gmail.com
    7/10/21, 7:24 pm - ~K: W. Aslam.. Ok i will send you in a while
    7/10/21, 9:31 pm - Tayaba Malik Student: G sure teacher  ...
    7/10/21, 9:40 pm - ~K: It is ok if i send you the picture of the code...the folder seems to be infected which could In turn infect ur system too
    7/10/21, 9:41 pm - ~K: Is it*
    7/10/21, 9:41 pm - Tayaba Malik Student: Yes teacher...
    7/10/21, 9:41 pm - Tayaba Malik Student: Sure..
    7/10/21, 9:41 pm - ~K: Ok
    7/10/21, 9:42 pm - Tayaba Malik Student: Thanku...
    7/10/21, 9:42 pm - ~K: <Media omitted>
    7/10/21, 9:42 pm - ~K: My pleasure 🌸
    7/10/21, 9:43 pm - Tayaba Malik Student: Ok fine... its clear...
    7/10/21, 9:43 pm - Tayaba Malik Student: 😇
    13/10/21, 7:24 pm - ~K: Assalam u alaikum!
    I will let u know today's class time in a while
    13/10/21, 7:24 pm - Tayaba Malik Student: Waslam...
    13/10/21, 7:24 pm - Tayaba Malik Student: Ok
    13/10/21, 7:26 pm - ~K: Until then download anydesk in ur system
    13/10/21, 7:26 pm - Tayaba Malik Student: Okay
    13/10/21, 8:09 pm - ~K: Should we start?
    13/10/21, 8:10 pm - Tayaba Malik Student: Yes
    13/10/21, 8:10 pm - ~K: download kr lia ap ny?
    13/10/21, 8:11 pm - Tayaba Malik Student: Ni teacher  w ni hua...
    13/10/21, 8:11 pm - Tayaba Malik Student: Na cell phone  m na PC m...
    13/10/21, 8:11 pm - ~K: laptop main krna tha na
    13/10/21, 8:11 pm - Tayaba Malik Student: Google  meet chly g???
    13/10/21, 8:11 pm - Tayaba Malik Student: Kia h lakin ni hua...
    13/10/21, 8:12 pm - Tayaba Malik Student: M picture  bjti...
    13/10/21, 8:12 pm - ~K: ni...main apki screen ka access lon ge...usky liay anydesk chahiay
    13/10/21, 8:12 pm - ~K: google per likhain..."download anydesk" first link ko open kr k download kr lain
    13/10/21, 8:12 pm - Tayaba Malik Student: Teacher  kal m academy  ahu gi... t check  kar ln...
    13/10/21, 8:12 pm - Tayaba Malik Student: Ok
    13/10/21, 8:13 pm - ~K: <Media omitted>
    13/10/21, 8:13 pm - ~K: is link sy krain download
    13/10/21, 8:14 pm - Tayaba Malik Student: Oky
    13/10/21, 8:14 pm - ~K: download kr k mjy btaiay phir
    13/10/21, 8:14 pm - Tayaba Malik Student: G teacher
    13/10/21, 8:20 pm - Tayaba Malik Student: Teacher  yh installed  h gya
    13/10/21, 8:21 pm - Tayaba Malik Student: <Media omitted>
    13/10/21, 8:22 pm - ~K: g thk hai install ho gya hai
    13/10/21, 8:22 pm - Tayaba Malik Student: G
    13/10/21, 8:23 pm - ~K: ab main apky is address k through access kron ge ...request accept kijiay ga
    13/10/21, 8:23 pm - Tayaba Malik Student: Ok
    13/10/21, 8:23 pm - ~K: on krain anydesk apna
    13/10/21, 8:24 pm - Tayaba Malik Student: On h
    13/10/21, 8:25 pm - ~K: main apko 10 min tk call krti hn whats app per he
    13/10/21, 8:26 pm - Tayaba Malik Student: Ok
    13/10/21, 8:26 pm - ~K: tb tk main apko practice btati hn wo krain
    13/10/21, 8:26 pm - Tayaba Malik Student: Ok
    13/10/21, 8:27 pm - ~K: bal k...main abhi krti hn call apko
    13/10/21, 8:27 pm - Tayaba Malik Student: Ok
    13/10/21, 9:28 pm - Tayaba Malik Student: <Media omitted>
    13/10/21, 9:34 pm - ~K: Session end ho gya apki side sy anydesk ka?
    13/10/21, 9:34 pm - Tayaba Malik Student: G.. h gya
    13/10/21, 9:34 pm - ~K: Ok
    13/10/21, 9:34 pm - Tayaba Malik Student: Thanku teacher
    13/10/21, 9:35 pm - ~K: Ur most welcome 🌸
    14/10/21, 7:21 pm - ~K: Can we start?
    14/10/21, 7:22 pm - Tayaba Malik Student: yes teacher
    14/10/21, 7:22 pm - ~K: Ok i will call you in 5 min
    14/10/21, 7:23 pm - Tayaba Malik Student: ok
    14/10/21, 7:26 pm - ~K: Sae ni aa rhe apko awaz?
    14/10/21, 7:27 pm - ~K: Meri side ka internet weak ho gya hai
    14/10/21, 7:27 pm - ~K: Stable hota hai to main dobara call krti hn apko
    14/10/21, 7:27 pm - Tayaba Malik Student: Ok... teacher  we wait...for while
    14/10/21, 7:28 pm - Tayaba Malik Student: Ok
    14/10/21, 7:28 pm - ~K: Sae hota hai to main inform krti hn apkk
    14/10/21, 7:28 pm - ~K: Apko*
    14/10/21, 7:28 pm - Tayaba Malik Student: Ok
    14/10/21, 8:06 pm - ~K: Let me try now
    14/10/21, 8:06 pm - ~K: Completely sae ni hoa... But can give it a try
    14/10/21, 8:06 pm - Tayaba Malik Student: Ok
    14/10/21, 8:35 pm - Tayaba Malik Student: <Media omitted>
    14/10/21, 8:36 pm - Tayaba Malik Student: <Media omitted>
    14/10/21, 8:37 pm - Tayaba Malik Student: <Media omitted>
    14/10/21, 8:41 pm - ~K: Ap aik krain... Is code ko copy kr k word main paste krain
    14/10/21, 8:41 pm - ~K: Kam*
    14/10/21, 8:42 pm - Tayaba Malik Student: ok
    14/10/21, 8:43 pm - ~K: Us file... Mtlb word ki file ko save krain... Desktop per he kr dain beshak
    14/10/21, 8:43 pm - Tayaba Malik Student: ok
    14/10/21, 8:44 pm - ~K: ab is ko close krain
    14/10/21, 8:44 pm - ~K: codeblocks ko
    14/10/21, 8:44 pm - ~K: or system ko restart krain
    14/10/21, 8:48 pm - Tayaba Malik Student: ok
    14/10/21, 8:48 pm - Tayaba Malik Student: m code block m karti
    14/10/21, 8:50 pm - ~K: Restart krain ge phir is program krain ge to hopefully ni ay ga error yeh wala
    14/10/21, 8:53 pm - Tayaba Malik Student: ok thanku teacher
    14/10/21, 8:54 pm - ~K: Error aya dobara to do let me know then
    14/10/21, 8:59 pm - Tayaba Malik Student: Ok... kar rahi teacher
    15/10/21, 8:07 pm - ~K: Can we start?
    15/10/21, 8:11 pm - Tayaba Malik Student: No teacher.... sorry  aj ni....
    15/10/21, 8:13 pm - ~K: Ok
    15/10/21, 8:13 pm - ~K: But is there any reason?
    15/10/21, 8:13 pm - Tayaba Malik Student: Aj teacher  m ghar ni hu... t system  ni h...
    15/10/21, 8:13 pm - ~K: Ok ok no problem
    15/10/21, 8:14 pm - Tayaba Malik Student: No  teacher...
    15/10/21, 8:14 pm - Tayaba Malik Student: Aj birthday  h t bahir  khna h..
    15/10/21, 8:15 pm - ~K: Ohhh... Happy birthday 🌸🌸
    15/10/21, 8:15 pm - ~K: Chalain enjoy krain phir aj to bilkul ni Banta apka parhna😂
    15/10/21, 8:15 pm - Tayaba Malik Student: Thanku so much  teacher❤️❤️
    15/10/21, 8:16 pm - ~K: My pleasure 🌸
    15/10/21, 8:16 pm - Tayaba Malik Student: I am really  sorry...
    15/10/21, 9:25 pm - ~K: No no... Don't be.. It's ok
    16/10/21, 7:19 pm - ~K: Aj ka bta dain mjy
    16/10/21, 7:19 pm - Tayaba Malik Student: Yes teacher  aj class l ln...
    16/10/21, 7:19 pm - ~K: Ok phir... Can we start the class now?
    16/10/21, 7:20 pm - Tayaba Malik Student: Yes ..
    16/10/21, 7:23 pm - ~K: Chalain
    16/10/21, 7:23 pm - Tayaba Malik Student: G
    18/10/21, 7:30 pm - ~K: Should we start the class?
    18/10/21, 8:12 pm - Tayaba Malik Student: G teacher
    18/10/21, 8:12 pm - Tayaba Malik Student: Lakin aj hmary  wifi ni chl raha...
    18/10/21, 8:12 pm - Tayaba Malik Student: And sorry abhi m na ap k msg deakha...
    18/10/21, 8:13 pm - ~K: To phir ab?
    18/10/21, 8:13 pm - ~K: G late kr dia hai na ap ny aj
    18/10/21, 8:13 pm - Tayaba Malik Student: G teacher  sorry
    18/10/21, 8:13 pm - Tayaba Malik Student: Teacher  kuch net chl jy g
    18/10/21, 8:13 pm - ~K: Chalain phir... Kal free hon ge ap? Milad wagaira to ni Hai apky ghar?
    18/10/21, 8:14 pm - Tayaba Malik Student: Ni...
    18/10/21, 8:14 pm - Tayaba Malik Student: Free hu
    18/10/21, 8:14 pm - ~K: Kal lon ge ab main apki class.. Q k aj already abhi msg late daikhny ki wja sy late kr dia hai ap ny
    18/10/21, 8:14 pm - Tayaba Malik Student: Ok no issue
    18/10/21, 8:14 pm - Tayaba Malik Student: I am really  sorry teacher
    18/10/21, 8:15 pm - ~K: Chalain koi bt ni... But dhayan rakha krain.. Is time phone ko Thora pas rakha krain apny
    18/10/21, 8:15 pm - Tayaba Malik Student: Teacher  ap mujy koi task  d dn karny k liya
    18/10/21, 8:15 pm - Tayaba Malik Student: Ok.. Next time asa ni h ga inshallah
    18/10/21, 8:15 pm - ~K: Last time grade wala program kia tha hm ny?
    18/10/21, 8:15 pm - Tayaba Malik Student: G
    18/10/21, 8:19 pm - ~K: Main btati hn apko task
    18/10/21, 8:19 pm - Tayaba Malik Student: G teacher
    18/10/21, 8:20 pm - ~K: <Media omitted>
    18/10/21, 8:22 pm - Tayaba Malik Student: First hum
     cin number  
    Karn g
    18/10/21, 8:22 pm - ~K: Usky bahd
    18/10/21, 8:22 pm - ~K: Condition mjy btay... Kaisy lagay ge
    18/10/21, 8:23 pm - Tayaba Malik Student: If if else use karn g...
    18/10/21, 8:23 pm - ~K: If (yahan per kya ay ga)
    18/10/21, 8:23 pm - ~K: Condition ny to brackets k andar lagna hai na... Or Sara apka condition ki base per he hoga decide
    18/10/21, 8:24 pm - Tayaba Malik Student: First if m hum condition lakin g
    If(num/2)
    18/10/21, 8:25 pm - Tayaba Malik Student: J number  enter karn g us k q 2 s divide kary g j 2 s devide  h jya g w even ... h ga air if m store h jya g
    18/10/21, 8:24 pm - ~K: <Media omitted>
    18/10/21, 8:25 pm - ~K: Condition likh k btay
    18/10/21, 8:26 pm - ~K: <Media omitted>
    18/10/21, 8:26 pm - Tayaba Malik Student: Even number w number  hty hn jin p 2 k table jata h
    18/10/21, 8:26 pm - Tayaba Malik Student: Ok
    18/10/21, 8:27 pm - ~K: Bilkul
    18/10/21, 8:27 pm - ~K: <Media omitted>
    18/10/21, 8:28 pm - Tayaba Malik Student: 2 k table s bi..
    18/10/21, 8:29 pm - ~K: Ap tasali sy sochain na... Phir mjy btay
    18/10/21, 8:30 pm - Tayaba Malik Student: Ok
    18/10/21, 8:30 pm - ~K: <Media omitted>
    18/10/21, 8:32 pm - Tayaba Malik Student: Divide  kar k... 2 s agar pura Divide h jya g remainder 0 h  t even  h ga...
    18/10/21, 8:32 pm - Tayaba Malik Student: Aur remainder koi number hua t odd h ga aur else m store h ga...
    18/10/21, 8:44 pm - ~K: Kahan sy daikha hai? 😂
    18/10/21, 8:44 pm - Tayaba Malik Student: Khain s ni
    18/10/21, 8:44 pm - ~K: Ok thk Hai... Condition laga k run krain
    18/10/21, 8:44 pm - Tayaba Malik Student: Teacher math m koi bara number  h us k divde karty
    18/10/21, 8:45 pm - ~K: Code ki picture mjy bejhain agr run ni hota to
    18/10/21, 8:45 pm - Tayaba Malik Student: Aur even k liya hum 3 s karn g
    18/10/21, 8:45 pm - Tayaba Malik Student: Ok
    18/10/21, 8:45 pm - Tayaba Malik Student: Teacher  condition  kia bny gi
    18/10/21, 8:45 pm - ~K: Apkiii... Bt smj ni ai mjy... Kyax keh rhe hain ap
    18/10/21, 8:45 pm - ~K: Yahe to sochna hai na ap ny ab
    18/10/21, 8:46 pm - Tayaba Malik Student: Koi bara number h us p table la k jna h t divide yh multiply  karty
    18/10/21, 8:46 pm - Tayaba Malik Student: Ok
    18/10/21, 8:46 pm - ~K: Yeh condition hoge
    18/10/21, 8:46 pm - Tayaba Malik Student: Ni
    18/10/21, 8:46 pm - ~K: Laiken isko ap likhain ge kaisy... Yeh sochain ap Thora sa ab
    18/10/21, 8:46 pm - Tayaba Malik Student: Num / 2 h gi
    18/10/21, 8:47 pm - ~K: <Media omitted>
    18/10/21, 8:47 pm - ~K: <Media omitted>
    18/10/21, 8:48 pm - Tayaba Malik Student: Divide quotient  return  karta
    18/10/21, 8:49 pm - Tayaba Malik Student: Modules remainder return karta
    18/10/21, 8:49 pm - ~K: Exactly
    18/10/21, 8:49 pm - Tayaba Malik Student: T modules  k operator h g
    18/10/21, 8:50 pm - ~K: To ab itna smj aya apko to zra sochain... Kis trah honi chahiye condition
    18/10/21, 8:50 pm - ~K: G
    18/10/21, 8:50 pm - ~K: <Media omitted>
    18/10/21, 8:50 pm - Tayaba Malik Student: Num  modules  2
    18/10/21, 8:50 pm - ~K: Bilkul
    18/10/21, 8:50 pm - ~K: <Media omitted>
    18/10/21, 8:51 pm - Tayaba Malik Student: J user enter kary g us k modules karn g
    18/10/21, 8:52 pm - Tayaba Malik Student: Teacher agar w zero hua t store h jya g... ni t else m aha jya g
    18/10/21, 8:53 pm - ~K: Agr wo zero hai... Is cheez ko condition main kaisy likhain ge?
    18/10/21, 8:53 pm - ~K: ==
    Yeh operator use hoga
    18/10/21, 8:53 pm - ~K: <Media omitted>
    18/10/21, 8:54 pm - Tayaba Malik Student: T condition yh h gi
    Num modules  2 
    Modules ==0
    18/10/21, 8:55 pm - ~K: 2 ka bahd dobara modules q laga rhe hain?
    18/10/21, 8:55 pm - Tayaba Malik Student: Teacher w 2 l zero na l l iss liya
    18/10/21, 8:56 pm - ~K: Ap laga k run krain
    18/10/21, 8:56 pm - ~K: Or check krain zra isko
    18/10/21, 8:56 pm - Tayaba Malik Student: Ok
    19/10/21, 7:48 pm - ~K: Should we start?
    19/10/21, 7:49 pm - Tayaba Malik Student: Yes
    21/10/21, 7:09 pm - ~K: Should we start the class?
    21/10/21, 7:09 pm - Tayaba Malik Student: Yes
    21/10/21, 7:22 pm - ~K: Smj ni aa rhe?
    21/10/21, 7:22 pm - Tayaba Malik Student: Ni
    21/10/21, 7:23 pm - Tayaba Malik Student: Bilkul  samj ni sha rahi
    21/10/21, 7:23 pm - ~K: Apko msg b late receive hoa hai
    21/10/21, 7:23 pm - Tayaba Malik Student: G
    21/10/21, 7:23 pm - ~K: Apky end per b hai issue
    21/10/21, 7:23 pm - Tayaba Malik Student: Gg
    21/10/21, 7:25 pm - ~K: Write a program in which you will take a input from user and check whether it is alphabet or consonant, also restrict user from entering any other character than alphabet by showing a screen msg
    21/10/21, 7:31 pm - ~K: Meri awaz bht late aa rhe hai apko
    21/10/21, 7:35 pm - Tayaba Malik Student: Teacher  ap ki awaz cut rshi
    21/10/21, 7:35 pm - ~K: Likhain ap
    21/10/21, 7:35 pm - Tayaba Malik Student: Rahi**
    22/10/21, 7:41 pm - ~K: The class will be started on 7 50
    22/10/21, 7:41 pm - Tayaba Malik Student: Okay
    22/10/21, 7:46 pm - ~K: Should we start?
    22/10/21, 7:48 pm - Tayaba Malik Student: Yes teacher  ik minute  m laptop nikal lu
    22/10/21, 7:49 pm - ~K: Ok nikal lain
    22/10/21, 7:51 pm - Tayaba Malik Student: Ok teacher lets start
    23/10/21, 7:31 pm - ~K: Tayaba ap Kal full day ghar he hony Wali hain ?
    23/10/21, 7:32 pm - ~K: It is ok if we shift our today class on Sunday?
    23/10/21, 7:32 pm - Tayaba Malik Student: G teacher
    23/10/21, 7:32 pm - Tayaba Malik Student: Yes sure
    23/10/21, 7:33 pm - ~K: Ok phir main apki aj Wali class kal ly lon ge
    23/10/21, 7:33 pm - ~K: Time main apko kal he bta don ge
    23/10/21, 7:33 pm - Tayaba Malik Student: Ok
    24/10/21, 5:40 pm - ~K: We will start the class at 6
    24/10/21, 5:42 pm - Tayaba Malik Student: Ok
    24/10/21, 5:55 pm - ~K: Should we start?
    24/10/21, 5:55 pm - Tayaba Malik Student: Yes
    24/10/21, 6:04 pm - Tayaba Malik Student: <Media omitted>
    24/10/21, 6:05 pm - Tayaba Malik Student: <Media omitted>
    24/10/21, 6:07 pm - Tayaba Malik Student: // Linked list operations in C++
    #include <iostream>
    using namespace std;
     // Create a node struct Node 
     struct Node {
     int data;
     struct Node* next;
      };
       void insertAtBeginning(struct Node** head_ref, int new_data) {
        // Allocate memory to a node
    	 struct Node* new_node = (struct Node*)malloc(sizeof(struct Node) );
    	 // insert the data
    	   new_node->data = new_data;
    	    new_node->next = (head_ref);
    	 // Move head to new node
    	  (*head_ref) = new_node;
    	   }
    	 // Insert a node after a node
    	  void insertAfter(struct Node * prev_node, int new_data) { 
    	  if (prev_node == NULL) {
    	  cout << "the given previous node cannot be NULL";
    	   return;
    	    }
    		 struct Node* new_node = (struct Node*)malloc(sizeof(struct Node) );
    		  new_node->data = new_data;
    		  new_node->next = prev_node->next;
    		 prev_node->next = new_node;
    		  }
    		   // Insert at the end
    		    void insertAtEnd(struct Node** head_ref, int new_data) { 
    			struct Node* new_node = (struct Node*)malloc(sizeof(struct Node)); 
    			struct Node* last = head_ref; / used in step 5*/
    			new_node->data = new_data;
    			new_node->next = NULL;
    			if (head_ref == NULL) {
    			*head_ref = new_node;
    			 return;
    			  }
    			   while (last->next != NULL) last = last->next;
    			    last->next = new_node;
    				 return;
    				  }
    				   // Delete a node
    				    void deleteNode(struct Node* head_ref, int key) { 
    					struct Node *temp = *head_ref, *prev;
    					 if (temp != NULL && temp->data == key) {
    					  *head_ref = temp->next;
    					   free(temp);
    					    return;
    						 }
    24/10/21, 7:11 pm - ~K: Paint k ss ko word main paste kr lijiay ga
    24/10/21, 7:12 pm - Tayaba Malik Student: Teacher  w ma na save  kar liya
    24/10/21, 7:12 pm - ~K: Thk hai
    24/10/21, 7:51 pm - Tayaba Malik Student: <Media omitted>
    24/10/21, 7:51 pm - Tayaba Malik Student: is  m add kar ln g suba
    24/10/21, 7:52 pm - Tayaba Malik Student: m na bht try kia abhi tak bna rahi hu
    24/10/21, 7:52 pm - Tayaba Malik Student: h gya t kar ln g ni t suba wasi bi hard form m dni h kar ln g
    24/10/21, 7:54 pm - ~K: to abhi apki assignment ka koi solution nikla??
    24/10/21, 7:55 pm - ~K: yeh apki kisi frnd ki hai?
    24/10/21, 7:55 pm - Tayaba Malik Student: Ni teacher...
    24/10/21, 7:55 pm - Tayaba Malik Student: Ni
    24/10/21, 7:55 pm - Tayaba Malik Student: Yh sir na manual  diya h...
    24/10/21, 7:55 pm - Tayaba Malik Student: K iss tarah insertion  deletion exta hti h
    24/10/21, 7:56 pm - ~K: chalain main daikhti hn
    24/10/21, 7:56 pm - ~K: btati hn apko phir
    24/10/21, 7:57 pm - Tayaba Malik Student: Ok teacher lkin abhi ap rest kar ln.. bad kar  ln g
    24/10/21, 7:58 pm - ~K: apki is file main to sirf program ki statement hai
    24/10/21, 8:00 pm - Tayaba Malik Student: <Media omitted>
    24/10/21, 8:17 pm - ~K: tayyabba !
    24/10/21, 9:42 pm - Tayaba Malik Student: G teacher
    24/10/21, 10:50 pm - Tayaba Malik Student: Congratulations
    24/10/21, 10:51 pm - ~K: Ap b Mery khyal sy phone side per rakh k match daikh rhe the 😂
    24/10/21, 10:52 pm - Tayaba Malik Student: Ni
    24/10/21, 10:52 pm - Tayaba Malik Student: Teacher  match ni deakhti
    24/10/21, 10:52 pm - ~K: Main ny to q k kaha k apka program krty hain match k sath
    24/10/21, 10:53 pm - Tayaba Malik Student: Ni teacher  chorn ab ... rest karn
    24/10/21, 10:53 pm - Tayaba Malik Student: Phir kabhi discuss  kar ln g
    24/10/21, 10:53 pm - ~K: Apko msg Kia Tha usi k liay main ny
    24/10/21, 10:54 pm - ~K: Han g ab to Sony ka he time hai
    24/10/21, 10:54 pm - Tayaba Malik Student: G... m na late dekha
    24/10/21, 10:54 pm - Tayaba Malik Student: G
    24/10/21, 10:54 pm - Tayaba Malik Student: Good night  have sweet  dreams
    24/10/21, 10:55 pm - ~K: Ok g gud nite... Sweet dreams to u 2🌸
    25/10/21, 7:35 pm - ~K: Tayabba today I will start your class after 8 currently not feeling well
    25/10/21, 7:35 pm - Tayaba Malik Student: Okay
    25/10/21, 8:19 pm - ~K: Should we start?
    25/10/21, 8:20 pm - Tayaba Malik Student: G teacher  ok...
    25/10/21, 8:20 pm - Tayaba Malik Student: M laptop nikal lu...
    25/10/21, 8:20 pm - Tayaba Malik Student: Ik second
    25/10/21, 8:20 pm - ~K: Ok
    25/10/21, 8:21 pm - ~K: Do let me know
    25/10/21, 8:22 pm - Tayaba Malik Student: Ok
    25/10/21, 8:22 pm - Tayaba Malik Student: On h raha ...
    25/10/21, 8:25 pm - ~K: Ho gya?
    25/10/21, 8:25 pm - Tayaba Malik Student: Teacher
    25/10/21, 8:25 pm - Tayaba Malik Student: Is k sath koi issue h...
    25/10/21, 8:25 pm - Tayaba Malik Student: On h gya h... lkin screen ni aha rahi
    25/10/21, 8:25 pm - Tayaba Malik Student: Yh likha aha raha h
    25/10/21, 8:25 pm - ~K: Photo dikhay
    25/10/21, 8:26 pm - Tayaba Malik Student: <Media omitted>
    25/10/21, 8:26 pm - ~K: Isko hony dain zra
    25/10/21, 8:26 pm - Tayaba Malik Student: Ok
    25/10/21, 8:26 pm - ~K: Ho skta hai undoing kr k on kr dy yeh
    25/10/21, 8:26 pm - Tayaba Malik Student: Ok...
    25/10/21, 8:27 pm - ~K: On hota hai to phir btay mjy
    25/10/21, 8:27 pm - Tayaba Malik Student: Ok
    25/10/21, 8:31 pm - Tayaba Malik Student: Teacher on h gya h...
    25/10/21, 8:33 pm - ~K: Ok
    25/10/21, 8:38 pm - Tayaba Malik Student: <Media omitted>
    25/10/21, 8:38 pm - Tayaba Malik Student: <Media omitted>
    26/10/21, 7:26 pm - ~K: Tayabba ap Kal uni sy kitny bjy wapis ayn ge?
    26/10/21, 7:33 pm - Tayaba Malik Student: G teacher
    26/10/21, 7:33 pm - Tayaba Malik Student: At 5
    26/10/21, 7:34 pm - Tayaba Malik Student: Might  be possible  kal jaldi aha jau... jab bi ahi msg kar k ap k inform  kar du gi
    26/10/21, 7:47 pm - ~K: Chalain thk Hai... Filhal k liay hm abhi ki class start krain?
    26/10/21, 8:11 pm - Tayaba Malik Student: Teacher abhi...
    26/10/21, 8:11 pm - Tayaba Malik Student: Cancel  kar ln late h gya h
    26/10/21, 8:12 pm - ~K: ok..then kal phir hm 2 classes kr lain gy
    26/10/21, 8:12 pm - Tayaba Malik Student: Ok
    26/10/21, 8:12 pm - Tayaba Malik Student: Thanku
    26/10/21, 8:13 pm - ~K: 2 hrs...consecutive easy hoa ap k liay to consecutive classes kr lain gy...warna with some break between
    26/10/21, 8:13 pm - Tayaba Malik Student: Ok
    26/10/21, 8:13 pm - ~K: or kal phir...jaldi b start krna hoga is bt ka b dhayan rakhiay ga
    26/10/21, 8:13 pm - Tayaba Malik Student: Teacher kal t sahi  University  wala sene  h g
    26/10/21, 8:14 pm - Tayaba Malik Student: Ok
    26/10/21, 8:14 pm - ~K: hm 2 classes k beech main gap rakh lain gy...us main to issue ni hai
    26/10/21, 8:14 pm - ~K: chalain ap mjy uni sy wapiis aty he msg kijiay ga lazmi
    26/10/21, 8:14 pm - Tayaba Malik Student: Ok teacher
    26/10/21, 8:14 pm - Tayaba Malik Student: No issue
    26/10/21, 8:14 pm - Tayaba Malik Student: Ok
    27/10/21, 6:26 pm - ~K: ??
    27/10/21, 6:27 pm - Tayaba Malik Student: G teacher
    27/10/21, 6:27 pm - ~K: Ap aa gai uni sy wapis?
    27/10/21, 6:27 pm - Tayaba Malik Student: Gg
    27/10/21, 6:28 pm - Tayaba Malik Student: 5 30
    27/10/21, 6:28 pm - ~K: Mjy msg krna Tha na
    27/10/21, 6:28 pm - Tayaba Malik Student: Sorry mujy yaad ni raha btna
    27/10/21, 6:28 pm - ~K: Start krain hm class phir?
    27/10/21, 6:28 pm - Tayaba Malik Student: G
    27/10/21, 6:28 pm - ~K: Ok will text you in a while... Approx 15 min later
    27/10/21, 6:29 pm - Tayaba Malik Student: Ok
    27/10/21, 6:32 pm - ~K: I postponed what I was about to do... Ap farig ho to hm abhi start kr lain?
    27/10/21, 6:32 pm - Tayaba Malik Student: G
    27/10/21, 6:32 pm - Tayaba Malik Student: M free hu
    27/10/21, 8:41 pm - ~K: <Media omitted>
    27/10/21, 8:42 pm - Tayaba Malik Student: Ok teacher  thanku
    27/10/21, 8:43 pm - ~K: Isko smjiay ga b lazmi
    27/10/21, 8:43 pm - Tayaba Malik Student: G
    28/10/21, 7:30 pm - ~K: Should we start the class?
    28/10/21, 7:44 pm - Tayaba Malik Student: G teacher
    28/10/21, 7:45 pm - Tayaba Malik Student: Teacher at 8 plz... abhi ma presentation  d k class ki free hui
    28/10/21, 7:47 pm - ~K: Phir 9 bjy end hoge class
    28/10/21, 7:47 pm - ~K: Postponed kr daity hain phir aj ki class... Sunday ko ya on some other day ly lon ge main yeh Wali apki
    28/10/21, 7:47 pm - Tayaba Malik Student: Ok
    28/10/21, 7:47 pm - Tayaba Malik Student: Thanku
    28/10/21, 7:47 pm - Tayaba Malik Student: Sukar hai
    28/10/21, 7:48 pm - Tayaba Malik Student: Thanku so much  ✨✨✨
    28/10/21, 7:48 pm - ~K: Cancle hony per? 😅
    28/10/21, 7:48 pm - ~K: No problem... Rest krain
    28/10/21, 7:49 pm - Tayaba Malik Student: G teacher  aj ma n vaccine  lagwai hai 2nd t hath m bht dard hai  ... aur abhi presentation  di hai
    28/10/21, 7:49 pm - Tayaba Malik Student: Chat p ja k
    28/10/21, 7:49 pm - ~K: O ho... Chalain koi ni rest krain phir ap aj
    28/10/21, 7:50 pm - Tayaba Malik Student: Ok thanku
    28/10/21, 7:50 pm - Tayaba Malik Student: ✨✨✨
    29/10/21, 7:36 pm - ~K: Tyabba I won't be able take today's class, will let u know about this one too, when will I be able to take
    29/10/21, 7:47 pm - Tayaba Malik Student: Ok teacher
    29/10/21, 7:47 pm - Tayaba Malik Student: Today I am also  sleeping...
    29/10/21, 7:47 pm - Tayaba Malik Student: Ok no issue
    29/10/21, 7:49 pm - ~K: Shabash
    29/10/21, 7:50 pm - Tayaba Malik Student: G teacher
    30/10/21, 7:34 pm - ~K: Start krain aj ki class?
    30/10/21, 10:12 pm - Tayaba Malik Student: Gg teacher sorry
    30/10/21, 10:12 pm - Tayaba Malik Student: Aj m class ni la saki
    31/10/21, 8:38 am - ~K: Acha tayaba as I have already thought k min 2 classes ly lon ge main apki aj... So that jo week main miss hoi hmari uska cover ho jay... Iska mjy ap apna jaldi inform kr dain
    31/10/21, 8:46 am - Tayaba Malik Student: Ok teacher...
    31/10/21, 10:51 am - ~K: Tayabba one of ur class will be on 11
    31/10/21, 11:10 am - Tayaba Malik Student: Teacher
    31/10/21, 11:10 am - Tayaba Malik Student: Aj cancelled kar dn...
    31/10/21, 11:10 am - Tayaba Malik Student: Monday s regularly  karn g...
    31/10/21, 11:45 am - ~K: To aj phir ap ny classes ni laini? Jo miss hoi the last week
    31/10/21, 11:45 am - Tayaba Malik Student: Ni teacher
    31/10/21, 11:45 am - Tayaba Malik Student: Monday s ab...
    31/10/21, 11:46 am - ~K: To aj ap free ni the?
    31/10/21, 11:46 am - Tayaba Malik Student: Teacher abhi itnay  kam hn quiz bi hn kal
    31/10/21, 11:46 am - Tayaba Malik Student: Week end hai iss liya
    31/10/21, 11:46 am - ~K: Ok.. Chalain thk hai
    31/10/21, 11:46 am - Tayaba Malik Student: Ok teacher  thanku
    1/11/21, 7:30 pm - ~K: Han g... Aj kya mood hai tyabba? Start krain glass?
    1/11/21, 7:30 pm - ~K: Class*
    1/11/21, 7:31 pm - Tayaba Malik Student: Gg teacher
    1/11/21, 7:31 pm - ~K: Ok
    1/11/21, 7:31 pm - Tayaba Malik Student: Abhi??
    1/11/21, 7:31 pm - ~K: G to phir kab?
    1/11/21, 7:31 pm - Tayaba Malik Student: M laptop  niklau
    1/11/21, 7:31 pm - Tayaba Malik Student: Ok ...
    1/11/21, 7:32 pm - ~K: G g nikal lain aram sy
    1/11/21, 7:32 pm - Tayaba Malik Student: Ok
    2/11/21, 7:21 pm - ~K: Should we start the class?
    2/11/21, 7:21 pm - Tayaba Malik Student: Gg teacher  ik second  m laptop  nikal lu
    2/11/21, 7:22 pm - ~K: Ok
    2/11/21, 7:23 pm - ~K: Done?
    2/11/21, 7:24 pm - Tayaba Malik Student: Yes
    2/11/21, 7:24 pm - Tayaba Malik Student: Bs on h raha hai
    2/11/21, 7:24 pm - ~K: Ok let me know jb ho jay to
    2/11/21, 7:24 pm - Tayaba Malik Student: G it's done
    4/11/21, 7:17 pm - ~K: Should we start?
    4/11/21, 7:17 pm - Tayaba Malik Student: G
    4/11/21, 7:17 pm - Tayaba Malik Student: Ik minute m laptop  nikal lu
    4/11/21, 7:18 pm - ~K: G Nikal lain
    4/11/21, 7:21 pm - Tayaba Malik Student: Oky
    4/11/21, 7:21 pm - Tayaba Malik Student: M na nikal liya..
    4/11/21, 7:21 pm - Tayaba Malik Student: Abhi on h raha....
    4/11/21, 7:21 pm - ~K: On ho jay to mjy btay
    4/11/21, 7:21 pm - Tayaba Malik Student: Ok
    4/11/21, 7:24 pm - Tayaba Malik Student: Teacher on h gya hai
    5/11/21, 5:54 pm - Tayaba Malik Student: Assalam-o-Alaikum  teacher aj off h na...
    5/11/21, 7:19 pm - ~K: Mtlb.. Kahe Jana hai ap ny?
    5/11/21, 8:15 pm - Tayaba Malik Student: Ni ni teacher
    5/11/21, 8:15 pm - Tayaba Malik Student: M na sona tha...
    5/11/21, 8:15 pm - Tayaba Malik Student: Aur m so gi abhi ap k msg dekha
    6/11/21, 8:35 am - ~K: Chalain aj 2 classes lain gy phir hm
    6/11/21, 1:41 pm - Tayaba Malik Student: Gg
    6/11/21, 1:41 pm - Tayaba Malik Student: Ok
    6/11/21, 7:30 pm - ~K: Tyabba I will start your class around 8
    6/11/21, 7:30 pm - Tayaba Malik Student: Okay
    6/11/21, 7:50 pm - ~K: Should we start?
    6/11/21, 7:52 pm - Tayaba Malik Student: Gg
    6/11/21, 7:52 pm - Tayaba Malik Student: Lap top on hai aur any desk bi
    8/11/21, 7:03 pm - ~K: Should we start the class?
    8/11/21, 7:05 pm - Tayaba Malik Student: Gg
    8/11/21, 7:05 pm - Tayaba Malik Student: M laptop nikal lu  ik minute  teacher
    8/11/21, 7:11 pm - ~K: 10 min tk main krti hn apko call
    8/11/21, 7:11 pm - Tayaba Malik Student: Oky
    9/11/21, 7:29 pm - ~K: Tyabba apki aj ki class ni Hoge
    9/11/21, 7:30 pm - Tayaba Malik Student: Ok  teacher
    9/11/21, 7:30 pm - Tayaba Malik Student: Thanku
    10/11/21, 6:08 pm - ~K: Should we start the class?
    10/11/21, 6:40 pm - Tayaba Malik Student: Sorry teacher  m na msg ni dekha ...
    10/11/21, 6:43 pm - ~K: Ok
    10/11/21, 6:44 pm - ~K: Laini Hai abhi ap ny class phir?
    10/11/21, 6:44 pm - Tayaba Malik Student: Teacher jsy ap khyn
    10/11/21, 6:45 pm - Tayaba Malik Student: Teacher wasi bi monday s paper hn...
    10/11/21, 6:45 pm - ~K: Phir to definitely apki Class lon ge main
    10/11/21, 6:45 pm - ~K: Main krti hn call apko 5 10 min tk
    10/11/21, 6:46 pm - Tayaba Malik Student: Q teacher
    10/11/21, 6:46 pm - ~K: Q Kya... Class ni laini? 😂
    10/11/21, 6:46 pm - Tayaba Malik Student: Ni
    10/11/21, 6:46 pm - Tayaba Malik Student: M kha rahi l ab 20 s start karn g...
    10/11/21, 6:47 pm - ~K: 10 din bahd?
    10/11/21, 6:47 pm - Tayaba Malik Student: G
    10/11/21, 6:47 pm - ~K: Aj ap ny class ni laini phir?
    10/11/21, 6:47 pm - Tayaba Malik Student: Ni aj ni
    10/11/21, 6:47 pm - ~K: To abhi ap paper ki tyari kr rhe hain?
    10/11/21, 6:47 pm - Tayaba Malik Student: Ni
    10/11/21, 6:47 pm - Tayaba Malik Student: Abhi t m University  s ahi
    10/11/21, 6:47 pm - Tayaba Malik Student: Aj late h gya thy
    10/11/21, 6:48 pm - ~K: Ni abhi phir mjy clear kr dain... We will start onward from 20th November... Right?
    10/11/21, 6:51 pm - Tayaba Malik Student: Gg
    10/11/21, 6:54 pm - ~K: Ok
    10/11/21, 6:55 pm - Tayaba Malik Student: Thanku teacher
    10/11/21, 7:38 pm - ~K: Your welcome
    21/11/21, 12:41 pm - Tayaba Malik Student: Assalam-o-Alaikum  teacher... mery paper finish  h gya hn....ab hum regularly  Monday s start kar ln classes
    21/11/21, 5:16 pm - ~K: G thk Hai
    22/11/21, 6:56 pm - ~K: Tyabba we will start the class on 7 30
    22/11/21, 6:56 pm - Tayaba Malik Student: Okay
    22/11/21, 7:29 pm - ~K: Should we start?
    22/11/21, 7:47 pm - Tayaba Malik Student: Gg
    22/11/21, 7:53 pm - ~K: Tyabba itni jaldi? 😅
    22/11/21, 7:53 pm - ~K: Reply kia ap ny
    22/11/21, 7:53 pm - Tayaba Malik Student: Teacher  m so gai thu
    22/11/21, 7:53 pm - Tayaba Malik Student: Thi
    22/11/21, 7:53 pm - Tayaba Malik Student: Chln kal s start  karty
    22/11/21, 7:53 pm - Tayaba Malik Student: Kal m ghar hu gi...
    22/11/21, 7:54 pm - ~K: Ab chuti Maryn aj... Aj Wali class isi week main kisi din adjust kro ge main
    22/11/21, 7:54 pm - Tayaba Malik Student: Oky
    22/11/21, 7:54 pm - ~K: Morning main ghar hon ge ap?
    22/11/21, 7:54 pm - Tayaba Malik Student: Gg
    22/11/21, 7:54 pm - ~K: Thk Hai... Bs phir kal 2 classes lon ge main apki
    22/11/21, 7:55 pm - Tayaba Malik Student: Oky
    22/11/21, 7:55 pm - Tayaba Malik Student: Fine
    22/11/21, 7:55 pm - Tayaba Malik Student: Jazak Allah teacher
    22/11/21, 7:56 pm - ~K: WA iyyaki🌸
    23/11/21, 10:03 am - ~K: Tyabba hm ny last time kya kia tha?
    23/11/21, 10:07 am - Tayaba Malik Student: Functions kar rahy thy
    23/11/21, 10:08 am - ~K: Program kon sa kia tha last time?
    23/11/21, 10:08 am - Tayaba Malik Student: Teacher  yh ni yad
    23/11/21, 10:08 am - ~K: Ap jag gai hain?
    23/11/21, 10:08 am - Tayaba Malik Student: Gg bs nashta kar rahi
    23/11/21, 10:09 am - ~K: Agr uth gai hain to mjy kindly daikh kr btay... Last program kon sa kia tha hm ny
    23/11/21, 10:09 am - ~K: Chalo nashta kr k mjy btana daikh k
    23/11/21, 10:09 am - Tayaba Malik Student: Ok teacher
    23/11/21, 10:09 am - Tayaba Malik Student: Ok
    23/11/21, 11:08 am - ~K: ??
    23/11/21, 11:09 am - Tayaba Malik Student: Teacher  mera laptop  off hai on ni h raha
    23/11/21, 11:09 am - Tayaba Malik Student: Light  ni hai  shayd iss wajha s...
    23/11/21, 11:09 am - Tayaba Malik Student: M na ups s lagya hua hai
    23/11/21, 11:09 am - ~K: To abhi phir?
    23/11/21, 11:09 am - ~K: Charge ni ho rha us per wo?
    23/11/21, 11:10 am - Tayaba Malik Student: Ni
    23/11/21, 11:10 am - Tayaba Malik Student: CHARGING  light hi ni oh h rahi
    23/11/21, 11:10 am - ~K: Ok... Phir ab mjy eve main btaiay ga ap... K eve main class Laina apky liay possible hoga ya ni
    23/11/21, 11:10 am - ~K: Eve main aik he class possible hoge
    23/11/21, 11:11 am - Tayaba Malik Student: Ok
    23/11/21, 11:11 am - Tayaba Malik Student: Teacher  yh on na hua t phir
    23/11/21, 11:11 am - ~K: And isko kisi doc ko check kra do ap🤦‍♀️
    23/11/21, 11:11 am - ~K: Apny laptop ko
    23/11/21, 11:11 am - Tayaba Malik Student: Hahah  oky
    23/11/21, 11:11 am - ~K: Phir ap mjy inform kr dijiay ga
    23/11/21, 11:11 am - Tayaba Malik Student: Ok
    23/11/21, 11:12 am - ~K: Laiken msg kr daina sae yad sy khud
    23/11/21, 11:12 am - Tayaba Malik Student: Ok
    23/11/21, 11:12 am - Tayaba Malik Student: Teacher
    23/11/21, 5:19 pm - Tayaba Malik Student: Assalam-o-Alaikum  teacher  I can able to take class...
    23/11/21, 6:36 pm - ~K: Ok... Class will be started at 7
    23/11/21, 6:43 pm - Tayaba Malik Student: Oky
    23/11/21, 6:46 pm - ~K: Ap laptop on kr k mjy last program bta dain tb tk
    23/11/21, 6:47 pm - Tayaba Malik Student: Oky teacher
    23/11/21, 7:00 pm - ~K: Should we start?
    23/11/21, 7:00 pm - Tayaba Malik Student: Yes
    23/11/21, 8:13 pm - ~K: Mjy yad sy course content pf ka send krna Hai ap ny
    23/11/21, 8:14 pm - Tayaba Malik Student: Ok teacher
    24/11/21, 6:55 pm - ~K: Class will be started at 7 30
    24/11/21, 7:05 pm - Tayaba Malik Student: Oky
    24/11/21, 7:30 pm - ~K: Should we start?
    24/11/21, 7:40 pm - Tayaba Malik Student: Gg teacher  ... m khna khny chli gai thi sorry
    24/11/21, 7:43 pm - ~K: Start krain phir ab?
    24/11/21, 7:44 pm - Tayaba Malik Student: Gg
    24/11/21, 7:44 pm - Tayaba Malik Student: Lkin laptop  kha rha hai just a minute
    24/11/21, 7:44 pm - ~K: Laptop on krain or anydesk on kr k mjy btay
    24/11/21, 7:44 pm - Tayaba Malik Student: Oky
    24/11/21, 7:46 pm - Tayaba Malik Student: Teacher it's  on
    24/11/21, 7:47 pm - ~K: Ok will call you in 5 min
    24/11/21, 7:47 pm - Tayaba Malik Student: Okay
    24/11/21, 8:38 pm - Tayaba Malik Student: <Media omitted>
    24/11/21, 8:39 pm - Tayaba Malik Student: <Media omitted>
    24/11/21, 8:39 pm - Tayaba Malik Student: Dsa
    24/11/21, 8:39 pm - ~K: Thk ho gai bt
    24/11/21, 8:39 pm - Tayaba Malik Student: Suba inshallah  pf ki bj du gi
    24/11/21, 8:40 pm - ~K: G thk hai
    25/11/21, 7:21 pm - ~K: Should we start the class?
    25/11/21, 7:23 pm - Tayaba Malik Student: Teacher aj cancelle kar dn agar...
    25/11/21, 7:24 pm - Tayaba Malik Student: Kal aur Saturday  k l ln
    25/11/21, 7:24 pm - ~K: Q? Cancle q krni Hai?
    25/11/21, 7:24 pm - Tayaba Malik Student: Asi  teacher  ... koi reson  ni hai
    25/11/21, 7:25 pm - ~K: Shabash🙄
    25/11/21, 7:25 pm - Tayaba Malik Student: M n Saturday  k academy  ana t ... Saturday  k rakh ln
    25/11/21, 7:25 pm - Tayaba Malik Student: Wasi  bi teacher  hmari  week m 2 din off hn g
    25/11/21, 7:25 pm - ~K: Wo to thk hai... Per sat ko b class to online he hoge
    25/11/21, 7:25 pm - Tayaba Malik Student: Oky
    25/11/21, 7:25 pm - Tayaba Malik Student: Online  hi l ln
    25/11/21, 7:25 pm - Tayaba Malik Student: Saturday  k l ln
    25/11/21, 7:25 pm - Tayaba Malik Student: Aj off kar dn
    25/11/21, 7:26 pm - ~K: Ok then cancle ni Hoge... We will move it to some other day
    25/11/21, 7:26 pm - Tayaba Malik Student: Oky
    25/11/21, 7:26 pm - Tayaba Malik Student: Teacher  kal agar ap free hn t ksi bi time class l ln... m ghar hu gi
    25/11/21, 7:27 pm - ~K: Chalo lets see... Agr mera liay morning main possible hoa to main btao ge apko phir
    25/11/21, 7:28 pm - Tayaba Malik Student: Oky
    26/11/21, 7:04 pm - Tayaba Malik Student: Assalam-o-Alaikum  teacher  I am not able to take class today...
    26/11/21, 7:29 pm - ~K: You are not at home?
    26/11/21, 7:45 pm - Tayaba Malik Student: Gg teacher  m ghar ni hu
    26/11/21, 7:46 pm - Tayaba Malik Student: Mera dada abu k operation  tha t un k deakhny ahyn hn
    26/11/21, 7:46 pm - ~K: Ok
    27/11/21, 6:53 pm - ~K: Tyabba aj ap academy gai the?
    27/11/21, 6:55 pm - Tayaba Malik Student: Ni teacher
    27/11/21, 6:55 pm - Tayaba Malik Student: Aj  m ni aha saki
    27/11/21, 7:01 pm - ~K: O ho... Main ny to sir ko bola tha aj tyabba ay ge sir unka istakbal kijiay ga 😅
    27/11/21, 7:01 pm - ~K: Acha mjy aj ki class ka b btay
    27/11/21, 7:01 pm - Tayaba Malik Student: Haha
    27/11/21, 7:01 pm - Tayaba Malik Student: Sorry teacher  m ni aha sakhi
    27/11/21, 7:02 pm - Tayaba Malik Student: Gg teacher  
    Ap btyn
    27/11/21, 7:02 pm - ~K: Ghar hain na ap?
    27/11/21, 7:02 pm - Tayaba Malik Student: Gg
    27/11/21, 7:02 pm - Tayaba Malik Student: Ghar hu
    27/11/21, 7:02 pm - ~K: Mtlb available hain?
    27/11/21, 7:02 pm - Tayaba Malik Student: Gg
    27/11/21, 7:02 pm - ~K: Bs thk hai... Phir Shuro krty hain. Main laptop on kr k call krti hn apko
    27/11/21, 7:02 pm - Tayaba Malik Student: Ok
    27/11/21, 7:02 pm - Tayaba Malik Student: M b laptop on karti
    27/11/21, 7:03 pm - ~K: Ok kr lai ap b
    27/11/21, 7:03 pm - ~K: On*
    27/11/21, 7:08 pm - ~K: ?
    27/11/21, 7:18 pm - Tayaba Malik Student: <Media omitted>
    27/11/21, 7:19 pm - Tayaba Malik Student: <Media omitted>
    28/11/21, 1:45 pm - Tayaba Malik Student: <Media omitted>
    28/11/21, 1:45 pm - Tayaba Malik Student: Teacher project  aha gya
    28/11/21, 1:46 pm - Tayaba Malik Student: Airport management system topic hai
    28/11/21, 2:24 pm - ~K: Due kab hai?
    28/11/21, 2:25 pm - Tayaba Malik Student: <Media omitted>
    28/11/21, 2:26 pm - ~K: Mtlb we have a month to complete?
    28/11/21, 2:26 pm - Tayaba Malik Student: Yes
    28/11/21, 2:27 pm - ~K: Chalo phir to thk ho gya... Zyada time mill jay ga to main apko zyada achy sy smjha don ge
    28/11/21, 2:28 pm - ~K: Or bnana c++ main he hai na?
    28/11/21, 2:30 pm - Tayaba Malik Student: G teacher  baki suba sir guide karn  g k kia karna hai ksy karna hai
    28/11/21, 2:30 pm - Tayaba Malik Student: Gg c++
    28/11/21, 2:30 pm - ~K: Wo info phir ap achy sy sari likh laina
    28/11/21, 2:30 pm - Tayaba Malik Student: Oky
    28/11/21, 2:31 pm - ~K: Ta k jo jo apky sir chah rhy hain k project main ho hm sy miss na ho kuch b
    28/11/21, 2:31 pm - Tayaba Malik Student: G theek hai
    28/11/21, 6:29 pm - ~K: <Media omitted>
    28/11/21, 7:03 pm - Tayaba Malik Student: Oky  teacher
    29/11/21, 7:01 pm - ~K: Should we start the class?
    29/11/21, 7:02 pm - Tayaba Malik Student: Yes  teacher  in 5 minutes
    29/11/21, 7:02 pm - Tayaba Malik Student: M laptop nikal lu
    29/11/21, 7:02 pm - ~K: Ok
    29/11/21, 7:02 pm - ~K: Btay mjy on kr k
    29/11/21, 7:06 pm - Tayaba Malik Student: Teacher  it's done
    29/11/21, 7:53 pm - Tayaba Malik Student: Teacher
    29/11/21, 7:53 pm - ~K: Ap ny end ki hai call?
    29/11/21, 7:54 pm - Tayaba Malik Student: Ni
    29/11/21, 7:55 pm - ~K: Pick ni ki ap ny call
    30/11/21, 7:08 pm - ~K: Start krain class?
    30/11/21, 7:12 pm - Tayaba Malik Student: Gg teacher
    30/11/21, 7:12 pm - Tayaba Malik Student: M laptop nikal lu
    30/11/21, 7:12 pm - ~K: Ok nikal k btay
    30/11/21, 7:16 pm - ~K: Ho gya?
    30/11/21, 7:16 pm - Tayaba Malik Student: Ni teacher
    30/11/21, 7:16 pm - Tayaba Malik Student: Update h raha
    30/11/21, 7:16 pm - ~K: Chalo g🤦‍♀️
    30/11/21, 7:17 pm - Tayaba Malik Student: H gya hai
    30/11/21, 7:17 pm - ~K: Ho gya on?
    30/11/21, 7:17 pm - Tayaba Malik Student: Gg
    30/11/21, 7:17 pm - ~K: Ok
    30/11/21, 7:29 pm - Tayaba Malik Student: <Media omitted>
    30/11/21, 7:44 pm - Tayaba Malik Student: Missed voice call
    1/12/21, 9:32 am - ~K: Yeh Jo tyabba ap ny mjy send kia tha... Yeh report hai?
    1/12/21, 9:36 am - Tayaba Malik Student: Teacher yh zip file hai iss m oops k project hai us k code  report and presentation
    1/12/21, 9:40 am - ~K: G thk Hai wo unzip kr k main ny daikh Lia hai
    1/12/21, 9:40 am - ~K: Acha jo main ny puchny k liay kaha tha apko... Wo puch lia sir sy ap ny abhi ya ni?
    1/12/21, 9:43 am - Tayaba Malik Student: Teacher  abhi lab l rahy free h k puchti
    1/12/21, 9:44 am - ~K: Puch k mjy idhar he phir bta dijiay ga
    1/12/21, 9:45 am - Tayaba Malik Student: Oky
    1/12/21, 7:11 pm - ~K: Should we start the class?
    2/12/21, 6:53 pm - Tayaba Malik Student: Assalam-o-Alaikum teacher  aj class thora late kar ln... m apny baba g s milny ahi hu
    2/12/21, 6:54 pm - ~K: Kitna late?
    2/12/21, 6:54 pm - ~K: W. Aslam
    2/12/21, 8:02 pm - Tayaba Malik Student: Teacher   can  we take class now
    2/12/21, 8:22 pm - ~K: Ni tyabba abhi to ni possible
    2/12/21, 8:23 pm - Tayaba Malik Student: Oky teacher
    3/12/21, 7:25 pm - ~K: Should we start?
    3/12/21, 7:28 pm - Tayaba Malik Student: Yes teacher
    3/12/21, 7:29 pm - Tayaba Malik Student: In 5 minutes  m laptop nikal lu
    3/12/21, 7:29 pm - ~K: Ok
    3/12/21, 7:31 pm - Tayaba Malik Student: Yes teacher  now we can
    4/12/21, 6:57 pm - ~K: Should we start the class?
    4/12/21, 6:58 pm - Tayaba Malik Student: G in  5 minutes  m laptop on kR lu
    4/12/21, 6:58 pm - ~K: Ok
    4/12/21, 7:03 pm - ~K: Done?
    4/12/21, 7:03 pm - Tayaba Malik Student: Yes teacher we can
    6/12/21, 6:50 pm - ~K: Should we start the class?
    6/12/21, 6:55 pm - Tayaba Malik Student: Yes teacher  in 5 minutes... laptop on kar lu
    6/12/21, 6:56 pm - ~K: Ok
    6/12/21, 7:00 pm - Tayaba Malik Student: Yes teacher
    7/12/21, 7:00 pm - Tayaba Malik Student: Assalam-o-Alaikum teacher I can't able to take class ...
    7/12/21, 7:30 pm - ~K: W. Aslam
    7/12/21, 7:30 pm - ~K: Ok
    8/12/21, 9:59 am - ~K: Tayabba aj ap ny uni sy kitny bjy wapis aa Jana hai?
    8/12/21, 10:18 am - Tayaba Malik Student: AJ  3 30 Free hu gi aur atty  atty  late h jau gi
    8/12/21, 10:23 am - ~K: Ap to jaldi any ka ni bta rhe the aj ka?
    8/12/21, 10:23 am - Tayaba Malik Student: Make up classes  hn
    8/12/21, 10:46 am - Tayaba Malik Student: Teacher arranged classes hn
    8/12/21, 11:40 am - ~K: Main ny socha tha aj ap aa jati academy... Per chaly ab isi week Saturday ka kr lain gy
    8/12/21, 11:54 am - Tayaba Malik Student: Ok
    8/12/21, 7:26 pm - Tayaba Malik Student: Teacher  aj yh join  karu
    9/12/21, 7:32 pm - ~K: Tyabba join kia ap ny?
    9/12/21, 7:34 pm - Tayaba Malik Student: Kia teacher
    9/12/21, 7:35 pm - ~K: Apko text kia hai main ny sim per
    9/12/21, 7:35 pm - Tayaba Malik Student: Teacher  yh msg abhi  ma na parha
    9/12/21, 7:35 pm - Tayaba Malik Student: Teacher aj chorn class  k wasi bi bht late h gi
    9/12/21, 7:36 pm - ~K: Kya Late? 🙄
    9/12/21, 7:36 pm - ~K: Larki 6 min late hoay hain sirf... Wo b apko msg main ny pehly ka kia hoa tha
    9/12/21, 7:36 pm - Tayaba Malik Student: Gg ... teacher
    9/12/21, 7:37 pm - Tayaba Malik Student: M na abhi parha... iss liya... chorn ab start  karn g t end kab h gi...
    9/12/21, 7:37 pm - Tayaba Malik Student: Kal l ln
    9/12/21, 7:37 pm - ~K: Kya he Kahy banda ab apko
    9/12/21, 7:37 pm - Tayaba Malik Student: Haha
    9/12/21, 7:38 pm - Tayaba Malik Student: Teacher ap khyn kitni  achi student  hai
    9/12/21, 7:38 pm - ~K: G g aisi waisi.... Bs Mery sy puchy koi apki achai ka
    9/12/21, 7:39 pm - Tayaba Malik Student: Haha
    9/12/21, 7:39 pm - Tayaba Malik Student: Teacher  🥺
    9/12/21, 7:39 pm - ~K: Chalain g... Aish krain. Kya yad kryn ge kis sakhi teacher sy pala para tha 😂
    9/12/21, 7:39 pm - ~K: Chuti marain phir
    9/12/21, 7:40 pm - Tayaba Malik Student: Okok
    9/12/21, 7:40 pm - Tayaba Malik Student: U r the best
    9/12/21, 7:40 pm - ~K: Han masky marwa lo bs
    9/12/21, 7:40 pm - ~K: Acha meri bt suno... Sat ki ghar main bt kr li hai na ap ny?
    9/12/21, 7:40 pm - Tayaba Malik Student: No maska
    9/12/21, 7:41 pm - Tayaba Malik Student: Btya hai.... k ma na jna hai
    9/12/21, 7:41 pm - Tayaba Malik Student: Kal puchu gi... ksy jau gi
    9/12/21, 7:41 pm - ~K: Q k sat ko lazmi ana hai... Or samjhana hai main ny apko plus working b dikhani hai
    9/12/21, 7:41 pm - ~K: G lazmiiii
    9/12/21, 7:41 pm - Tayaba Malik Student: Okok
    9/12/21, 7:42 pm - Tayaba Malik Student: INSHALLAH
    10/12/21, 7:22 pm - ~K: Should we start?
    10/12/21, 7:26 pm - Tayaba Malik Student: Yes in 5 minutes
    10/12/21, 7:26 pm - Tayaba Malik Student: Laptop on kar lu
    10/12/21, 7:27 pm - ~K: G g kr lain
    10/12/21, 7:30 pm - ~K: On kr k btay
    10/12/21, 7:32 pm - Tayaba Malik Student: H gya
    10/12/21, 7:33 pm - ~K: Meri awaz aa rhe hai apko?
    10/12/21, 7:33 pm - ~K: Yeh btay
    10/12/21, 7:34 pm - Tayaba Malik Student: G ap ki aha rahi meri aha rahi hai
    10/12/21, 7:34 pm - Tayaba Malik Student: Kab s hello hello kha rahi
    10/12/21, 7:34 pm - ~K: Ni apki awaz ni aa rhe mjy
    10/12/21, 7:34 pm - Tayaba Malik Student: Oky
    10/12/21, 7:35 pm - Tayaba Malik Student: Sab normal hai
    10/12/21, 7:35 pm - Tayaba Malik Student: Setting  ok
    10/12/21, 7:35 pm - Tayaba Malik Student: Full  hai
    10/12/21, 7:36 pm - Tayaba Malik Student: Ok
    10/12/21, 7:37 pm - ~K: Kia hai join?
    10/12/21, 7:38 pm - Tayaba Malik Student: G
    10/12/21, 7:38 pm - ~K: Koi or wo ni join kr lia
    10/12/21, 7:38 pm - ~K: Q us Waly meet k link main to ni ai abhi ap
    10/12/21, 7:38 pm - Tayaba Malik Student: W hi kia hai
    10/12/21, 7:38 pm - Tayaba Malik Student: Ap mujy in karn
    10/12/21, 7:46 pm - ~K: Join krain dobara
    10/12/21, 8:00 pm - Tayaba Malik Student: Teacher  Internet  connection  lost
    10/12/21, 8:06 pm - ~K: Apka net b sae time per khrab hoa hai
    10/12/21, 8:06 pm - Tayaba Malik Student: Gg teacher  pta  ni kia  hua hai
    10/12/21, 8:06 pm - ~K: Us program ko daikha hai phir? K band kr dia
    10/12/21, 8:07 pm - Tayaba Malik Student: Deakha hai
    10/12/21, 8:07 pm - Tayaba Malik Student: Samj t aha gi hai ...
    10/12/21, 8:07 pm - ~K: Sara smj aa gya?
    10/12/21, 8:07 pm - Tayaba Malik Student: Lakin ap  questions  kartik  t shad  zyda evaluation  hti
    10/12/21, 8:07 pm - Tayaba Malik Student: G lag t asa hi raha hai
    10/12/21, 8:08 pm - ~K: Abhi ap chahy to hm class ly laity hain
    10/12/21, 8:08 pm - ~K: Us program ko zabani likhain
    10/12/21, 8:09 pm - Tayaba Malik Student: Ni ab ni lani... kal academy  m theek hai
    10/12/21, 8:09 pm - Tayaba Malik Student: Lakin kasy
    10/12/21, 8:09 pm - Tayaba Malik Student: Yhn
    10/12/21, 8:09 pm - ~K: Zubani likhain us program ko phir khud abhi ap
    10/12/21, 8:10 pm - Tayaba Malik Student: Ok
    11/12/21, 1:40 pm - ~K: Tyabba I will reach academy by around 2 15... Ap b usi hisab sy ghar sy nikaliay ga
    11/12/21, 1:42 pm - Tayaba Malik Student: Ok teacher  I am also around  2 20
    11/12/21, 6:56 pm - ~K: Tyabba ap apna laptop dy ai hain?
    11/12/21, 7:14 pm - Tayaba Malik Student: G teacher  dy ahi
    11/12/21, 7:15 pm - ~K: Kya keh rhy hain kab tk mill jay ga?
    11/12/21, 7:15 pm - Tayaba Malik Student: Yh ni pta... shad w yh wapsi kara k koi aur  lyn....
    11/12/21, 7:16 pm - Tayaba Malik Student: Iss ki battery  bi kharab hai
    11/12/21, 7:16 pm - Tayaba Malik Student: 10000 hard  disk k lagy g
    11/12/21, 7:17 pm - Tayaba Malik Student: Aur  5 6 battery  j
    11/12/21, 7:17 pm - Tayaba Malik Student: K
    11/12/21, 7:17 pm - Tayaba Malik Student: T w kha rahy thy  k asa karty yh l k jty hn aur l aty hn isss ... itny pasy  dal k
    11/12/21, 7:17 pm - Tayaba Malik Student: Naya
    11/12/21, 7:18 pm - ~K: 10k q? Ap ny kitny size ki dalny k liay kaha hai?
    11/12/21, 7:18 pm - Tayaba Malik Student: 500
    11/12/21, 7:18 pm - Tayaba Malik Student: Yh 400 j dal dn
    11/12/21, 7:18 pm - ~K: To ab phir new apka kab tk aa jay ga?
    11/12/21, 7:18 pm - Tayaba Malik Student: Yh ni pta
    11/12/21, 7:19 pm - Tayaba Malik Student: Kha hai jaldi  la dn
    11/12/21, 7:19 pm - Tayaba Malik Student: 2 din m
    11/12/21, 7:20 pm - ~K: Pindi sy lo ge?
    11/12/21, 7:20 pm - Tayaba Malik Student: Gg
    11/12/21, 7:21 pm - ~K: Mushkil hai phir to... K 2 din tk aa jay
    11/12/21, 7:22 pm - ~K: Chalo per jb aya to phir btana mjy... Hm phir start krain gy dobara classes
    11/12/21, 7:22 pm - Tayaba Malik Student: gari hamri jya gi... deakhn  ab
    11/12/21, 7:22 pm - Tayaba Malik Student: Oky
    11/12/21, 7:23 pm - ~K: Acha or mjy yeh btay... Apko jo working main ny project ki dikhai the... Wo yad Hai apko... K Kya kya tha?
    11/12/21, 7:23 pm - Tayaba Malik Student: Gg
    11/12/21, 7:23 pm - Tayaba Malik Student: Admin aur user  k functions perform  kiya thy
    11/12/21, 7:24 pm - ~K: Admin ki side per kya kya tha... Or user ki side per kya kya wo yad Hai apko?
    11/12/21, 7:24 pm - Tayaba Malik Student: G
    11/12/21, 7:25 pm - ~K: <Media omitted>
    11/12/21, 7:27 pm - Tayaba Malik Student: Oky
    12/12/21, 4:22 pm - ~K: <Media omitted>
    12/12/21, 4:27 pm - ~K: <Media omitted>
    12/12/21, 4:27 pm - ~K: <Media omitted>
    12/12/21, 4:31 pm - ~K: <Media omitted>
    12/12/21, 5:08 pm - Tayaba Malik Student: Waslam  ok teacher  mujy  samj aha gi...
    12/12/21, 5:29 pm - ~K: By Monday... Mjy yeh sari cheezain btani hai ap ny... Apny sir sy puch k
    12/12/21, 5:29 pm - Tayaba Malik Student: Oky
    13/12/21, 6:26 pm - ~K: Tyabba apka laptop aa gya?
    13/12/21, 6:33 pm - Tayaba Malik Student: Ni
    13/12/21, 6:35 pm - ~K: Pta kia ap ny? K kab tk ay ga
    13/12/21, 6:39 pm - Tayaba Malik Student: Teacher pta ni kab aya h
    13/12/21, 6:39 pm - Tayaba Malik Student: G*
    13/12/21, 6:39 pm - Tayaba Malik Student: M kal kuch karti .... aj m khud late h gi... bht
    13/12/21, 6:41 pm - ~K: G koshish krain jaldi laptop ay apka... Q k tb he continue kr skty hain hm u know
    13/12/21, 6:42 pm - ~K: Or mjy yeh btay ap ny apny sir sy pta kia tha?
    13/12/21, 6:42 pm - Tayaba Malik Student: G
    13/12/21, 6:43 pm - Tayaba Malik Student: Teacher  un n kha k ik data structure  use kar sakty aut us k sary function jsy link list ki insertion  deletions  transversiom
    13/12/21, 6:43 pm - Tayaba Malik Student: Aur array use karny hn must
    13/12/21, 6:46 pm - ~K: Ap ny apny project ka Sara kuch jaisy main ny apko audio main btaya tha... Waisy btaya tha unhain?
    13/12/21, 6:46 pm - Tayaba Malik Student: G wasa hi btya
    13/12/21, 6:47 pm - ~K: Yeh pucha k insertion deletion sir jo ap ny kray hain wo hm apny project main kahan use krain?
    13/12/21, 6:49 pm - ~K: Ap free hain to mjy btay main call krti hn apko
    13/12/21, 7:08 pm - Tayaba Malik Student: Ok
    13/12/21, 7:08 pm - Tayaba Malik Student: Yes teacher  u can call
    13/12/21, 7:08 pm - Tayaba Malik Student: I am free
    13/12/21, 7:40 pm - ~K: Or dosra task... Mjy singly link list sy related Sara kuch send krain... Jo b apko sir ny kraya hai
    13/12/21, 7:40 pm - Tayaba Malik Student: Ok
    13/12/21, 7:41 pm - Tayaba Malik Student: <Media omitted>
    13/12/21, 7:43 pm - Tayaba Malik Student: <Media omitted>
    13/12/21, 7:44 pm - Tayaba Malik Student: <Media omitted>
    13/12/21, 7:45 pm - Tayaba Malik Student: <Media omitted>
    13/12/21, 7:45 pm - Tayaba Malik Student: <Media omitted>
    13/12/21, 7:52 pm - Tayaba Malik Student: Kal hard disk change kary g
    13/12/21, 7:52 pm - Tayaba Malik Student: Nya ni lty
    13/12/21, 7:52 pm - ~K: Battery or hard disk ka kam kr k kal tk dy dy ga laptop wo?
    13/12/21, 7:52 pm - Tayaba Malik Student: Gg
    13/12/21, 7:53 pm - ~K: Chalo acha ho gya 👍
    13/12/21, 7:53 pm - Tayaba Malik Student: Yes
    13/12/21, 7:53 pm - Tayaba Malik Student: Inshallah  bhta Acha karn g
    13/12/21, 7:53 pm - ~K: <Media omitted>
    13/12/21, 7:54 pm - Tayaba Malik Student: Dta k kha diya
    13/12/21, 7:54 pm - ~K: Mehnat ki hm ny to result Acha he hoga in shaa Allah
    13/12/21, 7:54 pm - Tayaba Malik Student: Inshallah
    13/12/21, 7:54 pm - ~K: Data transfer kr k ka tk dy ga?
    13/12/21, 7:54 pm - Tayaba Malik Student: G
    13/12/21, 7:54 pm - ~K: Kal*
    13/12/21, 7:54 pm - ~K: Bs sae ho gya phir
    13/12/21, 7:54 pm - Tayaba Malik Student: Kal kary g sahi
    13/12/21, 7:54 pm - Tayaba Malik Student: 2 din m d g
    13/12/21, 7:55 pm - ~K: Ni ... 2 din mtlb... Thursday ko?
    13/12/21, 7:55 pm - Tayaba Malik Student: G
    13/12/21, 7:55 pm - Tayaba Malik Student: Kal s sahi kary g
    13/12/21, 7:55 pm - ~K: Acha Acha.. Mjy laga kal... Return kr dy ga sae kr k
    13/12/21, 7:55 pm - ~K: Per chalain thk Hai aisy b
    13/12/21, 7:56 pm - Tayaba Malik Student: Ok
    16/12/21, 9:56 am - ~K: Tyabba jb apka laptop thk ho k aa gya to mjy btaiay ga.. Agr aj aa gya to b inform kr daina mjy
    16/12/21, 10:45 am - Tayaba Malik Student: Oky
    17/12/21, 5:55 pm - ~K: Apka laptop ni ya tyyaba abhi tk?
    17/12/21, 5:55 pm - ~K: Aya*
    17/12/21, 6:43 pm - Tayaba Malik Student: Ni teacher  ni aya
    17/12/21, 6:43 pm - Tayaba Malik Student: Kal j k pta  karu gi
    17/12/21, 6:44 pm - ~K: 17 ho gai hai aj
    17/12/21, 6:44 pm - Tayaba Malik Student: G teacher
    17/12/21, 6:44 pm - ~K: Or link list ko add kr k main bta rhe hn apka program Acha khasa mushkil ho gya Hai already
    17/12/21, 6:44 pm - Tayaba Malik Student: M n ghalti ki hai d k m na presentation  bni thi
    17/12/21, 6:45 pm - Tayaba Malik Student: Itni muskil  hui mujy
    17/12/21, 6:45 pm - Tayaba Malik Student: Project  h gya hai
    17/12/21, 6:45 pm - ~K: Jo b hai us bandy sy pta krain.. Bal k abhi pta krwao phone kr k kisi sy
    17/12/21, 6:45 pm - Tayaba Malik Student: W Monday  k check karna hai  l k ja k
    17/12/21, 6:45 pm - ~K: Ni abhi uski implementation complete ni hoi...chal rha hai abhi
    17/12/21, 6:45 pm - Tayaba Malik Student: Phone  karwa tha kha raha tha ni hua abhi
    17/12/21, 6:46 pm - Tayaba Malik Student: Ab suba j k pta karu gi
    17/12/21, 6:46 pm - ~K: Usko bolo jaldi kry
    17/12/21, 6:46 pm - Tayaba Malik Student: Ok
    17/12/21, 6:46 pm - Tayaba Malik Student: G
    17/12/21, 6:46 pm - ~K: Acha aik or cheez b yad ai mjy puchni
    17/12/21, 6:46 pm - Tayaba Malik Student: Wasi Monday  k project  l k jna hai  jitna hua hai sir na kha k office  m aha k check  karya har group
    17/12/21, 6:47 pm - Tayaba Malik Student: Kal m academy  ahu gi passy dny project  k sir k
    17/12/21, 6:47 pm - Tayaba Malik Student: T ap s milu gi
    17/12/21, 6:47 pm - Tayaba Malik Student: Gg
    17/12/21, 6:47 pm - ~K: Kal ap kis time ay ge?
    17/12/21, 6:47 pm - Tayaba Malik Student: 4 tak
    17/12/21, 6:48 pm - ~K: Ap ny December ki sir ko fees di the? Sir mj sy puch rhy thy to main ny kaha to ni pta k di Hai ya ni
    17/12/21, 6:48 pm - Tayaba Malik Student: Ni
    17/12/21, 6:48 pm - ~K: Or sir ko b bhoola hoa Tha... K ap ny di Hai ya ni
    17/12/21, 6:48 pm - Tayaba Malik Student: W bi ni  di
    17/12/21, 6:48 pm - ~K: Shabash
    17/12/21, 6:48 pm - Tayaba Malik Student: Last time lahi thi sir thy hi ni
    17/12/21, 6:49 pm - ~K: Chalo phir yeh b dy daina kal yad sy
    17/12/21, 6:49 pm - Tayaba Malik Student: Gg
    17/12/21, 6:49 pm - ~K: Q k abhi unko aisa lag rha Hai... K ap ny dy di Hai or unko yad ni
    17/12/21, 6:49 pm - Tayaba Malik Student: Jal yh project  fee aur  laptop  k kam  clear karti
    17/12/21, 6:49 pm - ~K: Or kal... Laptop hona chahiye Tayyaba apky pas.. Lazmi
    17/12/21, 6:49 pm - Tayaba Malik Student: Ni m na ni di
    17/12/21, 6:50 pm - Tayaba Malik Student: Ok
    17/12/21, 6:50 pm - ~K: Mazeed late na ho... Warna end time main wakhta parh skta hai hmain
    17/12/21, 6:50 pm - ~K: Chalo kal Laina sir sy Sara hisab clear
    17/12/21, 6:50 pm - ~K: Or call kr Laina... Any sy pehly sir ko
    17/12/21, 6:50 pm - Tayaba Malik Student: G
    17/12/21, 6:50 pm - Tayaba Malik Student: Oky
    19/12/21, 11:22 am - ~K: Assalam u alaikum!! 
    Tyabba apky sir ny apko is sy related kya bola tha... K jo b data structure use krain gy usky sary functions use krny hain??
    19/12/21, 11:23 am - ~K: Aisa kuch bola tha unho ny?
    19/12/21, 11:23 am - Tayaba Malik Student: Waslam
    19/12/21, 11:23 am - Tayaba Malik Student: Gg asa hi kha tha
    19/12/21, 11:24 am - ~K: Apki link list ny Bara khapaya hoa hai waisy
    19/12/21, 11:24 am - Tayaba Malik Student: Haha
    19/12/21, 11:24 am - Tayaba Malik Student: Yh hai hi asi
    19/12/21, 11:24 am - ~K: <Media omitted>
    19/12/21, 12:00 pm - Tayaba Malik Student: Teacher  Monday  k ati phir discuss  karty isss k
    20/12/21, 6:55 pm - ~K: Tayyaba ly ai ap laptop?
    20/12/21, 7:11 pm - ~K: ??
    Btayn ta k main phir apko btaon aj ka
    20/12/21, 7:36 pm - Tayaba Malik Student: Sorry  teacher
    20/12/21, 7:36 pm - Tayaba Malik Student: Ni aya
    20/12/21, 7:36 pm - ~K: To phir ab?
    20/12/21, 7:37 pm - Tayaba Malik Student: W kha rahy  k ik din bs ...
    20/12/21, 7:38 pm - ~K: To abhi main project apko send kr Don... To apko agr samjhaya ni main ny thora bht... To apky sir ko sedha shak hoga
    20/12/21, 7:38 pm - ~K: K ap ny ni bnaya. Or laptop k bagair abhi kaisy smjao ge main apko
    20/12/21, 7:39 pm - Tayaba Malik Student: Teacher ap mujy sirf w admin wala bj dn ... aur kuch thora s voice  m bta dn...
    20/12/21, 7:42 pm - ~K: Ok... Or mjy btay... K abhi apko link list ki implementation k sath wala chahiay ya pehly wala?
    20/12/21, 7:43 pm - Tayaba Malik Student: Ni link list wala ni bjhn  abhi  us k mujy kuch pta  ni hai...
    20/12/21, 7:44 pm - Tayaba Malik Student: Bs admin user wala bj dn... us  k m kuch  kar lu gi
    20/12/21, 7:44 pm - ~K: Ok
    20/12/21, 7:44 pm - ~K: Or... Iski payment ka mamla apka sir k sath ho gya Hai na? Bcz mjy ni pta main apko source file send kron ge abhi q k sir sy puchy bagair... To phir issue na bany
    20/12/21, 7:45 pm - Tayaba Malik Student: Us ki output  wasi  hai... jsi  ap na mujy dekahi  thi....
    20/12/21, 7:45 pm - ~K: Or dosra yeh apky uni k sir... Isky number to ni lgay gy na? Abhi jo ap log check kray gy... Iski marking i mean hoge?
    20/12/21, 7:45 pm - ~K: G
    20/12/21, 7:46 pm - Tayaba Malik Student: Ni m na sir k kha hai aj k project  bny g t madam  s m samjny  k liya ahu gi ... t payment  kar du gi us  ki...
    20/12/21, 7:46 pm - Tayaba Malik Student: Ni marking  ni hai  w bs deakhn  g k kam h raha k no kitna  hua... just this...
    20/12/21, 7:47 pm - ~K: Phir abhi source file... Soch main dal dia hai ap ny mjy... K ab send kron main ya sir sy puch k send kron
    20/12/21, 7:47 pm - Tayaba Malik Student: Aur yh bi iss liya kha k aj hamra  off  aha gya ...
    20/12/21, 7:48 pm - Tayaba Malik Student: Ap sir s puch ln...  wsi khud b
    20/12/21, 7:48 pm - ~K: Msg main ny Kia hoa hai... Per online ni hain abhi
    20/12/21, 7:48 pm - Tayaba Malik Student: Ok ap un s puch ln...
    20/12/21, 7:49 pm - ~K: Wo late jwb dain gy shayd... Phir us time late ho jay ga... Main apko send kr daiti hn phir abhi
    20/12/21, 7:50 pm - Tayaba Malik Student: Ok...
    20/12/21, 7:50 pm - ~K: Bahd main phir unko yeh inform kr don ge main
    20/12/21, 7:50 pm - Tayaba Malik Student: M phir  kal yh Wednesday  k sir k project  ki payment  b bjwa du gi
    20/12/21, 7:50 pm - ~K: Or aik or cheez jo mjy puchni the... Ap Kal sir ko... Code dikhay ge ya sirf output?
    20/12/21, 7:50 pm - Tayaba Malik Student: Sirf output
    20/12/21, 7:51 pm - Tayaba Malik Student: Output  check  karsni bs
    20/12/21, 7:51 pm - Tayaba Malik Student: Karani *
    20/12/21, 7:51 pm - ~K: Or agr apky sir ny... Code sy pucha kuch to phir?
    20/12/21, 7:53 pm - ~K: Ap apni email id send krain mjy
    20/12/21, 7:52 pm - Tayaba Malik Student: W phir  classes  aur file wla j karwa  tha ap na us k m kar lu gi
    20/12/21, 7:56 pm - Tayaba Malik Student: Oky
    20/12/21, 7:56 pm - Tayaba Malik Student: 20-SE-061@student.hitecuni.edu.pk
    20/12/21, 7:56 pm - Tayaba Malik Student: Tayyabamalik70000@gmail.com
    20/12/21, 7:57 pm - ~K: Ok
    20/12/21, 8:03 pm - ~K: <Media omitted>
    20/12/21, 8:04 pm - Tayaba Malik Student: Teacher  yh open  kis m h g
    20/12/21, 8:05 pm - ~K: Unzip krain ge isko
    20/12/21, 8:05 pm - Tayaba Malik Student: G phir
    20/12/21, 8:05 pm - Tayaba Malik Student: Teacher  w admin  I'd  aur password
    20/12/21, 8:06 pm - ~K: Admin email : admin1234@pakAviation.com
    Admin pass: 1234
    20/12/21, 8:07 pm - ~K: Iski output ap... Kisi frnd k laptop main dikhay ge phir?
    20/12/21, 8:07 pm - Tayaba Malik Student: Teacher kai dusry  group  walon  k ni deakhna  hta...
    20/12/21, 8:07 pm - Tayaba Malik Student: Ni t sir phir  consider  ni karty project
    20/12/21, 8:08 pm - ~K: Ap aik krain... Call per ayn zra... Iska main Thora bht btati hn apko
    20/12/21, 8:08 pm - Tayaba Malik Student: Gg
    20/12/21, 8:29 pm - ~K: <Media omitted>
    20/12/21, 8:36 pm - Tayaba Malik Student: Teacher  download  h rahi
    20/12/21, 8:40 pm - ~K: <Media omitted>
    20/12/21, 8:41 pm - ~K: <Media omitted>
    20/12/21, 8:41 pm - ~K: Ok
    20/12/21, 8:42 pm - Tayaba Malik Student: Teacher  yh m n deakh  liya  yh samj aha gi
    20/12/21, 8:42 pm - Tayaba Malik Student: Teacher  tysm
    20/12/21, 8:42 pm - ~K: Baki b aa rhe hain
    20/12/21, 8:43 pm - ~K: Wo b daikh k btay phir
    20/12/21, 8:43 pm - Tayaba Malik Student: Gg
    20/12/21, 8:43 pm - ~K: Am just trying in every possible way k apka achy sy ho jay bs
    20/12/21, 8:44 pm - Tayaba Malik Student: Allah  kary bs yh h jya
    20/12/21, 8:45 pm - ~K: Pehli video sy onward admin side is main hai
    20/12/21, 8:45 pm - Tayaba Malik Student: Ok yh open h rahi
    20/12/21, 8:46 pm - ~K: Apki frnd sy hoa rabta apka?
    20/12/21, 8:47 pm - Tayaba Malik Student: G techer  msg kia hua
    20/12/21, 8:47 pm - Tayaba Malik Student: Abhi call kar rahi
    20/12/21, 8:49 pm - Tayaba Malik Student: Ni utha rahi
    20/12/21, 8:49 pm - ~K: Apki saheli b ap sy do hath agy hai
    20/12/21, 8:50 pm - ~K: Yeh user side
    20/12/21, 8:50 pm - Tayaba Malik Student: Teacher  ni utha rahi abhi b kar rahi
    20/12/21, 8:51 pm - Tayaba Malik Student: Yh b ok hai
    20/12/21, 8:51 pm - ~K: <Media omitted>
    20/12/21, 8:51 pm - ~K: Aa gai smj?
    20/12/21, 8:52 pm - Tayaba Malik Student: G aha gi
    20/12/21, 8:52 pm - ~K: Ok chor do... Abhi main jag rhe hn 11 tk... Wo bahd main reply krti Hai to ap tb bta daina mjy... Guide kr Don ge main apko
    20/12/21, 8:53 pm - Tayaba Malik Student: Ok teacher lakin ap rest karn  ab...
    20/12/21, 8:54 pm - Tayaba Malik Student: Suba m khud open   kar lu gi... us k  laptop  m  phir  ap s puch lu gi
    20/12/21, 8:54 pm - ~K: Yeh remaining user side
    20/12/21, 8:55 pm - ~K: Chalain thk hai
    20/12/21, 8:55 pm - Tayaba Malik Student: G deakh  rahi
    20/12/21, 8:55 pm - Tayaba Malik Student: Ok teacher
    20/12/21, 8:55 pm - Tayaba Malik Student: Thanku so much... dua karna  bht acha h
    20/12/21, 8:56 pm - ~K: .Try ur best... Baki Acha he hoga sb in shaa Allah
    20/12/21, 8:56 pm - Tayaba Malik Student: Inshallah
    21/12/21, 7:03 pm - ~K: Tyabba Ap ny laini Hai aj ki class?
    22/12/21, 6:47 pm - ~K: Tyabba apka laptop ka ho gya na aj k liay arrangement?
    22/12/21, 7:25 pm - Tayaba Malik Student: Ni teacher...
    22/12/21, 7:26 pm - Tayaba Malik Student: Teacher  project k time  agy h gya
    22/12/21, 7:26 pm - Tayaba Malik Student: Chution  ki wajha s
    22/12/21, 7:26 pm - Tayaba Malik Student: M ap k update  karti  sir btyn t
    22/12/21, 7:29 pm - ~K: Abhi ni pta k kab hai last b iski?
    22/12/21, 7:30 pm - Tayaba Malik Student: Teacher  yh suddenly  chutian  h gi... t abhi w labs  k complete kar rahy  aur assignments. ... project k b kha rahy m btau  g ... sab k
    22/12/21, 7:31 pm - ~K: Chutyan to apki January sy ni hon ge start?
    22/12/21, 7:32 pm - Tayaba Malik Student: Ni
    22/12/21, 7:32 pm - Tayaba Malik Student: University  k h gi...
    22/12/21, 7:32 pm - Tayaba Malik Student: Aj s
    22/12/21, 7:32 pm - Tayaba Malik Student: Lkin hmm k Fridays  s hn....
    22/12/21, 7:32 pm - ~K: Or kab tk hain?
    22/12/21, 7:32 pm - Tayaba Malik Student: 10 Jan
    22/12/21, 7:33 pm - Tayaba Malik Student: Aur extension  k b chances  hn
    22/12/21, 7:33 pm - ~K: Iska mtlb.... 10 Jan k to bahd he apky project ki submission hoge?
    22/12/21, 7:34 pm - Tayaba Malik Student: G
    22/12/21, 7:37 pm - ~K: Chalain thk hai
    24/12/21, 2:10 pm - ~K: Koi laptop ka tyabba hoa Kam phir apka?
    24/12/21, 2:26 pm - Tayaba Malik Student: Teacher  m University  m ghar j k batai
    24/12/21, 2:30 pm - ~K: Ok
    25/12/21, 6:46 pm - ~K: Ap academy tyabba gai to ni the aj kahe?
    25/12/21, 7:34 pm - Tayaba Malik Student: Ni teacher  aj m ni gai
    25/12/21, 7:51 pm - ~K: Or mjy btaya ni ap ny laptop ka
    25/12/21, 7:51 pm - ~K: Or yeh b btay mjy... K date ka apky sir ny phir kuch confirm kia?
    25/12/21, 8:14 pm - Tayaba Malik Student: Teacher lap top ni aya...
    25/12/21, 8:15 pm - Tayaba Malik Student: Ik  week extend h gi...
    25/12/21, 8:15 pm - Tayaba Malik Student: 10 k University  jna hia  then l k jna hai complete.... with report  ,presentation, code
    25/12/21, 8:18 pm - ~K: Mtlb 10 Jan abhi last date hai?
    25/12/21, 9:33 pm - Tayaba Malik Student: G
    28/12/21, 11:14 am - ~K: Apka project complete ho gya Hai... Ab mjy btaiay ga phir k ap ny smjhna kab sy start krna hai
    28/12/21, 1:50 pm - Tayaba Malik Student: Oky... teacher  inshallah... Thursday  s start karty.... abhi m ghr ni hu..  Thursday  k ahu gi...
    28/12/21, 7:02 pm - ~K: Ok
    30/12/21, 6:43 pm - ~K: Assalam u alaikum Tayyaba
    Your class will be started at 7 20
    30/12/21, 6:54 pm - Tayaba Malik Student: No teacher
    30/12/21, 6:54 pm - Tayaba Malik Student: Aj laptop ni aya
    30/12/21, 7:04 pm - ~K: Tyabba apka laptop abhi tk ni aya?
    30/12/21, 7:29 pm - Tayaba Malik Student: Ni teacher...
    30/12/21, 7:29 pm - Tayaba Malik Student: Koi lny ni gya... kal pta karu gi... khud j k
    30/12/21, 7:30 pm - ~K: Tyabba... Mtlb koi irada hai project smjny ka b k ni😐
    30/12/21, 7:37 pm - Tayaba Malik Student: Ni teacher hai irada 
    ....
    30/12/21, 7:37 pm - Tayaba Malik Student: Laptop  aya t m ap k inform karu gi...
    30/12/21, 7:39 pm - ~K: Chalain g bta dijiay ga sae yad sy... Q k din ja rhy hain or Khali code k number ni dainy waly apky sir.. Or time lagy ga smjny main
    30/12/21, 7:40 pm - Tayaba Malik Student: Gg
    30/12/21, 7:40 pm - Tayaba Malik Student: Oky
    3/1/22, 7:52 pm - Tayaba Malik Student: A.o.a teacher.... hum Wednesday  start  kar sakty  hn....
    3/1/22, 7:52 pm - Tayaba Malik Student: Mera laptop kal aha  jya g...
    3/1/22, 7:52 pm - Tayaba Malik Student: Sir jabar s sahi karwaya  finally.... almost h gya...
    3/1/22, 7:53 pm - Tayaba Malik Student: Aur project  ki payment  kar di hai.... ap project  send kar dn... complete  hmm n presentation and report  bni  ....
    3/1/22, 8:04 pm - ~K: W. Aslam
    3/1/22, 8:04 pm - ~K: G thk Hai main send krti hn apko
    3/1/22, 8:06 pm - ~K: <Media omitted>
    3/1/22, 8:06 pm - Tayaba Malik Student: Teacher  yh start s hai....
    3/1/22, 8:07 pm - ~K: yeh apka pura project hai using linked list
    3/1/22, 8:08 pm - Tayaba Malik Student: Teacher  yh ap copy  kar k input j project ki hai send kar dn w hum s lab report  ms world m paste karna....
    3/1/22, 8:09 pm - ~K: admin ka password or email he hai..or to koi as such input ni hai
    3/1/22, 8:09 pm - Tayaba Malik Student: Oky..
    3/1/22, 8:09 pm - ~K: baki destinations k naam wo to ap koi b naam as a input use  kr skty hain
    3/1/22, 8:10 pm - Tayaba Malik Student: Ok
    3/1/22, 8:10 pm - Tayaba Malik Student: Teacher  yh hum we'd s start karty
    3/1/22, 8:10 pm - Tayaba Malik Student: Ap samjha dna...
    3/1/22, 8:10 pm - ~K: open kr k daikh lijiay ga...agr koi issue ata hai to mjy bta daina phir ap
    3/1/22, 8:10 pm - Tayaba Malik Student: Kal sham k aha jya g
    ....
    3/1/22, 8:11 pm - ~K: daikh lain ...kam din hain..smj lain ge ap?
    3/1/22, 8:11 pm - ~K: sir jabar ko kab dia tha ap ny?
    3/1/22, 8:11 pm - Tayaba Malik Student: Ok..
     Teacher  10 k jna hai  chutian  zyda b h sakti... aur... ik week  10 k bad b h ga....
    3/1/22, 8:12 pm - ~K: due date kya hai abhi apki?
    3/1/22, 8:12 pm - Tayaba Malik Student: Yh mujy ni pta kab diya... aj jab bahi k sath gi t w sir  k pas gya...
    3/1/22, 8:12 pm - Tayaba Malik Student: Yh abhi ni btya...
    3/1/22, 8:12 pm - Tayaba Malik Student: Chutian  h gai achanak
    3/1/22, 8:13 pm - Tayaba Malik Student: T sir n kha jab University  khuly gi tab btyn g...
    3/1/22, 8:13 pm - ~K: to phir 10 k bahd aik or week kaisy hai?
    3/1/22, 8:13 pm - ~K: acha acha...due usky bahd dain gy?
    3/1/22, 8:13 pm - Tayaba Malik Student: Week  m ik class hti...
    3/1/22, 8:13 pm - ~K: acha acha is trah...sae sae
    3/1/22, 8:13 pm - Tayaba Malik Student: Gg
    3/1/22, 8:13 pm - Tayaba Malik Student: G
    3/1/22, 8:13 pm - ~K: chalain phir hopefully ho he jay ga
    3/1/22, 8:14 pm - ~K: in shaa Allah
    3/1/22, 8:14 pm - Tayaba Malik Student: Inshallah
    3/1/22, 8:14 pm - Tayaba Malik Student: Thanku teacher  for project  and cooperation... 💗
    3/1/22, 8:14 pm - ~K: no problem🌸🌸
    4/1/22, 5:01 pm - Tayaba Malik Student: A.o.a teacher  mera laptop aha aya hai.... we start from today
    4/1/22, 6:11 pm - Tayaba Malik Student: Teacher  project  open ni h raha...
    4/1/22, 6:58 pm - ~K: G thk Hai.. 7 30 k around start hoge class
    4/1/22, 7:01 pm - Tayaba Malik Student: Oky
    4/1/22, 7:11 pm - Tayaba Malik Student: <Media omitted>
    4/1/22, 7:12 pm - ~K: Main daikhti hn class start hoti hai to
    4/1/22, 7:12 pm - Tayaba Malik Student: Oky
    4/1/22, 7:25 pm - ~K: Should we start?
    4/1/22, 7:25 pm - Tayaba Malik Student: Ok...in 5 minutes
    4/1/22, 7:25 pm - ~K: Ok call be when you are ready
    4/1/22, 7:27 pm - Tayaba Malik Student: Ok.. we can
    5/1/22, 12:01 pm - ~K: Confirm hai na apka?
    5/1/22, 12:02 pm - Tayaba Malik Student: G teacher
    5/1/22, 12:02 pm - ~K: Ok
    5/1/22, 1:15 pm - ~K: Register or pen ly k aiay ga
    5/1/22, 1:36 pm - Tayaba Malik Student: Ok teacher
    5/1/22, 1:36 pm - Tayaba Malik Student: Bs namaz parh k aha rahi
    5/1/22, 1:59 pm - ~K: Ap kab tk ponch jay ge academy?
    5/1/22, 2:02 pm - Tayaba Malik Student: Aha gai hu
    5/1/22, 2:03 pm - Tayaba Malik Student: AUR lock hai academy
    5/1/22, 2:03 pm - ~K: Yeh kyaaa
    5/1/22, 2:03 pm - ~K: Ruko sir ko call krti hn main
    5/1/22, 2:03 pm - Tayaba Malik Student: Oky
    5/1/22, 2:11 pm - Tayaba Malik Student: Missed voice call
    6/1/22, 10:19 am - ~K: Tyabba aj ka academy ka confirm ni Hai... Main apko 1 bjy tk confirm krti hn
    6/1/22, 11:24 am - Tayaba Malik Student: Ok
    6/1/22, 1:05 pm - ~K: Online he Hoge aj apki class
    6/1/22, 1:05 pm - Tayaba Malik Student: Ok
    6/1/22, 6:10 pm - ~K: Today's class will be started at 6 20
    6/1/22, 6:10 pm - Tayaba Malik Student: Teacher  at 6 30 plz
    6/1/22, 6:10 pm - ~K: Ok
    6/1/22, 6:36 pm - ~K: Start krain?
    6/1/22, 6:39 pm - Tayaba Malik Student: G teacher m laptop   lga lu
    6/1/22, 6:39 pm - ~K: G krain on
    7/1/22, 2:17 pm - Tayaba Malik Student: Teacher
    7/1/22, 2:17 pm - Tayaba Malik Student: Koi arrange  ni hua agar m 3 bjy aha jau....
    7/1/22, 2:18 pm - Tayaba Malik Student: Teacher???
    7/1/22, 2:18 pm - Tayaba Malik Student: Missed voice call
    7/1/22, 2:18 pm - Tayaba Malik Student: Missed voice call
    7/1/22, 2:18 pm - Tayaba Malik Student: Missed voice call
    7/1/22, 2:22 pm - Tayaba Malik Student: Missed voice call
    8/1/22, 12:07 pm - ~K: Tyabba from today's onward we will have all of our classes online
    8/1/22, 1:57 pm - Tayaba Malik Student: Ok
    8/1/22, 6:16 pm - ~K: Aj apki class ni hoge
    8/1/22, 6:16 pm - ~K: Or code ap ny apna submit kra dia hai?
    8/1/22, 6:30 pm - Tayaba Malik Student: Ok teacher
    8/1/22, 6:31 pm - Tayaba Malik Student: Ni ... 9 k karna hai.. kal
    8/1/22, 8:47 pm - ~K: Ok then mjy code sy kuch cout ki statements remove krni Hai usky bahd he ap Kal submit kraiay ga
    8/1/22, 9:01 pm - Tayaba Malik Student: Ok
    9/1/22, 4:25 pm - ~K: Anydesk on krain
    9/1/22, 4:53 pm - Tayaba Malik Student: Teacher abhi...
    9/1/22, 4:58 pm - ~K: Ap cout ki statements khud remove kr lain ge?
    9/1/22, 5:02 pm - ~K: Phir sham main mjy control dijiay ga laptop ka main remove kr Don ge... Class ni Hoge sirf control daina hai mjy ap ny
    9/1/22, 5:04 pm - Tayaba Malik Student: Oky teacher....
    9/1/22, 5:05 pm - Tayaba Malik Student: Teacher  iss project  k dev p b run kar dn...
    9/1/22, 6:13 pm - ~K: Open krain anydesk ko abhi jaldi sy
    9/1/22, 6:14 pm - Tayaba Malik Student: Ok teacher
    9/1/22, 6:16 pm - Tayaba Malik Student: Teacher on hai
    9/1/22, 6:35 pm - ~K: System ko restart kr k mjy btay
    9/1/22, 6:35 pm - Tayaba Malik Student: Oky
    9/1/22, 6:38 pm - Tayaba Malik Student: Teacher  h gya hai
    9/1/22, 6:39 pm - ~K: Anydesk
    9/1/22, 6:39 pm - Tayaba Malik Student: Kar li
    9/1/22, 6:42 pm - ~K: Yeh apny system main aa rha... Mery pas ni a rha yeh
    9/1/22, 6:42 pm - Tayaba Malik Student: Ok teacher
    9/1/22, 6:42 pm - ~K: Yeh project ap apni frnd ko send kr k check krain... Unky laptop main ata hai ya ni
    9/1/22, 6:43 pm - Tayaba Malik Student: Teacher  ab iss code k dev p b run karwa dn...
    9/1/22, 6:43 pm - ~K: Open krain isko dev py
    9/1/22, 6:43 pm - Tayaba Malik Student: Teacher  us k m n bj diya  tha... lkin us k pan winraw ni tha... na instal hua t us k open ni hua...
    9/1/22, 6:45 pm - Tayaba Malik Student: Teacher  h gya hai...
    9/1/22, 6:52 pm - ~K: Black screen ai hai?
    9/1/22, 6:52 pm - ~K: Ya screen stuck hoi hoi hai yeh
    9/1/22, 6:52 pm - Tayaba Malik Student: Ni
    9/1/22, 6:53 pm - ~K: Chalain g
    9/1/22, 6:53 pm - Tayaba Malik Student: Ab aha gi hai...
    9/1/22, 6:53 pm - ~K: Mubarik ho... Ho gya run
    9/1/22, 6:53 pm - Tayaba Malik Student: Teacher  ab iss k save kasy  karu
    9/1/22, 6:53 pm - Tayaba Malik Student: Thanku...
    9/1/22, 6:53 pm - ~K: Close krny sy dev ka b save ho ni Jay ga... Jaisy code blocks main hota hai
    9/1/22, 6:53 pm - Tayaba Malik Student: Oky
    9/1/22, 6:54 pm - ~K: Close krain isko.. Or dobara open kr k aik br run krain
    9/1/22, 6:54 pm - Tayaba Malik Student: G
    9/1/22, 6:54 pm - Tayaba Malik Student: H gya ...
    9/1/22, 6:55 pm - Tayaba Malik Student: Thanku...
    9/1/22, 6:56 pm - ~K: Abhi aik br... Pury project ko run krain... Sary options check krain... K dev main sb kuch sae sy chal rha hai ya ni?
    9/1/22, 6:56 pm - ~K: Agr kahe issue ata hai to bta daina phir mjy ap
    9/1/22, 6:56 pm - Tayaba Malik Student: Ok teacher
    9/1/22, 7:03 pm - Tayaba Malik Student: Teacher sab run h rahy
    9/1/22, 7:12 pm - ~K: Thk hai
    9/1/22, 7:13 pm - Tayaba Malik Student: G
    10/1/22, 5:37 pm - Tayaba Malik Student: A.o.a teacher I am not able to take class I am outside... so plz cancelled  today lecture.....
    10/1/22, 6:23 pm - ~K: Ok
    10/1/22, 6:23 pm - ~K: Ap ko present krny ki date mili hai?
    10/1/22, 6:24 pm - Tayaba Malik Student: Ni teacher
    10/1/22, 6:24 pm - Tayaba Malik Student: Aj  m University b ni gi...
    10/1/22, 6:25 pm - ~K: Iska pta kray phir kal tk
    10/1/22, 10:01 pm - Tayaba Malik Student: Ok teacher
    11/1/22, 7:00 pm - ~K: Class will be started at 7 30
    11/1/22, 7:09 pm - Tayaba Malik Student: Oky
    11/1/22, 7:24 pm - ~K: Should we start?
    11/1/22, 7:30 pm - Tayaba Malik Student: G teacher  5 minutes  m laptop on kar lu
    11/1/22, 7:31 pm - ~K: On kr k btay
    11/1/22, 7:36 pm - Tayaba Malik Student: Ok teacher
    11/1/22, 7:36 pm - Tayaba Malik Student: System update  h raha...
    11/1/22, 7:37 pm - ~K: Ho jay to btay
    11/1/22, 7:37 pm - Tayaba Malik Student: G
    11/1/22, 7:39 pm - Tayaba Malik Student: H gya teacher
    11/1/22, 8:23 pm - Tayaba Malik Student: Teacher???
    12/1/22, 6:51 pm - ~K: Class will be started at 7 30
    12/1/22, 6:51 pm - Tayaba Malik Student: Oky
    12/1/22, 6:52 pm - ~K: Laptop 7 30 sy pehly on kr lijiay ga
    12/1/22, 6:52 pm - Tayaba Malik Student: Oky
    12/1/22, 7:28 pm - ~K: Should we start?
    12/1/22, 7:28 pm - Tayaba Malik Student: Yes
    14/1/22, 7:00 pm - ~K: Laini Hai ap ny aj class?
    14/1/22, 7:09 pm - Tayaba Malik Student: Ni teacher  ....
    14/1/22, 7:09 pm - Tayaba Malik Student: Teacher... Ap s ik bat  karni hai... project  s related  koi new project  bnwana hai... ghar ponch  k karti
    14/1/22, 7:17 pm - ~K: Ok
    15/1/22, 6:42 pm - ~K: Aj ka kya krna Hai ap ny tayyaba?
    15/1/22, 6:42 pm - Tayaba Malik Student: Teacher lni hai class
    15/1/22, 6:43 pm - ~K: Ok main apko msg krti hn start time ka thori dair tk
    15/1/22, 6:43 pm - Tayaba Malik Student: Ok
    15/1/22, 6:53 pm - ~K: Class will be started at 7:05
    15/1/22, 6:53 pm - ~K: Laptop kr lijiay ga pehly he
    15/1/22, 7:05 pm - ~K: Should we start?
    15/1/22, 7:06 pm - Tayaba Malik Student: G
    15/1/22, 7:12 pm - Tayaba Malik Student: <Media omitted>
    15/1/22, 7:13 pm - Tayaba Malik Student: Online travel portal
    15/1/22, 7:17 pm - Tayaba Malik Student: <Media omitted>
    15/1/22, 7:17 pm - Tayaba Malik Student: <Media omitted>
    15/1/22, 8:58 pm - ~K: Apni email or password mjy bejhain
    15/1/22, 8:59 pm - Tayaba Malik Student: Ok
    15/1/22, 8:59 pm - Tayaba Malik Student: tayaba1389@gmail.com 
    03042030887
    15/1/22, 9:00 pm - Tayaba Malik Student: Iss k password  change  kar ln... teacher  yh... meri University  m pc m b login hai... project  jab bnyn... ta ka  ksi aur k na mily...
    15/1/22, 9:01 pm - ~K: Kisi or ko kaisy mily ga
    15/1/22, 9:02 pm - Tayaba Malik Student: Teacher jab humm lab lty... t log in karty...
    15/1/22, 9:02 pm - Tayaba Malik Student: Iss liya...
    15/1/22, 9:02 pm - Tayaba Malik Student: PC wahn login hai...
    15/1/22, 9:02 pm - Tayaba Malik Student: Logout ni kia. ..
    15/1/22, 9:02 pm - ~K: <Media omitted>
    15/1/22, 9:03 pm - Tayaba Malik Student: Ok
    15/1/22, 9:11 pm - ~K: Is course ka baki Sara material b mjy bejhain
    15/1/22, 9:26 pm - Tayaba Malik Student: Ok teacher  thori deer m... khna kha k
    15/1/22, 9:34 pm - ~K: Ok
    16/1/22, 7:12 pm - ~K: Tyabba apki class ni Hoge aj
    16/1/22, 8:15 pm - Tayaba Malik Student: Oky
    17/1/22, 7:24 am - Tayaba Malik Student: <Media omitted>
    17/1/22, 7:24 am - Tayaba Malik Student: A.o.a teacher  iss project  k dekhn...
    17/1/22, 7:25 am - Tayaba Malik Student: Aur btyn iss m kia bnana hai... aur ksy... kia karna hai...
    17/1/22, 7:25 am - Tayaba Malik Student: Koi website  ??? Kuch b
    17/1/22, 9:40 am - Tayaba Malik Student: <Media omitted>
    17/1/22, 10:33 am - ~K: Han g kuch isi trah ki simulation bnany k liay uper kaha gya hai
    17/1/22, 10:33 am - ~K: Yeh kon sa project hai apka
    17/1/22, 11:23 am - Tayaba Malik Student: Graphics  k
    17/1/22, 11:23 am - Tayaba Malik Student: Srs
    17/1/22, 11:25 am - ~K: Iski due kab hai?
    17/1/22, 11:31 am - Tayaba Malik Student: Kal 9 s phly
    17/1/22, 11:32 am - ~K: To yeh ap ny bna Lia hai?
    17/1/22, 11:41 am - Tayaba Malik Student: Ni bnya
    17/1/22, 11:41 am - Tayaba Malik Student: Aj mila
    17/1/22, 11:41 am - ~K: Agr Mery sy banwana hoa to mjy time sy btay ge to ho pay ga
    17/1/22, 11:41 am - Tayaba Malik Student: Hai
    17/1/22, 11:41 am - ~K: Kaisy bnany ka irada hai phir isko?
    17/1/22, 11:41 am - Tayaba Malik Student: Kal suba 9 k karna
    17/1/22, 11:42 am - Tayaba Malik Student: Mujy ni ata bnnna
    17/1/22, 11:42 am - Tayaba Malik Student: Aur coding c  m karni
    17/1/22, 11:42 am - ~K: Itni jaldi q hai submission iski
    17/1/22, 11:42 am - Tayaba Malik Student: Pta ni
    17/1/22, 11:42 am - ~K: Teacher sy bolain na ap k Thora to time dain bai
    17/1/22, 11:42 am - Tayaba Malik Student: Assignment  hai ik tarah ki
    17/1/22, 11:42 am - ~K: Request to krain teacher sy
    17/1/22, 11:43 am - Tayaba Malik Student: Sab n ki hai ...
    17/1/22, 11:43 am - Tayaba Malik Student: T aj rat s kal 9 k hua
    17/1/22, 11:43 am - Tayaba Malik Student: Suba
    17/1/22, 11:43 am - ~K: Opengl software hai I guess main ny daikha hai
    17/1/22, 11:43 am - ~K: Ap ko krwaya hoa hai Yeh software uni walo ny? Mtlb parhaya hoa hai?
    17/1/22, 11:44 am - Tayaba Malik Student: Pta ni kia hai... teacher  mery s upper s guzAr raha sab kuch
    17/1/22, 11:44 am - Tayaba Malik Student: Ni...
    17/1/22, 11:44 am - ~K: To phir ab.. Kya krna Hai? Mery sy banwana chah rhe hain ap yeh?
    17/1/22, 11:44 am - Tayaba Malik Student: Teacher  kab tak bna dn gi...
    17/1/22, 11:44 am - Tayaba Malik Student: Q k time ni hai.
    17/1/22, 11:45 am - Tayaba Malik Student: Aur ap n ik aur b bnana hai.... hci k..
    17/1/22, 11:45 am - ~K: Yahe naa
    17/1/22, 11:45 am - ~K: Time iska bht he Thora hai
    17/1/22, 11:45 am - Tayaba Malik Student: Us k time b thora hai
    17/1/22, 11:45 am - Tayaba Malik Student: Gg
    17/1/22, 11:45 am - ~K: Iski exact date kya hai?
    17/1/22, 11:46 am - Tayaba Malik Student: M n senior  s kha hai... k agar unho na kia hua... t baj dn.
    17/1/22, 11:46 am - ~K: HCI Waly ki
    17/1/22, 11:46 am - Tayaba Malik Student: Wednesday  next
    17/1/22, 11:46 am - Tayaba Malik Student: Ik yh hai iss s agla we'dnesday
    17/1/22, 11:46 am - ~K: G thk Hai... Pta krain milta hai to well and good... Ni milta to mjy btay phir daikhti hn main kuch
    17/1/22, 11:46 am - Tayaba Malik Student: Oky
    17/1/22, 11:46 am - Tayaba Malik Student: Sham tak btatai
    17/1/22, 11:46 am - ~K: Wo phir ban jay gay easily in shaa Allah
    17/1/22, 11:47 am - Tayaba Malik Student: Oky
    17/1/22, 11:47 am - ~K: Phir time ni bachy ga na peechy
    17/1/22, 11:47 am - Tayaba Malik Student: Ok... 4 tak btati... abhi University
    17/1/22, 11:47 am - ~K: <Media omitted>
    17/1/22, 11:48 am - Tayaba Malik Student: Oky teacher...
    17/1/22, 11:48 am - ~K: Jaldi btay phir mjy.. Am waiting
    17/1/22, 11:48 am - ~K: Call kr lain unhain
    17/1/22, 11:49 am - Tayaba Malik Student: G kar rahi
    17/1/22, 11:49 am - ~K: G thk Hai btay
    17/1/22, 12:22 pm - ~K: Hoi bt senior sy?
    17/1/22, 12:33 pm - Tayaba Malik Student: Gg
    17/1/22, 12:33 pm - Tayaba Malik Student: H gi hai...
    17/1/22, 12:33 pm - Tayaba Malik Student: H jya hai arrange
    17/1/22, 12:34 pm - ~K: Chalain shukar hai
    17/1/22, 6:41 pm - ~K: Class will be started at 7
    17/1/22, 6:46 pm - Tayaba Malik Student: Oky
    17/1/22, 6:47 pm - Tayaba Malik Student: Teacher at 7 15..
    17/1/22, 6:47 pm - Tayaba Malik Student: Plz
    17/1/22, 6:50 pm - ~K: Ok
    17/1/22, 7:15 pm - ~K: Should we start?
    17/1/22, 7:20 pm - Tayaba Malik Student: Gg
    17/1/22, 7:33 pm - Tayaba Malik Student: <Media omitted>
    17/1/22, 7:34 pm - Tayaba Malik Student: <Media omitted>
    17/1/22, 7:45 pm - Tayaba Malik Student: Wesy to is week ki Friday Hy..but extend krwaty hain
    18/1/22, 10:09 am - ~K: Tayabba ap uni main hain?
    18/1/22, 10:18 am - Tayaba Malik Student: G
    18/1/22, 10:23 am - ~K: <Media omitted>
    18/1/22, 10:24 am - ~K: Phir ta k main unhi cheezon ko prototype main dalon
    18/1/22, 10:26 am - Tayaba Malik Student: Ok
    18/1/22, 10:26 am - ~K: Agr wo ai hoi hai... Ya hain uni main to mjy phir jaldi puch k btaiay ga
    18/1/22, 10:27 am - Tayaba Malik Student: Okok
    18/1/22, 10:27 am - Tayaba Malik Student: Class l k jati
    18/1/22, 10:27 am - Tayaba Malik Student: 11 bjy tak batati
    18/1/22, 10:27 am - ~K: Thk hai
    18/1/22, 11:33 am - ~K: <Media omitted>
    18/1/22, 11:34 am - ~K: Apki teacher ny jo doc bejha tha... Us main sy sari requirements nikal k is main likhi hain... Isko parh k mjy confirm kr dain k is sb k ilawa or kuch to ni Hai
    18/1/22, 11:39 am - Tayaba Malik Student: Oky
    18/1/22, 11:40 am - ~K: Parha hai isko?
    18/1/22, 11:42 am - Tayaba Malik Student: Teacher  class m
    18/1/22, 11:44 am - ~K: Class ly k mjy phir jaldi btay
    18/1/22, 12:36 pm - Tayaba Malik Student: G
    18/1/22, 12:36 pm - Tayaba Malik Student: Gari  m bath gi
    18/1/22, 12:36 pm - ~K: Teacher sy pucha hai ap ny?
    18/1/22, 12:36 pm - Tayaba Malik Student: Gg
    18/1/22, 12:36 pm - Tayaba Malik Student: Teacher
    18/1/22, 12:37 pm - Tayaba Malik Student: Pucha hai
    18/1/22, 12:37 pm - Tayaba Malik Student: Ghar j k call karti
    18/1/22, 12:37 pm - Tayaba Malik Student: Free h gi
    18/1/22, 12:37 pm - Tayaba Malik Student: Ghar aha rahj
    18/1/22, 12:37 pm - Tayaba Malik Student: Rahi *
    18/1/22, 12:37 pm - Tayaba Malik Student: Online travel  portal hai
    18/1/22, 12:37 pm - Tayaba Malik Student: Topic
    18/1/22, 12:38 pm - ~K: Chalain phir ponch k btay... Main free hoi tb to phir discuss kr lain gy isko
    18/1/22, 12:38 pm - Tayaba Malik Student: Oky
    18/1/22, 6:24 pm - ~K: Tayyaba aj jaldi class start krain gy OK?
    18/1/22, 6:26 pm - Tayaba Malik Student: Ok
    18/1/22, 6:26 pm - Tayaba Malik Student: 7 bjy
    18/1/22, 6:26 pm - ~K: No... On 6 45
    18/1/22, 6:26 pm - Tayaba Malik Student: Oky
    18/1/22, 6:26 pm - ~K: Lambi hoge aj ki class to jaldi Shuro is liay krni hai
    18/1/22, 6:27 pm - Tayaba Malik Student: Oky
    18/1/22, 6:43 pm - Tayaba Malik Student: Teacher  m 5 minutes  m khna kha lu...
    18/1/22, 6:45 pm - ~K: Ok kha k btay phir
    18/1/22, 6:45 pm - Tayaba Malik Student: Ok in 5 minutes
    18/1/22, 6:56 pm - Tayaba Malik Student: Oky
    18/1/22, 6:56 pm - Tayaba Malik Student: Teacher  we start
    18/1/22, 9:18 pm - Tayaba Malik Student: Yh to nhi pta..but project fail ho to maybe semester fail hi hota hy
    18/1/22, 10:04 pm - ~K: Tayyaba ap ny linear ki assignment kab submit krani hai?
    18/1/22, 10:05 pm - ~K: Or mjy assignment phir jaldi send kijiay ga.
    18/1/22, 10:08 pm - Tayaba Malik Student: W submit  ni karnai... lkin lazmi larni hai...
    18/1/22, 10:08 pm - Tayaba Malik Student: 30 s phly
    18/1/22, 10:08 pm - Tayaba Malik Student: 31 k paper hai... linear k
    18/1/22, 10:09 pm - ~K: Wo mill gai hai apko?
    18/1/22, 10:09 pm - Tayaba Malik Student: G
    18/1/22, 10:09 pm - ~K: Bejhain mjy wo b
    18/1/22, 10:09 pm - ~K: Or notifications wala bejha ni ap ny mjy
    18/1/22, 10:10 pm - Tayaba Malik Student: Gg w ma na kha hai bjny k meri friend  s
    18/1/22, 10:10 pm - ~K: Or kal... HCI wali teacher sy Lazmi bt kijiay ga.. Aik do din ki extension ki
    18/1/22, 10:10 pm - Tayaba Malik Student: G
    18/1/22, 10:10 pm - Tayaba Malik Student: Oky
    19/1/22, 9:26 am - Tayaba Malik Student: Teacher great J.b...
    19/1/22, 9:26 am - Tayaba Malik Student: Job*
    19/1/22, 9:26 am - Tayaba Malik Student: Wah wah h gi...
    19/1/22, 9:54 am - ~K: Ho was that?
    19/1/22, 9:54 am - ~K: How*
    19/1/22, 9:54 am - ~K: Free hain ap abhi ya class main hain?
    19/1/22, 9:54 am - Tayaba Malik Student: It's was great awesome
    19/1/22, 9:55 am - Tayaba Malik Student: Class  m bathy
    19/1/22, 9:55 am - ~K: Teacher aa gai?
    19/1/22, 9:55 am - ~K: Chalain g zabardast... Din bna Dia ap ny Mera b😂
    Han per complete details btani hai ap ny mjy
    19/1/22, 9:58 am - Tayaba Malik Student: Gg
    19/1/22, 9:58 am - Tayaba Malik Student: Ok
    19/1/22, 9:58 am - ~K: Chalain phir abhi class lain... Or dosri khushkhabri b mjy sunay... HCI ki date extension ki
    19/1/22, 10:29 am - Tayaba Malik Student: Oku
    19/1/22, 5:59 pm - Tayaba Malik Student: <Media omitted>
    19/1/22, 6:49 pm - ~K: Kha Lia khana ap ny... Hain free?
    19/1/22, 6:50 pm - Tayaba Malik Student: Ni abhi ni...
    19/1/22, 6:50 pm - Tayaba Malik Student: Teacher  late h jyn g...
    19/1/22, 6:50 pm - Tayaba Malik Student: Abhi  class lni t l ln
    19/1/22, 6:50 pm - ~K: Acha class ni Hoge apki aj or kal
    19/1/22, 6:50 pm - Tayaba Malik Student: Ok
    19/1/22, 6:50 pm - Tayaba Malik Student: M b yh hi chati thi...
    19/1/22, 6:50 pm - ~K: Abhi sirf project ka btany k liay main call kr rhe hn app
    19/1/22, 6:50 pm - ~K: Ko*
    19/1/22, 6:51 pm - Tayaba Malik Student: Teacher  can I call  u
    19/1/22, 6:51 pm - Tayaba Malik Student: Okok
    19/1/22, 7:04 pm - Tayaba Malik Student: <Media omitted>
    19/1/22, 7:04 pm - Tayaba Malik Student: <Media omitted>
    19/1/22, 7:04 pm - Tayaba Malik Student: <Media omitted>
    19/1/22, 7:14 pm - Tayaba Malik Student: <Media omitted>
    19/1/22, 7:15 pm - ~K: Or Han... Sir ko msg kr dijiay ga phir ap.. K meri presentation ho gai hai
    19/1/22, 7:16 pm - Tayaba Malik Student: Oky
    19/1/22, 7:23 pm - ~K: <Media omitted>
    19/1/22, 7:36 pm - Tayaba Malik Student: Oky
    19/1/22, 7:37 pm - ~K: Or abhi apky project per he Kam kr rhe hn... Jo b cheez puchni hoge to wo main apko audio main bejh don ge ap wo b kal teacher sy puch lijiay ga waisy he
    19/1/22, 7:41 pm - Tayaba Malik Student: Oky
    19/1/22, 7:41 pm - Tayaba Malik Student: M na sir k msg kia...
    19/1/22, 7:51 pm - Tayaba Malik Student: W Salam.. pleasure to know this, 
    Stay Blessed
    19/1/22, 8:19 pm - ~K: Ap ny Kya Kia tha msg
    19/1/22, 9:32 pm - Tayaba Malik Student: A.o.a sir aj meri final project  ki presentation  thi... alhumdulillah  ap ki corporation  aur teacher ki effort  s its is really  amazing.... my university  sir like and appreciate  me ... Thank you
    19/1/22, 11:15 pm - ~K: Acha Tayyaba ap ny apni teacher sy tool tip ka b puchna haj
    19/1/22, 11:15 pm - Tayaba Malik Student: Oky
    19/1/22, 11:15 pm - ~K: Hai*
    Puchna teacher tool tip main hm ny Kya dalna hai?
    19/1/22, 11:16 pm - Tayaba Malik Student: Oky
    19/1/22, 11:16 pm - ~K: Or jo Friday ki apko date milli hoi hai... Uska time kya hai?
    19/1/22, 11:17 pm - ~K: Mtlb Friday kis time tk submit kra skty hain
    19/1/22, 11:17 pm - Tayaba Malik Student: Wait
    19/1/22, 11:18 pm - Tayaba Malik Student: 12
    19/1/22, 11:18 pm - Tayaba Malik Student: Rat k
    20/1/22, 8:33 am - ~K: Ok
    20/1/22, 11:40 am - ~K: Project ki extension hoi ya ni usky bary main mjy btaiay ga jaisy he apki class ho jay ge HCI ki
    20/1/22, 11:43 am - Tayaba Malik Student: 1 50 class hai
    20/1/22, 11:43 am - Tayaba Malik Student: Oku
    20/1/22, 6:38 pm - ~K: .
    20/1/22, 6:46 pm - Tayaba Malik Student: Ni...
    20/1/22, 6:46 pm - Tayaba Malik Student: M  ap k 7 tak call karti..
    20/1/22, 6:54 pm - ~K: Ok
    20/1/22, 7:27 pm - Tayaba Malik Student: Teacher  abhi project  k date extension  p lgy huy...
    20/1/22, 7:28 pm - Tayaba Malik Student: Madam na  University   m t na kar di
    .. lkin abhi group  m Madam kha rahi  ap kam karn  m btati....hod  s
    20/1/22, 7:29 pm - ~K: Thk Hai... Phir wo btay ge to mjy bta dijiay ga
    20/1/22, 7:29 pm - Tayaba Malik Student: Oky
    20/1/22, 7:29 pm - Tayaba Malik Student: Teacher  m call karu
    20/1/22, 7:30 pm - ~K: Kr lain isky ilawa ap ny kuch or b discuss krna Hai to
    20/1/22, 7:30 pm - Tayaba Malik Student: Gg
    20/1/22, 7:30 pm - ~K: Apni teacher sy wo cheezain puchi the jo main ny apko kaha tha puchny k liay?
    20/1/22, 7:30 pm - Tayaba Malik Student: J ap na btya tha
    20/1/22, 7:31 pm - Tayaba Malik Student: Puchnu k liya
    20/1/22, 7:45 pm - ~K: <Media omitted>
    20/1/22, 7:45 pm - ~K: Or unka Sara record kr Laina ap phir
    20/1/22, 8:34 pm - Tayaba Malik Student: Time  extension  h gi hai
    20/1/22, 8:35 pm - Tayaba Malik Student: Monday  k uploaded  karna...
    20/1/22, 8:35 pm - Tayaba Malik Student: Teacher  ik bat karni hai????
    20/1/22, 8:40 pm - ~K: G krain
    20/1/22, 8:40 pm - ~K: Chalo shukr hai
    20/1/22, 8:41 pm - Tayaba Malik Student: Teacher
    20/1/22, 8:41 pm - Tayaba Malik Student: Suba dsa ki final lab hai...
    20/1/22, 8:41 pm - Tayaba Malik Student: Sir ik  code karyn g...
    20/1/22, 8:41 pm - ~K: G to 🙄
    20/1/22, 8:42 pm - Tayaba Malik Student: Ap k msg karu gi agar humy net available  hua... t ap btna...
    20/1/22, 8:42 pm - ~K: Smj ni ai mjy apki bt
    20/1/22, 8:42 pm - ~K: Us lab report ka kya krna hai
    20/1/22, 8:42 pm - Tayaba Malik Student: W ni dni...
    20/1/22, 8:43 pm - Tayaba Malik Student: Bs University  m sir k ik code check karwna.... h g kar k
    20/1/22, 8:43 pm - Tayaba Malik Student: Final  lab ....
    20/1/22, 8:43 pm - ~K: Kis time?
    20/1/22, 8:43 pm - Tayaba Malik Student: Mobile  t pas hta hai  lakin... net ni ata... service  block  h jati hai
    20/1/22, 8:43 pm - Tayaba Malik Student: Agar net available  hua.. t...
    20/1/22, 8:43 pm - Tayaba Malik Student: 8 40
    20/1/22, 8:44 pm - ~K: Net availability na hoi to?
    20/1/22, 8:44 pm - Tayaba Malik Student: T khud karn g...
    20/1/22, 8:45 pm - Tayaba Malik Student: Yh sath walon ki try karn g cheating karny ki
    20/1/22, 8:45 pm - ~K: Or net available hoa to?
    20/1/22, 8:45 pm - Tayaba Malik Student: T ap karwana...
    20/1/22, 8:46 pm - ~K: 8 15 per to main uth'ti hn😂
    20/1/22, 8:46 pm - ~K: Chalain possible hoa to kra don ge
    20/1/22, 8:46 pm - Tayaba Malik Student: Oky
    20/1/22, 8:47 pm - ~K: Acha is project ki Monday kis time tk hai
    20/1/22, 8:47 pm - Tayaba Malik Student: Rat 12 tak...Sunday  k 12 tak rat
    20/1/22, 8:47 pm - Tayaba Malik Student: Agha din Monday hta...
    20/1/22, 8:48 pm - ~K: Sunday 11 59 pm!?
    20/1/22, 8:48 pm - Tayaba Malik Student: G
    20/1/22, 8:49 pm - ~K: Mtlb Monday sy pehly banta hai Yeh to
    20/1/22, 8:49 pm - Tayaba Malik Student: Hmm
    20/1/22, 8:49 pm - ~K: Per chalain ab easily ban jay ga
    20/1/22, 8:49 pm - Tayaba Malik Student: Oky
    20/1/22, 8:50 pm - ~K: <Media omitted>
    20/1/22, 9:07 pm - Tayaba Malik Student: Oky
    21/1/22, 8:48 am - Tayaba Malik Student: Ik hi code hai
    21/1/22, 8:48 am - Tayaba Malik Student: <Media omitted>
    21/1/22, 8:48 am - Tayaba Malik Student: <Media omitted>
    21/1/22, 8:50 am - Tayaba Malik Student: Missed voice call
    21/1/22, 8:52 am - Tayaba Malik Student: Missed voice call
    21/1/22, 8:53 am - Tayaba Malik Student: Teacher  kar dn... sir na kha hai help l sakty net s yh kahin  s open ended  hai
    21/1/22, 8:55 am - Tayaba Malik Student: Missed voice call
    21/1/22, 8:56 am - Tayaba Malik Student: 9 30 tak time
    21/1/22, 9:01 am - Tayaba Malik Student: Missed voice call
    21/1/22, 9:04 am - ~K: Is main apko nazar aa rha hai?
    21/1/22, 9:04 am - ~K: Clear picture bejhain mjy
    21/1/22, 9:06 am - Tayaba Malik Student: <Media omitted>
    21/1/22, 9:06 am - Tayaba Malik Student: This message was deleted
    21/1/22, 9:06 am - ~K: Krna kya hai program main
    21/1/22, 9:07 am - Tayaba Malik Student: Stack  should  be implemented  using link list or array
    21/1/22, 9:09 am - Tayaba Malik Student: Write  a c ++ to store first 5 even number  in a stack using  array or link  list then pop elements one hu one and make binary  tree for that pop values  Write  the code to display  output  in inorder pre oder of the tree
    21/1/22, 9:10 am - ~K: Lamba code hai Yeh to kafi
    21/1/22, 9:10 am - Tayaba Malik Student: Teacher half  h gya hai m na kar liya
    21/1/22, 9:10 am - ~K: Ap aik Kam krain na...mery laptop on krty krty time lag jay ga
    21/1/22, 9:10 am - ~K: Main apko btati hn ap krain
    21/1/22, 9:11 am - Tayaba Malik Student: Implementation of stack using linked list
    21/1/22, 9:11 am - ~K: Half kr Lia hai? Phir Kya tension hai
    21/1/22, 9:11 am - Tayaba Malik Student: Ni ni wo sirf post order wlaa kia ha
    21/1/22, 9:11 am - Tayaba Malik Student: Yh wala krwa dn
    21/1/22, 9:11 am - ~K: Stack main sy elements ko pop krwa k array main store krway
    21/1/22, 9:12 am - Tayaba Malik Student: Ni ata ap kr Dean
    21/1/22, 9:12 am - ~K: To array kr lain... Zroori to ni link list sy krain
    21/1/22, 9:12 am - ~K: Ap k sir ny labs main apko code krway hoay hain na stack ly?
    21/1/22, 9:12 am - Tayaba Malik Student: Array  karwa dn
    21/1/22, 9:12 am - ~K: K*
    21/1/22, 9:12 am - Tayaba Malik Student: // C++ program for different tree traversals
    #include <iostream>
    using namespace std;
    
    /* A binary tree node has data, pointer to left child
    and a pointer to right child */
    struct Node {
    	int data;
    	struct Node *left, *right;
    };
    
    //Utility function to create a new tree node
    Node* newNode(int data)
    {
    	Node* temp = new Node;
    	temp->data = data;
    	temp->left = temp->right = NULL;
    	return temp;
    }
    
    /* Given a binary tree, print its nodes according to the
    "bottom-up" postorder traversal. */
    void printPostorder(struct Node* node)
    {
    	if (node == NULL)
    		return;
    
    	// first recur on left subtree
    	printPostorder(node->left);
    
    	// then recur on right subtree
    	printPostorder(node->right);
    
    	// now deal with the node
    	cout << node->data << " ";
    }
    
    /* Given a binary tree, print its nodes in inorder*/
    void printInorder(struct Node* node)
    {
    	if (node == NULL)
    		return;
    
    	/* first recur on left child */
    	printInorder(node->left);
    
    	/* then print the data of node */
    	cout << node->data << " ";
    
    	/* now recur on right child */
    	printInorder(node->right);
    }
    
    /* Given a binary tree, print its nodes in preorder*/
    void printPreorder(struct Node* node)
    {
    	if (node == NULL)
    		return;
    
    	/* first print data of node */
    	cout << node->data << " ";
    
    	/* then recur on left subtree */
    	printPreorder(node->left);
    
    	/* now recur on right subtree */
    	printPreorder(node->right);
    }
    
    /* Driver program to test above functions*/
    int main()
    {
    	struct Node* root = newNode(1);
    	root->left = newNode(2);
    	root->right = newNode(3);
    	root->left->left = newNode(4);
    	root->left->right = newNode(5);
    
    	cout << "\nPreorder traversal of binary tree is \n";
    	printPreorder(root);
    
    	cout << "\nInorder traversal of binary tree is \n";
    	printInorder(root);
    
    	cout << "\nPostorder traversal of binary tree is \n";
    	printPostorder(root);
    
    	return 0;
    }
    21/1/22, 9:12 am - ~K: Wahan sy isko copy paste marain
    21/1/22, 9:12 am - Tayaba Malik Student: Wahn s yh ni hai
    21/1/22, 9:13 am - ~K: Or array ka size 5 set kr dain bs
    21/1/22, 9:13 am - ~K: Yeh to tree ka hai
    21/1/22, 9:13 am - Tayaba Malik Student: Ni l
    Karwa  hua
    21/1/22, 9:13 am - ~K: Stack sy related kuch to kraya hoga sir ny
    21/1/22, 9:14 am - ~K: Main daikhti hn net per... Q k khud likhny ka to time ni Hai thora time reh gya hai
    21/1/22, 9:14 am - ~K: Milta hai to apko bejhti hn
    21/1/22, 9:14 am - Tayaba Malik Student: G
    21/1/22, 9:14 am - ~K: Ap b daikhain... Net per mill jay ga yeh
    21/1/22, 9:14 am - Tayaba Malik Student: 10 s phly karwa dn... q k m na viva dna hai.... abhi
    21/1/22, 9:17 am - ~K: Before implementing actual operations, first follow the below steps to create an empty stack.
    
    Step 1 - Include all the header files which are used in the program and define a constant 'SIZE' with specific value.
    Step 2 - Declare all the functions used in stack implementation.
    Step 3 - Create a one dimensional array with fixed size (int stack[SIZE])
    Step 4 - Define a integer variable 'top' and initialize with '-1'. (int top = -1)
    Step 5 - In main method, display menu with list of operations and make suitable function calls to perform operation selected by the user on the stack.
    21/1/22, 9:17 am - ~K: push(value) - Inserting value into the stack
    In a stack, push() is a function used to insert an element into the stack. In a stack, the new element is always inserted at top position. Push function takes one integer value as parameter and inserts that value into the stack. We can use the following steps to push an element on to the stack...
    
    Step 1 - Check whether stack is FULL. (top == SIZE-1)
    Step 2 - If it is FULL, then display "Stack is FULL!!! Insertion is not possible!!!" and terminate the function.
    Step 3 - If it is NOT FULL, then increment top value by one (top++) and set stack[top] to value (stack[top] = value).
    21/1/22, 9:18 am - ~K: pop() - Delete a value from the Stack
    In a stack, pop() is a function used to delete an element from the stack. In a stack, the element is always deleted from top position. Pop function does not take any value as parameter. We can use the following steps to pop an element from the stack...
    
    Step 1 - Check whether stack is EMPTY. (top == -1)
    Step 2 - If it is EMPTY, then display "Stack is EMPTY!!! Deletion is not possible!!!" and terminate the function.
    Step 3 - If it is NOT EMPTY, then delete stack[top] and decrement top value by one (top--).
    21/1/22, 9:18 am - ~K: Yeh ap viva k liay parh lain... Is main push k operation k steps b hain or pop k b
    21/1/22, 9:19 am - ~K: #include<stdio.h>
    #include<conio.h>
    
    #define SIZE 10
    
    void push(int);
    void pop();
    void display();
    
    int stack[SIZE], top = -1;
    
    void main()
    {
       int value, choice;
       clrscr();
       while(1){
          printf("\n\n***** MENU *****\n");
          printf("1. Push\n2. Pop\n3. Display\n4. Exit");
          printf("\nEnter your choice: ");
          scanf("%d",&choice);
          switch(choice){
    	 case 1: printf("Enter the value to be insert: ");
    		 scanf("%d",&value);
    		 push(value);
    		 break;
    	 case 2: pop();
    		 break;
    	 case 3: display();
    		 break;
    	 case 4: exit(0);
    	 default: printf("\nWrong selection!!! Try again!!!");
          }
       }
    }
    void push(int value){
       if(top == SIZE-1)
          printf("\nStack is Full!!! Insertion is not possible!!!");
       else{
          top++;
          stack[top] = value;
          printf("\nInsertion success!!!");
       }
    }
    void pop(){
       if(top == -1)
          printf("\nStack is Empty!!! Deletion is not possible!!!");
       else{
          printf("\nDeleted : %d", stack[top]);
          top--;
       }
    }
    void display(){
       if(top == -1)
          printf("\nStack is Empty!!!");
       else{
          int i;
          printf("\nStack elements are:\n");
          for(i=top; i>=0; i--)
    	 printf("%d\n",stack[i]);
       }
    }
    21/1/22, 9:20 am - ~K: Chalain ab main room sy Bahir ja rhe hn... Hmary ghar Kam laga hoa hai to mjy call ki awaz ni ay ge apki... Abhi puchna to ni Hai na ap ny kuch or?
    21/1/22, 9:22 am - Tayaba Malik Student: Teacher  code bajhn
    21/1/22, 9:22 am - Tayaba Malik Student: M copy kar l paste kar du...
    21/1/22, 9:22 am - Tayaba Malik Student: Oky
    21/1/22, 9:22 am - Tayaba Malik Student: Oky
    21/1/22, 9:22 am - Tayaba Malik Student: Yh kar du
    21/1/22, 9:24 am - Tayaba Malik Student: Teacher  yh glat hai
    21/1/22, 9:25 am - ~K: Q galat hai
    21/1/22, 9:26 am - ~K: Sirf size change kr dain Iska 10 ki jaga 5 kr dain
    21/1/22, 9:27 am - Tayaba Malik Student: Write  a c ++ to store first 5 even number  in a stack using  array
    21/1/22, 9:27 am - ~K: Acha Acha even krny hain
    21/1/22, 9:28 am - ~K: Phir loop chalana pary ga... Or increment jahan n++ hota hai wahan n+2 kr dain gy
    21/1/22, 9:40 am - Tayaba Malik Student: Write  a c ++ to store first 5 even number  in a stack using  array
    21/1/22, 9:40 am - Tayaba Malik Student: Bs yh karn...
    21/1/22, 9:40 am - Tayaba Malik Student: Yh 3 task thy...
    21/1/22, 9:41 am - Tayaba Malik Student: 1 stack should  be implemented  using link list or aarays
    21/1/22, 9:41 am - Tayaba Malik Student: 2 binary  tree should  be implemented  using double link list
    21/1/22, 9:42 am - Tayaba Malik Student: 3 properly  display preorder ,
    in order, post order
    21/1/22, 9:42 am - Tayaba Malik Student: Ab 1st kar dn
    21/1/22, 9:46 am - ~K: Isi main push k operation main main apko change kra daiti hn
    21/1/22, 6:58 pm - ~K: Tayyaba ap ny aj class laini Hai?
    21/1/22, 7:45 pm - Tayaba Malik Student: Ni
    21/1/22, 7:48 pm - ~K: Or is month main onward laini Hai ap ny class ya tyari krni Hai papers ki?
    21/1/22, 7:49 pm - Tayaba Malik Student: Ni teacher  papers  ki  tiyari
    21/1/22, 7:49 pm - Tayaba Malik Student: Ab days  bht short
    21/1/22, 7:49 pm - ~K: G thk Hai
    23/1/22, 10:32 am - ~K: Assalam u alaikum Tayyaba
    Tooltip or message box ka jo apki teacher ny btaya tha wo zra mjy bta dain
    23/1/22, 10:49 am - Tayaba Malik Student: Waslamm...
    23/1/22, 10:50 am - Tayaba Malik Student: Teacher msg k yh hai... jsy koi  laptop  m update  k msg hta... ata...hai iss tarah  koi msg show karny...
    23/1/22, 10:50 am - Tayaba Malik Student: Tools  k na add karn...
    23/1/22, 10:51 am - ~K: Teacher ny bola hai Yeh?
    23/1/22, 10:51 am - Tayaba Malik Student: Gg
    23/1/22, 10:51 am - ~K: To wo to notification jaisa he ho jay ga na... Or notification to alag sy dalny k liay kaha jo hai apki teacher ny
    23/1/22, 10:51 am - Tayaba Malik Student: M n btya  hamza online  travel  portal  t us m kia tools hn g...
    23/1/22, 10:51 am - Tayaba Malik Student: T unho na kha na dalan
    23/1/22, 10:52 am - Tayaba Malik Student: Gg...
    23/1/22, 10:52 am - ~K: Chalain wo to thk hai
    23/1/22, 10:52 am - Tayaba Malik Student: Lakin notification  aur msg show karny... hn
    23/1/22, 10:52 am - ~K: To phir main notification Wali cheez he dal rhe hn sirf... Ap apni teacher ko btaiay ga k hm ny isi ko as a message box b use kia hai
    23/1/22, 10:53 am - ~K: Q k notification or message Wali cheez same lag rhe Hai mjy jaisy apki teacher keh rhe hain
    23/1/22, 10:53 am - Tayaba Malik Student: Oky
    23/1/22, 10:53 am - Tayaba Malik Student: G
    23/1/22, 10:53 am - Tayaba Malik Student: Oky  theek hai
    23/1/22, 10:53 am - ~K: Or baki ap ny project apni teacher ko mail krna Hai?
    23/1/22, 10:54 am - Tayaba Malik Student: Teacher ... Google  class room m upload  karna ... aj rat 12 s phly
    23/1/22, 10:54 am - Tayaba Malik Student: Aur phir us k lab m presentation  karni
    23/1/22, 10:54 am - ~K: G thk hai
    23/1/22, 10:54 am - ~K: Presentation iski apki kal hoge?
    23/1/22, 10:55 am - Tayaba Malik Student: Yh ni pta abhi... koi shedule  ni aya abhi tak
    23/1/22, 10:55 am - Tayaba Malik Student: Tuesday  yh Wednesday  k bi h sakti
    23/1/22, 10:56 am - ~K: Mtlb bahd main smja don main apko uska prototype koi issue to ni na?
    23/1/22, 10:56 am - Tayaba Malik Student: G kal samja  dna..
    23/1/22, 10:57 am - Tayaba Malik Student: Lakin aj raat tak iss k complete karna... hai
    23/1/22, 10:57 am - ~K: G g wo ho jay ga
    23/1/22, 10:57 am - Tayaba Malik Student: Oky
    23/1/22, 10:57 am - Tayaba Malik Student: TY
    23/1/22, 10:58 am - ~K: Koshish krti hn main sham tk he ho jay
    23/1/22, 10:58 am - Tayaba Malik Student: Oky
    23/1/22, 12:41 pm - ~K: Tayyaba apko uni k ilawa what's app per teacher sy rabta krna allowed hota hai?
    23/1/22, 12:42 pm - ~K: Mtlb what's app ya mail wagaira kr skty hain agr kuch puchna ho to?
    23/1/22, 1:31 pm - Tayaba Malik Student: Ni
    23/1/22, 7:46 pm - Tayaba Malik Student: Teacher  project???
    23/1/22, 7:47 pm - ~K: Bs bejh rhe hn adhy Ganty tk
    23/1/22, 7:50 pm - Tayaba Malik Student: Oky
    23/1/22, 8:30 pm - ~K: Email kron apko project ya what's app
    23/1/22, 9:40 pm - Tayaba Malik Student: What's app
    23/1/22, 9:41 pm - ~K: isko aik br...run kr k...check kr k send kijiay ga
    23/1/22, 9:41 pm - ~K: <Media omitted>
    23/1/22, 9:42 pm - Tayaba Malik Student: Oky
    23/1/22, 9:42 pm - ~K: is file ko khol lain ge ap figma main?
    23/1/22, 9:42 pm - Tayaba Malik Student: Ok teacher
    23/1/22, 9:43 pm - Tayaba Malik Student: Thanku teacher
    23/1/22, 9:44 pm - ~K: my pleasure
    23/1/22, 9:44 pm - Tayaba Malik Student: ♥️
    23/1/22, 9:44 pm - ~K: baki mera dil tha ap isko...aik br daikh k send krain
    23/1/22, 9:45 pm - Tayaba Malik Student: Pissy phir next month after papers
    23/1/22, 9:45 pm - ~K: sari cheezain...design wagaira daikh k
    23/1/22, 9:45 pm - Tayaba Malik Student: <Media omitted>
    23/1/22, 9:45 pm - ~K: G G no problem
    23/1/22, 9:45 pm - ~K: yeh kya hai
    23/1/22, 9:45 pm - Tayaba Malik Student: Teacher m check  karti kal thora time nikal k... smjha jna..
    23/1/22, 9:45 pm - Tayaba Malik Student: Dna*
    23/1/22, 9:46 pm - Tayaba Malik Student: Dare sheet finals ki
    23/1/22, 9:46 pm - ~K: ok
    23/1/22, 9:46 pm - ~K: tyari kaisi hai apki papers ki?
    23/1/22, 9:47 pm - Tayaba Malik Student: Teacher  kar rahi dua karn...
    23/1/22, 9:47 pm - Tayaba Malik Student: Koi issue  hua t ap s contact  karu gi...
    23/1/22, 9:47 pm - ~K: in shaa ALLAH...mehnat krain baki ALLAH malik hai
    23/1/22, 9:47 pm - ~K: g g sure
    23/1/22, 9:47 pm - ~K: baki best of luck apky papers k liay
    23/1/22, 9:49 pm - Tayaba Malik Student: ♥️♥️♥️
    24/1/22, 6:49 pm - ~K: Tyabba ap ny prototype kab smjni hai?
    24/1/22, 7:25 pm - Tayaba Malik Student: Ni teacher  chutain  h gi hn.... ab Monday  k jna direct  papers
    24/1/22, 7:26 pm - ~K: Present ni krna mtlb abhi?
    24/1/22, 7:27 pm - Tayaba Malik Student: Ni teacher  ni krna...
    24/1/22, 7:27 pm - Tayaba Malik Student: Ab Monday  k jna hai...  papers   k liya
    24/1/22, 7:27 pm - Tayaba Malik Student: Covid  ki wajha s bnd h gi...
    24/1/22, 7:27 pm - ~K: Chalain thk ho gya
    24/1/22, 7:28 pm - ~K: Unis band kr di hain inho ny? Ya finals sy pehly jo chutya hoti hain yeh wo hoi hain apko
    24/1/22, 7:28 pm - Tayaba Malik Student: Covid ki wajha s bnd ki
    24/1/22, 7:29 pm - Tayaba Malik Student: Hamri class m 4 bachon k
    24/1/22, 7:29 pm - Tayaba Malik Student: Aur  hostel  m b sab k ....
    24/1/22, 7:29 pm - ~K: Or paper apky on campus he hon gy?
    24/1/22, 7:29 pm - Tayaba Malik Student: Ggg
    24/1/22, 7:29 pm - Tayaba Malik Student: Abhi Tak ... yh hi hai oncampus... lkin latest notification  na ahya.....
    24/1/22, 7:30 pm - Tayaba Malik Student: Agar government  n bnd kar diya.... yh semester  agay hua j....b
    24/1/22, 7:30 pm - ~K: Ho skta hai kr dain online.. Lets see
    24/1/22, 7:30 pm - Tayaba Malik Student: Phir us k according  shedule  h ga
    24/1/22, 7:30 pm - Tayaba Malik Student: Hmm
    24/1/22, 7:30 pm - Tayaba Malik Student: Agr online  paper huy... t ap b Ready rehna...
    24/1/22, 7:30 pm - ~K: Gov ny band ki to b paper ni krain gy yeh online?
    24/1/22, 7:31 pm - Tayaba Malik Student: Ap k pass aha k du gi
    24/1/22, 7:31 pm - ~K: Meharbani krooo
    24/1/22, 7:31 pm - Tayaba Malik Student: Gg
    24/1/22, 7:31 pm - ~K: Mjy to aisa lag rha Hai... Mera kisi ny uni main dobara admission kra dia hai
    24/1/22, 7:31 pm - Tayaba Malik Student: Asa hi smajhn
    24/1/22, 7:32 pm - ~K: Ni ap bhala krain yeh khud tyari kr k dain😂Warna mjy dua krni pary ge k online na hon
    24/1/22, 7:32 pm - Tayaba Malik Student: Ni teacher...
    24/1/22, 7:32 pm - ~K: Khair chalain jo b ho... Acha ho bs apky haq main
    24/1/22, 7:32 pm - Tayaba Malik Student: Inshallah
    24/1/22, 7:32 pm - Tayaba Malik Student: Dua karn... meri b degrees  hbjya
    24/1/22, 7:33 pm - ~K: Ho jay ge... Is azab sy nikal jayn ge ap b
    24/1/22, 7:33 pm - ~K: Phir bahd main... Ap b Mera trah kisi or ko nikalny main help krna 😅
    24/1/22, 7:33 pm - Tayaba Malik Student: Kar hi na du....
    24/1/22, 7:34 pm - Tayaba Malik Student: Apni kar k sukar  ada karu gi
    24/1/22, 7:34 pm - ~K: 😂
    24/1/22, 7:34 pm - ~K: Acha ap ny wo project to yakeenan khol k ni daikha hoga
    24/1/22, 7:34 pm - Tayaba Malik Student: Ni teacher  ... ni open kia... Time hi ni mila
    24/1/22, 7:35 pm - Tayaba Malik Student: Aj test hty rahy covid...k
    24/1/22, 7:35 pm - Tayaba Malik Student: Ambulance  ati aur bachon  k l jati...
    24/1/22, 7:35 pm - Tayaba Malik Student: Vaccination  hti  rahi
    24/1/22, 7:35 pm - ~K: Sb ko ly k gay?
    24/1/22, 7:35 pm - ~K: O ho ho... Yeh to sae phir apka pura din isi main guzar gya hoga
    24/1/22, 7:35 pm - Tayaba Malik Student: Gg
    24/1/22, 7:36 pm - Tayaba Malik Student: Phly hostel k...
    24/1/22, 7:36 pm - Tayaba Malik Student: Bad m departments k
    24/1/22, 7:36 pm - Tayaba Malik Student: Gg...
    24/1/22, 7:36 pm - ~K: Acha chalain... Ap.. Jb agr academy papers k bahd academy ayn ge na... To tb main apko dikha don ge
    24/1/22, 7:36 pm - ~K: Ya kisi din online class main dikha don ge
    24/1/22, 7:36 pm - Tayaba Malik Student: Oky
    24/1/22, 7:36 pm - ~K: Acha aik or bt... Apky is dono projects k jb b number ayn gy to mjy btaiay ga
    24/1/22, 7:37 pm - ~K: In*
    24/1/22, 7:37 pm - Tayaba Malik Student: Oky
    25/1/22, 3:37 pm - Tayaba Malik Student: A.o.a teacher yh open ni h raha hai... ap n apny emil p bnya hai... t ID aur password  dn....
    25/1/22, 3:37 pm - Tayaba Malik Student: Kal iss  project  ki  presentation  hai online
    25/1/22, 3:50 pm - ~K: Main share krti hn yeh project
    25/1/22, 3:50 pm - ~K: Email btayn mjy apni koi
    25/1/22, 3:52 pm - Tayaba Malik Student: tayaba1389@gmail.com 
    03042030887
    25/1/22, 3:55 pm - ~K: Mail check krain zra apni
    25/1/22, 3:55 pm - Tayaba Malik Student: Mil gya
    25/1/22, 3:55 pm - ~K: Link aya hai koi?
    25/1/22, 3:55 pm - Tayaba Malik Student: Pdf bjo
    25/1/22, 3:56 pm - Tayaba Malik Student: Sorry
    25/1/22, 3:56 pm - Tayaba Malik Student: Ap k.ni karna tha
    25/1/22, 3:56 pm - ~K: Mjy yeh btay... Mail main apko koi link aya ya kya?
    25/1/22, 3:56 pm - ~K: Is mail per
    25/1/22, 3:56 pm - Tayaba Malik Student: G aha gi hai
    25/1/22, 3:57 pm - ~K: Check kr lain usy khol k... K open ho rha hai ya ni
    25/1/22, 3:58 pm - ~K: Or aj phir isko ap smj b lijiay ga agr ap ny kal present krna Hai to
    25/1/22, 3:59 pm - Tayaba Malik Student: Oky
    25/1/22, 7:02 pm - ~K: Ap ny prototype ka jb smjna hoa mjy bta dijiay ga
    25/1/22, 7:03 pm - Tayaba Malik Student: 7 30 tak...
    25/1/22, 7:32 pm - ~K: G should we start?
    25/1/22, 7:33 pm - Tayaba Malik Student: Sure
    25/1/22, 7:33 pm - Tayaba Malik Student: Lap top lagti 5 minutes
    25/1/22, 7:33 pm - ~K: Btayn on kr k
    25/1/22, 7:41 pm - Tayaba Malik Student: Yes  teacher  h gya
    27/1/22, 10:10 am - Tayaba Malik Student: A.o.a teacher yh j figma ki file hai iss k ss bjhn...
    27/1/22, 10:10 am - Tayaba Malik Student: Har Web page k....
    27/1/22, 10:11 am - Tayaba Malik Student: Prototyping  connections  k b
    27/1/22, 10:11 am - Tayaba Malik Student: Aur iss m serial effect hai???
    27/1/22, 10:36 am - ~K: Effects to hain obviously laiken as such main ny specify kr k ni lagay k yeh is sequence ka yeh word ya yeh button serial position effect main count hoga
    27/1/22, 10:44 am - Tayaba Malik Student: Gg
    27/1/22, 10:44 am - Tayaba Malik Student: Ss baj dn
    27/1/22, 10:48 am - ~K: <Media omitted>
    27/1/22, 10:49 am - ~K: <Media omitted>
    27/1/22, 10:51 am - Tayaba Malik Student: Teacher  interphase  k Web pegaes  k ss  bjhn
    27/1/22, 10:51 am - Tayaba Malik Student: Aur prototyping  k j arrow hn un k b
    27/1/22, 10:51 am - ~K: Apki presentation hoi ni abhi tk?
    27/1/22, 10:52 am - Tayaba Malik Student: Ni
    27/1/22, 10:52 am - ~K: Kab hai?
    27/1/22, 10:52 am - Tayaba Malik Student: Aj 1 bjy
    27/1/22, 10:52 am - ~K: Acha main laptop on krti hn to phir bejh don ge
    27/1/22, 10:52 am - Tayaba Malik Student: Ok
    27/1/22, 10:52 am - ~K: Agr apka laptop on hai... To figma main apky account main para hai project wo
    27/1/22, 11:04 am - Tayaba Malik Student: Teacher  whn ni open h raha
    27/1/22, 11:04 am - Tayaba Malik Student: Aur na dusri  laki k pas
    27/1/22, 11:05 am - Tayaba Malik Student: Iss liya teacher s kha k report  p connections j bny us k aur webpages k ss lga k submit  karyn
    27/1/22, 11:05 am - Tayaba Malik Student: Aur viva dn
    27/1/22, 11:14 am - ~K: Apko run kr k ss bejhny hain ya bagair run kiay?
    27/1/22, 11:15 am - Tayaba Malik Student: Run k baghir
    27/1/22, 11:15 am - Tayaba Malik Student: Har Web page k
    27/1/22, 11:15 am - Tayaba Malik Student: Aur h connections hn us k
    27/1/22, 11:15 am - ~K: Ap zra... Call per aa skti hain 2 min k liay?
    27/1/22, 11:23 am - ~K: <Media omitted>
    27/1/22, 11:29 am - Tayaba Malik Student: Ok
    27/1/22, 11:29 am - Tayaba Malik Student: TY
    27/1/22, 11:34 am - ~K: <Media omitted>
    27/1/22, 11:36 am - ~K: is picture main bht chota to ni lag rha ?
    27/1/22, 11:37 am - ~K: <Media omitted>
    27/1/22, 11:39 am - ~K: <Media omitted>
    27/1/22, 11:39 am - ~K: kafi hain?
    27/1/22, 11:39 am - Tayaba Malik Student: Ik login wala bj dn
    27/1/22, 11:39 am - Tayaba Malik Student: Bs
    27/1/22, 11:40 am - ~K: ok
    27/1/22, 11:40 am - ~K: <Media omitted>
    27/1/22, 11:41 am - Tayaba Malik Student: Ok
    27/1/22, 11:41 am - Tayaba Malik Student: Bs theek hai
    27/1/22, 1:10 pm - Tayaba Malik Student: Teacher
    27/1/22, 1:16 pm - Tayaba Malik Student: <Media omitted>
    27/1/22, 1:16 pm - Tayaba Malik Student: CV on figma
    27/1/22, 1:16 pm - ~K: Kya hai Yeh
    27/1/22, 1:17 pm - Tayaba Malik Student: Yh 2 task hain
    27/1/22, 1:17 pm - Tayaba Malik Student: Y b karna...
    27/1/22, 1:17 pm - Tayaba Malik Student: Kal s phly....
    27/1/22, 1:17 pm - Tayaba Malik Student: Ik figma p CV bnani
    27/1/22, 1:17 pm - Tayaba Malik Student: Qualification  khud s koi b zyda dal dn....
    27/1/22, 1:18 pm - Tayaba Malik Student: Aur ik yh task
    27/1/22, 1:18 pm - ~K: Tayyaba yeh to apko khud krna pary ga... Q k aj kal khair sy meri tabiat nasaz chal rhe hai
    27/1/22, 1:18 pm - ~K: Too....Yeh wala abhi ap khud kr lain
    27/1/22, 1:18 pm - Tayaba Malik Student: Teacher  4 hn
    27/1/22, 1:18 pm - Tayaba Malik Student: M 2 dusry kar rahi
    27/1/22, 1:19 pm - Tayaba Malik Student: Ik t abhi madam phara rahi
    27/1/22, 1:19 pm - ~K: To baki group members ko 2 bnany k liay keh dain na
    27/1/22, 1:19 pm - Tayaba Malik Student: Aur Monday k paper math k
    27/1/22, 1:19 pm - Tayaba Malik Student: Ni teacher  akely bnani
    27/1/22, 1:20 pm - Tayaba Malik Student: Acha ik kar dn
    27/1/22, 1:20 pm - Tayaba Malik Student: Yh wala
    27/1/22, 1:20 pm - Tayaba Malik Student: Cv m bna  lu gi
    27/1/22, 1:20 pm - ~K: Kab tk jama krana hai Yeh?
    27/1/22, 1:20 pm - Tayaba Malik Student: Kal tak
    27/1/22, 1:20 pm - ~K: Sb ko same mila hai?
    27/1/22, 1:21 pm - Tayaba Malik Student: Parson marks lagny
    27/1/22, 1:21 pm - Tayaba Malik Student: Gg
    27/1/22, 1:21 pm - ~K: To kisi frnd sy ly laina na ap yeh
    27/1/22, 1:21 pm - Tayaba Malik Student: Ni teacher 0 lag jty
    27/1/22, 1:21 pm - ~K: Or masla ni Hai... Main bna daiti... Per meri awaz ap ny suni the na call per
    27/1/22, 1:21 pm - Tayaba Malik Student: Gg
    27/1/22, 1:22 pm - Tayaba Malik Student: Ok m karti kuch
    27/1/22, 1:22 pm - ~K: Koshish krain khud arrange agr hota hai to
    27/1/22, 1:22 pm - Tayaba Malik Student: Oky
    27/1/22, 5:41 pm - Tayaba Malik Student: <Media omitted>
    27/1/22, 5:42 pm - Tayaba Malik Student: <Media omitted>
    27/1/22, 5:43 pm - Tayaba Malik Student: <Media omitted>
    27/1/22, 5:44 pm - Tayaba Malik Student: <Media omitted>
    27/1/22, 5:44 pm - Tayaba Malik Student: Teacher yh bna dn 4
    27/1/22, 5:44 pm - Tayaba Malik Student: Chotti chotti hn...
    27/1/22, 5:44 pm - Tayaba Malik Student: Ik ik functions lgny
    27/1/22, 5:44 pm - Tayaba Malik Student: Plz
    ...
    27/1/22, 5:45 pm - Tayaba Malik Student: 15 number  hn
    27/1/22, 5:45 pm - Tayaba Malik Student: Average  kharab h jya gi..
    27/1/22, 7:19 pm - ~K: Yeh Hai kya cheez... Kis subject ki hai
    27/1/22, 8:21 pm - Tayaba Malik Student: Yh lab reports hai.
    27/1/22, 8:21 pm - Tayaba Malik Student: ...
    27/1/22, 8:21 pm - ~K: Yeh kab submit krani hain a ap ny
    27/1/22, 8:21 pm - Tayaba Malik Student: Kal
    27/1/22, 8:21 pm - Tayaba Malik Student: Rat tak...
    27/1/22, 8:22 pm - ~K: 4ron?
    27/1/22, 8:22 pm - Tayaba Malik Student: Teacher dekhn ik minute  in k hain bht choti
    27/1/22, 8:22 pm - Tayaba Malik Student: Gg
    27/1/22, 8:22 pm - Tayaba Malik Student: Na itny Web pages  dlny
    27/1/22, 8:22 pm - ~K: Ni hai choti.. Acha bhala Kam hai is main krny wala
    27/1/22, 8:22 pm - Tayaba Malik Student: Ik ik functions hain
    27/1/22, 8:22 pm - ~K: Aik khol k parha Hai main ny
    27/1/22, 8:22 pm - Tayaba Malik Student: Teacher  kar dn plz...
    27/1/22, 8:23 pm - Tayaba Malik Student: Mery sab m 15 m s 11 12 13 14 marks
    27/1/22, 8:23 pm - Tayaba Malik Student: Bs yh reh gai....
    27/1/22, 8:23 pm - Tayaba Malik Student: Madam na kha kal tak karwa dn m Markes kar du gi
    27/1/22, 8:23 pm - Tayaba Malik Student: Monnday  k paper
    27/1/22, 8:23 pm - ~K: Acha main baki apko parh k btati hn
    27/1/22, 8:23 pm - Tayaba Malik Student: Oky
    27/1/22, 8:24 pm - Tayaba Malik Student: Itna zyda na karna jitna project  m kia...
    27/1/22, 8:24 pm - ~K: Per jitna apki teacher ny mention kia hoga... Wo to krna pary ga na
    27/1/22, 8:25 pm - Tayaba Malik Student: Hm
    27/1/22, 8:25 pm - ~K: Ap call per ayn zra
    27/1/22, 8:38 pm - Tayaba Malik Student: <Media omitted>
    27/1/22, 8:38 pm - Tayaba Malik Student: <Media omitted>
    27/1/22, 9:07 pm - Tayaba Malik Student: <Media omitted>
    27/1/22, 9:07 pm - Tayaba Malik Student: Lab 13 b cottool  p karni
    27/1/22, 9:07 pm - Tayaba Malik Student: Aur time nikalna hau
    27/1/22, 9:07 pm - Tayaba Malik Student: Hai*
    27/1/22, 9:20 pm - ~K: Han g wo parha Hai main ny... Wo direct usi tool per bnana pary ga
    27/1/22, 9:27 pm - Tayaba Malik Student: Oky
    27/1/22, 9:28 pm - ~K: Charges main apko kal tk bta don ge... Teeno ko kal tk main daikh lon ge sae sy phir bta don ge apko
    27/1/22, 9:28 pm - ~K: <Media omitted>
    27/1/22, 9:39 pm - ~K: <Media omitted>
    27/1/22, 10:00 pm - Tayaba Malik Student: Ok
    27/1/22, 10:01 pm - Tayaba Malik Student: Gg ok ....
    27/1/22, 10:01 pm - ~K: Aik or cheez b.. Apki 12 Wali report main design ni bnana
    27/1/22, 10:01 pm - ~K: <Media omitted>
    27/1/22, 10:02 pm - ~K: <Media omitted>
    27/1/22, 10:03 pm - Tayaba Malik Student: Teacher w cogtool p bnani hai... aur figma  s cogtool  p ni lar skaty
    27/1/22, 10:03 pm - Tayaba Malik Student: Teacher ... m 12 bna lati
    27/1/22, 10:03 pm - ~K: G... Wo wahan alag sy he krna pary ga apki lapreport 6 k liay
    27/1/22, 10:03 pm - Tayaba Malik Student: 12 chor dn
    27/1/22, 10:03 pm - ~K: Thk Hai... 6 or 13 ko daikhti hn main
    27/1/22, 10:03 pm - Tayaba Malik Student: <Media omitted>
    27/1/22, 10:03 pm - Tayaba Malik Student: <Media omitted>
    27/1/22, 10:03 pm - Tayaba Malik Student: Yh kar dn
    27/1/22, 10:04 pm - Tayaba Malik Student: Ab ... 7 12 14 aur 2 m khud kar lati
    27/1/22, 10:04 pm - ~K: G g inhi ko daikhny lage hn ab
    27/1/22, 10:04 pm - Tayaba Malik Student: Ok
    27/1/22, 10:04 pm - ~K: Q k in main technical kam hai ni as such... Likhny wali cheezain he hain
    27/1/22, 10:05 pm - Tayaba Malik Student: G
    27/1/22, 10:05 pm - Tayaba Malik Student: Oky
    28/1/22, 10:32 am - ~K: <Media omitted>
    28/1/22, 10:35 am - Tayaba Malik Student: Waslam  teacher....koi class ni hai...
    28/1/22, 10:35 am - Tayaba Malik Student: Teacher  short kam karn.... bs
    28/1/22, 10:39 am - ~K: <Media omitted>
    28/1/22, 10:57 am - Tayaba Malik Student: Abhi 13 krny lgi ho?
    28/1/22, 10:57 am - Tayaba Malik Student: Axha 13 hoi to mjhe send krnaa
    28/1/22, 10:57 am - Tayaba Malik Student: Pucha hai t yh
    28/1/22, 10:58 am - Tayaba Malik Student: Teacher zdya deeply  na kRn check  karni ni ksi na....
    28/1/22, 10:58 am - Tayaba Malik Student: Bs submit  karny s marks mil jyn g
    28/1/22, 11:24 am - ~K: Lo g... Ap ny pucha apki saheli ny to mangna Shuro kr dia
    28/1/22, 12:10 pm - ~K: <Media omitted>
    28/1/22, 12:13 pm - Tayaba Malik Student: Ok
    28/1/22, 12:22 pm - ~K: Jaldi puch k btay
    28/1/22, 12:22 pm - Tayaba Malik Student: Teacher  ss bjhn kia issue hai
    28/1/22, 12:22 pm - Tayaba Malik Student: W kha rahy hmara t chl raha
    28/1/22, 12:22 pm - ~K: <Media omitted>
    28/1/22, 12:22 pm - ~K: <Media omitted>
    28/1/22, 12:24 pm - Tayaba Malik Student: Ok
    28/1/22, 12:24 pm - Tayaba Malik Student: <Media omitted>
    28/1/22, 12:24 pm - Tayaba Malik Student: Version yh wala
    28/1/22, 12:25 pm - Tayaba Malik Student: Teacher  bs j hta bna dn beshak puri na bnyn
    28/1/22, 12:25 pm - Tayaba Malik Student: Teacher  n check ni karni
    28/1/22, 12:26 pm - ~K: <Media omitted>
    28/1/22, 12:27 pm - Tayaba Malik Student: G
    28/1/22, 12:27 pm - Tayaba Malik Student: Ok
    28/1/22, 12:27 pm - ~K: Yeh pta ni shayd Mery system k sath ni ho rha compatible
    28/1/22, 12:27 pm - Tayaba Malik Student: Bs j j gya  sahi hai
    28/1/22, 12:28 pm - Tayaba Malik Student: Check  ni karna ksi na
    28/1/22, 12:29 pm - ~K: <Media omitted>
    28/1/22, 12:29 pm - ~K: Yeh hoa hai phir filhal to
    28/1/22, 12:29 pm - Tayaba Malik Student: Yh manual  kn s
    28/1/22, 12:30 pm - ~K: Website Wali cheez is main include kra k... Non interactive widget mention kiay hain main ny first frame k
    28/1/22, 12:30 pm - ~K: 6
    28/1/22, 12:30 pm - Tayaba Malik Student: Ok
    28/1/22, 12:30 pm - Tayaba Malik Student: M submit  karwati
    28/1/22, 12:30 pm - ~K: <Media omitted>
    28/1/22, 12:30 pm - ~K: O sbr kr jaoooo... Yeh audio sun lo pehly
    28/1/22, 12:31 pm - Tayaba Malik Student: Oky  .... koi ni
    28/1/22, 12:31 pm - ~K: Aisy he submit krany lage ho ap?
    28/1/22, 12:31 pm - Tayaba Malik Student: G
    28/1/22, 12:31 pm - ~K: Ok
    28/1/22, 12:31 pm - ~K: <Media omitted>
    28/1/22, 12:33 pm - Tayaba Malik Student: Ok.... koi assumed time  dl k calculations  kar lna
    28/1/22, 12:33 pm - ~K: Ok
    28/1/22, 1:29 pm - ~K: <Media omitted>
    28/1/22, 1:30 pm - ~K: Labreport 13 Waly ki
    28/1/22, 1:52 pm - Tayaba Malik Student: Gg ok
    28/1/22, 1:52 pm - Tayaba Malik Student: Sahi hai
    28/1/22, 7:04 pm - ~K: Tayyaba yeh 13 wala main apko rat tk bejh don ge
    28/1/22, 7:13 pm - Tayaba Malik Student: Ok
    28/1/22, 8:03 pm - ~K: Yeh wala ap ny submit kra dia hai?
    28/1/22, 8:07 pm - ~K: <Media omitted>
    28/1/22, 8:10 pm - Tayaba Malik Student: Gg
    28/1/22, 8:10 pm - ~K: ni krana tha...uska b reaction time main calculate kr daiti apko
    28/1/22, 8:10 pm - Tayaba Malik Student: Teacher  is ki file  bjhn
    28/1/22, 8:10 pm - ~K: khair chalain wo ab kra dia hai to
    28/1/22, 8:11 pm - Tayaba Malik Student: G
    28/1/22, 8:11 pm - ~K: g wo b main bejhti hn apko
    28/1/22, 8:11 pm - Tayaba Malik Student: Oky
    28/1/22, 8:12 pm - ~K: <Media omitted>
    28/1/22, 8:12 pm - ~K: <Media omitted>
    28/1/22, 8:12 pm - Tayaba Malik Student: Ok tY
    28/1/22, 8:13 pm - Tayaba Malik Student: Teacher  sahi hai  j b hai
    28/1/22, 8:13 pm - ~K: Or formula main solve kr k main bejhti hn... Wo b confirm kr Laina
    28/1/22, 8:15 pm - Tayaba Malik Student: Ok
    28/1/22, 8:21 pm - ~K: <Media omitted>
    28/1/22, 8:23 pm - Tayaba Malik Student: Teacher  yh file  upload  ni h rahi
    28/1/22, 8:23 pm - Tayaba Malik Student: Google class room p
    28/1/22, 8:23 pm - ~K: <Media omitted>
    28/1/22, 8:23 pm - ~K: Q?
    28/1/22, 8:23 pm - ~K: Kya likha aa rha hai
    28/1/22, 8:24 pm - Tayaba Malik Student: File  show ni h rahi
    28/1/22, 8:24 pm - ~K: Picture bejhain
    28/1/22, 8:25 pm - Tayaba Malik Student: Teacher  isss file k open  karn apny pass. .. aur  ss l k word p paste kar k... bj dn
    28/1/22, 8:25 pm - Tayaba Malik Student: Sath yh b lga dn
    28/1/22, 8:25 pm - ~K: Kis interface ka ss bejhon?
    28/1/22, 8:25 pm - Tayaba Malik Student: Gg
    28/1/22, 8:25 pm - Tayaba Malik Student: Interphase  k
    28/1/22, 8:32 pm - ~K: <Media omitted>
    28/1/22, 8:32 pm - ~K: aik br khol k daikh lijiay ga
    28/1/22, 8:32 pm - Tayaba Malik Student: H gi
    28/1/22, 8:32 pm - Tayaba Malik Student: Ok
    28/1/22, 8:32 pm - Tayaba Malik Student: TY
    28/1/22, 8:32 pm - Tayaba Malik Student: Teacher  ab payment  bta dn..
    28/1/22, 8:33 pm - ~K: dono ka ap mjy 3000 dy daina
    28/1/22, 8:33 pm - Tayaba Malik Student: Oky
    28/1/22, 8:33 pm - Tayaba Malik Student: 8000
    28/1/22, 8:33 pm - ~K: per ALLAH puchy ga larki tmy...bemari main mery sy kam kraya hai
    28/1/22, 8:34 pm - Tayaba Malik Student: Sorry  teacher...
    28/1/22, 8:34 pm - Tayaba Malik Student: So sorry
    28/1/22, 8:34 pm - ~K: han g pichly to mila k takreban itny he banty hain
    28/1/22, 8:34 pm - Tayaba Malik Student: Oky
    28/1/22, 8:34 pm - ~K: abhi kam apka ho gya to abhi sorry😂
    28/1/22, 8:34 pm - ~K: khair koi bt ni....ho gya sae bs
    28/1/22, 8:34 pm - Tayaba Malik Student: Hahah
    28/1/22, 8:35 pm - Tayaba Malik Student: TY
    28/1/22, 8:35 pm - Tayaba Malik Student: Alot
    28/1/22, 8:35 pm - ~K: <Media omitted>
    28/1/22, 8:35 pm - ~K: No problem 🌸
    28/1/22, 8:36 pm - Tayaba Malik Student: Koi ni... teacher na check  karna koi ni
    28/1/22, 8:36 pm - ~K: Chalain g time sy pehly ho gya yeh bs sae ho gya
    28/1/22, 8:36 pm - ~K: Dosry waly apky ban gay hain?
    28/1/22, 8:36 pm - Tayaba Malik Student: G... 2 bny
    28/1/22, 8:36 pm - Tayaba Malik Student: Bs...
    28/1/22, 8:36 pm - Tayaba Malik Student: Ik ratha...
    28/1/22, 8:36 pm - Tayaba Malik Student: W rat k banu gi
    28/1/22, 8:37 pm - ~K: Thk Hai g
    28/1/22, 8:37 pm - Tayaba Malik Student: ♥️
    31/1/22, 6:50 pm - ~K: Tyabba apko sir ny location send ki hai?
    31/1/22, 7:09 pm - Tayaba Malik Student: Kon si location
    31/1/22, 7:09 pm - Tayaba Malik Student: Kin sir na
    31/1/22, 7:21 pm - Tayaba Malik Student: Teacher  btyn na....
    31/1/22, 7:21 pm - ~K: Sir Hamad ny
    31/1/22, 7:22 pm - ~K: Academy change ho gai hai na q k
    31/1/22, 7:22 pm - Tayaba Malik Student: Kis ki location
    31/1/22, 7:22 pm - Tayaba Malik Student: Where
    31/1/22, 7:22 pm - ~K: Seeds school pta hai apko?
    31/1/22, 7:22 pm - Tayaba Malik Student: Ni
    31/1/22, 7:22 pm - ~K: Kindergarten?
    31/1/22, 7:22 pm - Tayaba Malik Student: Khan p hai kis Road  p
    31/1/22, 7:22 pm - Tayaba Malik Student: Eid gha k pass
    31/1/22, 7:23 pm - ~K: Eid gaw road per
    31/1/22, 7:23 pm - Tayaba Malik Student: Oky
    31/1/22, 7:23 pm - Tayaba Malik Student: Seed school  s kidhar hai
    31/1/22, 7:23 pm - ~K: Han g... Eid gaw road per jo seeds school hai na... Udhar hai ab academy
    31/1/22, 7:23 pm - Tayaba Malik Student: Ok
    31/1/22, 7:23 pm - ~K: Ap ny kab ana hoga?
    31/1/22, 7:23 pm - Tayaba Malik Student: Teacher... ap k ghar khan hai
    31/1/22, 7:24 pm - ~K: Mery ghar ko kya krna Hai udhar ana hai ab? 😂
    31/1/22, 7:24 pm - Tayaba Malik Student: Isss pura week papers... next week m ksi din....
    31/1/22, 7:24 pm - Tayaba Malik Student: Gg...
    31/1/22, 7:24 pm - ~K: Tehsil road Wali side per hai waisy
    31/1/22, 7:24 pm - Tayaba Malik Student: M udhar aha jau gi....
    31/1/22, 7:24 pm - Tayaba Malik Student: Tehsil Road p kidhar
    31/1/22, 7:24 pm - ~K: Mery ghar?
    31/1/22, 7:24 pm - Tayaba Malik Student: Mera nano k ghar wahn
    31/1/22, 7:24 pm - Tayaba Malik Student: G....
    31/1/22, 7:25 pm - ~K: Ustad mian gamma sahb wala muhallah pta hai apko?
    31/1/22, 7:25 pm - ~K: To idhar mtlb mjy smj ni ai... Kis liay... Online ho rhy hain paper apky?
    31/1/22, 7:25 pm - Tayaba Malik Student: Teacher agly symester  m b j projects  k hua m directly ap s contact  karu gi.... academy  k involve ni karty... wahn j m class lti w hi bsss
    31/1/22, 7:26 pm - Tayaba Malik Student: Ni physically
    31/1/22, 7:26 pm - Tayaba Malik Student: Gg pta hai
    31/1/22, 7:26 pm - ~K: To wo to online main nipta lain gy na hm
    31/1/22, 7:26 pm - Tayaba Malik Student: Ggg
    31/1/22, 7:27 pm - ~K: Baki ap apni ame k cnic per easypaisa bna lain... To wo b jhanjhat khtm ho jay ga
    31/1/22, 7:27 pm - Tayaba Malik Student: Baki projects  ki payment ap k ghar karwa diya karu gi agly symester  s
    31/1/22, 7:27 pm - Tayaba Malik Student: Hmm ok....
    31/1/22, 7:27 pm - ~K: Special paisy dainy k liay kya chakkar lagao ge ab ap.. Process main apko bta don ge ap account bna laina
    31/1/22, 7:28 pm - ~K: Acha mjy yeh btay... Bank account hai apky ghar kisi ka?
    31/1/22, 7:28 pm - Tayaba Malik Student: Jab essipasa bn jya g t wasi karwa diya karu gi....
    31/1/22, 7:28 pm - Tayaba Malik Student: Hai sab k lkin mera ni...
    31/1/22, 7:28 pm - ~K: Han g waisy easy rhy ga apko b
    31/1/22, 7:29 pm - Tayaba Malik Student: Mujy agar chy hty t Mama baba j dn un k cash karwa lati
    31/1/22, 7:29 pm - Tayaba Malik Student: Oky
    31/1/22, 7:29 pm - ~K: Agr ap chahy to ghar main kisi k number per... Internet banking activate kra lain... Or ghar Beth k direct bank account main b transfer kr skti hain
    31/1/22, 7:29 pm - ~K: Yeh b ho skta hai aik tareka
    31/1/22, 7:29 pm - Tayaba Malik Student: Oky
    31/1/22, 7:30 pm - ~K: Mjy bta dijiay ga jo number chahiay hoa apko
    31/1/22, 7:30 pm - Tayaba Malik Student: Oky
    31/1/22, 7:30 pm - ~K: Or number ni pta chaly abhi tk?
    31/1/22, 7:30 pm - ~K: Dsa Waly or HCI Waly project k
    31/1/22, 7:30 pm - Tayaba Malik Student: Ni
    31/1/22, 7:31 pm - ~K: Ok
    31/1/22, 7:31 pm - Tayaba Malik Student: Abhi tak ni btya ksi n....
    31/1/22, 7:31 pm - Tayaba Malik Student: Pta chla t sab s phly ap k batu gi.... call  kar k
    31/1/22, 7:31 pm - ~K: Han bs Allah kr k achy number ay b
    31/1/22, 7:32 pm - Tayaba Malik Student: Ameen
    9/2/22, 7:42 pm - ~K: Assalam u alaikum Tayyaba... Projects ka result ni aya abhi tk?
    9/2/22, 7:42 pm - Tayaba Malik Student: Waslam teacher  ni
    9/2/22, 7:42 pm - Tayaba Malik Student: Aj t papers khatam huy
    9/2/22, 7:44 pm - ~K: Aj khtm hoay hain?
    9/2/22, 7:44 pm - ~K: To yeh grades main number aik sath he apko dal k dain gy?
    9/2/22, 7:44 pm - Tayaba Malik Student: Gg
    9/2/22, 7:45 pm - Tayaba Malik Student: Gg shad  q k abhi tak t ni btya
    9/2/22, 7:48 pm - ~K: Acha chalain phir grades he bta dijiay ga mjy jb ay ga result to
    9/2/22, 7:48 pm - ~K: Or academy kab tk ana hai ap ny?
    9/2/22, 7:48 pm - Tayaba Malik Student: Ok
    9/2/22, 7:48 pm - Tayaba Malik Student: Saturday  inshallah
    9/2/22, 7:48 pm - Tayaba Malik Student: Ap location  bj dn ...
    9/2/22, 7:49 pm - Tayaba Malik Student: Seeds school k kidhar
    9/2/22, 7:49 pm - ~K: G main location bejhti hn apkl6
    9/2/22, 7:49 pm - ~K: Apko *
    9/2/22, 7:49 pm - ~K: Seeds school tha na jidar... Wohe usi building main hai academy
    9/2/22, 7:49 pm - Tayaba Malik Student: Mein ap k call  karu gi guide kar dna ... jab ahu gi
    9/2/22, 7:49 pm - Tayaba Malik Student: Ok
    9/2/22, 7:49 pm - Tayaba Malik Student: Oky
    9/2/22, 7:49 pm - ~K: G thk hai
    9/2/22, 7:49 pm - ~K: Acha mjy yeh btay... Apko next sem k courses ka pta chala... Kon kon sy hon gy?
    9/2/22, 7:50 pm - Tayaba Malik Student: Gg pta chla ... mein ap k us k print du gi
    9/2/22, 7:50 pm - ~K: Soft main ni hai? Pictures wagaira
    9/2/22, 7:50 pm - Tayaba Malik Student: Ni abhi  soft mein ni hain
    9/2/22, 7:51 pm - ~K: Chalain phir jis din ap ayn ge academy usi din print ly aiay ga
    9/2/22, 7:51 pm - ~K: Baki... paper apky hoay kaisy?
    9/2/22, 7:51 pm - Tayaba Malik Student: Ok
    9/2/22, 7:51 pm - Tayaba Malik Student: Theek huy
    9/2/22, 7:51 pm - Tayaba Malik Student: Allah kary results  b Acha h
    9/2/22, 7:51 pm - ~K: Achy result ki umeed kr skty hain na
    9/2/22, 7:51 pm - Tayaba Malik Student: Pta ni
    9/2/22, 7:52 pm - ~K: Chalain Allah behtar kry GA... In shaa Allah
    9/2/22, 7:52 pm - Tayaba Malik Student: Relative  marking
    9/2/22, 7:52 pm - Tayaba Malik Student: Inshallah
    9/2/22, 7:52 pm - Tayaba Malik Student: Location  baj dn
    9/2/22, 7:52 pm - ~K: location: https://maps.google.com/?q=33.5642829,72.6450665
    9/2/22, 7:53 pm - ~K: Is main... Location eidgah road ki hai... Per agy academy usi road per hai
    9/2/22, 7:53 pm - ~K: Seeds school ka pta hai na apko?
    9/2/22, 7:53 pm - Tayaba Malik Student: Ni
    9/2/22, 7:53 pm - Tayaba Malik Student: Ksi s puch lu gi
    9/2/22, 7:53 pm - Tayaba Malik Student: Ponch  jau gi
    9/2/22, 7:54 pm - ~K: G puch lijiay ga... Easily mil jay ge
    9/2/22, 7:54 pm - ~K: Posters wagaira kafi lagy hoay hain Bahir
    9/2/22, 7:55 pm - Tayaba Malik Student: Oky
    12/2/22, 11:12 am - ~K: Tyabba agr ap aj ai to Mery sy mill lijiay ga Lazmi
    12/2/22, 11:12 am - Tayaba Malik Student: G teacher
    12/2/22, 11:12 am - ~K: Plus... Project ki payment academy main ni kijiay ga
    12/2/22, 11:13 am - Tayaba Malik Student: Q
    12/2/22, 11:13 am - Tayaba Malik Student: Can I call u
    12/2/22, 11:13 am - ~K: G kr lain
    12/2/22, 11:27 am - ~K: <Media omitted>
    12/2/22, 11:56 am - Tayaba Malik Student: Oky
    12/2/22, 11:56 am - Tayaba Malik Student: G samj aha gi
    12/2/22, 12:25 pm - ~K: Course list ap ly k aiay ga... Or mjy dikhaiy ga... Or sath he keh daina k teacher meri class start hon ge phir main btaon ge k in main sy koi parhna hai ya ni
    12/2/22, 12:31 pm - Tayaba Malik Student: Ok
    13/2/22, 9:49 am - ~K: Kal ap academy ni the phir tyabba
    13/2/22, 10:14 am - Tayaba Malik Student: Ni teacher  ni ahi
    13/2/22, 10:14 am - Tayaba Malik Student: Teacher  abhi chutian  hain next week mein ksi  din aha jau gi...
    13/2/22, 10:16 am - ~K: To phir ap ny idhar hmari side aj ana hai ya ni
    13/2/22, 10:16 am - Tayaba Malik Student: Ni teacher  aj ni
    13/2/22, 10:17 am - Tayaba Malik Student: Kal parson  tak
    13/2/22, 10:17 am - ~K: Ok
    15/2/22, 7:14 pm - ~K: Tayyaba apka yeh wala sem kab Shuro hoga? Mtlb kis date sy
    15/2/22, 7:14 pm - Tayaba Malik Student: Monday s
    15/2/22, 7:14 pm - Tayaba Malik Student: Yh j aha rahi hai..
    15/2/22, 7:14 pm - ~K: Ok ok
    15/2/22, 7:15 pm - ~K: Or phir chakkar ni lagaya ap ny main ny wait kia ap ka ap ai he ni
    15/2/22, 7:16 pm - Tayaba Malik Student: G teacher  ana hai... Sunday  k iss must ahu gi phir q k University  start  h jya gi time ni mily g
    15/2/22, 7:16 pm - ~K: G or dosra yeh b... K ap apni uni Shuro hony sy pehly apni courses ki list dain mjy
    15/2/22, 7:16 pm - Tayaba Malik Student: Aur academy  k deakhu gi kab ahu yh phir  sir s phone  p. At kar lu gi
    15/2/22, 7:16 pm - Tayaba Malik Student: Gg ok
    15/2/22, 7:17 pm - ~K: Ta k mjy pehly sy idea ho k ap k kon kon sy courses hon gy
    15/2/22, 7:17 pm - Tayaba Malik Student: Ok
    15/2/22, 7:17 pm - ~K: Han yeh b sae hai... Phone per bt kr Laina
    15/2/22, 7:17 pm - Tayaba Malik Student: Ik minute  mein ap k abhi download  kar k bajti
    15/2/22, 7:17 pm - ~K: Or agr... Apka ana mushkil ho rha hai na ya time ni mill rha... To ap apny bhai ko bejh dain... Rasta ghar ka main smja don ge ap unko smja daina
    15/2/22, 7:17 pm - ~K: Mtlb agr in case apko time ni mill rha to
    15/2/22, 7:19 pm - Tayaba Malik Student: Oky
    15/2/22, 7:19 pm - ~K: Or courses ki list b beshak hard main he apny bhai k hath dy bhejiay ga... Phir jo b discussion hoge wo phone per ap Mery sy kr laina
    15/2/22, 7:22 pm - Tayaba Malik Student: CS-303 Operating System 4(3+1) , Dr. Mahwish 
     MT-302 Probability and Statistics 3(3+0), Ms. Rafay Mustafa 
    
     CS-304 Database Systems 4(3+1), Ms. Veena Dilshad 
    
    CS-302 Artificial Intelligence 3(2+1), Dr. Junaid Ali Khan ,Lec. Usama Khalid
    
    SE-202 Software Design and Architecture 3(3+1) , Lec Junaid Ali
    
    
    
    
    
    
    By 
    Dr. Junaid Ali Khan 
    Chairman, Department of Computer Science.
    15/2/22, 7:22 pm - Tayaba Malik Student: Yh course  hain
    15/2/22, 7:22 pm - ~K: Ohhh... Artificial intelligence b hai
    15/2/22, 7:22 pm - Tayaba Malik Student: Hmm
    15/2/22, 7:22 pm - Tayaba Malik Student: Q
    15/2/22, 7:22 pm - Tayaba Malik Student: Muskil  hai
    15/2/22, 7:22 pm - ~K: Or ap ny parhny kon kon sy hain?
    15/2/22, 7:23 pm - Tayaba Malik Student: Ap k pass
    15/2/22, 7:23 pm - ~K: Han thori bht.. Laiken depends upon k apko theory parhay gy ya kya
    15/2/22, 7:23 pm - ~K: G
    15/2/22, 7:23 pm - Tayaba Malik Student: Teacher  weekly hamri ik class  hti har subject  ki
    15/2/22, 7:24 pm - Tayaba Malik Student: T jis din j class  h gi j University  m parhn g ap k pas aha k woh hi kia karu gi
    15/2/22, 7:24 pm - Tayaba Malik Student: Bs maths  nikal dn
    15/2/22, 7:24 pm - Tayaba Malik Student: Probability  wala course  k alwa
    15/2/22, 7:24 pm - Tayaba Malik Student: Sab
    15/2/22, 7:25 pm - ~K: Ary yeh to bht zyada courses ho jay gy larki
    15/2/22, 7:25 pm - Tayaba Malik Student: Ni teacher  kidhar
    15/2/22, 7:26 pm - ~K: 4 courses parhai gi ap mtlb
    15/2/22, 7:26 pm - Tayaba Malik Student: Week mein ik class  h gi just
    15/2/22, 7:26 pm - ~K: Han but courses to alag alag hain na
    15/2/22, 7:26 pm - Tayaba Malik Student: Acha iss mein s coding  wala kon s
    15/2/22, 7:27 pm - ~K: <Media omitted>
    15/2/22, 7:28 pm - ~K: Software design wala to... I guess apky abhi Waly course k jaisa hoga Mery khyal sy... Jo SRE... Ya aisa kuch tha
    15/2/22, 7:30 pm - Tayaba Malik Student: Acha phir classes  start  hn phir batu gi kon kon s parhna
    15/2/22, 7:30 pm - Tayaba Malik Student: J mujy muskil lga w ap s parhu gi
    15/2/22, 7:31 pm - ~K: G thk hai
    15/2/22, 7:31 pm - ~K: Operating system ka to main apko confirm bta daiti hn wo mushkil lagy ga apko
    15/2/22, 7:31 pm - Tayaba Malik Student: Oky
    15/2/22, 7:31 pm - ~K: To agr ap ny wo parhna hoa... To koshish kijiay ga... Uni k sath he Shuro kijiay ga
    15/2/22, 7:31 pm - Tayaba Malik Student: Mujy t sab hi muskil lag rahy
    15/2/22, 7:31 pm - ~K: Q k phir uni waly nikal jaty hain phir cover kr pana Thora mushkil hota hai
    15/2/22, 7:31 pm - Tayaba Malik Student: Oky
    15/2/22, 7:32 pm - Tayaba Malik Student: Hmm ok
    15/2/22, 7:32 pm - Tayaba Malik Student: Sath hi start karn g
    15/2/22, 7:33 pm - ~K: G sae hai
    15/2/22, 7:34 pm - ~K: Or baki ap sy time ni nikal rha to beshak bhai ko bejh dijiay ga no issue
    15/2/22, 7:34 pm - Tayaba Malik Student: Oky
    21/2/22, 10:28 am - ~K: Tayabba ap ny sir ko call ki the phir?
    21/2/22, 10:52 am - Tayaba Malik Student: Ni ki teacher
    21/2/22, 10:53 am - Tayaba Malik Student: Abhi ghar j k karti... fees submit  karny ahi
    21/2/22, 11:11 am - ~K: Or dosra Kam b krain ta k pichly mamlat clear hon to hm apky agy ki cheezon ko daikh sky
    21/2/22, 11:17 am - Tayaba Malik Student: G theek hai
    21/2/22, 12:47 pm - ~K: Aj apki classes hoi the?
    21/2/22, 12:48 pm - Tayaba Malik Student: Ni teacher
    21/2/22, 12:48 pm - Tayaba Malik Student: Aj fees submit  karni thi bs
    21/2/22, 12:48 pm - ~K: Intro classes b ni hoi?
    21/2/22, 12:48 pm - Tayaba Malik Student: Ni
    21/2/22, 12:48 pm - ~K: Oh acha acha... Regular classes kab sy start hain phir
    21/2/22, 1:10 pm - Tayaba Malik Student: Monday  s
    21/2/22, 1:13 pm - ~K: Next?
    21/2/22, 1:13 pm - Tayaba Malik Student: Gg
    25/2/22, 10:18 am - ~K: Assalam u alaikum Tayyaba!
    Apky projects ki payment ni milli mjy abhi tk.. Uska kya krna Hai ap ny phir ?
    25/2/22, 10:18 am - Tayaba Malik Student: Teacher Saturday  k
    25/2/22, 10:18 am - Tayaba Malik Student: Kal
    25/2/22, 10:18 am - Tayaba Malik Student: Suba
    25/2/22, 10:19 am - ~K: Krain ge kaisy?
    25/2/22, 10:19 am - Tayaba Malik Student: Phir Monday  s classes  hain... aur march ki fee's  b ap k dni hai
    25/2/22, 10:19 am - Tayaba Malik Student: March s onwards  start karn g
    25/2/22, 10:19 am - ~K: March sy parhna start krain ge Mery pas?
    25/2/22, 10:19 am - Tayaba Malik Student: Khud aha k ap k ghar  d k jau gi...
    25/2/22, 10:19 am - Tayaba Malik Student: G
    25/2/22, 10:20 am - ~K: Acha chalain thk hai
    25/2/22, 10:20 am - ~K: Call kr lijiay ga mjy any sy pehly
    25/2/22, 10:20 am - Tayaba Malik Student: Teacher  mein sham k ahu gi t ap k ghar bahir s d jau gi
    25/2/22, 10:20 am - Tayaba Malik Student: Ok
    25/2/22, 10:20 am - Tayaba Malik Student: Ap attend  kar lna... ghar k b puchna h ga
    25/2/22, 10:20 am - Tayaba Malik Student: Agar zarurat  prhi
    25/2/22, 10:20 am - ~K: Main to phir us time ghar ni hon ge.. Laiken chalain ap aa jaiay ga meri ame ghar he hon ge
    25/2/22, 10:21 am - Tayaba Malik Student: Ap t academy  hn gi
    25/2/22, 10:21 am - Tayaba Malik Student: Ok
    25/2/22, 10:21 am - ~K: G g sure... Rasta wagaira puchna hoa to main smja don ge wo phone per apko
    25/2/22, 10:21 am - Tayaba Malik Student: Ok
    26/2/22, 6:46 pm - ~K: Ap ny ana ni Tha tayabba aj?
    26/2/22, 8:43 pm - Tayaba Malik Student: G teacher  ana tha... lkin ni aha saki shopping  k liya ahi thi lakin waspis ni ahi late h gai thi...
    26/2/22, 9:19 pm - ~K: Irada hai b apka any ka ya ni? 😂
    27/2/22, 3:11 pm - Tayaba Malik Student: A.o.a teacher  mein nano ghar ahi hui hu ap k ghar k pass hi hai... 5 bjy tak ap k ghar passy pakra du gi
    27/2/22, 7:47 pm - ~K: G bht shukarya k ap khud ai... Laiken andar ati ap to zyada acha tha
    27/2/22, 8:29 pm - Tayaba Malik Student: Teacher  sorry  andar  ni ahi... jaldi thi...
    27/2/22, 8:29 pm - Tayaba Malik Student: Next time inshallah
    27/2/22, 8:29 pm - Tayaba Malik Student: Aur teacher  suba s class start kar dn gi plz
    27/2/22, 8:30 pm - Tayaba Malik Student: Class  fee ni di abhi ak k actually  aj bank mein passy khtam huy thy cash ni h rahy thy...
    27/2/22, 8:31 pm - ~K: Koi bt ni... Dy dijiay ga bahd main
    27/2/22, 8:31 pm - ~K: Operating system ki bt kr rhe hain?
    27/2/22, 8:32 pm - Tayaba Malik Student: Teacher  yh suba mein ap k batu gi...
    27/2/22, 8:32 pm - Tayaba Malik Student: K kon s parhna ...
    27/2/22, 8:32 pm - ~K: Thk Hai mjy bta dijiay ga phir yad sy jaldi
    27/2/22, 8:33 pm - ~K: Or uni main to classes apki subah sy ni na start 1st March sy hain na?
    27/2/22, 8:34 pm - Tayaba Malik Student: Ok
    27/2/22, 8:34 pm - Tayaba Malik Student: Suba s Monday
    27/2/22, 8:47 pm - ~K: Chalain ap phir kal classes lain or daikh lain kon sa course lag rha hai jo parhna pary ga apko phir bta dijiay ga mjy
    27/2/22, 8:48 pm - Tayaba Malik Student: Ok
    27/2/22, 8:48 pm - Tayaba Malik Student: Thanku teacher  so much
    27/2/22, 8:49 pm - ~K: Thank u kis bat k liay
    27/2/22, 8:49 pm - Tayaba Malik Student: Har bat k liya
    27/2/22, 8:50 pm - Tayaba Malik Student: Sorry b
    27/2/22, 8:50 pm - Tayaba Malik Student: Aj ander na any k liya late any k liya
    27/2/22, 8:50 pm - Tayaba Malik Student: Teacher??
    27/2/22, 8:50 pm - ~K: Acha Acha koi bt ni jnab... Waisy b... Cooperate Mery khyal sy har mamly main krna chahiay phir wo apky student he q na ho
    27/2/22, 8:50 pm - ~K: G
    27/2/22, 8:51 pm - Tayaba Malik Student: Ab t mra ik symester  h gya ap k sath ab t koi dp lga ln koi awv hi ...
    27/2/22, 8:51 pm - Tayaba Malik Student: Bht muskil hta ap s bat karna ..
    27/2/22, 8:51 pm - ~K: 😂 Acha chalo main lagati hn
    27/2/22, 8:51 pm - Tayaba Malik Student: Hmm
    27/2/22, 8:51 pm - ~K: To search q ni krti ap naam Mera... Mtlb agr naam what's app main neechy Chala jata hai to
    27/2/22, 8:52 pm - Tayaba Malik Student: Ni teacher  dp sahi rekhti
    27/2/22, 8:52 pm - Tayaba Malik Student: Aur mein ap ki chat pin karti... ab
    27/2/22, 8:52 pm - Tayaba Malik Student: Bht kam parhty ap s
    27/2/22, 8:52 pm - ~K: Acha chalo main laga laiti hn
    27/2/22, 8:52 pm - Tayaba Malik Student: Ok
    27/2/22, 8:52 pm - ~K: Acha mjy yeh btay... Number ni pta chaly abhi tk un projects k
    27/2/22, 8:53 pm - Tayaba Malik Student: Ni
    27/2/22, 8:53 pm - Tayaba Malik Student: 4 k results  hain
    27/2/22, 8:54 pm - ~K: 4 k result aa gay hain?
    27/2/22, 9:08 pm - Tayaba Malik Student: 4 k hai
    27/2/22, 9:08 pm - Tayaba Malik Student: ❤️ dp
    27/2/22, 9:37 pm - ~K: 🌸
    27/2/22, 9:37 pm - ~K: Chalain wo phir kal mjy call per btaiay ga kis kis k ay or Kya aya grade
    28/2/22, 7:14 pm - Tayaba Malik Student: A.o.a teacher  aj mein gai thi.. lkin koi class ni hui
    28/2/22, 10:21 pm - ~K: Ok
    28/2/22, 10:21 pm - ~K: W. Aslam
    1/3/22, 6:40 pm - ~K: Tyabba aj apki classes hoi the?
    1/3/22, 6:50 pm - Tayaba Malik Student: G
    1/3/22, 6:50 pm - Tayaba Malik Student: Hui thi
    1/3/22, 6:50 pm - Tayaba Malik Student: Ik lab
    1/3/22, 6:50 pm - Tayaba Malik Student: Dbs ki
    1/3/22, 6:51 pm - Tayaba Malik Student: Data base structure
    1/3/22, 6:51 pm - ~K: Ap ny aj class laini Hai phir?
    1/3/22, 6:52 pm - Tayaba Malik Student: Ji teacher dbs ki lab k koi issue  ni hai...
    1/3/22, 6:52 pm - Tayaba Malik Student: Us o Microsoft  asses  visio prha rahy
    1/3/22, 6:52 pm - ~K: Ap zra 5 min call per ayn
    1/3/22, 6:52 pm - Tayaba Malik Student: W easy hai
    1/3/22, 6:52 pm - Tayaba Malik Student: G
    2/3/22, 7:01 pm - ~K: Tyabba ap phir Friday sy pichly Waly in dino main classes laini hain?
    2/3/22, 7:03 pm - Tayaba Malik Student: Ni teacher
    2/3/22, 7:04 pm - ~K: Ok
    3/3/22, 8:57 am - Tayaba Malik Student: A.o.a  teacher  aj meri artificial  intelligence  ki class h rahi hai...
    3/3/22, 8:58 am - Tayaba Malik Student: Teacher  bs ik artificial  intelligence  ap s parhna hai...
    3/3/22, 8:58 am - Tayaba Malik Student: Lkin jsy academy mein start kia tha wasy hi... same bs us waqt c ++ language  ki ab python  karu gi
    3/3/22, 8:59 am - Tayaba Malik Student: Theory  ni karni  bs code hi karny ...
    3/3/22, 10:20 am - ~K: G thk Hai
    3/3/22, 10:20 am - ~K: Thk ho gai bt
    3/3/22, 10:55 am - ~K: Or apki class to Friday ko ni honi the iski?
    3/3/22, 10:59 am - Tayaba Malik Student: Teacher  time table  change h gya tha
    3/3/22, 11:03 am - ~K: Ok mjy phir bta dijiay ga ap ny jb classes start krni hoi to
    8/3/22, 3:18 pm - ~K: Tyabba ap ny python start krni Hai phir ya ni?
    8/3/22, 3:22 pm - Tayaba Malik Student: Teacher 2 labs hui hain dono mein na kar li
    8/3/22, 3:25 pm - ~K: Smj aa rhe hai python apko?
    8/3/22, 3:28 pm - Tayaba Malik Student: G teacher  abhi tak t sahi ja raha hai
    8/3/22, 3:28 pm - Tayaba Malik Student: Basics  hain
    8/3/22, 7:25 pm - ~K: Chalain ache bt Hai... Problem aya jb to phir mjy btaiay ga
    8/3/22, 7:36 pm - Tayaba Malik Student: Ok
    8/3/22, 8:07 pm - ~K: Apko lab main kra kya rhy hain... Python programming?
    8/3/22, 8:12 pm - Tayaba Malik Student: Teacher ik t introduction  clasd thi aur us mein python k installed  karna btya use karna bs
    8/3/22, 8:12 pm - Tayaba Malik Student: 2nd p
    8/3/22, 8:13 pm - ~K: 2nd main kya kraya tha?
    8/3/22, 8:13 pm - Tayaba Malik Student: <Media omitted>
    8/3/22, 8:13 pm - Tayaba Malik Student: <Media omitted>
    8/3/22, 8:13 pm - Tayaba Malik Student: <Media omitted>
    8/3/22, 8:13 pm - Tayaba Malik Student: <Media omitted>
    8/3/22, 8:13 pm - Tayaba Malik Student: Yh bs
    8/3/22, 8:13 pm - Tayaba Malik Student: Is k bs yh kam hua
    8/3/22, 8:13 pm - Tayaba Malik Student: <Media omitted>
    8/3/22, 8:13 pm - Tayaba Malik Student: Jab k baki sub subjects k 4 lectures  karwa diya
    8/3/22, 8:14 pm - Tayaba Malik Student: Is k koi lecture  class  b as such koi ni hti...
    8/3/22, 8:14 pm - ~K: AI ki theory main apko kya kra rhy hain?
    8/3/22, 8:15 pm - Tayaba Malik Student: Kuch ni
    8/3/22, 8:15 pm - ~K: Sirf labs ho rhe hain?
    8/3/22, 8:15 pm - Tayaba Malik Student: Koi lecture  ni huy
    8/3/22, 8:15 pm - Tayaba Malik Student: G
    8/3/22, 8:16 pm - ~K: Yeh install kya kraya hai python k liay apko.. Pycharm ?
    8/3/22, 8:17 pm - Tayaba Malik Student: G
    8/3/22, 8:17 pm - ~K: OS main kya kr rhy hai ap log?
    8/3/22, 8:17 pm - Tayaba Malik Student: Us mein  commands k bs terminal p use karty
    8/3/22, 8:18 pm - Tayaba Malik Student: Us k theory class b hti Us mein zyda parhty.... commands yaad karni hti
    8/3/22, 8:19 pm - ~K: Sae sae
    8/3/22, 8:20 pm - Tayaba Malik Student: Linux
    Operating system
    Visio
     Lucid charts...
    Microsoft  access 
    Drawing. Io
    8/3/22, 8:21 pm - Tayaba Malik Student: Yh tools use kar rahy iss symester  mein
    8/3/22, 8:21 pm - ~K: Yeh to kaafi saary kra rhy hain apko khair sy
    8/3/22, 8:21 pm - ~K: Visio main kya kr rhy Hain ap log
    8/3/22, 8:22 pm - Tayaba Malik Student: Us mein relations bnwaty mandatory one mandatory  many waly... entities  bna k
    8/3/22, 8:22 pm - ~K: Or lucit chart main?
    8/3/22, 8:23 pm - Tayaba Malik Student: Use case diagram  bnaty activity  diagram
    8/3/22, 8:23 pm - Tayaba Malik Student: Is tarah sari bnani hain scenario d dty us ki bnaty
    8/3/22, 8:25 pm - ~K: Acha Acha is trah
    3/5/22, 6:29 am - Tayaba Malik Student: May you be blessed with kindness, patience, happiness, and love 
    
    
    God shower his choicest blessings on Eid. Wish you a Happy Eid ul Fitr!
    
    
    May peace, safety, good health and prosperity be yours.
               Eid Mubarak!
    3/5/22, 8:30 am - ~K: Khair mubarak 🌸 🌸
    3/5/22, 8:30 am - ~K: <Media omitted>
    11/6/22, 12:54 pm - Tayaba Malik Student: Ao.a  teacher
    11/6/22, 12:57 pm - ~K: W. Aslam
    11/6/22, 12:59 pm - Tayaba Malik Student: Teacher  ksi hain
    11/6/22, 1:00 pm - ~K: Allah ka shukar main thk thak... Ap btay kaisi ja rhe studies
    11/6/22, 1:00 pm - Tayaba Malik Student: Teacher bht achi alhu
    11/6/22, 1:00 pm - Tayaba Malik Student: Alhumdulillah
    11/6/22, 1:01 pm - Tayaba Malik Student: Bs symester  khtam hny wala
    11/6/22, 1:01 pm - Tayaba Malik Student: 25 k final paper
    11/6/22, 1:01 pm - Tayaba Malik Student: Ik kam tha teacher ap s
    11/6/22, 1:03 pm - ~K: Mtlb kareeb he hain
    11/6/22, 1:03 pm - ~K: G btay
    11/6/22, 1:06 pm - Tayaba Malik Student: G
    11/6/22, 1:07 pm - Tayaba Malik Student: Teacher mery 4 project  hain
    11/6/22, 1:07 pm - ~K: Yeh na kro 😂🙏
    11/6/22, 1:08 pm - ~K: Yeh semester apka 4th hai na
    11/6/22, 1:08 pm - Tayaba Malik Student: 3 mein na lar liya .... artificial intelligence , software design Argetecture,and operating system k
    11/6/22, 1:08 pm - Tayaba Malik Student: Ik bna rahi  us k ik part ap kar dn
    11/6/22, 1:08 pm - Tayaba Malik Student: Sirf ik bat
    11/6/22, 1:08 pm - Tayaba Malik Student: Part*
    11/6/22, 1:08 pm - Tayaba Malik Student: G
    11/6/22, 1:09 pm - ~K: Kis course ka hai
    11/6/22, 1:09 pm - Tayaba Malik Student: Data base k
    11/6/22, 1:09 pm - Tayaba Malik Student: Data base
    11/6/22, 1:09 pm - ~K: Due kab hai
    11/6/22, 1:09 pm - Tayaba Malik Student: Us mein ER diagram  bnanai class diagram  report presentation  normalization  ... yeh karna bs
    11/6/22, 1:09 pm - ~K: Mjy check krna pary ga... Q k aj kal am already working on something... Uski b deadline nazdeek hai... Have to see agr Mery liay possible hota hai to
    11/6/22, 1:10 pm - Tayaba Malik Student: ER mein na bna li class b  report b bna lu gi aur presentation  b
    11/6/22, 1:10 pm - Tayaba Malik Student: Ap bs normalization  kar dn
    11/6/22, 1:10 pm - Tayaba Malik Student: Monday tk
    11/6/22, 1:10 pm - ~K: Yeh Jo Monday aa rha hai?
    11/6/22, 1:10 pm - Tayaba Malik Student: Teacher plz karn kuch
    11/6/22, 1:10 pm - Tayaba Malik Student: G
    11/6/22, 1:11 pm - Tayaba Malik Student: Mila Friday k hai
    11/6/22, 1:11 pm - Tayaba Malik Student: Iss
    11/6/22, 1:11 pm - ~K: Yr bht sir per hai Yeh to
    11/6/22, 1:11 pm - Tayaba Malik Student: Phly ni mila hua tha ni t ap s sara bnwa lati
    11/6/22, 1:11 pm - ~K: Wo sari batyn to thk hai.. Per main time kidar sy nikalo geeee
    11/6/22, 1:11 pm - Tayaba Malik Student: <Media omitted>
    11/6/22, 1:11 pm - Tayaba Malik Student: <Media omitted>
    11/6/22, 1:11 pm - Tayaba Malik Student: Bs yeh karna asy
    11/6/22, 1:12 pm - ~K: Chalo ap mjy send kro project main koi apni frnd daikhti hn... Q k Mery pas time nikalna bht mushkil ho jay ga
    11/6/22, 1:12 pm - Tayaba Malik Student: Yeh example  hai j class mein karwai
    11/6/22, 1:12 pm - Tayaba Malik Student: Ok
    11/6/22, 1:12 pm - Tayaba Malik Student: Mein ap k bjti
    11/6/22, 1:13 pm - Tayaba Malik Student: Hospital management system
    11/6/22, 1:13 pm - Tayaba Malik Student: Attributes dlny hn
    11/6/22, 1:13 pm - Tayaba Malik Student: Recipients doc
    11/6/22, 1:13 pm - Tayaba Malik Student: Appointment
    11/6/22, 1:14 pm - Tayaba Malik Student: Monday, Tuesday   tak karwa sakty ... bs iss s late ni
    11/6/22, 1:15 pm - ~K: Chalo main apko phir jaldi inform kr Don ge... K mjy koi bandi milli ya ni... Bnany k liay
    11/6/22, 1:16 pm - Tayaba Malik Student: Ok
    11/6/22, 3:15 pm - ~K: <Media omitted>
    11/6/22, 3:17 pm - Tayaba Malik Student: Use case , ERD diagram  presentation  bnanai 
    Aur report normalization
    11/6/22, 3:17 pm - Tayaba Malik Student: Abhi start ni kia teacher
    11/6/22, 3:18 pm - Tayaba Malik Student: Report  aur presentation  t last mein bnani jab use case ERD and normalization  h jya gi
    11/6/22, 3:21 pm - ~K: <Media omitted>
    11/6/22, 3:21 pm - ~K: <Media omitted>
    11/6/22, 3:25 pm - Tayaba Malik Student: Ni teacher bs basic j net p thy w hi
    11/6/22, 3:25 pm - Tayaba Malik Student: Pharmacy
    11/6/22, 3:25 pm - Tayaba Malik Student: Doctors nurses staf
    11/6/22, 3:25 pm - Tayaba Malik Student: Bs yeh hi abhi tak
    11/6/22, 3:28 pm - ~K: Ok
    11/6/22, 7:24 pm - ~K: <Media omitted>
    11/6/22, 7:31 pm - Tayaba Malik Student: Gg
    11/6/22, 7:31 pm - Tayaba Malik Student: 3 nf
    11/6/22, 7:31 pm - Tayaba Malik Student: Tk
    11/6/22, 8:00 pm - ~K: <Media omitted>
    11/6/22, 8:00 pm - ~K: <Media omitted>
    11/6/22, 8:00 pm - ~K: Yeh check krain zra
    11/6/22, 8:13 pm - Tayaba Malik Student: Ik second teacher
    11/6/22, 8:18 pm - Tayaba Malik Student: <Media omitted>
    11/6/22, 8:24 pm - Tayaba Malik Student: <Media omitted>
    11/6/22, 8:24 pm - Tayaba Malik Student: <Media omitted>
    11/6/22, 10:46 pm - ~K: <Media omitted>
    11/6/22, 11:20 pm - Tayaba Malik Student: Teacher abhi us na bnya ni...
    11/6/22, 11:20 pm - Tayaba Malik Student: Phir b mein  kha dti
    12/6/22, 9:35 am - ~K: Ok
    13/6/22, 7:03 pm - Tayaba Malik Student: A.o.a. teacher
    13/6/22, 7:03 pm - Tayaba Malik Student: Kia bna project  k
    13/6/22, 7:12 pm - ~K: Apko main ny sample ka kaha hoa Tha tayyaba
    13/6/22, 7:12 pm - ~K: Ap ny ni send kia to mjy laga phir us sy onward ap ny khud daikh Lia hoga
    13/6/22, 7:13 pm - Tayaba Malik Student: Teacher  ksi na ni bnaya agar bnya b h ga t koi ni d g
    13/6/22, 7:14 pm - ~K: Phir abhi mjy kaisy idea hoga
    13/6/22, 7:15 pm - Tayaba Malik Student: Teacher ap k jsy samj ata bna dn
    13/6/22, 7:15 pm - Tayaba Malik Student: Normalization  kar dn
    13/6/22, 7:15 pm - ~K: Meri frnd ko bola tha main ny... Yeh us ny bejha hai mjy
    13/6/22, 7:15 pm - ~K: Abhi us ko phir dobara kya Bolon main... Aik din ka gap aa gya beech main
    13/6/22, 7:16 pm - ~K: Ap aik Kam kro... Jo is ka reh gya wo ap khud try kro... Shayd ban jay
    13/6/22, 7:16 pm - Tayaba Malik Student: Bs theek hi teacher ap kar dn ... yh karwa dn
    13/6/22, 7:16 pm - Tayaba Malik Student: Aur payment  k b bta dn
    13/6/22, 7:16 pm - ~K: Main busy hn na aj kal khud
    13/6/22, 7:16 pm - Tayaba Malik Student: Ni teacher  mery s ni hta ap karwa dn
    13/6/22, 7:17 pm - ~K: Or yeh to apka... Isi Monday ko due ni Tha?
    13/6/22, 7:17 pm - ~K: Mtlb aj ki date ni the due ki
    13/6/22, 7:17 pm - Tayaba Malik Student: Kal  rat k b time hai
    13/6/22, 7:17 pm - ~K: Tuesday 11 59 pm?
    13/6/22, 7:17 pm - Tayaba Malik Student: Monday  Tuesday  tak karwa skty
    13/6/22, 7:17 pm - Tayaba Malik Student: G
    13/6/22, 7:18 pm - ~K: Chalo main bolti hn frnd ko
    13/6/22, 7:18 pm - Tayaba Malik Student: Okok teacher
    13/6/22, 7:18 pm - Tayaba Malik Student: Thanku so much
    13/6/22, 7:19 pm - ~K: Per Sunday ko apko contact krna chahiay tha na... Mjy laga ap khud kr rhe ho shayd
    13/6/22, 7:19 pm - Tayaba Malik Student: Teacher sab s mang rahi thi koi sample mil jya ksi s ni mila
    13/6/22, 7:19 pm - Tayaba Malik Student: Aj University  mein b kha sab k
    13/6/22, 7:19 pm - Tayaba Malik Student: A hi wapis  aha k ap k btya
    13/6/22, 7:20 pm - ~K: Ok Chalo krwati hn main kahe sy
    13/6/22, 7:20 pm - Tayaba Malik Student: Ok
    14/6/22, 8:49 am - Tayaba Malik Student: A.o.a teacher 2  din aur mil gya
    14/6/22, 8:49 am - Tayaba Malik Student: Thursday  rat k 12 tak
    14/6/22, 9:15 am - ~K: Chalo shukar hai... Next do din Mery apny pas Thora sa time nikal rha tha waisy b
    14/6/22, 9:21 am - Tayaba Malik Student: Ok teacher  phir  ap kar dn ...
    14/6/22, 9:21 am - Tayaba Malik Student: Aur payment  k b bta dn
    14/6/22, 9:22 am - Tayaba Malik Student: Ik aur b cheez karwani  hai py charm p... ik code
    14/6/22, 9:22 am - ~K: Or Kya cheez krani hai ab
    14/6/22, 9:22 am - ~K: Python?
    14/6/22, 9:23 am - Tayaba Malik Student: Gg
    14/6/22, 9:23 am - ~K: Is Waly ki main sham tk ya kal tk btati hn apko
    14/6/22, 9:25 am - Tayaba Malik Student: Okok
    14/6/22, 9:25 am - Tayaba Malik Student: <Media omitted>
    14/6/22, 9:26 am - Tayaba Malik Student: Python  p karna hai dekhn j easy h jis k code net p available  h
    14/6/22, 9:26 am - Tayaba Malik Student: Koi ik library  sirf use karni h gi...
    14/6/22, 9:27 am - ~K: Net per ap check krain na kis ka available hai
    14/6/22, 9:27 am - Tayaba Malik Student: Teacher ap dekhn
    14/6/22, 9:27 am - Tayaba Malik Student: Mujy kia pta  w sahi b h yh ni
    14/6/22, 9:27 am - ~K: Implement to ap ny khud ni krna isko?
    14/6/22, 9:28 am - Tayaba Malik Student: Teacher ik mein na kia hai yh ik aur assignment  hai
    14/6/22, 9:28 am - ~K: Run kr k check hoga na wo to
    14/6/22, 9:28 am - Tayaba Malik Student: Yh  khud choose  kar sakty apni merzi s
    14/6/22, 9:28 am - ~K: To abhi iska kya krna Hai basically
    14/6/22, 9:29 am - Tayaba Malik Student: Iss k code bnana
    14/6/22, 9:29 am - Tayaba Malik Student: Ik library  use karni hai just
    14/6/22, 9:29 am - ~K: Implement ap khud krain ge? Main apko dhoond k don? Yeh keh rhe hain
    14/6/22, 9:29 am - Tayaba Malik Student: Ni implement b ap karn g
    14/6/22, 9:29 am - ~K: Koi b system is photo main sy... Jo ap ny bejhi hai... Aik library use kr k to ni hoga
    14/6/22, 9:30 am - Tayaba Malik Student: Bs muja  in mein s ksi b topic  p code  pura output  k sath bna dn
    14/6/22, 9:30 am - ~K: Iski due kab hai?
    14/6/22, 9:30 am - Tayaba Malik Student: G koi b system
    14/6/22, 9:30 am - Tayaba Malik Student: Monday 12 pm
    14/6/22, 9:30 am - ~K: Han g... Per aik library sy ni hona... Yeh kis ny kaha ap sy
    14/6/22, 9:31 am - ~K: 20 jun?
    14/6/22, 9:31 am - Tayaba Malik Student: Ap k jsy shi lagta koi b library  lga ln...
    14/6/22, 9:31 am - ~K: Acha chalo main daikhti hn
    14/6/22, 9:31 am - Tayaba Malik Student: Sir na kha ap j library  b choose karn w ap k phir  sahi s ani chy
    14/6/22, 9:31 am - Tayaba Malik Student: Okok
    14/6/22, 9:32 am - ~K: Wo phir apko kaisy ay ge😂agr main bnao ge to
    14/6/22, 9:32 am - Tayaba Malik Student: Teacher  25 k hmra paper
    14/6/22, 9:32 am - Tayaba Malik Student: Koi presentation  ni h gi na koi puchy g
    14/6/22, 9:33 am - ~K: Finals start hain 25 sy?
    14/6/22, 9:33 am - Tayaba Malik Student: Bs bna k submit  karwana
    14/6/22, 9:33 am - Tayaba Malik Student: Number  LG jyn g
    14/6/22, 9:33 am - Tayaba Malik Student: G
    14/6/22, 9:33 am - ~K: Confirm hai na... Q k aisa na hoa to phir apky liay issue na ban jay kahe
    14/6/22, 9:33 am - Tayaba Malik Student: Gg
    14/6/22, 9:34 am - ~K: Chalo pehly to main apka normalization wala complete krti hn na kal tk... Phir is dusry ko daikhti hn
    14/6/22, 9:34 am - Tayaba Malik Student: Time ni hai ... iss liya sir na kha yh ap submit  karwa dn just mein deakh lu g aur Grading kr dn g
    14/6/22, 9:34 am - Tayaba Malik Student: Ok
    14/6/22, 9:34 am - ~K: Chalo sae hai
    14/6/22, 9:34 am - Tayaba Malik Student: Ok teacher  thanku
    15/6/22, 8:17 pm - Tayaba Malik Student: A.o.a
    15/6/22, 8:17 pm - Tayaba Malik Student: Teacher  kia hua task k
    15/6/22, 8:51 pm - ~K: W. Aslam... Normalization wala he abhi apka krny bethi hn main
    15/6/22, 8:52 pm - ~K: Acha mjy yeh btay...normalization main to shayd page per kron ge... Wo phir ap kaisy lain ge mj sy... Pictures ki form main?
    15/6/22, 8:52 pm - ~K: Q k wo phir apko khud daikh k bnana pary ga
    15/6/22, 9:41 pm - ~K: Mjy btay ta k main start kron phir
    15/6/22, 10:12 pm - Tayaba Malik Student: Teacher  world ki file bna dn
    15/6/22, 10:40 pm - ~K: Pictures khench k?
    15/6/22, 10:40 pm - Tayaba Malik Student: Doc ki file mein
    15/6/22, 10:41 pm - ~K: Mtlb udhar he pictures paste kr k na?
    15/6/22, 10:41 pm - Tayaba Malik Student: G
    15/6/22, 10:41 pm - ~K: Ok
    15/6/22, 10:41 pm - Tayaba Malik Student: Thanku  teacher
    15/6/22, 10:44 pm - ~K: Or isky 2000 dy dijiay ga ap phir mjy
    15/6/22, 10:44 pm - Tayaba Malik Student: Ok
    15/6/22, 10:50 pm - ~K: Acha Tayyaba aik or Kam b kro na ap zra
    15/6/22, 10:51 pm - ~K: Jis larki sy ap ny pehly pucha tha... Us sy ya kisi or sy pucho... System k kitny tables ki normalization kr rhy Hain sary
    15/6/22, 10:53 pm - ~K: Ya apni teacher sy he puch lain k atleast or at most us system k kitny tables ki normalization krni hai
    16/6/22, 6:15 am - Tayaba Malik Student: Ok
    16/6/22, 9:01 am - Tayaba Malik Student: Teacher  almost  3
    16/6/22, 9:01 am - Tayaba Malik Student: Iss s kam ni
    16/6/22, 9:03 am - ~K: Mtlb 3 sy zyada b na hon?
    16/6/22, 9:13 am - Tayaba Malik Student: G
    16/6/22, 9:13 am - Tayaba Malik Student: 3 s kam b na hn
    16/6/22, 9:13 am - Tayaba Malik Student: Aur tables  world p banany
    16/6/22, 9:13 am - Tayaba Malik Student: Madam s pucha
    16/6/22, 9:13 am - Tayaba Malik Student: Abhi
    16/6/22, 9:15 am - ~K: Yeh to apki teacher ny khap or barha di hai
    16/6/22, 9:19 am - Tayaba Malik Student: Q
    16/6/22, 9:20 am - ~K: Likh k sae tha na... Yeh word per bnany wala additional time ly ga ab
    16/6/22, 9:21 am - Tayaba Malik Student: Teacher presentation  k time ni hai w kha rahi ap ki grading  mein files k deakh k karu gi iss liya
    16/6/22, 9:22 am - ~K: Han per word ki file main mjy tables to create krny pary gy na
    16/6/22, 9:22 am - ~K: Or normalization b phir word per he honi hai sari
    16/6/22, 9:23 am - Tayaba Malik Student: Hmm
    16/6/22, 2:48 pm - ~K: <Media omitted>
    16/6/22, 2:48 pm - ~K: yeh jaldi sy check kr k mjy btay
    16/6/22, 2:48 pm - Tayaba Malik Student: Ok teacher
    16/6/22, 2:49 pm - ~K: Isko laptop main khol k check kijiay ga... Phone per ajeeb sa aa rha hai yeh
    16/6/22, 2:50 pm - Tayaba Malik Student: Teacher agar ap wait karn t mein madam k check karwa du
    16/6/22, 2:50 pm - Tayaba Malik Student: Abhi class h rahi...
    16/6/22, 2:50 pm - Tayaba Malik Student: 3 10 tak check karwati
    16/6/22, 2:50 pm - ~K: G g krwa dain
    16/6/22, 2:50 pm - Tayaba Malik Student: Okok
    16/6/22, 2:50 pm - ~K: Laiken zyada late ni krna.. Phir main ny academy k liay nikla Jana hoga
    16/6/22, 2:50 pm - Tayaba Malik Student: Okok
    16/6/22, 2:51 pm - ~K: Laptop hai na apky pas?
    16/6/22, 2:51 pm - ~K: Laptop main check krwana isko ap apni teacher ko
    16/6/22, 2:52 pm - Tayaba Malik Student: G
    16/6/22, 2:52 pm - Tayaba Malik Student: Ok
    16/6/22, 3:08 pm - ~K: Or python wala project ap ny Monday ko submit krana hai?
    16/6/22, 3:12 pm - Tayaba Malik Student: G
    16/6/22, 3:21 pm - ~K: Ok is Waly ka phir mjy confirm krain jaldi
    16/6/22, 3:55 pm - Tayaba Malik Student: Yh sahi hai teacher
    16/6/22, 3:55 pm - ~K: Pura sae hai?
    16/6/22, 3:55 pm - ~K: Teacher ko dikhaya ap ny?
    16/6/22, 3:55 pm - Tayaba Malik Student: Gg
    16/6/22, 3:56 pm - Tayaba Malik Student: G unhon na kha sahi hai
    16/6/22, 3:56 pm - ~K: Chalo thk Hai phir
    16/6/22, 3:56 pm - Tayaba Malik Student: Yes ok hai
    16/6/22, 8:14 pm - ~K: Tyabba apka phir confirm hai wo project ap ny Mery sy he banwana hai?
    16/6/22, 9:06 pm - Tayaba Malik Student: Teacher yh normalization  h gai hai bs ik yeh karna tha ...
    16/6/22, 9:06 pm - Tayaba Malik Student: <Media omitted>
    16/6/22, 9:06 pm - Tayaba Malik Student: Yeh project  ni hai
    16/6/22, 9:06 pm - Tayaba Malik Student: Yeh assignment  hai ... python  p karna ...
    16/6/22, 9:07 pm - Tayaba Malik Student: Khud apni merzi s topics choose  kar sakty...
    16/6/22, 9:07 pm - Tayaba Malik Student: Sir na kha tha k net p almost  sab k code available  hain... ap l sakty  whn  s ...
    16/6/22, 9:07 pm - Tayaba Malik Student: T ap is mein s ksi b topic  p code bna dn... yh net s nikal dn ...
    16/6/22, 9:08 pm - Tayaba Malik Student: Lkin teacher  project  ki form ma na h ....
    16/6/22, 9:08 pm - Tayaba Malik Student: Jsy ap na phly bna k diya tha wasy itna lengthy  ni ...
    16/6/22, 10:35 pm - ~K: Kitny marks ki assignment hai Yeh apki
    16/6/22, 10:37 pm - Tayaba Malik Student: Marks ni pta...
    16/6/22, 10:37 pm - Tayaba Malik Student: Suba puch k batu gi ap k...
    16/6/22, 10:37 pm - Tayaba Malik Student: Sir s
    16/6/22, 10:40 pm - ~K: Waisy yeh wala I would suggest ap khud bnao
    16/6/22, 10:40 pm - Tayaba Malik Student: Teacher  meri abhi tak classes h rahu
    16/6/22, 10:40 pm - Tayaba Malik Student: Presentation  h rahi
    16/6/22, 10:41 pm - Tayaba Malik Student: Bilkul time ni
    16/6/22, 10:41 pm - Tayaba Malik Student: Papers ki tiyari  k ...
    16/6/22, 10:41 pm - Tayaba Malik Student: 1st paper b probability and Statistics  k
    16/6/22, 10:42 pm - ~K: Wo to thk hai... Per waisy khud krny Wala zyada convenient option hoga apky liay
    16/6/22, 10:42 pm - ~K: Per Chalo main daikhti hn isko... K net sy ly k aya exucute ho jay ga... Ya change krna pary ga code... Ya Kitna Kam krna pary ga abhi to mjy b koi idea ni
    16/6/22, 10:43 pm - Tayaba Malik Student: Ok
    16/6/22, 10:43 pm - Tayaba Malik Student: Mein ap k suba iss assignment k se related  sab bata du gi sir s puch k
    16/6/22, 10:44 pm - ~K: G thk Hai bta daina... Per mjy to yahe lag rha hai.. Yeh apki normal assignment jaisi ni Hoge shayd
    16/6/22, 10:44 pm - Tayaba Malik Student: Hmm
    16/6/22, 10:44 pm - Tayaba Malik Student: Ok teacher  kal inform kar du gi j b details  hui
    16/6/22, 10:45 pm - ~K: Ok
    17/6/22, 11:44 am - ~K: Apny sir sy puch k mjy details jaldi btaiay ga... Q k ap btay ge usky bahd he start kro ge iska krna main
    17/6/22, 11:49 am - Tayaba Malik Student: Okok
    17/6/22, 11:49 am - Tayaba Malik Student: Call kar k batati
    17/6/22, 11:53 am - Tayaba Malik Student: Abhi class mein
    17/6/22, 1:26 pm - ~K: Ok
    17/6/22, 3:16 pm - ~K: Classes khtm ni hoi apki abhi tk?
    17/6/22, 4:18 pm - Tayaba Malik Student: 4 30
    17/6/22, 8:41 pm - ~K: Tayyaba mjy project ki details ap time per ni btay ge to Mery liay mushkil hoga phir bnana time per
    17/6/22, 8:43 pm - Tayaba Malik Student: G teacher  bat ki thi sir s
    17/6/22, 8:43 pm - Tayaba Malik Student: Kha rahy thy  numbers t abhi final ni kia k kitny numbers ki yh assignment  rakhn g
    17/6/22, 8:44 pm - Tayaba Malik Student: Kha rahy thy watig  zyda h gi iss kia
    17/6/22, 8:44 pm - Tayaba Malik Student: Ki*
    17/6/22, 8:44 pm - Tayaba Malik Student: Tka average  bn jya aur zyda bchy pass h jyn course  mein
    17/6/22, 9:32 pm - ~K: Ok
    17/6/22, 9:32 pm - ~K: Mtlb marks zyada he hon gy... As compare to other assignments
    18/6/22, 9:18 am - Tayaba Malik Student: Hmm
    18/6/22, 10:15 pm - ~K: Monday 11 59 pm??
    18/6/22, 10:15 pm - Tayaba Malik Student: Sunday 12 pm
    18/6/22, 10:16 pm - ~K: Sunday din ko?
    18/6/22, 10:17 pm - Tayaba Malik Student: Rat k 12
    18/6/22, 10:17 pm - ~K: To 11 59 pm hoa na phir
    18/6/22, 10:17 pm - Tayaba Malik Student: Gg
    18/6/22, 10:17 pm - Tayaba Malik Student: Sorry  kuch samj hi ni aha raha
    18/6/22, 10:18 pm - Tayaba Malik Student: Means 12 tak rat k time
    18/6/22, 10:18 pm - Tayaba Malik Student: Aur teacher  payments k b bta dn ...
    18/6/22, 10:18 pm - Tayaba Malik Student: Easipasa  karwa du gi... ik friend na bnya hai t us s karwa du gi
    18/6/22, 10:47 pm - ~K: Ok
    18/6/22, 10:47 pm - ~K: 4000 dy daina ap mjy isky
    18/6/22, 10:47 pm - ~K: Thk Hai easypaisa kra Daina ap mjy
    19/6/22, 8:48 am - ~K: Or jb yeh ban jay ga to mjy yad kraiay ga apko main apky system per run b kr k dy don ge... Q k khud ni hoga ap sy run cmd per b kuch cheezain pehly krni parhni hai q k
    19/6/22, 10:07 am - Tayaba Malik Student: Ok
    19/6/22, 10:07 am - Tayaba Malik Student: Ok
    19/6/22, 11:27 am - ~K: Mjy yeh cheez btay... Yeh jo list hai... Is main 2 logo ka same project agr ho gya... To apky sir masla to ni bnay gy na
    19/6/22, 11:27 am - ~K: Q k most probably jo hm kr rhy Hain... Wo apki class main koi or b kr rha ho
    19/6/22, 11:27 am - Tayaba Malik Student: Ni
    19/6/22, 11:28 am - Tayaba Malik Student: Teacher  project  jsa na bnana
    19/6/22, 11:28 am - Tayaba Malik Student: Itna lengthy ni
    19/6/22, 11:28 am - ~K: Ary... Jitna hai... Utna to hoga na
    19/6/22, 11:28 am - Tayaba Malik Student: Jsy last time bnya tha wasa ni
    19/6/22, 11:28 am - Tayaba Malik Student: Yh assignment  hai
    19/6/22, 11:28 am - Tayaba Malik Student: Project  ni
    19/6/22, 11:28 am - Tayaba Malik Student: Sahi
    19/6/22, 11:28 am - Tayaba Malik Student: Okok
    19/6/22, 11:29 am - ~K: Abhi kal 1 hr 30 min Kam Kia main ny... Or koi 20 30 min error remove krny main lagy
    19/6/22, 11:29 am - Tayaba Malik Student: Ok
    19/6/22, 11:29 am - Tayaba Malik Student: Thanku  teacher  mery liya time  nikla
    19/6/22, 11:30 am - Tayaba Malik Student: Teacher ap s ik kam aur b hai
    19/6/22, 11:30 am - Tayaba Malik Student: Ap academy  jti hain
    19/6/22, 11:30 am - Tayaba Malik Student: Kitny bjy
    19/6/22, 11:30 am - Tayaba Malik Student: Tuition bjna tha mama na bahi k
    19/6/22, 11:30 am - ~K: G bs dua krain... Time per ban b jay... Q k aj sham 6 tk... Aik project k Kam main phansi rho ge main... Apka Kam 6 sy onward start kron ge
    19/6/22, 11:31 am - ~K: Dua kro time per complete ho jay sae
    19/6/22, 11:31 am - Tayaba Malik Student: 7 class mein hai ...  2 bachy hn  g  math  karny k liya aur science  b
    19/6/22, 11:31 am - ~K: G main jati hn
    19/6/22, 11:31 am - Tayaba Malik Student: Inshallah  h jya g
    19/6/22, 11:31 am - ~K: 7 or kon c class main
    19/6/22, 11:31 am - ~K: Dusra bacha
    19/6/22, 11:31 am - Tayaba Malik Student: Timing  b btyn
    19/6/22, 11:31 am - Tayaba Malik Student: Dono 7 mein
    19/6/22, 11:32 am - ~K: Academy ki timing to 4 to 6 30 hai... Bacho ki timings
    19/6/22, 11:32 am - Tayaba Malik Student: Okkk
    19/6/22, 11:32 am - ~K: Science k liay sir kisi or teacher k pas bejhain gy phir unko
    19/6/22, 11:32 am - Tayaba Malik Student: Ok
    19/6/22, 11:32 am - ~K: Q k main to sirf math krati hn na academy main
    19/6/22, 11:33 am - Tayaba Malik Student: Chln w academy  aha k puchty sir s fees k b ... Monday  k bj dn g un k
    19/6/22, 11:33 am - Tayaba Malik Student: Kia pta English  b prhn
    19/6/22, 11:33 am - ~K: Han g.. Wo fees wagaira or baki sb cheezain sir bta dain gy phir unko
    19/6/22, 11:33 am - Tayaba Malik Student: Ok
    19/6/22, 11:33 am - ~K: Thk Hai sir ko bta dijiay ga... Jo jo subjects parhny hoay
    19/6/22, 11:34 am - Tayaba Malik Student: Ok
    19/6/22, 1:39 pm - Tayaba Malik Student: Teacher
    19/6/22, 1:39 pm - Tayaba Malik Student: J normalization  ki hai us k... ik kam aur b kar dn...
    19/6/22, 2:37 pm - ~K: Us ka kya kam
    19/6/22, 2:38 pm - ~K: Wo to ap ny submit kra ni di?
    19/6/22, 2:40 pm - Tayaba Malik Student: Karwa diya hai ik file aur attache karni
    19/6/22, 2:40 pm - ~K: Kya file
    19/6/22, 2:41 pm - Tayaba Malik Student: Raat tk uml r class diagram bhjo
    19/6/22, 2:41 pm - Tayaba Malik Student: Aj raat tk chiye lzmi
    19/6/22, 2:41 pm - Tayaba Malik Student: <Media omitted>
    19/6/22, 2:41 pm - Tayaba Malik Student: Uml h gai hai
    19/6/22, 2:41 pm - Tayaba Malik Student: 0 pdf b mein na bna li
    19/6/22, 2:41 pm - Tayaba Malik Student: Ap class bna dn
    ..
    19/6/22, 2:42 pm - Tayaba Malik Student: Draw.io p bnanai ... wahn s export  Kr k picture  bj dn...
    19/6/22, 2:42 pm - ~K: Tyabba aj rat tk...
    19/6/22, 2:42 pm - Tayaba Malik Student: G
    19/6/22, 2:43 pm - Tayaba Malik Student: Mery pas hai meim ap k deakhti
    19/6/22, 2:43 pm - Tayaba Malik Student: <Media omitted>
    19/6/22, 2:43 pm - Tayaba Malik Student: Yeh car show room k abhi mein na bni ... asi
    19/6/22, 2:47 pm - ~K: To usko bna lo na ap he
    19/6/22, 3:00 pm - Tayaba Malik Student: Teacher abhi mujy isss ki use use b bni activity diagram b bnani
    19/6/22, 3:00 pm - Tayaba Malik Student: Ap hospital  waly ki bs  use case bna dn
    19/6/22, 3:48 pm - ~K: Chalo per abhi main done ni kr skti... Phir dusry wala apka Kam kr k time bacha to phir main apko btaon ge
    19/6/22, 3:49 pm - Tayaba Malik Student: Teacher ap AI k bnyn
    19/6/22, 3:49 pm - Tayaba Malik Student: Yh mein bna rahi  class diagram
    19/6/22, 3:49 pm - Tayaba Malik Student: AI b aj rat tak submitted karni
    19/6/22, 3:50 pm - ~K: Class diagram he ap mjy bnany k liay keh rhe the?
    19/6/22, 3:50 pm - Tayaba Malik Student: G
    19/6/22, 3:50 pm - Tayaba Malik Student: Lkin ab mein bna rahi
    19/6/22, 4:04 pm - ~K: Ok good bnayn
    19/6/22, 9:36 pm - ~K: Tyabba apka project ho gya hai
    19/6/22, 9:37 pm - ~K: Laiken accuracy approximately 50 percent Hai... Ab mjy btay... Iska apky sir issue bnay gy ya ni?
    19/6/22, 9:40 pm - Tayaba Malik Student: Kia matalb  teacher
    19/6/22, 9:40 pm - ~K: Mtlb accuracy compromise hai
    19/6/22, 9:40 pm - Tayaba Malik Student: Agar w run karn program  t output  ni aya gi
    19/6/22, 9:40 pm - ~K: <Media omitted>
    19/6/22, 9:42 pm - Tayaba Malik Student: Teacher  mein kia kha sakti ab
    19/6/22, 9:42 pm - Tayaba Malik Student: Sahi hai j h gya
    19/6/22, 9:42 pm - ~K: <Media omitted>
    19/6/22, 9:44 pm - Tayaba Malik Student: Bs theek  hai  5 images  k j bta raha
    19/6/22, 9:44 pm - Tayaba Malik Student: Q k time ni hai
    19/6/22, 9:44 pm - ~K: <Media omitted>
    19/6/22, 9:46 pm - Tayaba Malik Student: Teacher  j h gya  hai w submit  kara dty  ...
    19/6/22, 9:46 pm - Tayaba Malik Student: Iss ki grading  Thursday  k h gi
    19/6/22, 9:46 pm - ~K: Number Kam na lag jay na apky
    19/6/22, 9:46 pm - Tayaba Malik Student: Tab tk hum kam krty rahyn g project  p
    19/6/22, 9:46 pm - ~K: Mjy issue ni Hai... Main abhi apko... Apky system per deploy kr k dy daiti hn
    19/6/22, 9:46 pm - Tayaba Malik Student: Samjha  b last  day
    19/6/22, 9:47 pm - ~K: Kya mtlb
    19/6/22, 9:47 pm - Tayaba Malik Student: Mera  pass py charm ni installed
    19/6/22, 9:47 pm - ~K: Phir?
    19/6/22, 10:02 pm - ~K: <Media omitted>
    19/6/22, 10:08 pm - Tayaba Malik Student: Ok teacher
    19/6/22, 10:08 pm - Tayaba Malik Student: Submit  karwa di hai
    19/6/22, 10:09 pm - Tayaba Malik Student: Thanku so much
    19/6/22, 10:17 pm - ~K: No prob 🌸bs apky model ki accuracy improve ho jay sae... Phir sae ho jay ga
    21/6/22, 3:57 pm - ~K: Project deploy ap Mery sy aj he krwa Laina.. Kal hmari light ni hoge
    21/6/22, 4:01 pm - Tayaba Malik Student: Teacher aj t University  mein  off h gi
    21/6/22, 4:01 pm - Tayaba Malik Student: AB suba hi h sakta
    21/6/22, 4:01 pm - Tayaba Malik Student: Mery pass py charm ni hai khud
    21/6/22, 4:26 pm - ~K: To apki dost k pas laptop ghar main b to hoga na
    21/6/22, 4:28 pm - Tayaba Malik Student: Ok teacher  ghar ja k batati
    21/6/22, 4:28 pm - Tayaba Malik Student: Phir aj h ska t ka ln g
    21/6/22, 4:30 pm - ~K: Ho skta hai ni... Aj he deploy krwa lain mj sy.. Kal pura din hmari light ni hoge
    21/6/22, 4:30 pm - Tayaba Malik Student: Ok
    21/6/22, 4:31 pm - ~K: Ap abhi uni hain?
    21/6/22, 4:32 pm - Tayaba Malik Student: No
    21/6/22, 4:32 pm - Tayaba Malik Student: Nikl ahi
    21/6/22, 4:32 pm - Tayaba Malik Student: Bht barish  h rahi
    21/6/22, 4:33 pm - ~K: Ok then apni frnd ko sham main ap pohanch kr contact krain... K wo mjy control dy apny laptop ka or phir main usy deploy kr k dy don project
    21/6/22, 4:33 pm - Tayaba Malik Student: Ok
    21/6/22, 10:35 pm - ~K: Ap phir wo wala project kal sir ko dikha daina jo main ny apko zip kr k bejha tha
    21/6/22, 10:35 pm - Tayaba Malik Student: Ok teacher
    21/6/22, 10:36 pm - Tayaba Malik Student: Aur smj ni saky aj wahn light ni thi aj t charging  ni hai us k pass
    21/6/22, 10:36 pm - Tayaba Malik Student: Maybe viva b na h
    21/6/22, 10:36 pm - Tayaba Malik Student: Q k time ni hai
    21/6/22, 10:37 pm - Tayaba Malik Student: Even hmra final paper Saturday  k start h rahy aur Sunday k b paper hai
    21/6/22, 10:37 pm - Tayaba Malik Student: <Media omitted>
    21/6/22, 10:38 pm - ~K: Chalain sae ho gya
    21/6/22, 10:38 pm - ~K: Or easypaisa phir kab tk ho jay ga... Kal tk krwa dain ge ap?
    21/6/22, 10:38 pm - Tayaba Malik Student: Ok
    21/6/22, 10:38 pm - Tayaba Malik Student: Ok kal karwa du gi ..
    21/6/22, 10:39 pm - ~K: Abhi apka yeh... Jo submit kraya hai... Usi ki base per marks lagain gy?
    21/6/22, 10:39 pm - Tayaba Malik Student: G
    22/6/22, 9:33 pm - ~K: - pip install numpy
    - pip install opencv-python
    - pip install matplotlib
    - pip install tensorflow
    22/6/22, 9:33 pm - ~K: <Media omitted>
    22/6/22, 9:36 pm - Tayaba Malik Student: Okok
    23/6/22, 9:00 am - Tayaba Malik Student: A.o.a teacher
    23/6/22, 9:01 am - Tayaba Malik Student: Yh open ni h raha hai... project
    23/6/22, 9:12 am - ~K: Aa gya Hai Mera internet btayn ab
    23/6/22, 9:22 am - ~K: Or Thora jaldi krain
    23/6/22, 9:22 am - Tayaba Malik Student: Teacher
    23/6/22, 9:23 am - Tayaba Malik Student: Controll l ln
    23/6/22, 9:23 am - ~K: Photo bejhain
    23/6/22, 9:23 am - Tayaba Malik Student: <Media omitted>
    23/6/22, 9:23 am - Tayaba Malik Student: Jaldi s
    23/6/22, 9:23 am - Tayaba Malik Student: Net aha gya hmara b
    23/6/22, 9:23 am - Tayaba Malik Student: Any desk k
    23/6/22, 9:23 am - Tayaba Malik Student: Teacher  hum na ap k request  bji hai
    23/6/22, 9:23 am - ~K: Disconnect ho jay ga phir
    23/6/22, 9:23 am - Tayaba Malik Student: Ni h
    23/6/22, 9:23 am - Tayaba Malik Student: G
    23/6/22, 9:23 am - ~K: <Media omitted>
    23/6/22, 9:23 am - Tayaba Malik Student: L ln jaldi s
    23/6/22, 9:23 am - Tayaba Malik Student: Controll
    23/6/22, 9:24 am - ~K: Apna anydesk on rakhain phir
    23/6/22, 9:24 am - Tayaba Malik Student: <Media omitted>
    23/6/22, 9:24 am - ~K: Apna mouse na hilayn
    23/6/22, 9:25 am - ~K: Disconnect ho gya
    23/6/22, 9:25 am - ~K: Yahan sy right click ni krna Tha... Close krain isko
    23/6/22, 9:29 am - ~K: Anydesk on kia hoa hai ap ny apna sath main?
    23/6/22, 9:29 am - Tayaba Malik Student: Gg w b on hai
    23/6/22, 9:29 am - Tayaba Malik Student: <Media omitted>
    23/6/22, 9:32 am - Tayaba Malik Student: <Media omitted>
    23/6/22, 9:35 am - ~K: Photo bejhain
    23/6/22, 9:36 am - Tayaba Malik Student: <Media omitted>
    23/6/22, 9:36 am - ~K: Han g... Yahe code hai
    23/6/22, 9:37 am - ~K: Ab libraries download krain jaldi sy command prompt per
    23/6/22, 9:37 am - Tayaba Malik Student: Ok
    23/6/22, 9:37 am - Tayaba Malik Student: Teacher
    23/6/22, 9:37 am - ~K: <Media omitted>
    23/6/22, 9:38 am - Tayaba Malik Student: Ok
    23/6/22, 9:39 am - ~K: Libraries kr lain ge khud download ab ap?
    23/6/22, 9:39 am - Tayaba Malik Student: Gg
    23/6/22, 9:40 am - Tayaba Malik Student: Net k bht issue  University  mein agar na hui t khli code deakha k b marks lag jyn g
    23/6/22, 9:40 am - ~K: Thk Hai phir... Q k wo libraries download hony main apna acha khasa time laiti hain achy Waly net per b
    23/6/22, 9:41 am - ~K: <Media omitted>
    23/6/22, 9:41 am - Tayaba Malik Student: Ok
    23/6/22, 9:41 am - Tayaba Malik Student: Bs yh code theek hai
    23/6/22, 9:42 am - Tayaba Malik Student: Ok
    23/6/22, 7:45 pm - ~K: Demo ho gya tha phir apka?
    23/6/22, 7:47 pm - Tayaba Malik Student: Ni
    23/6/22, 7:47 pm - Tayaba Malik Student: Kal h ga
    23/6/22, 7:47 pm - ~K: Apki Bari ni ai?
    23/6/22, 7:48 pm - Tayaba Malik Student: Gg
    23/6/22, 7:48 pm - Tayaba Malik Student: Bari hi ni ahi
    24/6/22, 8:33 am - Tayaba Malik Student: Teacher
    24/6/22, 8:33 am - Tayaba Malik Student: Ik kam kar dn
    24/6/22, 8:33 am - Tayaba Malik Student: Project  k screen short bj dn
    24/6/22, 8:33 am - Tayaba Malik Student: Output k
    24/6/22, 9:06 am - ~K: To apka run ni hoa?
    24/6/22, 9:07 am - Tayaba Malik Student: Sir kha rahy hai. Ap output aur code k ss deakha dn
    24/6/22, 9:07 am - Tayaba Malik Student: Office aha k
    24/6/22, 9:08 am - ~K: To screenshot q... Run ni hoa wo?
    24/6/22, 9:08 am - Tayaba Malik Student: Ni hua
    24/6/22, 9:09 am - Tayaba Malik Student: Ap code k aur us ki output  k ss bj dn
    24/6/22, 9:09 am - ~K: Ok bahd main laptop on krti hn to phir bejh don ge apko
    24/6/22, 9:11 am - Tayaba Malik Student: Ok
    24/6/22, 9:11 am - Tayaba Malik Student: 10 bjy tak
    24/6/22, 9:22 am - ~K: Main free ho kr bejhti hn apko
    24/6/22, 9:24 am - Tayaba Malik Student: Ok
    24/6/22, 10:45 am - Tayaba Malik Student: Teacher
    24/6/22, 10:45 am - Tayaba Malik Student: Ab bj dn ...
    24/6/22, 10:45 am - Tayaba Malik Student: Ss
    24/6/22, 10:45 am - Tayaba Malik Student: 11 bjy hmari  bari hai
    24/6/22, 11:03 am - ~K: <Media omitted>
    24/6/22, 11:03 am - ~K: <Media omitted>
    24/6/22, 11:06 am - ~K: Is main code ka ss add kr lijiay ga wo mery zehan main ni rha add krna
    24/6/22, 11:08 am - Tayaba Malik Student: Okok thanku
    24/6/22, 11:09 am - ~K: Ho gya apka ya abhi hona hai?
    24/6/22, 11:10 am - Tayaba Malik Student: Abhi jna
    24/6/22, 11:10 am - Tayaba Malik Student: Bs iss group  k bad
    24/6/22, 11:10 am - ~K: Ok
    26/6/22, 7:11 pm - Tayaba Malik Student: A.o.a teacher
    26/6/22, 7:12 pm - Tayaba Malik Student: Meim na suba University  feed dni hai... t ATM s ap k passy b niklwa liya
    26/6/22, 7:12 pm - Tayaba Malik Student: Easipaisa  k bta dn ksy karwany... kia details hain...
    26/6/22, 7:20 pm - ~K: W. Aslam
    26/6/22, 7:21 pm - ~K: Ap apni frnd ko dain ge na mera yeh number...or usko bolain isko save kry... Easypaisa app per ja k contacts main usko Mera number show ho jay ga... Bs us per easypaisa kr dy wo
    26/6/22, 7:22 pm - ~K: Or ap usy payment by hand dy dijiay ga... Apna number main idhar apko text msg per likh k b bta daiti hn... Yahe sy daikh k usy bta daina
    26/6/22, 7:22 pm - ~K: 03125962717
    26/6/22, 7:26 pm - Tayaba Malik Student: Ok
    26/6/22, 7:30 pm - ~K: <Media omitted>
    26/6/22, 7:36 pm - Tayaba Malik Student: Okok
    28/6/22, 1:05 pm - ~K: Tyabba apko frnd sy procedure ho gya tha phir yeh wala?
    28/6/22, 1:05 pm - ~K: Apki *
    28/6/22, 1:05 pm - Tayaba Malik Student: G h gya tha
    28/6/22, 1:05 pm - Tayaba Malik Student: Passy d diya
    28/6/22, 1:06 pm - ~K: To ap ny pucha us sy?
    28/6/22, 1:06 pm - ~K: K bejh diay us ny ya ni
    28/6/22, 1:06 pm - Tayaba Malik Student: Kal gai thi easipaais  krny
    28/6/22, 1:06 pm - ~K: Phir?
    28/6/22, 1:06 pm - Tayaba Malik Student: Lkin ni huy ... boll ki dates hain t
    28/6/22, 1:06 pm - ~K: Bill ki dates?
    28/6/22, 1:08 pm - Tayaba Malik Student: G
    28/6/22, 1:08 pm - Tayaba Malik Student: Us k easipasa mein  itny pasy ni thy
    28/6/22, 1:08 pm - ~K: G wo mjy idea ho gya tha apki frnd k account main ni hon gy
    28/6/22, 1:08 pm - Tayaba Malik Student: Kha rahi thi sham k eassipas karu gi baj gu gi
    28/6/22, 1:09 pm - Tayaba Malik Student: T kal 3000 huy bs
    28/6/22, 1:09 pm - Tayaba Malik Student: Aj phir jya gi t kal tk h jyn g
    28/6/22, 1:09 pm - ~K: Us larki k account main?
    28/6/22, 1:10 pm - Tayaba Malik Student: G
    28/6/22, 1:10 pm - ~K: Sae sae
    29/6/22, 7:54 pm - ~K: Tyabba!
    29/6/22, 8:18 pm - Tayaba Malik Student: G
    29/6/22, 8:18 pm - Tayaba Malik Student: <Media omitted>
    29/6/22, 8:18 pm - Tayaba Malik Student: Yh ap k aj bjhn hain
    ..
    29/6/22, 8:19 pm - ~K: Han g 5000 recieve hoa hai mjy
    29/6/22, 8:19 pm - Tayaba Malik Student: Abhi itny hi akhty huy thy... aj t yh bjwa diya... q k aj last day tha...
    29/6/22, 8:19 pm - Tayaba Malik Student: Chitian h gi
    29/6/22, 8:19 pm - Tayaba Malik Student: T mein na yh bjwa diya aj ....b
    29/6/22, 8:19 pm - ~K: Last day kis cheez ka?
    29/6/22, 8:19 pm - Tayaba Malik Student: 500  500  akhty kia ...
    29/6/22, 8:20 pm - Tayaba Malik Student: Chutian h gi hain paper khatam h gya
    29/6/22, 8:20 pm - ~K: Paper ho gay apky?
    29/6/22, 8:21 pm - Tayaba Malik Student: G
    29/6/22, 8:21 pm - Tayaba Malik Student: Aj last tha
    29/6/22, 8:21 pm - ~K: Acha Acha apky pas ni ikathy hoay thy? Yeh keh rhe hain
    29/6/22, 8:21 pm - ~K: Kaisy hoay paper apky
    29/6/22, 8:21 pm - Tayaba Malik Student: Papers achy huy
    29/6/22, 8:22 pm - ~K: Or demo or wo normalization Wali assignment k number pta chaly?
    29/6/22, 8:22 pm - Tayaba Malik Student: Teacher w bat yh hai ....k jis k easipasa  s bjwa na w hmry group k hain... un k pass 6000 ni thy easipasa  mein... mein na un k cash diya t University  k bahir kahin easipasa  hai wahn gya... karwany
    29/6/22, 8:23 pm - Tayaba Malik Student: T 3000 ik din huy
    29/6/22, 8:23 pm - Tayaba Malik Student: Baki 500 500 kr k University  class mein jis k easipasa  tha us s liya un k cash d di jis na jitny bjy...
    29/6/22, 8:23 pm - Tayaba Malik Student: Phir 5000 bna aj aur ap k bjwaya
    29/6/22, 8:24 pm - Tayaba Malik Student: Q k aj off  h rha tha chutian  h rahi thi... t mein na kha k ap l jitni bjwa sku
    29/6/22, 8:24 pm - Tayaba Malik Student: T 5000 bj diya... aj phir
    29/6/22, 8:25 pm - ~K: Acha Acha.... Ufff toba... Itni lambi khap Bani mtlb apki
    29/6/22, 8:26 pm - ~K: Mery zehan main he ni rha... Bahd main aya... K jb ap bank gai the nikalwany... Wohe sy direct ap Mery account main transfer krwa daiti... Wo apky liay b asan hota yeh to sae Khap aik kisam ki Bani hai
    29/6/22, 8:27 pm - Tayaba Malik Student: Hmm aj hum passy hi mangy rahy
    29/6/22, 8:28 pm - ~K: Apky ghar main account ni Hai kisi ka?
    29/6/22, 8:28 pm - ~K: Bank account
    29/6/22, 8:28 pm - Tayaba Malik Student: Ni
    29/6/22, 8:28 pm - Tayaba Malik Student: Koi use ni karta na easypais  na jazz cash
    29/6/22, 8:28 pm - Tayaba Malik Student: W hai
    29/6/22, 8:29 pm - ~K: Direct account to account b transfer ho jaty hain
    29/6/22, 8:29 pm - Tayaba Malik Student: Acha... chln next time ab phir asy kar ln g
    29/6/22, 8:29 pm - ~K: Acha khair chorain usy... Phir wo apka class fellow ab to chutiyan hain... Easily remaining bejh day ga
    29/6/22, 8:29 pm - ~K: Abhi apka sem break hai phir?
    29/6/22, 8:30 pm - Tayaba Malik Student: 1000 rh gya...
    29/6/22, 8:30 pm - Tayaba Malik Student: W b bjwa du gi
    29/6/22, 8:30 pm - Tayaba Malik Student: Eid k bad jna hai  abhi t
    29/6/22, 8:30 pm - ~K: Han g... Internet banking beshak activate kra lain... Ya bank ja k transfer krwa lain
    29/6/22, 8:30 pm - ~K: Yeh sem k bahd break ni milna tha apko?
    29/6/22, 8:32 pm - Tayaba Malik Student: Ni
    29/6/22, 8:32 pm - Tayaba Malik Student: Teacher kn s app ss bj dn
    29/6/22, 8:33 pm - ~K: Jis bank main account hota hai na... Uski website per hota hai ja kr
    29/6/22, 8:34 pm - Tayaba Malik Student: Ok
    29/6/22, 8:38 pm - ~K: Or numbero ka ni btaya tayabba ap ny mjy
    29/6/22, 8:39 pm - ~K: Kya bana unka
    29/6/22, 8:39 pm - Tayaba Malik Student: Abhi kuch ni pta chla
    29/6/22, 8:45 pm - ~K: Internals ni pta chaly?
    29/6/22, 8:45 pm - Tayaba Malik Student: Internal kia hta hai
    29/6/22, 8:46 pm - ~K: 😂
    29/6/22, 8:46 pm - ~K: I guess ap log sessional kehty ho usy
    29/6/22, 8:46 pm - Tayaba Malik Student: Sachi ni pta
    29/6/22, 8:46 pm - Tayaba Malik Student: G
    29/6/22, 8:46 pm - Tayaba Malik Student: Us k sab mein achy
    29/6/22, 8:46 pm - ~K: 50 ya 60 marks ka paper hota hai na final ka... Us k ilawa jo marks hoty hain wo
    29/6/22, 8:46 pm - Tayaba Malik Student: Ab yaad ni hai
    29/6/22, 8:46 pm - Tayaba Malik Student: Kitny  thy
    29/6/22, 8:47 pm - ~K: Acha Acha chalain... Mjy to q k ap ny tension main he dal dia Tha us din bta k
    29/6/22, 8:47 pm - Tayaba Malik Student: Hahah
    29/6/22, 8:48 pm - Tayaba Malik Student: Khud samj ni ahi... teacher k h kia gya...
    29/6/22, 8:48 pm - Tayaba Malik Student: Suba s l l k project  ki presentation  khud ki halat  khrab  thi
    29/6/22, 8:48 pm - ~K: Dusry wala demo kaisa hoa Tha apka
    29/6/22, 8:48 pm - ~K: AI ka
    29/6/22, 8:48 pm - Tayaba Malik Student: W Acha hua tha
    29/6/22, 8:48 pm - Tayaba Malik Student: W sahi hua
    29/6/22, 8:48 pm - ~K: Us per to ni kaha sir ny kuch
    29/6/22, 8:48 pm - Tayaba Malik Student: Kuch b ni pucha sir n
    29/6/22, 8:48 pm - Tayaba Malik Student: Bs output deakhi
    29/6/22, 8:49 pm - ~K: Chalo shukar hai
    29/6/22, 8:49 pm - ~K: Adhi degree akhir kar phir apki b ho he gai
    29/6/22, 8:49 pm - ~K: Finally 😂
    29/6/22, 8:49 pm - Tayaba Malik Student: Yes
    29/6/22, 8:49 pm - Tayaba Malik Student: Sukr hai
    29/6/22, 8:49 pm - ~K: Agly sem main kya courses hon gy?
    29/6/22, 8:49 pm - Tayaba Malik Student: Now I am half engineer
    29/6/22, 8:49 pm - Tayaba Malik Student: Abhi ni pta  chly
    29/6/22, 8:49 pm - ~K: Bilkul  😂
    29/6/22, 8:50 pm - ~K: Ary larki fees jo jama kra k ai ho... To pta ni Chala sath
    29/6/22, 9:20 pm - Tayaba Malik Student: Teacher w mein  na improvement wali kri
    30/6/22, 10:38 am - ~K: Acha acha..sae
    1/7/22, 6:55 pm - Tayaba Malik Student: A.o.a teacher
    1/7/22, 6:56 pm - Tayaba Malik Student: J ap na python ki assignment  bna k di
    1/7/22, 6:56 pm - Tayaba Malik Student: Us k code  k ss bj dn
    1/7/22, 6:56 pm - Tayaba Malik Student: W open ni h rahi
    1/7/22, 7:18 pm - ~K: Ab uska kya krna Hai ap ny
    1/7/22, 7:19 pm - Tayaba Malik Student: Teacher sir k chy
    1/7/22, 7:19 pm - Tayaba Malik Student: Submit  karwana hai
    1/7/22, 7:19 pm - ~K: Acha main bejhti hn apko
    1/7/22, 7:25 pm - Tayaba Malik Student: Ok
    1/7/22, 7:25 pm - ~K: <Media omitted>
    1/7/22, 7:25 pm - ~K: <Media omitted>
    1/7/22, 7:26 pm - Tayaba Malik Student: Okok
    1/7/22, 7:26 pm - Tayaba Malik Student: Thanku
    10/7/22, 4:51 am - Tayaba Malik Student: <Media omitted>
    10/7/22, 9:23 am - ~K: <Media omitted>
    10/7/22, 9:23 am - ~K: Khair mubarak 🌸 🌸
    10/7/22, 9:24 am - Tayaba Malik Student: Khair Mubarak ❤️
    22/7/22, 9:25 am - ~K: Tyabba!
    22/7/22, 9:25 am - ~K: Apki uni start ho gai?
    22/7/22, 9:41 am - Tayaba Malik Student: Ni teacher
    22/7/22, 9:42 am - ~K: Acha jo apky classfellow hain... Unko bolain k... Jo remaining thy wo mjy bejh dain
    22/7/22, 9:42 am - ~K: Abhi tk recieve ni hoay mjy
    22/7/22, 9:42 am - ~K: Ap ny to dy diay thy na unhain?
    22/7/22, 9:44 am - Tayaba Malik Student: Teacher  mein na un k diya hi ni thy
    22/7/22, 9:45 am - ~K: Ap ny puri payment us bandy ko dy ni di the... 6k?
    22/7/22, 9:47 am - Tayaba Malik Student: Ni
    22/7/22, 9:47 am - Tayaba Malik Student: Di thi
    22/7/22, 9:47 am - Tayaba Malik Student: Unhon na wapis kr di thi
    22/7/22, 9:47 am - ~K: Acha phir uska kya krna hai
    22/7/22, 9:48 am - Tayaba Malik Student: 5000 h gya thy
    22/7/22, 9:48 am - Tayaba Malik Student: W l liya tha
    22/7/22, 9:48 am - Tayaba Malik Student: 1000 wapis kr diya thy
    22/7/22, 9:48 am - Tayaba Malik Student: Teacher  bjwa du gi...ksi tra
    22/7/22, 9:48 am - Tayaba Malik Student: By hand
    22/7/22, 9:49 am - Tayaba Malik Student: Yh easipasa hi krwa du gi
    22/7/22, 9:49 am - ~K: Ary yr... Kya ab aik hazar k liay special bejho ge ap kisi ko
    22/7/22, 9:49 am - ~K: Han yeh kr daina... Much better
    22/7/22, 9:49 am - Tayaba Malik Student: Ok
    29/7/22, 8:31 am - ~K: Han g tyabba.. Easypaisa app ap nay siry sy bnany to ni lag gai kahe 😅
    29/7/22, 8:39 am - Tayaba Malik Student: Teacher  mein na kha  tha cash bjwa dti  hu
    29/7/22, 8:46 am - ~K: Phir... Bejha tha kisi ko ap ny?
    29/7/22, 8:46 am - ~K: Easypaisa ka procedure apko ni pta to mjy btao... Uska smja daiti hn main apko... Ana ni pary ga na waisy
    29/7/22, 8:52 am - Tayaba Malik Student: Ok mein krti kuch
    29/7/22, 8:52 am - Tayaba Malik Student: 2 3 din tk bjwa du gi
    29/7/22, 9:00 am - ~K: Thk Hai... Sunday sy pehly pehly phir bejhwa dain mjy
    29/7/22, 9:10 am - Tayaba Malik Student: Ok
    3/8/22, 7:55 am - ~K: .
    3/8/22, 7:55 am - Tayaba Malik Student: G teacher
    3/8/22, 7:55 am - ~K: Yeh agly walo k sath dainy ka to plan ni Hai tyabba? 😂
    3/8/22, 7:55 am - Tayaba Malik Student: Teacher  ksi k easipasa  ni hai
    3/8/22, 7:55 am - Tayaba Malik Student: Kia kru
    3/8/22, 7:56 am - Tayaba Malik Student: Jis k number s phly  bjwa thy
    3/8/22, 7:56 am - Tayaba Malik Student: W chutin hain ghar gya hua
    3/8/22, 7:56 am - Tayaba Malik Student: University  bnd hai
    3/8/22, 7:57 am - ~K: Phir ap by hand bejhwa dain
    3/8/22, 7:57 am - ~K: Shops per ja kr q ni krwa daiti ap easypaisa
    3/8/22, 7:57 am - ~K: Bht sari shops hoti hain jo easypaisa krwa daiti hain paisy
    3/8/22, 7:57 am - Tayaba Malik Student: Ok
    3/8/22, 7:57 am - Tayaba Malik Student: Jazz cash  ???
    3/8/22, 7:58 am - ~K: Easypaisa
    3/8/22, 7:58 am - ~K: Ab agli kis date ki umeed lagao main? 😂
    3/8/22, 7:58 am - Tayaba Malik Student: Jazz cash hai
    3/8/22, 7:58 am - ~K: Jazz cash ka apka account hai??
    3/8/22, 7:59 am - Tayaba Malik Student: Ni
    3/8/22, 7:59 am - ~K: Agr aik side jazz cash ka account ho.. Or dusry bandy ka easypaisa... Tb b paisy transfer ho jaty hain
    3/8/22, 7:59 am - Tayaba Malik Student: Lkin mein jazz cash krwa du
    3/8/22, 7:59 am - ~K: Shop sy krwao ge?
    3/8/22, 8:00 am - Tayaba Malik Student: Hmm
    3/8/22, 8:00 am - ~K: Bs... Usko ja k bolna... Yeh no hai... Easypaisa ka account hai... Is per paisy send kr dain... Agy unko pta hota hai
    3/8/22, 8:00 am - Tayaba Malik Student: Ok
    3/8/22, 8:00 am - ~K: Laiken... Separately btana yeh... K easypaisa account hai... Mtlb mera
    3/8/22, 8:01 am - Tayaba Malik Student: Hm
    11/8/22, 8:12 pm - ~K: Aoa! Tyabba ap ny remaining wali payment ka kya krna Hai phir? Daini hai ya rakhni hai pas?
    11/8/22, 8:46 pm - Tayaba Malik Student: Waslam
    11/8/22, 8:46 pm - Tayaba Malik Student: Teacher mein q rkhu gi
    11/8/22, 8:48 pm - ~K: Yar to date daikho na... Kab ap ny project banwaya tha mj sy
    11/8/22, 8:48 pm - ~K: Mtlb mjy aisy bar bar kehna Acha ni lagta asal main
    11/8/22, 8:49 pm - Tayaba Malik Student: G... ok
    11/8/22, 8:49 pm - Tayaba Malik Student: Teacher mein na ik lrki k kha doya
    11/8/22, 8:49 pm - Tayaba Malik Student: Diya
    11/8/22, 8:49 pm - Tayaba Malik Student: W kha rahi easipasa  kr du gi
    11/8/22, 8:49 pm - Tayaba Malik Student: T easipasa  krwa du gi
    11/8/22, 8:50 pm - ~K: To ap apny ghar walo main sy kisi k number per easypaisa q ni banwati... Mjy smj ni ati bt
    11/8/22, 8:51 pm - Tayaba Malik Student: Teacher yhn ksi k pass ni hai
    11/8/22, 8:52 pm - ~K: Yar banwa lo... 5 min ni lagty
    11/8/22, 8:52 pm - ~K: Mtlb... Aisy kabi kis ko kehna kabi kis ko.. Yeh b koi bht acha method ni Hai na... Khud account bna k jhanjat sy farig ho
    11/8/22, 9:01 pm - Tayaba Malik Student: Ok mein abhi bnati
    11/8/22, 9:08 pm - ~K: G bnay
    11/8/22, 9:08 pm - ~K: And I didn't mean to talk like that... But the fact is... K mjy br br kehna bs Acha ni lagta
    11/8/22, 9:08 pm - Tayaba Malik Student: Teacher
    11/8/22, 9:08 pm - Tayaba Malik Student: Mein Instal kr rahi
    11/8/22, 9:08 pm - ~K: Install kr k mjy btay... Agr apko smj ni ata... Account kaisy bnana hai to
    11/8/22, 9:08 pm - Tayaba Malik Student: Teacher it's ok
    11/8/22, 9:09 pm - Tayaba Malik Student: Koi  bat ni
    12/8/22, 10:13 am - ~K: Install ho gai the?
    12/8/22, 10:13 am - Tayaba Malik Student: Ni teacher
    12/8/22, 10:14 am - ~K: Q
    12/8/22, 10:14 am - Tayaba Malik Student: Mery play store  s kuch ni instal h raha tha
    12/8/22, 10:14 am - Tayaba Malik Student: Kal
    12/8/22, 10:14 am - Tayaba Malik Student: Abhi try krti
    12/8/22, 10:14 am - ~K: G krain try
    12/8/22, 10:14 am - ~K: Or btayn phir mjy
    12/8/22, 10:14 am - Tayaba Malik Student: Gg
    12/8/22, 10:17 am - Tayaba Malik Student: <Media omitted>
    12/8/22, 10:17 am - ~K: Isko open krain
    12/8/22, 10:17 am - ~K: Or apny phone ki storage b check krain
    12/8/22, 10:17 am - ~K: Kahe phone out of storage to ni ho gya
    12/8/22, 10:17 am - Tayaba Malik Student: Hmm
    12/8/22, 10:17 am - Tayaba Malik Student: Ok
    12/8/22, 10:19 am - Tayaba Malik Student: Teacher storage  theek  hai
    12/8/22, 10:21 am - ~K: Isko open kia ap ny?
    12/8/22, 10:22 am - Tayaba Malik Student: G
    12/8/22, 10:22 am - Tayaba Malik Student: Kia
    12/8/22, 10:22 am - ~K: Kya khula samny
    12/8/22, 10:22 am - Tayaba Malik Student: Wait for fixing  problem
    12/8/22, 10:22 am - ~K: Ss bejhain
    12/8/22, 10:23 am - Tayaba Malik Student: <Media omitted>
    12/8/22, 10:23 am - ~K: Koi b app ni download ho rhe?
    12/8/22, 10:23 am - ~K: Ya sirf yahe ni ho rhe?
    12/8/22, 10:24 am - ~K: Koi or app zra download kr k check krain
    12/8/22, 10:24 am - Tayaba Malik Student: Koi b ni h raha
    12/8/22, 10:24 am - Tayaba Malik Student: Mera
    12/8/22, 10:24 am - Tayaba Malik Student: Kal s
    12/8/22, 10:24 am - Tayaba Malik Student: Sab p yh likh ata
    12/8/22, 10:24 am - Tayaba Malik Student: Wait
    12/8/22, 10:24 am - Tayaba Malik Student: For fixing  problem
    12/8/22, 10:25 am - ~K: Acha let me check... K sirf apka yeh issue hai... Ya sb ka hai Yeh issue
    12/8/22, 10:25 am - Tayaba Malik Student: Hmm
    12/8/22, 10:25 am - Tayaba Malik Student: Ok
    12/8/22, 10:26 am - ~K: Screen recording krni ati hai apko?
    12/8/22, 10:26 am - Tayaba Malik Student: Ni
    12/8/22, 10:27 am - Tayaba Malik Student: Us s kia h ga
    12/8/22, 10:27 am - ~K: <Media omitted>
    12/8/22, 10:28 am - Tayaba Malik Student: Ok
    12/8/22, 10:28 am - ~K: Kr lo ge?
    12/8/22, 10:31 am - Tayaba Malik Student: Sahi hai
    12/8/22, 10:31 am - Tayaba Malik Student: <Media omitted>
    12/8/22, 10:32 am - ~K: <Media omitted>
    12/8/22, 10:33 am - ~K: <Media omitted>
    12/8/22, 10:33 am - Tayaba Malik Student: Sign in ksy kru
    12/8/22, 10:33 am - ~K: <Media omitted>
    12/8/22, 10:34 am - Tayaba Malik Student: Ok
    12/8/22, 10:35 am - Tayaba Malik Student: <Media omitted>
    12/8/22, 10:37 am - ~K: Main btati hn apko iska koi hal
    12/8/22, 10:37 am - Tayaba Malik Student: Hmm
    12/8/22, 10:42 am - ~K: Aik Kam krain
    12/8/22, 10:42 am - ~K: <Media omitted>
    12/8/22, 10:44 am - Tayaba Malik Student: <Media omitted>
    12/8/22, 10:46 am - ~K: <Media omitted>
    12/8/22, 10:46 am - ~K: Is main jayn
    12/8/22, 10:50 am - Tayaba Malik Student: Teacher  ni hua
    12/8/22, 10:50 am - Tayaba Malik Student: Clear cache b kia
    12/8/22, 10:50 am - Tayaba Malik Student: Koi extra app b ni
    12/8/22, 10:51 am - ~K: Google store ka cache clear kia ap ny?
    12/8/22, 10:52 am - Tayaba Malik Student: Ok
    12/8/22, 10:52 am - Tayaba Malik Student: Deakhti
    12/8/22, 10:53 am - Tayaba Malik Student: Gg kia
    12/8/22, 10:54 am - ~K: Dobara install kr k try kia ap ny?
    12/8/22, 10:54 am - ~K: <Media omitted>
    12/8/22, 10:55 am - Tayaba Malik Student: Ni hua phir b
    12/8/22, 10:55 am - Tayaba Malik Student: Ok
    12/8/22, 10:56 am - Tayaba Malik Student: <Media omitted>
    12/8/22, 10:57 am - ~K: <Media omitted>
    12/8/22, 10:58 am - Tayaba Malik Student: Hmm ok
    12/8/22, 10:59 am - Tayaba Malik Student: <Media omitted>
    12/8/22, 10:59 am - Tayaba Malik Student: <Media omitted>
    12/8/22, 11:00 am - ~K: Yeh dusry account sy try kia hai ap ny?
    12/8/22, 11:00 am - ~K: Install krna
    12/8/22, 11:00 am - Tayaba Malik Student: G
    12/8/22, 11:00 am - Tayaba Malik Student: Ni hua
    12/8/22, 11:00 am - Tayaba Malik Student: Same issue
    12/8/22, 11:01 am - ~K: Yeh kya problem hai
    12/8/22, 11:01 am - Tayaba Malik Student: Pta ni
    12/8/22, 11:01 am - Tayaba Malik Student: Teacher
    12/8/22, 11:01 am - ~K: <Media omitted>
    12/8/22, 11:01 am - Tayaba Malik Student: Koi app b install  ni h rga
    12/8/22, 11:01 am - Tayaba Malik Student: Rha
    12/8/22, 11:02 am - Tayaba Malik Student: Ok
    12/8/22, 11:06 am - ~K: Daikhi ap ny?
    12/8/22, 11:06 am - ~K: <Media omitted>
    12/8/22, 11:07 am - Tayaba Malik Student: Teacher
    12/8/22, 11:07 am - Tayaba Malik Student: UPDATED hai
    12/8/22, 11:07 am - Tayaba Malik Student: Koi system update  ni ahi
    12/8/22, 11:07 am - Tayaba Malik Student: Teacher kl kia kal b yh issue  tha
    12/8/22, 11:08 am - Tayaba Malik Student: Ab kr rahi ab b
    12/8/22, 11:08 am - Tayaba Malik Student: Net ni week sab use kr rahy
    12/8/22, 11:08 am - Tayaba Malik Student: Aur mein ghar hu
    12/8/22, 11:08 am - Tayaba Malik Student: T ghar k ksy week h ga net
    12/8/22, 11:08 am - ~K: Mjy uska ss bejhain zra
    12/8/22, 11:08 am - ~K: Ho b jata hai na aksar
    12/8/22, 11:08 am - Tayaba Malik Student: Ok
    12/8/22, 11:09 am - Tayaba Malik Student: <Media omitted>
    12/8/22, 11:10 am - Tayaba Malik Student: YouTube b chl rha
    12/8/22, 11:10 am - ~K: Hmmm... Latest he hai Yeh to
    12/8/22, 11:10 am - ~K: <Media omitted>
    12/8/22, 11:11 am - Tayaba Malik Student: Kal s
    12/8/22, 11:11 am - Tayaba Malik Student: Usy phly kuch instal ni kia
    12/8/22, 11:13 am - ~K: Lamba he masla hai... Chalo I'll check agr mjy kuch solution milta hai iska to
    12/8/22, 11:13 am - Tayaba Malik Student: Ok
    12/8/22, 11:13 am - Tayaba Malik Student: Wasi teacher  mein na ik uni ki lrki h kha diya
    12/8/22, 11:13 am - Tayaba Malik Student: W kr d gi
    12/8/22, 11:13 am - Tayaba Malik Student: Us na kha hai
    12/8/22, 11:14 am - Tayaba Malik Student: Khti mujy passy dna  mein bjwa du gi
    12/8/22, 11:14 am - Tayaba Malik Student: Aj humy chuti thi
    12/8/22, 11:14 am - Tayaba Malik Student: Monday  k kr d gi
    12/8/22, 11:14 am - ~K: Han but... Apky pas app to honi chahiay na
    12/8/22, 11:15 am - Tayaba Malik Student: Hmm
    12/8/22, 11:15 am - Tayaba Malik Student: Yh mein kru gi install
    12/8/22, 11:16 am - Tayaba Malik Student: Phir mujy btya g k iss easipasa  mein account  bnny k
    12/8/22, 11:15 am - ~K: <Media omitted>
    12/8/22, 11:16 am - ~K: Han g... Per pehly yeh issue to hal ho
    12/8/22, 11:16 am - Tayaba Malik Student: Hm
    12/8/22, 11:16 am - Tayaba Malik Student: Ok
    17/8/22, 12:08 pm - ~K: Tayabba apki payment Monday ko any ni wali the?
    17/8/22, 12:08 pm - Tayaba Malik Student: Teacher  mein abhi University  ni
    17/8/22, 12:09 pm - Tayaba Malik Student: Gai kal jna hai
    17/8/22, 12:09 pm - Tayaba Malik Student: Abhi chutin  h gai
    17/8/22, 12:09 pm - Tayaba Malik Student: Kal bjwa du gi
    17/8/22, 12:09 pm - ~K: To us larki ko msg kr k ap bol dain
    17/8/22, 12:09 pm - Tayaba Malik Student: Mein us lrki k passy du gi w kr d gi
    17/8/22, 12:09 pm - Tayaba Malik Student: Kha hai khti passy dna kr du gi
    17/8/22, 12:09 pm - Tayaba Malik Student: Abhi University  off hai suba  s jna
    17/8/22, 12:10 pm - Tayaba Malik Student: T suba 1st yh bjwa du gi
    17/8/22, 12:11 pm - ~K: Ok
    18/8/22, 8:25 am - Tayaba Malik Student: Aoa
    18/8/22, 8:25 am - Tayaba Malik Student: Teacher
    18/8/22, 8:25 am - Tayaba Malik Student: 900 rupees  available  hain us k account  mein mein na w bjwa diya
    18/8/22, 8:26 am - ~K: G... W. Aslam
    18/8/22, 8:26 am - ~K: Mjy to ni milly
    18/8/22, 8:26 am - Tayaba Malik Student: <Media omitted>
    18/8/22, 8:26 am - Tayaba Malik Student: 30.minutes tk aha jyn g
    18/8/22, 8:26 am - Tayaba Malik Student: Jazz cash s bjwa hain
    18/8/22, 8:27 am - ~K: Han g aa gay
    18/8/22, 8:27 am - ~K: Thank you
    18/8/22, 8:27 am - Tayaba Malik Student: Ok
    18/8/22, 8:27 am - Tayaba Malik Student: Ab 100 rh gya hain
    18/8/22, 8:28 am - Tayaba Malik Student: W mein ksi aur s puchti hu
    18/8/22, 8:28 am - ~K: Wo ap masjid main dal dain😂
    18/8/22, 8:28 am - Tayaba Malik Student: Iss k account  meim bs itny hi thy
    18/8/22, 8:28 am - ~K: Rehny dain 100 rp ko
    18/8/22, 8:28 am - Tayaba Malik Student: Sry bjwa diya
    18/8/22, 8:28 am - Tayaba Malik Student: Hmm
    18/8/22, 8:29 am - Tayaba Malik Student: Acha teacher
    18/8/22, 8:29 am - Tayaba Malik Student: Meri kal sir
    18/8/22, 8:29 am - Tayaba Malik Student: S bat  hui
    18/8/22, 8:29 am - Tayaba Malik Student: Sir hammad s
    18/8/22, 8:29 am - ~K: Kis bary main
    18/8/22, 8:29 am - Tayaba Malik Student: Accaemeny  bjna tha bahi k
    18/8/22, 8:29 am - Tayaba Malik Student: 1st year ki
    18/8/22, 8:29 am - ~K: Acha phir? Ay ga bhai apka?
    18/8/22, 8:30 am - Tayaba Malik Student: G
    18/8/22, 8:30 am - Tayaba Malik Student: Sir na kha hai
    18/8/22, 8:30 am - Tayaba Malik Student: Bi dn
    18/8/22, 8:30 am - Tayaba Malik Student: Bj*
    18/8/22, 8:30 am - ~K: Chalain sae ho gya
    18/8/22, 8:30 am - Tayaba Malik Student: G
    18/8/22, 8:30 am - ~K: Main to ni krwati waisy 1st year k bacho ko but sir hain usky liay
    18/8/22, 8:31 am - Tayaba Malik Student: Acha
    18/8/22, 8:31 am - Tayaba Malik Student: Chln
    18/8/22, 8:31 am - Tayaba Malik Student: Thanku  to all
    20/9/23, 9:01 am - Tayaba Malik Student: A.o.a  teacher...
    20/9/23, 9:01 am - Tayaba Malik Student: Here tayyaba... jb free hn t btiya  g bat krni h...
    20/9/23, 9:11 am - ~K: W.aslam...g btayn
    20/9/23, 9:11 am - Tayaba Malik Student: Teacher ... python  krwa dn gi
    20/9/23, 9:11 am - Tayaba Malik Student: Project  krna h ... uss p
    20/9/23, 9:11 am - Tayaba Malik Student: Project  m b help chy ...
    20/9/23, 9:12 am - Tayaba Malik Student: Topic  h ... *AI* based gesture  controlled  system  for smart devices
    20/9/23, 9:13 am - Tayaba Malik Student: Gestures limited  hn ... data set madam na dia h bs uss k works krna  aur system bna h....
    20/9/23, 9:20 am - Tayaba Malik Student: Teacher m ap k call krti hu... abhi class h rhi...
    20/9/23, 9:21 am - ~K: Meri phir meeting start ho jay ge, chalain sham main phir main Apko call kr lon ge to discuss in detail
    20/9/23, 9:21 am - Tayaba Malik Student: Okok
    20/9/23, 6:22 pm - ~K: Am home, ap apni availability K hisab sy call kr laina mjy before 11
    22/9/23, 12:33 pm - Tayaba Malik Student: https://docs.google.com/forms/d/e/1FAIpQLSdDaho4prchzRK20oaQjdePn7Tt7QwaiMrOa84zkUJ_g3VOGA/viewform?usp=sf_link
    22/9/23, 1:07 pm - ~K: Kya discussion hoi apki apni supervisor K sath?
    22/9/23, 8:18 pm - Tayaba Malik Student: Teacher  hua h dissus
    22/9/23, 8:18 pm - Tayaba Malik Student: Khti m templates  share krti
    22/9/23, 8:18 pm - Tayaba Malik Student: Phr 5 bjy off  hui  uni tb tk t ni di ...
    22/9/23, 8:19 pm - Tayaba Malik Student: Soft format  m b ni bjhi abhi tk
    22/9/23, 9:24 pm - ~K: Form unho ny Kaha Apko fill krany K liay?
    23/9/23, 10:41 am - Tayaba Malik Student: Gg
    23/9/23, 10:41 am - Tayaba Malik Student: Circulate b krna  aur fill b
    23/9/23, 11:06 am - ~K: Aik Kam kro let me know when you are free hm is per dobara aik quick discussion session Rakh laity Hain
    23/9/23, 11:06 am - Tayaba Malik Student: Ok
    23/9/23, 11:06 am - Tayaba Malik Student: Ap jb khyn
    23/9/23, 11:06 am - Tayaba Malik Student: Aj mra off h
    23/9/23, 11:06 am - Tayaba Malik Student: M free hu
    23/9/23, 11:08 am - ~K: Main krti hn Apko call thori dair tk
    23/9/23, 11:08 am - Tayaba Malik Student: Ok
    7/10/23, 11:27 am - ~K: Tayyaba Apka proposal ho Gaya final?
    7/10/23, 7:55 pm - Tayaba Malik Student: G teacher  h gya h ... aj hi defenses tha
    7/10/23, 9:43 pm - ~K: Chalo SAE Hai...mjy ap update kr Daina phir accordingly
    7/10/23, 9:47 pm - Tayaba Malik Student: Teacher laptop  m proposal h mein ap k forward  krti hu uss m sb likha h k kia ksa krna h ... suba Inshallah  call p explain  kru gi h b aj hua questions waghira sb
    7/10/23, 10:37 pm - ~K: G thk hai
    10/10/23, 10:26 pm - Tayaba Malik Student: <Media omitted>
    11/10/23, 9:23 pm - ~K: <Media omitted>
    11/10/23, 9:25 pm - Tayaba Malik Student: Teacher aj suba madam s bulya  h btyn gi k kia krna h ... humy
    11/10/23, 9:26 pm - Tayaba Malik Student: SRs bnana k khaa rhi thi
    11/10/23, 9:26 pm - Tayaba Malik Student: Abhi yh b ni btya k kia krna hai kis kis na yh document bs liya h ..
    11/10/23, 9:27 pm - ~K: Acha yeh supervisor ny dia Hai ap logo ko doc?
    11/10/23, 9:27 pm - Tayaba Malik Student: G
    11/10/23, 9:28 pm - ~K: <Media omitted>
    11/10/23, 9:28 pm - Tayaba Malik Student: Oky teacher
    1/1/24, 12:02 am - Tayaba Malik Student: ~Happy New  Year~               *May  health, wealth, and prosperity follow you always*✨✨✨
    1/1/24, 9:57 am - ~K: Ameen🌸🌸
    
    


```python
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
     'Tayaba Malik Student: <Media omitted>\n',
     'Tayaba Malik Student: Assalam-o-Alaikum  teacher  time table...\n',
     'Tayaba Malik Student: 1 wla mera h... is week m\n',
     '~K: W. Aslam... SE 3rd A apka hai?\n',
     'Tayaba Malik Student: G\n',
     '~K: To Jin days main 12 40 last class hai apki... Ap ghar kab tk wapis aa jay ge?\n',
     'Tayaba Malik Student: Pta ni... teacher  yh ab gari waly s us din btata h..  k w kab lany ay g...\n',
     'Tayaba Malik Student: Lakin 4 s phly aha jau gi\n',
     '~K: Ap ny khud kya socha hai... Kis kis din aa sky ge ap?\n',
     '~K: Q k Mery khyal sy to Monday ko chor k baki days main flexibility hai any ki\n',
     'Tayaba Malik Student: Teacher m jis din ghar 4 bajy aha gi... m aha jau gi...\n',
     'Tayaba Malik Student: Jis din late h gi phir  off...\n',
     '~K: Chalain thk Hai jaisy easy lagy apko kr laina\n',
     'Tayaba Malik Student: G teacher\n',
     'Tayaba Malik Student: Thanku\n',
     'Tayaba Malik Student: Assalam-o-Alaikum  teacher\n',
     'Tayaba Malik Student: <Media omitted>\n',
     '~K: W. Aslam\n',
     '~K: So u have no class on Sat?\n',
     'Tayaba Malik Student: G teacher  agar  koi arrange  na ki..\n',
     '~K: so currently thursday and saturday are seems to be easy, which other days you think are gonna be easier for you?\n',
     'Tayaba Malik Student: G\n',
     'Tayaba Malik Student: Kal on Monday...\n',
     'Tayaba Malik Student: And  Friday\n',
     '~K: Ok that sounds good. now then you should try to be there on these 4 days\n',
     'Tayaba Malik Student: Yes.. inshallah\n',
     'Tayaba Malik Student: Assalam-o-Alaikum  teacher  aj m ahu gi... m ghar  aha gi ...\n',
     'Tayaba Malik Student: Assalam-o-Alaikum... teacher  email...\n',
     'Tayaba Malik Student: tayaba1389@gmail.com\n',
     '~K: W. Aslam.. Ok i will send you in a while\n',
     'Tayaba Malik Student: G sure teacher  ...\n',
     '~K: It is ok if i send you the picture of the code...the folder seems to be infected which could In turn infect ur system too\n',
     '~K: Is it*\n',
     'Tayaba Malik Student: Yes teacher...\n',
     'Tayaba Malik Student: Sure..\n',
     '~K: Ok\n',
     'Tayaba Malik Student: Thanku...\n',
     '~K: <Media omitted>\n',
     '~K: My pleasure 🌸\n',
     'Tayaba Malik Student: Ok fine... its clear...\n',
     'Tayaba Malik Student: 😇\n',
     "~K: Assalam u alaikum!\nI will let u know today's class time in a while\n",
     'Tayaba Malik Student: Waslam...\n',
     'Tayaba Malik Student: Ok\n',
     '~K: Until then download anydesk in ur system\n',
     'Tayaba Malik Student: Okay\n',
     '~K: Should we start?\n',
     'Tayaba Malik Student: Yes\n',
     '~K: download kr lia ap ny?\n',
     'Tayaba Malik Student: Ni teacher  w ni hua...\n',
     'Tayaba Malik Student: Na cell phone  m na PC m...\n',
     '~K: laptop main krna tha na\n',
     'Tayaba Malik Student: Google  meet chly g???\n',
     'Tayaba Malik Student: Kia h lakin ni hua...\n',
     'Tayaba Malik Student: M picture  bjti...\n',
     '~K: ni...main apki screen ka access lon ge...usky liay anydesk chahiay\n',
     '~K: google per likhain..."download anydesk" first link ko open kr k download kr lain\n',
     'Tayaba Malik Student: Teacher  kal m academy  ahu gi... t check  kar ln...\n',
     'Tayaba Malik Student: Ok\n',
     '~K: <Media omitted>\n',
     '~K: is link sy krain download\n',
     'Tayaba Malik Student: Oky\n',
     '~K: download kr k mjy btaiay phir\n',
     'Tayaba Malik Student: G teacher\n',
     'Tayaba Malik Student: Teacher  yh installed  h gya\n',
     'Tayaba Malik Student: <Media omitted>\n',
     '~K: g thk hai install ho gya hai\n',
     'Tayaba Malik Student: G\n',
     '~K: ab main apky is address k through access kron ge ...request accept kijiay ga\n',
     'Tayaba Malik Student: Ok\n',
     '~K: on krain anydesk apna\n',
     'Tayaba Malik Student: On h\n',
     '~K: main apko 10 min tk call krti hn whats app per he\n',
     'Tayaba Malik Student: Ok\n',
     '~K: tb tk main apko practice btati hn wo krain\n',
     'Tayaba Malik Student: Ok\n',
     '~K: bal k...main abhi krti hn call apko\n',
     'Tayaba Malik Student: Ok\n',
     'Tayaba Malik Student: <Media omitted>\n',
     '~K: Session end ho gya apki side sy anydesk ka?\n',
     'Tayaba Malik Student: G.. h gya\n',
     '~K: Ok\n',
     'Tayaba Malik Student: Thanku teacher\n',
     '~K: Ur most welcome 🌸\n',
     '~K: Can we start?\n',
     'Tayaba Malik Student: yes teacher\n',
     '~K: Ok i will call you in 5 min\n',
     'Tayaba Malik Student: ok\n',
     '~K: Sae ni aa rhe apko awaz?\n',
     '~K: Meri side ka internet weak ho gya hai\n',
     '~K: Stable hota hai to main dobara call krti hn apko\n',
     'Tayaba Malik Student: Ok... teacher  we wait...for while\n',
     'Tayaba Malik Student: Ok\n',
     '~K: Sae hota hai to main inform krti hn apkk\n',
     '~K: Apko*\n',
     'Tayaba Malik Student: Ok\n',
     '~K: Let me try now\n',
     '~K: Completely sae ni hoa... But can give it a try\n',
     'Tayaba Malik Student: Ok\n',
     'Tayaba Malik Student: <Media omitted>\n',
     'Tayaba Malik Student: <Media omitted>\n',
     'Tayaba Malik Student: <Media omitted>\n',
     '~K: Ap aik krain... Is code ko copy kr k word main paste krain\n',
     '~K: Kam*\n',
     'Tayaba Malik Student: ok\n',
     '~K: Us file... Mtlb word ki file ko save krain... Desktop per he kr dain beshak\n',
     'Tayaba Malik Student: ok\n',
     '~K: ab is ko close krain\n',
     '~K: codeblocks ko\n',
     '~K: or system ko restart krain\n',
     'Tayaba Malik Student: ok\n',
     'Tayaba Malik Student: m code block m karti\n',
     '~K: Restart krain ge phir is program krain ge to hopefully ni ay ga error yeh wala\n',
     'Tayaba Malik Student: ok thanku teacher\n',
     '~K: Error aya dobara to do let me know then\n',
     'Tayaba Malik Student: Ok... kar rahi teacher\n',
     '~K: Can we start?\n',
     'Tayaba Malik Student: No teacher.... sorry  aj ni....\n',
     '~K: Ok\n',
     '~K: But is there any reason?\n',
     'Tayaba Malik Student: Aj teacher  m ghar ni hu... t system  ni h...\n',
     '~K: Ok ok no problem\n',
     'Tayaba Malik Student: No  teacher...\n',
     'Tayaba Malik Student: Aj birthday  h t bahir  khna h..\n',
     '~K: Ohhh... Happy birthday 🌸🌸\n',
     '~K: Chalain enjoy krain phir aj to bilkul ni Banta apka parhna😂\n',
     'Tayaba Malik Student: Thanku so much  teacher❤️❤️\n',
     '~K: My pleasure 🌸\n',
     'Tayaba Malik Student: I am really  sorry...\n',
     "~K: No no... Don't be.. It's ok\n",
     '~K: Aj ka bta dain mjy\n',
     'Tayaba Malik Student: Yes teacher  aj class l ln...\n',
     '~K: Ok phir... Can we start the class now?\n',
     'Tayaba Malik Student: Yes ..\n',
     '~K: Chalain\n',
     'Tayaba Malik Student: G\n',
     '~K: Should we start the class?\n',
     'Tayaba Malik Student: G teacher\n',
     'Tayaba Malik Student: Lakin aj hmary  wifi ni chl raha...\n',
     'Tayaba Malik Student: And sorry abhi m na ap k msg deakha...\n',
     '~K: To phir ab?\n',
     '~K: G late kr dia hai na ap ny aj\n',
     'Tayaba Malik Student: G teacher  sorry\n',
     'Tayaba Malik Student: Teacher  kuch net chl jy g\n',
     '~K: Chalain phir... Kal free hon ge ap? Milad wagaira to ni Hai apky ghar?\n',
     'Tayaba Malik Student: Ni...\n',
     'Tayaba Malik Student: Free hu\n',
     '~K: Kal lon ge ab main apki class.. Q k aj already abhi msg late daikhny ki wja sy late kr dia hai ap ny\n',
     'Tayaba Malik Student: Ok no issue\n',
     'Tayaba Malik Student: I am really  sorry teacher\n',
     '~K: Chalain koi bt ni... But dhayan rakha krain.. Is time phone ko Thora pas rakha krain apny\n',
     'Tayaba Malik Student: Teacher  ap mujy koi task  d dn karny k liya\n',
     'Tayaba Malik Student: Ok.. Next time asa ni h ga inshallah\n',
     '~K: Last time grade wala program kia tha hm ny?\n',
     'Tayaba Malik Student: G\n',
     '~K: Main btati hn apko task\n',
     'Tayaba Malik Student: G teacher\n',
     '~K: <Media omitted>\n',
     'Tayaba Malik Student: First hum\n cin number  \nKarn g\n',
     '~K: Usky bahd\n',
     '~K: Condition mjy btay... Kaisy lagay ge\n',
     'Tayaba Malik Student: If if else use karn g...\n',
     '~K: If (yahan per kya ay ga)\n',
     '~K: Condition ny to brackets k andar lagna hai na... Or Sara apka condition ki base per he hoga decide\n',
     'Tayaba Malik Student: First if m hum condition lakin g\nIf(num/2)\n',
     'Tayaba Malik Student: J number  enter karn g us k q 2 s divide kary g j 2 s devide  h jya g w even ... h ga air if m store h jya g\n',
     '~K: <Media omitted>\n',
     '~K: Condition likh k btay\n',
     '~K: <Media omitted>\n',
     'Tayaba Malik Student: Even number w number  hty hn jin p 2 k table jata h\n',
     'Tayaba Malik Student: Ok\n',
     '~K: Bilkul\n',
     '~K: <Media omitted>\n',
     'Tayaba Malik Student: 2 k table s bi..\n',
     '~K: Ap tasali sy sochain na... Phir mjy btay\n',
     'Tayaba Malik Student: Ok\n',
     '~K: <Media omitted>\n',
     'Tayaba Malik Student: Divide  kar k... 2 s agar pura Divide h jya g remainder 0 h  t even  h ga...\n',
     'Tayaba Malik Student: Aur remainder koi number hua t odd h ga aur else m store h ga...\n',
     '~K: Kahan sy daikha hai? 😂\n',
     'Tayaba Malik Student: Khain s ni\n',
     '~K: Ok thk Hai... Condition laga k run krain\n',
     'Tayaba Malik Student: Teacher math m koi bara number  h us k divde karty\n',
     '~K: Code ki picture mjy bejhain agr run ni hota to\n',
     'Tayaba Malik Student: Aur even k liya hum 3 s karn g\n',
     'Tayaba Malik Student: Ok\n',
     'Tayaba Malik Student: Teacher  condition  kia bny gi\n',
     '~K: Apkiii... Bt smj ni ai mjy... Kyax keh rhe hain ap\n',
     '~K: Yahe to sochna hai na ap ny ab\n',
     'Tayaba Malik Student: Koi bara number h us p table la k jna h t divide yh multiply  karty\n',
     'Tayaba Malik Student: Ok\n',
     '~K: Yeh condition hoge\n',
     'Tayaba Malik Student: Ni\n',
     '~K: Laiken isko ap likhain ge kaisy... Yeh sochain ap Thora sa ab\n',
     'Tayaba Malik Student: Num / 2 h gi\n',
     '~K: <Media omitted>\n',
     '~K: <Media omitted>\n',
     'Tayaba Malik Student: Divide quotient  return  karta\n',
     'Tayaba Malik Student: Modules remainder return karta\n',
     '~K: Exactly\n',
     'Tayaba Malik Student: T modules  k operator h g\n',
     '~K: To ab itna smj aya apko to zra sochain... Kis trah honi chahiye condition\n',
     '~K: G\n',
     '~K: <Media omitted>\n',
     'Tayaba Malik Student: Num  modules  2\n',
     '~K: Bilkul\n',
     '~K: <Media omitted>\n',
     'Tayaba Malik Student: J user enter kary g us k modules karn g\n',
     'Tayaba Malik Student: Teacher agar w zero hua t store h jya g... ni t else m aha jya g\n',
     '~K: Agr wo zero hai... Is cheez ko condition main kaisy likhain ge?\n',
     '~K: ==\nYeh operator use hoga\n',
     '~K: <Media omitted>\n',
     'Tayaba Malik Student: T condition yh h gi\nNum modules  2 \nModules ==0\n',
     '~K: 2 ka bahd dobara modules q laga rhe hain?\n',
     'Tayaba Malik Student: Teacher w 2 l zero na l l iss liya\n',
     '~K: Ap laga k run krain\n',
     '~K: Or check krain zra isko\n',
     'Tayaba Malik Student: Ok\n',
     '~K: Should we start?\n',
     'Tayaba Malik Student: Yes\n',
     '~K: Should we start the class?\n',
     'Tayaba Malik Student: Yes\n',
     '~K: Smj ni aa rhe?\n',
     'Tayaba Malik Student: Ni\n',
     'Tayaba Malik Student: Bilkul  samj ni sha rahi\n',
     '~K: Apko msg b late receive hoa hai\n',
     'Tayaba Malik Student: G\n',
     '~K: Apky end per b hai issue\n',
     'Tayaba Malik Student: Gg\n',
     '~K: Write a program in which you will take a input from user and check whether it is alphabet or consonant, also restrict user from entering any other character than alphabet by showing a screen msg\n',
     '~K: Meri awaz bht late aa rhe hai apko\n',
     'Tayaba Malik Student: Teacher  ap ki awaz cut rshi\n',
     '~K: Likhain ap\n',
     'Tayaba Malik Student: Rahi**\n',
     '~K: The class will be started on 7 50\n',
     'Tayaba Malik Student: Okay\n',
     '~K: Should we start?\n',
     'Tayaba Malik Student: Yes teacher  ik minute  m laptop nikal lu\n',
     '~K: Ok nikal lain\n',
     'Tayaba Malik Student: Ok teacher lets start\n',
     '~K: Tayaba ap Kal full day ghar he hony Wali hain ?\n',
     '~K: It is ok if we shift our today class on Sunday?\n',
     'Tayaba Malik Student: G teacher\n',
     'Tayaba Malik Student: Yes sure\n',
     '~K: Ok phir main apki aj Wali class kal ly lon ge\n',
     '~K: Time main apko kal he bta don ge\n',
     'Tayaba Malik Student: Ok\n',
     '~K: We will start the class at 6\n',
     'Tayaba Malik Student: Ok\n',
     '~K: Should we start?\n',
     'Tayaba Malik Student: Yes\n',
     'Tayaba Malik Student: <Media omitted>\n',
     'Tayaba Malik Student: <Media omitted>\n',
     'Tayaba Malik Student: // Linked list operations in C++\n#include <iostream>\nusing namespace std;\n // Create a node struct Node \n struct Node {\n int data;\n struct Node* next;\n  };\n   void insertAtBeginning(struct Node** head_ref, int new_data) {\n    // Allocate memory to a node\n\t struct Node* new_node = (struct Node*)malloc(sizeof(struct Node) );\n\t // insert the data\n\t   new_node->data = new_data;\n\t    new_node->next = (head_ref);\n\t // Move head to new node\n\t  (*head_ref) = new_node;\n\t   }\n\t // Insert a node after a node\n\t  void insertAfter(struct Node * prev_node, int new_data) { \n\t  if (prev_node == NULL) {\n\t  cout << "the given previous node cannot be NULL";\n\t   return;\n\t    }\n\t\t struct Node* new_node = (struct Node*)malloc(sizeof(struct Node) );\n\t\t  new_node->data = new_data;\n\t\t  new_node->next = prev_node->next;\n\t\t prev_node->next = new_node;\n\t\t  }\n\t\t   // Insert at the end\n\t\t    void insertAtEnd(struct Node** head_ref, int new_data) { \n\t\t\tstruct Node* new_node = (struct Node*)malloc(sizeof(struct Node)); \n\t\t\tstruct Node* last = head_ref; / used in step 5*/\n\t\t\tnew_node->data = new_data;\n\t\t\tnew_node->next = NULL;\n\t\t\tif (head_ref == NULL) {\n\t\t\t*head_ref = new_node;\n\t\t\t return;\n\t\t\t  }\n\t\t\t   while (last->next != NULL) last = last->next;\n\t\t\t    last->next = new_node;\n\t\t\t\t return;\n\t\t\t\t  }\n\t\t\t\t   // Delete a node\n\t\t\t\t    void deleteNode(struct Node* head_ref, int key) { \n\t\t\t\t\tstruct Node *temp = *head_ref, *prev;\n\t\t\t\t\t if (temp != NULL && temp->data == key) {\n\t\t\t\t\t  *head_ref = temp->next;\n\t\t\t\t\t   free(temp);\n\t\t\t\t\t    return;\n\t\t\t\t\t\t }\n',
     '~K: Paint k ss ko word main paste kr lijiay ga\n',
     'Tayaba Malik Student: Teacher  w ma na save  kar liya\n',
     '~K: Thk hai\n',
     'Tayaba Malik Student: <Media omitted>\n',
     'Tayaba Malik Student: is  m add kar ln g suba\n',
     'Tayaba Malik Student: m na bht try kia abhi tak bna rahi hu\n',
     'Tayaba Malik Student: h gya t kar ln g ni t suba wasi bi hard form m dni h kar ln g\n',
     '~K: to abhi apki assignment ka koi solution nikla??\n',
     '~K: yeh apki kisi frnd ki hai?\n',
     'Tayaba Malik Student: Ni teacher...\n',
     'Tayaba Malik Student: Ni\n',
     'Tayaba Malik Student: Yh sir na manual  diya h...\n',
     'Tayaba Malik Student: K iss tarah insertion  deletion exta hti h\n',
     '~K: chalain main daikhti hn\n',
     '~K: btati hn apko phir\n',
     'Tayaba Malik Student: Ok teacher lkin abhi ap rest kar ln.. bad kar  ln g\n',
     '~K: apki is file main to sirf program ki statement hai\n',
     'Tayaba Malik Student: <Media omitted>\n',
     '~K: tayyabba !\n',
     'Tayaba Malik Student: G teacher\n',
     'Tayaba Malik Student: Congratulations\n',
     '~K: Ap b Mery khyal sy phone side per rakh k match daikh rhe the 😂\n',
     'Tayaba Malik Student: Ni\n',
     'Tayaba Malik Student: Teacher  match ni deakhti\n',
     '~K: Main ny to q k kaha k apka program krty hain match k sath\n',
     'Tayaba Malik Student: Ni teacher  chorn ab ... rest karn\n',
     'Tayaba Malik Student: Phir kabhi discuss  kar ln g\n',
     '~K: Apko msg Kia Tha usi k liay main ny\n',
     '~K: Han g ab to Sony ka he time hai\n',
     'Tayaba Malik Student: G... m na late dekha\n',
     'Tayaba Malik Student: G\n',
     'Tayaba Malik Student: Good night  have sweet  dreams\n',
     '~K: Ok g gud nite... Sweet dreams to u 2🌸\n',
     '~K: Tayabba today I will start your class after 8 currently not feeling well\n',
     'Tayaba Malik Student: Okay\n',
     '~K: Should we start?\n',
     'Tayaba Malik Student: G teacher  ok...\n',
     'Tayaba Malik Student: M laptop nikal lu...\n',
     'Tayaba Malik Student: Ik second\n',
     '~K: Ok\n',
     '~K: Do let me know\n',
     'Tayaba Malik Student: Ok\n',
     'Tayaba Malik Student: On h raha ...\n',
     '~K: Ho gya?\n',
     'Tayaba Malik Student: Teacher\n',
     'Tayaba Malik Student: Is k sath koi issue h...\n',
     'Tayaba Malik Student: On h gya h... lkin screen ni aha rahi\n',
     'Tayaba Malik Student: Yh likha aha raha h\n',
     '~K: Photo dikhay\n',
     'Tayaba Malik Student: <Media omitted>\n',
     '~K: Isko hony dain zra\n',
     'Tayaba Malik Student: Ok\n',
     '~K: Ho skta hai undoing kr k on kr dy yeh\n',
     'Tayaba Malik Student: Ok...\n',
     '~K: On hota hai to phir btay mjy\n',
     'Tayaba Malik Student: Ok\n',
     'Tayaba Malik Student: Teacher on h gya h...\n',
     '~K: Ok\n',
     'Tayaba Malik Student: <Media omitted>\n',
     'Tayaba Malik Student: <Media omitted>\n',
     '~K: Tayabba ap Kal uni sy kitny bjy wapis ayn ge?\n',
     'Tayaba Malik Student: G teacher\n',
     'Tayaba Malik Student: At 5\n',
     'Tayaba Malik Student: Might  be possible  kal jaldi aha jau... jab bi ahi msg kar k ap k inform  kar du gi\n',
     '~K: Chalain thk Hai... Filhal k liay hm abhi ki class start krain?\n',
     'Tayaba Malik Student: Teacher abhi...\n',
     'Tayaba Malik Student: Cancel  kar ln late h gya h\n',
     '~K: ok..then kal phir hm 2 classes kr lain gy\n',
     'Tayaba Malik Student: Ok\n',
     'Tayaba Malik Student: Thanku\n',
     '~K: 2 hrs...consecutive easy hoa ap k liay to consecutive classes kr lain gy...warna with some break between\n',
     'Tayaba Malik Student: Ok\n',
     '~K: or kal phir...jaldi b start krna hoga is bt ka b dhayan rakhiay ga\n',
     'Tayaba Malik Student: Teacher kal t sahi  University  wala sene  h g\n',
     'Tayaba Malik Student: Ok\n',
     '~K: hm 2 classes k beech main gap rakh lain gy...us main to issue ni hai\n',
     '~K: chalain ap mjy uni sy wapiis aty he msg kijiay ga lazmi\n',
     'Tayaba Malik Student: Ok teacher\n',
     'Tayaba Malik Student: No issue\n',
     'Tayaba Malik Student: Ok\n',
     '~K: ??\n',
     'Tayaba Malik Student: G teacher\n',
     '~K: Ap aa gai uni sy wapis?\n',
     'Tayaba Malik Student: Gg\n',
     'Tayaba Malik Student: 5 30\n',
     '~K: Mjy msg krna Tha na\n',
     'Tayaba Malik Student: Sorry mujy yaad ni raha btna\n',
     '~K: Start krain hm class phir?\n',
     'Tayaba Malik Student: G\n',
     '~K: Ok will text you in a while... Approx 15 min later\n',
     'Tayaba Malik Student: Ok\n',
     '~K: I postponed what I was about to do... Ap farig ho to hm abhi start kr lain?\n',
     'Tayaba Malik Student: G\n',
     'Tayaba Malik Student: M free hu\n',
     '~K: <Media omitted>\n',
     'Tayaba Malik Student: Ok teacher  thanku\n',
     '~K: Isko smjiay ga b lazmi\n',
     'Tayaba Malik Student: G\n',
     '~K: Should we start the class?\n',
     'Tayaba Malik Student: G teacher\n',
     'Tayaba Malik Student: Teacher at 8 plz... abhi ma presentation  d k class ki free hui\n',
     '~K: Phir 9 bjy end hoge class\n',
     '~K: Postponed kr daity hain phir aj ki class... Sunday ko ya on some other day ly lon ge main yeh Wali apki\n',
     'Tayaba Malik Student: Ok\n',
     'Tayaba Malik Student: Thanku\n',
     'Tayaba Malik Student: Sukar hai\n',
     'Tayaba Malik Student: Thanku so much  ✨✨✨\n',
     '~K: Cancle hony per? 😅\n',
     '~K: No problem... Rest krain\n',
     'Tayaba Malik Student: G teacher  aj ma n vaccine  lagwai hai 2nd t hath m bht dard hai  ... aur abhi presentation  di hai\n',
     'Tayaba Malik Student: Chat p ja k\n',
     '~K: O ho... Chalain koi ni rest krain phir ap aj\n',
     'Tayaba Malik Student: Ok thanku\n',
     'Tayaba Malik Student: ✨✨✨\n',
     "~K: Tyabba I won't be able take today's class, will let u know about this one too, when will I be able to take\n",
     'Tayaba Malik Student: Ok teacher\n',
     'Tayaba Malik Student: Today I am also  sleeping...\n',
     'Tayaba Malik Student: Ok no issue\n',
     '~K: Shabash\n',
     'Tayaba Malik Student: G teacher\n',
     '~K: Start krain aj ki class?\n',
     'Tayaba Malik Student: Gg teacher sorry\n',
     'Tayaba Malik Student: Aj m class ni la saki\n',
     '~K: Acha tayaba as I have already thought k min 2 classes ly lon ge main apki aj... So that jo week main miss hoi hmari uska cover ho jay... Iska mjy ap apna jaldi inform kr dain\n',
     'Tayaba Malik Student: Ok teacher...\n',
     '~K: Tayabba one of ur class will be on 11\n',
     'Tayaba Malik Student: Teacher\n',
     'Tayaba Malik Student: Aj cancelled kar dn...\n',
     'Tayaba Malik Student: Monday s regularly  karn g...\n',
     '~K: To aj phir ap ny classes ni laini? Jo miss hoi the last week\n',
     'Tayaba Malik Student: Ni teacher\n',
     'Tayaba Malik Student: Monday s ab...\n',
     '~K: To aj ap free ni the?\n',
     'Tayaba Malik Student: Teacher abhi itnay  kam hn quiz bi hn kal\n',
     'Tayaba Malik Student: Week end hai iss liya\n',
     '~K: Ok.. Chalain thk hai\n',
     'Tayaba Malik Student: Ok teacher  thanku\n',
     '~K: Han g... Aj kya mood hai tyabba? Start krain glass?\n',
     '~K: Class*\n',
     'Tayaba Malik Student: Gg teacher\n',
     '~K: Ok\n',
     'Tayaba Malik Student: Abhi??\n',
     '~K: G to phir kab?\n',
     'Tayaba Malik Student: M laptop  niklau\n',
     'Tayaba Malik Student: Ok ...\n',
     '~K: G g nikal lain aram sy\n',
     'Tayaba Malik Student: Ok\n',
     '~K: Should we start the class?\n',
     'Tayaba Malik Student: Gg teacher  ik second  m laptop  nikal lu\n',
     '~K: Ok\n',
     '~K: Done?\n',
     'Tayaba Malik Student: Yes\n',
     'Tayaba Malik Student: Bs on h raha hai\n',
     '~K: Ok let me know jb ho jay to\n',
     "Tayaba Malik Student: G it's done\n",
     '~K: Should we start?\n',
     'Tayaba Malik Student: G\n',
     'Tayaba Malik Student: Ik minute m laptop  nikal lu\n',
     '~K: G Nikal lain\n',
     'Tayaba Malik Student: Oky\n',
     'Tayaba Malik Student: M na nikal liya..\n',
     'Tayaba Malik Student: Abhi on h raha....\n',
     '~K: On ho jay to mjy btay\n',
     'Tayaba Malik Student: Ok\n',
     'Tayaba Malik Student: Teacher on h gya hai\n',
     'Tayaba Malik Student: Assalam-o-Alaikum  teacher aj off h na...\n',
     '~K: Mtlb.. Kahe Jana hai ap ny?\n',
     'Tayaba Malik Student: Ni ni teacher\n',
     'Tayaba Malik Student: M na sona tha...\n',
     'Tayaba Malik Student: Aur m so gi abhi ap k msg dekha\n',
     '~K: Chalain aj 2 classes lain gy phir hm\n',
     'Tayaba Malik Student: Gg\n',
     'Tayaba Malik Student: Ok\n',
     '~K: Tyabba I will start your class around 8\n',
     'Tayaba Malik Student: Okay\n',
     '~K: Should we start?\n',
     'Tayaba Malik Student: Gg\n',
     'Tayaba Malik Student: Lap top on hai aur any desk bi\n',
     '~K: Should we start the class?\n',
     'Tayaba Malik Student: Gg\n',
     'Tayaba Malik Student: M laptop nikal lu  ik minute  teacher\n',
     '~K: 10 min tk main krti hn apko call\n',
     'Tayaba Malik Student: Oky\n',
     '~K: Tyabba apki aj ki class ni Hoge\n',
     'Tayaba Malik Student: Ok  teacher\n',
     'Tayaba Malik Student: Thanku\n',
     '~K: Should we start the class?\n',
     'Tayaba Malik Student: Sorry teacher  m na msg ni dekha ...\n',
     '~K: Ok\n',
     '~K: Laini Hai abhi ap ny class phir?\n',
     'Tayaba Malik Student: Teacher jsy ap khyn\n',
     'Tayaba Malik Student: Teacher wasi bi monday s paper hn...\n',
     '~K: Phir to definitely apki Class lon ge main\n',
     '~K: Main krti hn call apko 5 10 min tk\n',
     'Tayaba Malik Student: Q teacher\n',
     '~K: Q Kya... Class ni laini? 😂\n',
     'Tayaba Malik Student: Ni\n',
     'Tayaba Malik Student: M kha rahi l ab 20 s start karn g...\n',
     '~K: 10 din bahd?\n',
     'Tayaba Malik Student: G\n',
     '~K: Aj ap ny class ni laini phir?\n',
     'Tayaba Malik Student: Ni aj ni\n',
     '~K: To abhi ap paper ki tyari kr rhe hain?\n',
     'Tayaba Malik Student: Ni\n',
     'Tayaba Malik Student: Abhi t m University  s ahi\n',
     'Tayaba Malik Student: Aj late h gya thy\n',
     '~K: Ni abhi phir mjy clear kr dain... We will start onward from 20th November... Right?\n',
     'Tayaba Malik Student: Gg\n',
     '~K: Ok\n',
     'Tayaba Malik Student: Thanku teacher\n',
     '~K: Your welcome\n',
     'Tayaba Malik Student: Assalam-o-Alaikum  teacher... mery paper finish  h gya hn....ab hum regularly  Monday s start kar ln classes\n',
     '~K: G thk Hai\n',
     '~K: Tyabba we will start the class on 7 30\n',
     'Tayaba Malik Student: Okay\n',
     '~K: Should we start?\n',
     'Tayaba Malik Student: Gg\n',
     '~K: Tyabba itni jaldi? 😅\n',
     '~K: Reply kia ap ny\n',
     'Tayaba Malik Student: Teacher  m so gai thu\n',
     'Tayaba Malik Student: Thi\n',
     'Tayaba Malik Student: Chln kal s start  karty\n',
     'Tayaba Malik Student: Kal m ghar hu gi...\n',
     '~K: Ab chuti Maryn aj... Aj Wali class isi week main kisi din adjust kro ge main\n',
     'Tayaba Malik Student: Oky\n',
     '~K: Morning main ghar hon ge ap?\n',
     'Tayaba Malik Student: Gg\n',
     '~K: Thk Hai... Bs phir kal 2 classes lon ge main apki\n',
     'Tayaba Malik Student: Oky\n',
     'Tayaba Malik Student: Fine\n',
     'Tayaba Malik Student: Jazak Allah teacher\n',
     '~K: WA iyyaki🌸\n',
     '~K: Tyabba hm ny last time kya kia tha?\n',
     'Tayaba Malik Student: Functions kar rahy thy\n',
     '~K: Program kon sa kia tha last time?\n',
     'Tayaba Malik Student: Teacher  yh ni yad\n',
     '~K: Ap jag gai hain?\n',
     'Tayaba Malik Student: Gg bs nashta kar rahi\n',
     '~K: Agr uth gai hain to mjy kindly daikh kr btay... Last program kon sa kia tha hm ny\n',
     '~K: Chalo nashta kr k mjy btana daikh k\n',
     'Tayaba Malik Student: Ok teacher\n',
     'Tayaba Malik Student: Ok\n',
     '~K: ??\n',
     'Tayaba Malik Student: Teacher  mera laptop  off hai on ni h raha\n',
     'Tayaba Malik Student: Light  ni hai  shayd iss wajha s...\n',
     'Tayaba Malik Student: M na ups s lagya hua hai\n',
     '~K: To abhi phir?\n',
     '~K: Charge ni ho rha us per wo?\n',
     'Tayaba Malik Student: Ni\n',
     'Tayaba Malik Student: CHARGING  light hi ni oh h rahi\n',
     '~K: Ok... Phir ab mjy eve main btaiay ga ap... K eve main class Laina apky liay possible hoga ya ni\n',
     '~K: Eve main aik he class possible hoge\n',
     'Tayaba Malik Student: Ok\n',
     'Tayaba Malik Student: Teacher  yh on na hua t phir\n',
     '~K: And isko kisi doc ko check kra do ap🤦\u200d♀️\n',
     '~K: Apny laptop ko\n',
     'Tayaba Malik Student: Hahah  oky\n',
     '~K: Phir ap mjy inform kr dijiay ga\n',
     'Tayaba Malik Student: Ok\n',
     '~K: Laiken msg kr daina sae yad sy khud\n',
     'Tayaba Malik Student: Ok\n',
     'Tayaba Malik Student: Teacher\n',
     'Tayaba Malik Student: Assalam-o-Alaikum  teacher  I can able to take class...\n',
     '~K: Ok... Class will be started at 7\n',
     'Tayaba Malik Student: Oky\n',
     '~K: Ap laptop on kr k mjy last program bta dain tb tk\n',
     'Tayaba Malik Student: Oky teacher\n',
     '~K: Should we start?\n',
     'Tayaba Malik Student: Yes\n',
     '~K: Mjy yad sy course content pf ka send krna Hai ap ny\n',
     'Tayaba Malik Student: Ok teacher\n',
     '~K: Class will be started at 7 30\n',
     'Tayaba Malik Student: Oky\n',
     '~K: Should we start?\n',
     'Tayaba Malik Student: Gg teacher  ... m khna khny chli gai thi sorry\n',
     '~K: Start krain phir ab?\n',
     'Tayaba Malik Student: Gg\n',
     'Tayaba Malik Student: Lkin laptop  kha rha hai just a minute\n',
     '~K: Laptop on krain or anydesk on kr k mjy btay\n',
     'Tayaba Malik Student: Oky\n',
     "Tayaba Malik Student: Teacher it's  on\n",
     '~K: Ok will call you in 5 min\n',
     'Tayaba Malik Student: Okay\n',
     'Tayaba Malik Student: <Media omitted>\n',
     'Tayaba Malik Student: <Media omitted>\n',
     'Tayaba Malik Student: Dsa\n',
     '~K: Thk ho gai bt\n',
     'Tayaba Malik Student: Suba inshallah  pf ki bj du gi\n',
     '~K: G thk hai\n',
     '~K: Should we start the class?\n',
     'Tayaba Malik Student: Teacher aj cancelle kar dn agar...\n',
     'Tayaba Malik Student: Kal aur Saturday  k l ln\n',
     '~K: Q? Cancle q krni Hai?\n',
     'Tayaba Malik Student: Asi  teacher  ... koi reson  ni hai\n',
     '~K: Shabash🙄\n',
     'Tayaba Malik Student: M n Saturday  k academy  ana t ... Saturday  k rakh ln\n',
     'Tayaba Malik Student: Wasi  bi teacher  hmari  week m 2 din off hn g\n',
     '~K: Wo to thk hai... Per sat ko b class to online he hoge\n',
     'Tayaba Malik Student: Oky\n',
     'Tayaba Malik Student: Online  hi l ln\n',
     'Tayaba Malik Student: Saturday  k l ln\n',
     'Tayaba Malik Student: Aj off kar dn\n',
     '~K: Ok then cancle ni Hoge... We will move it to some other day\n',
     'Tayaba Malik Student: Oky\n',
     'Tayaba Malik Student: Teacher  kal agar ap free hn t ksi bi time class l ln... m ghar hu gi\n',
     '~K: Chalo lets see... Agr mera liay morning main possible hoa to main btao ge apko phir\n',
     'Tayaba Malik Student: Oky\n',
     'Tayaba Malik Student: Assalam-o-Alaikum  teacher  I am not able to take class today...\n',
     '~K: You are not at home?\n',
     'Tayaba Malik Student: Gg teacher  m ghar ni hu\n',
     'Tayaba Malik Student: Mera dada abu k operation  tha t un k deakhny ahyn hn\n',
     '~K: Ok\n',
     '~K: Tyabba aj ap academy gai the?\n',
     'Tayaba Malik Student: Ni teacher\n',
     'Tayaba Malik Student: Aj  m ni aha saki\n',
     '~K: O ho... Main ny to sir ko bola tha aj tyabba ay ge sir unka istakbal kijiay ga 😅\n',
     '~K: Acha mjy aj ki class ka b btay\n',
     'Tayaba Malik Student: Haha\n',
     'Tayaba Malik Student: Sorry teacher  m ni aha sakhi\n',
     'Tayaba Malik Student: Gg teacher  \nAp btyn\n',
     '~K: Ghar hain na ap?\n',
     'Tayaba Malik Student: Gg\n',
     'Tayaba Malik Student: Ghar hu\n',
     '~K: Mtlb available hain?\n',
     'Tayaba Malik Student: Gg\n',
     '~K: Bs thk hai... Phir Shuro krty hain. Main laptop on kr k call krti hn apko\n',
     'Tayaba Malik Student: Ok\n',
     'Tayaba Malik Student: M b laptop on karti\n',
     '~K: Ok kr lai ap b\n',
     '~K: On*\n',
     '~K: ?\n',
     'Tayaba Malik Student: <Media omitted>\n',
     'Tayaba Malik Student: <Media omitted>\n',
     'Tayaba Malik Student: <Media omitted>\n',
     'Tayaba Malik Student: Teacher project  aha gya\n',
     'Tayaba Malik Student: Airport management system topic hai\n',
     '~K: Due kab hai?\n',
     'Tayaba Malik Student: <Media omitted>\n',
     '~K: Mtlb we have a month to complete?\n',
     'Tayaba Malik Student: Yes\n',
     '~K: Chalo phir to thk ho gya... Zyada time mill jay ga to main apko zyada achy sy smjha don ge\n',
     '~K: Or bnana c++ main he hai na?\n',
     'Tayaba Malik Student: G teacher  baki suba sir guide karn  g k kia karna hai ksy karna hai\n',
     'Tayaba Malik Student: Gg c++\n',
     '~K: Wo info phir ap achy sy sari likh laina\n',
     'Tayaba Malik Student: Oky\n',
     '~K: Ta k jo jo apky sir chah rhy hain k project main ho hm sy miss na ho kuch b\n',
     'Tayaba Malik Student: G theek hai\n',
     '~K: <Media omitted>\n',
     'Tayaba Malik Student: Oky  teacher\n',
     '~K: Should we start the class?\n',
     'Tayaba Malik Student: Yes  teacher  in 5 minutes\n',
     'Tayaba Malik Student: M laptop nikal lu\n',
     '~K: Ok\n',
     '~K: Btay mjy on kr k\n',
     "Tayaba Malik Student: Teacher  it's done\n",
     'Tayaba Malik Student: Teacher\n',
     '~K: Ap ny end ki hai call?\n',
     'Tayaba Malik Student: Ni\n',
     '~K: Pick ni ki ap ny call\n',
     '~K: Start krain class?\n',
     'Tayaba Malik Student: Gg teacher\n',
     'Tayaba Malik Student: M laptop nikal lu\n',
     '~K: Ok nikal k btay\n',
     '~K: Ho gya?\n',
     'Tayaba Malik Student: Ni teacher\n',
     'Tayaba Malik Student: Update h raha\n',
     '~K: Chalo g🤦\u200d♀️\n',
     'Tayaba Malik Student: H gya hai\n',
     '~K: Ho gya on?\n',
     'Tayaba Malik Student: Gg\n',
     '~K: Ok\n',
     'Tayaba Malik Student: <Media omitted>\n',
     'Tayaba Malik Student: Missed voice call\n',
     '~K: Yeh Jo tyabba ap ny mjy send kia tha... Yeh report hai?\n',
     'Tayaba Malik Student: Teacher yh zip file hai iss m oops k project hai us k code  report and presentation\n',
     '~K: G thk Hai wo unzip kr k main ny daikh Lia hai\n',
     '~K: Acha jo main ny puchny k liay kaha tha apko... Wo puch lia sir sy ap ny abhi ya ni?\n',
     'Tayaba Malik Student: Teacher  abhi lab l rahy free h k puchti\n',
     '~K: Puch k mjy idhar he phir bta dijiay ga\n',
     'Tayaba Malik Student: Oky\n',
     '~K: Should we start the class?\n',
     'Tayaba Malik Student: Assalam-o-Alaikum teacher  aj class thora late kar ln... m apny baba g s milny ahi hu\n',
     '~K: Kitna late?\n',
     '~K: W. Aslam\n',
     'Tayaba Malik Student: Teacher   can  we take class now\n',
     '~K: Ni tyabba abhi to ni possible\n',
     'Tayaba Malik Student: Oky teacher\n',
     '~K: Should we start?\n',
     'Tayaba Malik Student: Yes teacher\n',
     'Tayaba Malik Student: In 5 minutes  m laptop nikal lu\n',
     '~K: Ok\n',
     'Tayaba Malik Student: Yes teacher  now we can\n',
     '~K: Should we start the class?\n',
     'Tayaba Malik Student: G in  5 minutes  m laptop on kR lu\n',
     '~K: Ok\n',
     '~K: Done?\n',
     'Tayaba Malik Student: Yes teacher we can\n',
     '~K: Should we start the class?\n',
     'Tayaba Malik Student: Yes teacher  in 5 minutes... laptop on kar lu\n',
     '~K: Ok\n',
     'Tayaba Malik Student: Yes teacher\n',
     "Tayaba Malik Student: Assalam-o-Alaikum teacher I can't able to take class ...\n",
     '~K: W. Aslam\n',
     '~K: Ok\n',
     '~K: Tayabba aj ap ny uni sy kitny bjy wapis aa Jana hai?\n',
     'Tayaba Malik Student: AJ  3 30 Free hu gi aur atty  atty  late h jau gi\n',
     '~K: Ap to jaldi any ka ni bta rhe the aj ka?\n',
     'Tayaba Malik Student: Make up classes  hn\n',
     'Tayaba Malik Student: Teacher arranged classes hn\n',
     '~K: Main ny socha tha aj ap aa jati academy... Per chaly ab isi week Saturday ka kr lain gy\n',
     'Tayaba Malik Student: Ok\n',
     'Tayaba Malik Student: Teacher  aj yh join  karu\n',
     '~K: Tyabba join kia ap ny?\n',
     'Tayaba Malik Student: Kia teacher\n',
     '~K: Apko text kia hai main ny sim per\n',
     'Tayaba Malik Student: Teacher  yh msg abhi  ma na parha\n',
     'Tayaba Malik Student: Teacher aj chorn class  k wasi bi bht late h gi\n',
     '~K: Kya Late? 🙄\n',
     '~K: Larki 6 min late hoay hain sirf... Wo b apko msg main ny pehly ka kia hoa tha\n',
     'Tayaba Malik Student: Gg ... teacher\n',
     'Tayaba Malik Student: M na abhi parha... iss liya... chorn ab start  karn g t end kab h gi...\n',
     'Tayaba Malik Student: Kal l ln\n',
     '~K: Kya he Kahy banda ab apko\n',
     'Tayaba Malik Student: Haha\n',
     'Tayaba Malik Student: Teacher ap khyn kitni  achi student  hai\n',
     '~K: G g aisi waisi.... Bs Mery sy puchy koi apki achai ka\n',
     'Tayaba Malik Student: Haha\n',
     'Tayaba Malik Student: Teacher  🥺\n',
     '~K: Chalain g... Aish krain. Kya yad kryn ge kis sakhi teacher sy pala para tha 😂\n',
     '~K: Chuti marain phir\n',
     'Tayaba Malik Student: Okok\n',
     'Tayaba Malik Student: U r the best\n',
     '~K: Han masky marwa lo bs\n',
     '~K: Acha meri bt suno... Sat ki ghar main bt kr li hai na ap ny?\n',
     'Tayaba Malik Student: No maska\n',
     'Tayaba Malik Student: Btya hai.... k ma na jna hai\n',
     'Tayaba Malik Student: Kal puchu gi... ksy jau gi\n',
     '~K: Q k sat ko lazmi ana hai... Or samjhana hai main ny apko plus working b dikhani hai\n',
     '~K: G lazmiiii\n',
     'Tayaba Malik Student: Okok\n',
     'Tayaba Malik Student: INSHALLAH\n',
     '~K: Should we start?\n',
     'Tayaba Malik Student: Yes in 5 minutes\n',
     'Tayaba Malik Student: Laptop on kar lu\n',
     '~K: G g kr lain\n',
     '~K: On kr k btay\n',
     'Tayaba Malik Student: H gya\n',
     '~K: Meri awaz aa rhe hai apko?\n',
     '~K: Yeh btay\n',
     'Tayaba Malik Student: G ap ki aha rahi meri aha rahi hai\n',
     'Tayaba Malik Student: Kab s hello hello kha rahi\n',
     '~K: Ni apki awaz ni aa rhe mjy\n',
     'Tayaba Malik Student: Oky\n',
     'Tayaba Malik Student: Sab normal hai\n',
     'Tayaba Malik Student: Setting  ok\n',
     'Tayaba Malik Student: Full  hai\n',
     'Tayaba Malik Student: Ok\n',
     '~K: Kia hai join?\n',
     'Tayaba Malik Student: G\n',
     '~K: Koi or wo ni join kr lia\n',
     '~K: Q us Waly meet k link main to ni ai abhi ap\n',
     'Tayaba Malik Student: W hi kia hai\n',
     'Tayaba Malik Student: Ap mujy in karn\n',
     '~K: Join krain dobara\n',
     'Tayaba Malik Student: Teacher  Internet  connection  lost\n',
     '~K: Apka net b sae time per khrab hoa hai\n',
     'Tayaba Malik Student: Gg teacher  pta  ni kia  hua hai\n',
     '~K: Us program ko daikha hai phir? K band kr dia\n',
     'Tayaba Malik Student: Deakha hai\n',
     'Tayaba Malik Student: Samj t aha gi hai ...\n',
     '~K: Sara smj aa gya?\n',
     'Tayaba Malik Student: Lakin ap  questions  kartik  t shad  zyda evaluation  hti\n',
     'Tayaba Malik Student: G lag t asa hi raha hai\n',
     '~K: Abhi ap chahy to hm class ly laity hain\n',
     '~K: Us program ko zabani likhain\n',
     'Tayaba Malik Student: Ni ab ni lani... kal academy  m theek hai\n',
     'Tayaba Malik Student: Lakin kasy\n',
     'Tayaba Malik Student: Yhn\n',
     '~K: Zubani likhain us program ko phir khud abhi ap\n',
     'Tayaba Malik Student: Ok\n',
     '~K: Tyabba I will reach academy by around 2 15... Ap b usi hisab sy ghar sy nikaliay ga\n',
     'Tayaba Malik Student: Ok teacher  I am also around  2 20\n',
     '~K: Tyabba ap apna laptop dy ai hain?\n',
     'Tayaba Malik Student: G teacher  dy ahi\n',
     '~K: Kya keh rhy hain kab tk mill jay ga?\n',
     'Tayaba Malik Student: Yh ni pta... shad w yh wapsi kara k koi aur  lyn....\n',
     'Tayaba Malik Student: Iss ki battery  bi kharab hai\n',
     'Tayaba Malik Student: 10000 hard  disk k lagy g\n',
     'Tayaba Malik Student: Aur  5 6 battery  j\n',
     'Tayaba Malik Student: K\n',
     'Tayaba Malik Student: T w kha rahy thy  k asa karty yh l k jty hn aur l aty hn isss ... itny pasy  dal k\n',
     'Tayaba Malik Student: Naya\n',
     '~K: 10k q? Ap ny kitny size ki dalny k liay kaha hai?\n',
     'Tayaba Malik Student: 500\n',
     'Tayaba Malik Student: Yh 400 j dal dn\n',
     '~K: To ab phir new apka kab tk aa jay ga?\n',
     'Tayaba Malik Student: Yh ni pta\n',
     'Tayaba Malik Student: Kha hai jaldi  la dn\n',
     'Tayaba Malik Student: 2 din m\n',
     '~K: Pindi sy lo ge?\n',
     'Tayaba Malik Student: Gg\n',
     '~K: Mushkil hai phir to... K 2 din tk aa jay\n',
     '~K: Chalo per jb aya to phir btana mjy... Hm phir start krain gy dobara classes\n',
     'Tayaba Malik Student: gari hamri jya gi... deakhn  ab\n',
     'Tayaba Malik Student: Oky\n',
     '~K: Acha or mjy yeh btay... Apko jo working main ny project ki dikhai the... Wo yad Hai apko... K Kya kya tha?\n',
     'Tayaba Malik Student: Gg\n',
     'Tayaba Malik Student: Admin aur user  k functions perform  kiya thy\n',
     '~K: Admin ki side per kya kya tha... Or user ki side per kya kya wo yad Hai apko?\n',
     'Tayaba Malik Student: G\n',
     '~K: <Media omitted>\n',
     'Tayaba Malik Student: Oky\n',
     '~K: <Media omitted>\n',
     '~K: <Media omitted>\n',
     '~K: <Media omitted>\n',
     '~K: <Media omitted>\n',
     'Tayaba Malik Student: Waslam  ok teacher  mujy  samj aha gi...\n',
     '~K: By Monday... Mjy yeh sari cheezain btani hai ap ny... Apny sir sy puch k\n',
     'Tayaba Malik Student: Oky\n',
     '~K: Tyabba apka laptop aa gya?\n',
     'Tayaba Malik Student: Ni\n',
     '~K: Pta kia ap ny? K kab tk ay ga\n',
     'Tayaba Malik Student: Teacher pta ni kab aya h\n',
     'Tayaba Malik Student: G*\n',
     'Tayaba Malik Student: M kal kuch karti .... aj m khud late h gi... bht\n',
     '~K: G koshish krain jaldi laptop ay apka... Q k tb he continue kr skty hain hm u know\n',
     '~K: Or mjy yeh btay ap ny apny sir sy pta kia tha?\n',
     'Tayaba Malik Student: G\n',
     'Tayaba Malik Student: Teacher  un n kha k ik data structure  use kar sakty aut us k sary function jsy link list ki insertion  deletions  transversiom\n',
     'Tayaba Malik Student: Aur array use karny hn must\n',
     '~K: Ap ny apny project ka Sara kuch jaisy main ny apko audio main btaya tha... Waisy btaya tha unhain?\n',
     'Tayaba Malik Student: G wasa hi btya\n',
     '~K: Yeh pucha k insertion deletion sir jo ap ny kray hain wo hm apny project main kahan use krain?\n',
     '~K: Ap free hain to mjy btay main call krti hn apko\n',
     'Tayaba Malik Student: Ok\n',
     'Tayaba Malik Student: Yes teacher  u can call\n',
     'Tayaba Malik Student: I am free\n',
     '~K: Or dosra task... Mjy singly link list sy related Sara kuch send krain... Jo b apko sir ny kraya hai\n',
     'Tayaba Malik Student: Ok\n',
     'Tayaba Malik Student: <Media omitted>\n',
     'Tayaba Malik Student: <Media omitted>\n',
     'Tayaba Malik Student: <Media omitted>\n',
     'Tayaba Malik Student: <Media omitted>\n',
     'Tayaba Malik Student: <Media omitted>\n',
     'Tayaba Malik Student: Kal hard disk change kary g\n',
     'Tayaba Malik Student: Nya ni lty\n',
     '~K: Battery or hard disk ka kam kr k kal tk dy dy ga laptop wo?\n',
     'Tayaba Malik Student: Gg\n',
     '~K: Chalo acha ho gya 👍\n',
     'Tayaba Malik Student: Yes\n',
     'Tayaba Malik Student: Inshallah  bhta Acha karn g\n',
     '~K: <Media omitted>\n',
     'Tayaba Malik Student: Dta k kha diya\n',
     '~K: Mehnat ki hm ny to result Acha he hoga in shaa Allah\n',
     'Tayaba Malik Student: Inshallah\n',
     '~K: Data transfer kr k ka tk dy ga?\n',
     'Tayaba Malik Student: G\n',
     '~K: Kal*\n',
     '~K: Bs sae ho gya phir\n',
     'Tayaba Malik Student: Kal kary g sahi\n',
     'Tayaba Malik Student: 2 din m d g\n',
     '~K: Ni ... 2 din mtlb... Thursday ko?\n',
     'Tayaba Malik Student: G\n',
     'Tayaba Malik Student: Kal s sahi kary g\n',
     '~K: Acha Acha.. Mjy laga kal... Return kr dy ga sae kr k\n',
     '~K: Per chalain thk Hai aisy b\n',
     'Tayaba Malik Student: Ok\n',
     '~K: Tyabba jb apka laptop thk ho k aa gya to mjy btaiay ga.. Agr aj aa gya to b inform kr daina mjy\n',
     'Tayaba Malik Student: Oky\n',
     '~K: Apka laptop ni ya tyyaba abhi tk?\n',
     '~K: Aya*\n',
     'Tayaba Malik Student: Ni teacher  ni aya\n',
     'Tayaba Malik Student: Kal j k pta  karu gi\n',
     '~K: 17 ho gai hai aj\n',
     'Tayaba Malik Student: G teacher\n',
     '~K: Or link list ko add kr k main bta rhe hn apka program Acha khasa mushkil ho gya Hai already\n',
     'Tayaba Malik Student: M n ghalti ki hai d k m na presentation  bni thi\n',
     'Tayaba Malik Student: Itni muskil  hui mujy\n',
     'Tayaba Malik Student: Project  h gya hai\n',
     '~K: Jo b hai us bandy sy pta krain.. Bal k abhi pta krwao phone kr k kisi sy\n',
     'Tayaba Malik Student: W Monday  k check karna hai  l k ja k\n',
     '~K: Ni abhi uski implementation complete ni hoi...chal rha hai abhi\n',
     'Tayaba Malik Student: Phone  karwa tha kha raha tha ni hua abhi\n',
     'Tayaba Malik Student: Ab suba j k pta karu gi\n',
     '~K: Usko bolo jaldi kry\n',
     'Tayaba Malik Student: Ok\n',
     'Tayaba Malik Student: G\n',
     '~K: Acha aik or cheez b yad ai mjy puchni\n',
     'Tayaba Malik Student: Wasi Monday  k project  l k jna hai  jitna hua hai sir na kha k office  m aha k check  karya har group\n',
     'Tayaba Malik Student: Kal m academy  ahu gi passy dny project  k sir k\n',
     'Tayaba Malik Student: T ap s milu gi\n',
     'Tayaba Malik Student: Gg\n',
     '~K: Kal ap kis time ay ge?\n',
     'Tayaba Malik Student: 4 tak\n',
     '~K: Ap ny December ki sir ko fees di the? Sir mj sy puch rhy thy to main ny kaha to ni pta k di Hai ya ni\n',
     'Tayaba Malik Student: Ni\n',
     '~K: Or sir ko b bhoola hoa Tha... K ap ny di Hai ya ni\n',
     'Tayaba Malik Student: W bi ni  di\n',
     '~K: Shabash\n',
     'Tayaba Malik Student: Last time lahi thi sir thy hi ni\n',
     '~K: Chalo phir yeh b dy daina kal yad sy\n',
     'Tayaba Malik Student: Gg\n',
     '~K: Q k abhi unko aisa lag rha Hai... K ap ny dy di Hai or unko yad ni\n',
     'Tayaba Malik Student: Jal yh project  fee aur  laptop  k kam  clear karti\n',
     '~K: Or kal... Laptop hona chahiye Tayyaba apky pas.. Lazmi\n',
     'Tayaba Malik Student: Ni m na ni di\n',
     'Tayaba Malik Student: Ok\n',
     '~K: Mazeed late na ho... Warna end time main wakhta parh skta hai hmain\n',
     '~K: Chalo kal Laina sir sy Sara hisab clear\n',
     '~K: Or call kr Laina... Any sy pehly sir ko\n',
     'Tayaba Malik Student: G\n',
     'Tayaba Malik Student: Oky\n',
     '~K: Assalam u alaikum!! \nTyabba apky sir ny apko is sy related kya bola tha... K jo b data structure use krain gy usky sary functions use krny hain??\n',
     '~K: Aisa kuch bola tha unho ny?\n',
     'Tayaba Malik Student: Waslam\n',
     'Tayaba Malik Student: Gg asa hi kha tha\n',
     '~K: Apki link list ny Bara khapaya hoa hai waisy\n',
     'Tayaba Malik Student: Haha\n',
     'Tayaba Malik Student: Yh hai hi asi\n',
     '~K: <Media omitted>\n',
     'Tayaba Malik Student: Teacher  Monday  k ati phir discuss  karty isss k\n',
     '~K: Tayyaba ly ai ap laptop?\n',
     '~K: ??\nBtayn ta k main phir apko btaon aj ka\n',
     'Tayaba Malik Student: Sorry  teacher\n',
     'Tayaba Malik Student: Ni aya\n',
     '~K: To phir ab?\n',
     'Tayaba Malik Student: W kha rahy  k ik din bs ...\n',
     '~K: To abhi main project apko send kr Don... To apko agr samjhaya ni main ny thora bht... To apky sir ko sedha shak hoga\n',
     '~K: K ap ny ni bnaya. Or laptop k bagair abhi kaisy smjao ge main apko\n',
     'Tayaba Malik Student: Teacher ap mujy sirf w admin wala bj dn ... aur kuch thora s voice  m bta dn...\n',
     '~K: Ok... Or mjy btay... K abhi apko link list ki implementation k sath wala chahiay ya pehly wala?\n',
     'Tayaba Malik Student: Ni link list wala ni bjhn  abhi  us k mujy kuch pta  ni hai...\n',
     'Tayaba Malik Student: Bs admin user wala bj dn... us  k m kuch  kar lu gi\n',
     '~K: Ok\n',
     '~K: Or... Iski payment ka mamla apka sir k sath ho gya Hai na? Bcz mjy ni pta main apko source file send kron ge abhi q k sir sy puchy bagair... To phir issue na bany\n',
     'Tayaba Malik Student: Us ki output  wasi  hai... jsi  ap na mujy dekahi  thi....\n',
     '~K: Or dosra yeh apky uni k sir... Isky number to ni lgay gy na? Abhi jo ap log check kray gy... Iski marking i mean hoge?\n',
     '~K: G\n',
     'Tayaba Malik Student: Ni m na sir k kha hai aj k project  bny g t madam  s m samjny  k liya ahu gi ... t payment  kar du gi us  ki...\n',
     'Tayaba Malik Student: Ni marking  ni hai  w bs deakhn  g k kam h raha k no kitna  hua... just this...\n',
     '~K: Phir abhi source file... Soch main dal dia hai ap ny mjy... K ab send kron main ya sir sy puch k send kron\n',
     'Tayaba Malik Student: Aur yh bi iss liya kha k aj hamra  off  aha gya ...\n',
     'Tayaba Malik Student: Ap sir s puch ln...  wsi khud b\n',
     '~K: Msg main ny Kia hoa hai... Per online ni hain abhi\n',
     'Tayaba Malik Student: Ok ap un s puch ln...\n',
     '~K: Wo late jwb dain gy shayd... Phir us time late ho jay ga... Main apko send kr daiti hn phir abhi\n',
     'Tayaba Malik Student: Ok...\n',
     '~K: Bahd main phir unko yeh inform kr don ge main\n',
     'Tayaba Malik Student: M phir  kal yh Wednesday  k sir k project  ki payment  b bjwa du gi\n',
     '~K: Or aik or cheez jo mjy puchni the... Ap Kal sir ko... Code dikhay ge ya sirf output?\n',
     'Tayaba Malik Student: Sirf output\n',
     'Tayaba Malik Student: Output  check  karsni bs\n',
     'Tayaba Malik Student: Karani *\n',
     '~K: Or agr apky sir ny... Code sy pucha kuch to phir?\n',
     '~K: Ap apni email id send krain mjy\n',
     'Tayaba Malik Student: W phir  classes  aur file wla j karwa  tha ap na us k m kar lu gi\n',
     'Tayaba Malik Student: Oky\n',
     'Tayaba Malik Student: 20-SE-061@student.hitecuni.edu.pk\n',
     'Tayaba Malik Student: Tayyabamalik70000@gmail.com\n',
     '~K: Ok\n',
     '~K: <Media omitted>\n',
     'Tayaba Malik Student: Teacher  yh open  kis m h g\n',
     '~K: Unzip krain ge isko\n',
     'Tayaba Malik Student: G phir\n',
     "Tayaba Malik Student: Teacher  w admin  I'd  aur password\n",
     '~K: Admin email : admin1234@pakAviation.com\nAdmin pass: 1234\n',
     '~K: Iski output ap... Kisi frnd k laptop main dikhay ge phir?\n',
     'Tayaba Malik Student: Teacher kai dusry  group  walon  k ni deakhna  hta...\n',
     'Tayaba Malik Student: Ni t sir phir  consider  ni karty project\n',
     '~K: Ap aik krain... Call per ayn zra... Iska main Thora bht btati hn apko\n',
     'Tayaba Malik Student: Gg\n',
     '~K: <Media omitted>\n',
     'Tayaba Malik Student: Teacher  download  h rahi\n',
     '~K: <Media omitted>\n',
     '~K: <Media omitted>\n',
     '~K: Ok\n',
     'Tayaba Malik Student: Teacher  yh m n deakh  liya  yh samj aha gi\n',
     'Tayaba Malik Student: Teacher  tysm\n',
     '~K: Baki b aa rhe hain\n',
     '~K: Wo b daikh k btay phir\n',
     'Tayaba Malik Student: Gg\n',
     '~K: Am just trying in every possible way k apka achy sy ho jay bs\n',
     'Tayaba Malik Student: Allah  kary bs yh h jya\n',
     '~K: Pehli video sy onward admin side is main hai\n',
     'Tayaba Malik Student: Ok yh open h rahi\n',
     '~K: Apki frnd sy hoa rabta apka?\n',
     'Tayaba Malik Student: G techer  msg kia hua\n',
     'Tayaba Malik Student: Abhi call kar rahi\n',
     'Tayaba Malik Student: Ni utha rahi\n',
     '~K: Apki saheli b ap sy do hath agy hai\n',
     '~K: Yeh user side\n',
     'Tayaba Malik Student: Teacher  ni utha rahi abhi b kar rahi\n',
     'Tayaba Malik Student: Yh b ok hai\n',
     '~K: <Media omitted>\n',
     '~K: Aa gai smj?\n',
     'Tayaba Malik Student: G aha gi\n',
     '~K: Ok chor do... Abhi main jag rhe hn 11 tk... Wo bahd main reply krti Hai to ap tb bta daina mjy... Guide kr Don ge main apko\n',
     'Tayaba Malik Student: Ok teacher lakin ap rest karn  ab...\n',
     'Tayaba Malik Student: Suba m khud open   kar lu gi... us k  laptop  m  phir  ap s puch lu gi\n',
     '~K: Yeh remaining user side\n',
     '~K: Chalain thk hai\n',
     'Tayaba Malik Student: G deakh  rahi\n',
     'Tayaba Malik Student: Ok teacher\n',
     'Tayaba Malik Student: Thanku so much... dua karna  bht acha h\n',
     '~K: .Try ur best... Baki Acha he hoga sb in shaa Allah\n',
     'Tayaba Malik Student: Inshallah\n',
     '~K: Tyabba Ap ny laini Hai aj ki class?\n',
     '~K: Tyabba apka laptop ka ho gya na aj k liay arrangement?\n',
     'Tayaba Malik Student: Ni teacher...\n',
     'Tayaba Malik Student: Teacher  project k time  agy h gya\n',
     'Tayaba Malik Student: Chution  ki wajha s\n',
     'Tayaba Malik Student: M ap k update  karti  sir btyn t\n',
     '~K: Abhi ni pta k kab hai last b iski?\n',
     'Tayaba Malik Student: Teacher  yh suddenly  chutian  h gi... t abhi w labs  k complete kar rahy  aur assignments. ... project k b kha rahy m btau  g ... sab k\n',
     '~K: Chutyan to apki January sy ni hon ge start?\n',
     'Tayaba Malik Student: Ni\n',
     'Tayaba Malik Student: University  k h gi...\n',
     'Tayaba Malik Student: Aj s\n',
     'Tayaba Malik Student: Lkin hmm k Fridays  s hn....\n',
     '~K: Or kab tk hain?\n',
     'Tayaba Malik Student: 10 Jan\n',
     'Tayaba Malik Student: Aur extension  k b chances  hn\n',
     '~K: Iska mtlb.... 10 Jan k to bahd he apky project ki submission hoge?\n',
     'Tayaba Malik Student: G\n',
     '~K: Chalain thk hai\n',
     '~K: Koi laptop ka tyabba hoa Kam phir apka?\n',
     ...]




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
     '19/9/21, 8:23\u202fpm - ',
     '19/9/21, 8:37\u202fpm - ',
     '19/9/21, 8:40\u202fpm - ',
     '19/9/21, 8:41\u202fpm - ',
     '26/9/21, 1:43\u202fpm - ',
     '26/9/21, 1:43\u202fpm - ',
     '26/9/21, 2:18\u202fpm - ',
     '26/9/21, 2:19\u202fpm - ',
     '26/9/21, 3:22\u202fpm - ',
     '26/9/21, 3:35\u202fpm - ',
     '26/9/21, 3:36\u202fpm - ',
     '26/9/21, 3:36\u202fpm - ',
     '26/9/21, 3:37\u202fpm - ',
     '26/9/21, 3:38\u202fpm - ',
     '26/9/21, 4:55\u202fpm - ',
     '1/10/21, 2:00\u202fpm - ',
     '7/10/21, 7:01\u202fpm - ',
     '7/10/21, 7:01\u202fpm - ',
     '7/10/21, 7:24\u202fpm - ',
     '7/10/21, 9:31\u202fpm - ',
     '7/10/21, 9:40\u202fpm - ',
     '7/10/21, 9:41\u202fpm - ',
     '7/10/21, 9:41\u202fpm - ',
     '7/10/21, 9:41\u202fpm - ',
     '7/10/21, 9:41\u202fpm - ',
     '7/10/21, 9:42\u202fpm - ',
     '7/10/21, 9:42\u202fpm - ',
     '7/10/21, 9:42\u202fpm - ',
     '7/10/21, 9:43\u202fpm - ',
     '7/10/21, 9:43\u202fpm - ',
     '13/10/21, 7:24\u202fpm - ',
     '13/10/21, 7:24\u202fpm - ',
     '13/10/21, 7:24\u202fpm - ',
     '13/10/21, 7:26\u202fpm - ',
     '13/10/21, 7:26\u202fpm - ',
     '13/10/21, 8:09\u202fpm - ',
     '13/10/21, 8:10\u202fpm - ',
     '13/10/21, 8:10\u202fpm - ',
     '13/10/21, 8:11\u202fpm - ',
     '13/10/21, 8:11\u202fpm - ',
     '13/10/21, 8:11\u202fpm - ',
     '13/10/21, 8:11\u202fpm - ',
     '13/10/21, 8:11\u202fpm - ',
     '13/10/21, 8:12\u202fpm - ',
     '13/10/21, 8:12\u202fpm - ',
     '13/10/21, 8:12\u202fpm - ',
     '13/10/21, 8:12\u202fpm - ',
     '13/10/21, 8:12\u202fpm - ',
     '13/10/21, 8:13\u202fpm - ',
     '13/10/21, 8:13\u202fpm - ',
     '13/10/21, 8:14\u202fpm - ',
     '13/10/21, 8:14\u202fpm - ',
     '13/10/21, 8:14\u202fpm - ',
     '13/10/21, 8:20\u202fpm - ',
     '13/10/21, 8:21\u202fpm - ',
     '13/10/21, 8:22\u202fpm - ',
     '13/10/21, 8:22\u202fpm - ',
     '13/10/21, 8:23\u202fpm - ',
     '13/10/21, 8:23\u202fpm - ',
     '13/10/21, 8:23\u202fpm - ',
     '13/10/21, 8:24\u202fpm - ',
     '13/10/21, 8:25\u202fpm - ',
     '13/10/21, 8:26\u202fpm - ',
     '13/10/21, 8:26\u202fpm - ',
     '13/10/21, 8:26\u202fpm - ',
     '13/10/21, 8:27\u202fpm - ',
     '13/10/21, 8:27\u202fpm - ',
     '13/10/21, 9:28\u202fpm - ',
     '13/10/21, 9:34\u202fpm - ',
     '13/10/21, 9:34\u202fpm - ',
     '13/10/21, 9:34\u202fpm - ',
     '13/10/21, 9:34\u202fpm - ',
     '13/10/21, 9:35\u202fpm - ',
     '14/10/21, 7:21\u202fpm - ',
     '14/10/21, 7:22\u202fpm - ',
     '14/10/21, 7:22\u202fpm - ',
     '14/10/21, 7:23\u202fpm - ',
     '14/10/21, 7:26\u202fpm - ',
     '14/10/21, 7:27\u202fpm - ',
     '14/10/21, 7:27\u202fpm - ',
     '14/10/21, 7:27\u202fpm - ',
     '14/10/21, 7:28\u202fpm - ',
     '14/10/21, 7:28\u202fpm - ',
     '14/10/21, 7:28\u202fpm - ',
     '14/10/21, 7:28\u202fpm - ',
     '14/10/21, 8:06\u202fpm - ',
     '14/10/21, 8:06\u202fpm - ',
     '14/10/21, 8:06\u202fpm - ',
     '14/10/21, 8:35\u202fpm - ',
     '14/10/21, 8:36\u202fpm - ',
     '14/10/21, 8:37\u202fpm - ',
     '14/10/21, 8:41\u202fpm - ',
     '14/10/21, 8:41\u202fpm - ',
     '14/10/21, 8:42\u202fpm - ',
     '14/10/21, 8:43\u202fpm - ',
     '14/10/21, 8:43\u202fpm - ',
     '14/10/21, 8:44\u202fpm - ',
     '14/10/21, 8:44\u202fpm - ',
     '14/10/21, 8:44\u202fpm - ',
     '14/10/21, 8:48\u202fpm - ',
     '14/10/21, 8:48\u202fpm - ',
     '14/10/21, 8:50\u202fpm - ',
     '14/10/21, 8:53\u202fpm - ',
     '14/10/21, 8:54\u202fpm - ',
     '14/10/21, 8:59\u202fpm - ',
     '15/10/21, 8:07\u202fpm - ',
     '15/10/21, 8:11\u202fpm - ',
     '15/10/21, 8:13\u202fpm - ',
     '15/10/21, 8:13\u202fpm - ',
     '15/10/21, 8:13\u202fpm - ',
     '15/10/21, 8:13\u202fpm - ',
     '15/10/21, 8:14\u202fpm - ',
     '15/10/21, 8:14\u202fpm - ',
     '15/10/21, 8:15\u202fpm - ',
     '15/10/21, 8:15\u202fpm - ',
     '15/10/21, 8:15\u202fpm - ',
     '15/10/21, 8:16\u202fpm - ',
     '15/10/21, 8:16\u202fpm - ',
     '15/10/21, 9:25\u202fpm - ',
     '16/10/21, 7:19\u202fpm - ',
     '16/10/21, 7:19\u202fpm - ',
     '16/10/21, 7:19\u202fpm - ',
     '16/10/21, 7:20\u202fpm - ',
     '16/10/21, 7:23\u202fpm - ',
     '16/10/21, 7:23\u202fpm - ',
     '18/10/21, 7:30\u202fpm - ',
     '18/10/21, 8:12\u202fpm - ',
     '18/10/21, 8:12\u202fpm - ',
     '18/10/21, 8:12\u202fpm - ',
     '18/10/21, 8:13\u202fpm - ',
     '18/10/21, 8:13\u202fpm - ',
     '18/10/21, 8:13\u202fpm - ',
     '18/10/21, 8:13\u202fpm - ',
     '18/10/21, 8:13\u202fpm - ',
     '18/10/21, 8:14\u202fpm - ',
     '18/10/21, 8:14\u202fpm - ',
     '18/10/21, 8:14\u202fpm - ',
     '18/10/21, 8:14\u202fpm - ',
     '18/10/21, 8:14\u202fpm - ',
     '18/10/21, 8:15\u202fpm - ',
     '18/10/21, 8:15\u202fpm - ',
     '18/10/21, 8:15\u202fpm - ',
     '18/10/21, 8:15\u202fpm - ',
     '18/10/21, 8:15\u202fpm - ',
     '18/10/21, 8:19\u202fpm - ',
     '18/10/21, 8:19\u202fpm - ',
     '18/10/21, 8:20\u202fpm - ',
     '18/10/21, 8:22\u202fpm - ',
     '18/10/21, 8:22\u202fpm - ',
     '18/10/21, 8:22\u202fpm - ',
     '18/10/21, 8:23\u202fpm - ',
     '18/10/21, 8:23\u202fpm - ',
     '18/10/21, 8:23\u202fpm - ',
     '18/10/21, 8:24\u202fpm - ',
     '18/10/21, 8:25\u202fpm - ',
     '18/10/21, 8:24\u202fpm - ',
     '18/10/21, 8:25\u202fpm - ',
     '18/10/21, 8:26\u202fpm - ',
     '18/10/21, 8:26\u202fpm - ',
     '18/10/21, 8:26\u202fpm - ',
     '18/10/21, 8:27\u202fpm - ',
     '18/10/21, 8:27\u202fpm - ',
     '18/10/21, 8:28\u202fpm - ',
     '18/10/21, 8:29\u202fpm - ',
     '18/10/21, 8:30\u202fpm - ',
     '18/10/21, 8:30\u202fpm - ',
     '18/10/21, 8:32\u202fpm - ',
     '18/10/21, 8:32\u202fpm - ',
     '18/10/21, 8:44\u202fpm - ',
     '18/10/21, 8:44\u202fpm - ',
     '18/10/21, 8:44\u202fpm - ',
     '18/10/21, 8:44\u202fpm - ',
     '18/10/21, 8:45\u202fpm - ',
     '18/10/21, 8:45\u202fpm - ',
     '18/10/21, 8:45\u202fpm - ',
     '18/10/21, 8:45\u202fpm - ',
     '18/10/21, 8:45\u202fpm - ',
     '18/10/21, 8:45\u202fpm - ',
     '18/10/21, 8:46\u202fpm - ',
     '18/10/21, 8:46\u202fpm - ',
     '18/10/21, 8:46\u202fpm - ',
     '18/10/21, 8:46\u202fpm - ',
     '18/10/21, 8:46\u202fpm - ',
     '18/10/21, 8:46\u202fpm - ',
     '18/10/21, 8:47\u202fpm - ',
     '18/10/21, 8:47\u202fpm - ',
     '18/10/21, 8:48\u202fpm - ',
     '18/10/21, 8:49\u202fpm - ',
     '18/10/21, 8:49\u202fpm - ',
     '18/10/21, 8:49\u202fpm - ',
     '18/10/21, 8:50\u202fpm - ',
     '18/10/21, 8:50\u202fpm - ',
     '18/10/21, 8:50\u202fpm - ',
     '18/10/21, 8:50\u202fpm - ',
     '18/10/21, 8:50\u202fpm - ',
     '18/10/21, 8:50\u202fpm - ',
     '18/10/21, 8:51\u202fpm - ',
     '18/10/21, 8:52\u202fpm - ',
     '18/10/21, 8:53\u202fpm - ',
     '18/10/21, 8:53\u202fpm - ',
     '18/10/21, 8:53\u202fpm - ',
     '18/10/21, 8:54\u202fpm - ',
     '18/10/21, 8:55\u202fpm - ',
     '18/10/21, 8:55\u202fpm - ',
     '18/10/21, 8:56\u202fpm - ',
     '18/10/21, 8:56\u202fpm - ',
     '18/10/21, 8:56\u202fpm - ',
     '19/10/21, 7:48\u202fpm - ',
     '19/10/21, 7:49\u202fpm - ',
     '21/10/21, 7:09\u202fpm - ',
     '21/10/21, 7:09\u202fpm - ',
     '21/10/21, 7:22\u202fpm - ',
     '21/10/21, 7:22\u202fpm - ',
     '21/10/21, 7:23\u202fpm - ',
     '21/10/21, 7:23\u202fpm - ',
     '21/10/21, 7:23\u202fpm - ',
     '21/10/21, 7:23\u202fpm - ',
     '21/10/21, 7:23\u202fpm - ',
     '21/10/21, 7:25\u202fpm - ',
     '21/10/21, 7:31\u202fpm - ',
     '21/10/21, 7:35\u202fpm - ',
     '21/10/21, 7:35\u202fpm - ',
     '21/10/21, 7:35\u202fpm - ',
     '22/10/21, 7:41\u202fpm - ',
     '22/10/21, 7:41\u202fpm - ',
     '22/10/21, 7:46\u202fpm - ',
     '22/10/21, 7:48\u202fpm - ',
     '22/10/21, 7:49\u202fpm - ',
     '22/10/21, 7:51\u202fpm - ',
     '23/10/21, 7:31\u202fpm - ',
     '23/10/21, 7:32\u202fpm - ',
     '23/10/21, 7:32\u202fpm - ',
     '23/10/21, 7:32\u202fpm - ',
     '23/10/21, 7:33\u202fpm - ',
     '23/10/21, 7:33\u202fpm - ',
     '23/10/21, 7:33\u202fpm - ',
     '24/10/21, 5:40\u202fpm - ',
     '24/10/21, 5:42\u202fpm - ',
     '24/10/21, 5:55\u202fpm - ',
     '24/10/21, 5:55\u202fpm - ',
     '24/10/21, 6:04\u202fpm - ',
     '24/10/21, 6:05\u202fpm - ',
     '24/10/21, 6:07\u202fpm - ',
     '24/10/21, 7:11\u202fpm - ',
     '24/10/21, 7:12\u202fpm - ',
     '24/10/21, 7:12\u202fpm - ',
     '24/10/21, 7:51\u202fpm - ',
     '24/10/21, 7:51\u202fpm - ',
     '24/10/21, 7:52\u202fpm - ',
     '24/10/21, 7:52\u202fpm - ',
     '24/10/21, 7:54\u202fpm - ',
     '24/10/21, 7:55\u202fpm - ',
     '24/10/21, 7:55\u202fpm - ',
     '24/10/21, 7:55\u202fpm - ',
     '24/10/21, 7:55\u202fpm - ',
     '24/10/21, 7:55\u202fpm - ',
     '24/10/21, 7:56\u202fpm - ',
     '24/10/21, 7:56\u202fpm - ',
     '24/10/21, 7:57\u202fpm - ',
     '24/10/21, 7:58\u202fpm - ',
     '24/10/21, 8:00\u202fpm - ',
     '24/10/21, 8:17\u202fpm - ',
     '24/10/21, 9:42\u202fpm - ',
     '24/10/21, 10:50\u202fpm - ',
     '24/10/21, 10:51\u202fpm - ',
     '24/10/21, 10:52\u202fpm - ',
     '24/10/21, 10:52\u202fpm - ',
     '24/10/21, 10:52\u202fpm - ',
     '24/10/21, 10:53\u202fpm - ',
     '24/10/21, 10:53\u202fpm - ',
     '24/10/21, 10:53\u202fpm - ',
     '24/10/21, 10:54\u202fpm - ',
     '24/10/21, 10:54\u202fpm - ',
     '24/10/21, 10:54\u202fpm - ',
     '24/10/21, 10:54\u202fpm - ',
     '24/10/21, 10:55\u202fpm - ',
     '25/10/21, 7:35\u202fpm - ',
     '25/10/21, 7:35\u202fpm - ',
     '25/10/21, 8:19\u202fpm - ',
     '25/10/21, 8:20\u202fpm - ',
     '25/10/21, 8:20\u202fpm - ',
     '25/10/21, 8:20\u202fpm - ',
     '25/10/21, 8:20\u202fpm - ',
     '25/10/21, 8:21\u202fpm - ',
     '25/10/21, 8:22\u202fpm - ',
     '25/10/21, 8:22\u202fpm - ',
     '25/10/21, 8:25\u202fpm - ',
     '25/10/21, 8:25\u202fpm - ',
     '25/10/21, 8:25\u202fpm - ',
     '25/10/21, 8:25\u202fpm - ',
     '25/10/21, 8:25\u202fpm - ',
     '25/10/21, 8:25\u202fpm - ',
     '25/10/21, 8:26\u202fpm - ',
     '25/10/21, 8:26\u202fpm - ',
     '25/10/21, 8:26\u202fpm - ',
     '25/10/21, 8:26\u202fpm - ',
     '25/10/21, 8:26\u202fpm - ',
     '25/10/21, 8:27\u202fpm - ',
     '25/10/21, 8:27\u202fpm - ',
     '25/10/21, 8:31\u202fpm - ',
     '25/10/21, 8:33\u202fpm - ',
     '25/10/21, 8:38\u202fpm - ',
     '25/10/21, 8:38\u202fpm - ',
     '26/10/21, 7:26\u202fpm - ',
     '26/10/21, 7:33\u202fpm - ',
     '26/10/21, 7:33\u202fpm - ',
     '26/10/21, 7:34\u202fpm - ',
     '26/10/21, 7:47\u202fpm - ',
     '26/10/21, 8:11\u202fpm - ',
     '26/10/21, 8:11\u202fpm - ',
     '26/10/21, 8:12\u202fpm - ',
     '26/10/21, 8:12\u202fpm - ',
     '26/10/21, 8:12\u202fpm - ',
     '26/10/21, 8:13\u202fpm - ',
     '26/10/21, 8:13\u202fpm - ',
     '26/10/21, 8:13\u202fpm - ',
     '26/10/21, 8:13\u202fpm - ',
     '26/10/21, 8:14\u202fpm - ',
     '26/10/21, 8:14\u202fpm - ',
     '26/10/21, 8:14\u202fpm - ',
     '26/10/21, 8:14\u202fpm - ',
     '26/10/21, 8:14\u202fpm - ',
     '26/10/21, 8:14\u202fpm - ',
     '27/10/21, 6:26\u202fpm - ',
     '27/10/21, 6:27\u202fpm - ',
     '27/10/21, 6:27\u202fpm - ',
     '27/10/21, 6:27\u202fpm - ',
     '27/10/21, 6:28\u202fpm - ',
     '27/10/21, 6:28\u202fpm - ',
     '27/10/21, 6:28\u202fpm - ',
     '27/10/21, 6:28\u202fpm - ',
     '27/10/21, 6:28\u202fpm - ',
     '27/10/21, 6:28\u202fpm - ',
     '27/10/21, 6:29\u202fpm - ',
     '27/10/21, 6:32\u202fpm - ',
     '27/10/21, 6:32\u202fpm - ',
     '27/10/21, 6:32\u202fpm - ',
     '27/10/21, 8:41\u202fpm - ',
     '27/10/21, 8:42\u202fpm - ',
     '27/10/21, 8:43\u202fpm - ',
     '27/10/21, 8:43\u202fpm - ',
     '28/10/21, 7:30\u202fpm - ',
     '28/10/21, 7:44\u202fpm - ',
     '28/10/21, 7:45\u202fpm - ',
     '28/10/21, 7:47\u202fpm - ',
     '28/10/21, 7:47\u202fpm - ',
     '28/10/21, 7:47\u202fpm - ',
     '28/10/21, 7:47\u202fpm - ',
     '28/10/21, 7:47\u202fpm - ',
     '28/10/21, 7:48\u202fpm - ',
     '28/10/21, 7:48\u202fpm - ',
     '28/10/21, 7:48\u202fpm - ',
     '28/10/21, 7:49\u202fpm - ',
     '28/10/21, 7:49\u202fpm - ',
     '28/10/21, 7:49\u202fpm - ',
     '28/10/21, 7:50\u202fpm - ',
     '28/10/21, 7:50\u202fpm - ',
     '29/10/21, 7:36\u202fpm - ',
     '29/10/21, 7:47\u202fpm - ',
     '29/10/21, 7:47\u202fpm - ',
     '29/10/21, 7:47\u202fpm - ',
     '29/10/21, 7:49\u202fpm - ',
     '29/10/21, 7:50\u202fpm - ',
     '30/10/21, 7:34\u202fpm - ',
     '30/10/21, 10:12\u202fpm - ',
     '30/10/21, 10:12\u202fpm - ',
     '31/10/21, 8:38\u202fam - ',
     '31/10/21, 8:46\u202fam - ',
     '31/10/21, 10:51\u202fam - ',
     '31/10/21, 11:10\u202fam - ',
     '31/10/21, 11:10\u202fam - ',
     '31/10/21, 11:10\u202fam - ',
     '31/10/21, 11:45\u202fam - ',
     '31/10/21, 11:45\u202fam - ',
     '31/10/21, 11:45\u202fam - ',
     '31/10/21, 11:46\u202fam - ',
     '31/10/21, 11:46\u202fam - ',
     '31/10/21, 11:46\u202fam - ',
     '31/10/21, 11:46\u202fam - ',
     '31/10/21, 11:46\u202fam - ',
     '1/11/21, 7:30\u202fpm - ',
     '1/11/21, 7:30\u202fpm - ',
     '1/11/21, 7:31\u202fpm - ',
     '1/11/21, 7:31\u202fpm - ',
     '1/11/21, 7:31\u202fpm - ',
     '1/11/21, 7:31\u202fpm - ',
     '1/11/21, 7:31\u202fpm - ',
     '1/11/21, 7:31\u202fpm - ',
     '1/11/21, 7:32\u202fpm - ',
     '1/11/21, 7:32\u202fpm - ',
     '2/11/21, 7:21\u202fpm - ',
     '2/11/21, 7:21\u202fpm - ',
     '2/11/21, 7:22\u202fpm - ',
     '2/11/21, 7:23\u202fpm - ',
     '2/11/21, 7:24\u202fpm - ',
     '2/11/21, 7:24\u202fpm - ',
     '2/11/21, 7:24\u202fpm - ',
     '2/11/21, 7:24\u202fpm - ',
     '4/11/21, 7:17\u202fpm - ',
     '4/11/21, 7:17\u202fpm - ',
     '4/11/21, 7:17\u202fpm - ',
     '4/11/21, 7:18\u202fpm - ',
     '4/11/21, 7:21\u202fpm - ',
     '4/11/21, 7:21\u202fpm - ',
     '4/11/21, 7:21\u202fpm - ',
     '4/11/21, 7:21\u202fpm - ',
     '4/11/21, 7:21\u202fpm - ',
     '4/11/21, 7:24\u202fpm - ',
     '5/11/21, 5:54\u202fpm - ',
     '5/11/21, 7:19\u202fpm - ',
     '5/11/21, 8:15\u202fpm - ',
     '5/11/21, 8:15\u202fpm - ',
     '5/11/21, 8:15\u202fpm - ',
     '6/11/21, 8:35\u202fam - ',
     '6/11/21, 1:41\u202fpm - ',
     '6/11/21, 1:41\u202fpm - ',
     '6/11/21, 7:30\u202fpm - ',
     '6/11/21, 7:30\u202fpm - ',
     '6/11/21, 7:50\u202fpm - ',
     '6/11/21, 7:52\u202fpm - ',
     '6/11/21, 7:52\u202fpm - ',
     '8/11/21, 7:03\u202fpm - ',
     '8/11/21, 7:05\u202fpm - ',
     '8/11/21, 7:05\u202fpm - ',
     '8/11/21, 7:11\u202fpm - ',
     '8/11/21, 7:11\u202fpm - ',
     '9/11/21, 7:29\u202fpm - ',
     '9/11/21, 7:30\u202fpm - ',
     '9/11/21, 7:30\u202fpm - ',
     '10/11/21, 6:08\u202fpm - ',
     '10/11/21, 6:40\u202fpm - ',
     '10/11/21, 6:43\u202fpm - ',
     '10/11/21, 6:44\u202fpm - ',
     '10/11/21, 6:44\u202fpm - ',
     '10/11/21, 6:45\u202fpm - ',
     '10/11/21, 6:45\u202fpm - ',
     '10/11/21, 6:45\u202fpm - ',
     '10/11/21, 6:46\u202fpm - ',
     '10/11/21, 6:46\u202fpm - ',
     '10/11/21, 6:46\u202fpm - ',
     '10/11/21, 6:46\u202fpm - ',
     '10/11/21, 6:47\u202fpm - ',
     '10/11/21, 6:47\u202fpm - ',
     '10/11/21, 6:47\u202fpm - ',
     '10/11/21, 6:47\u202fpm - ',
     '10/11/21, 6:47\u202fpm - ',
     '10/11/21, 6:47\u202fpm - ',
     '10/11/21, 6:47\u202fpm - ',
     '10/11/21, 6:47\u202fpm - ',
     '10/11/21, 6:48\u202fpm - ',
     '10/11/21, 6:51\u202fpm - ',
     '10/11/21, 6:54\u202fpm - ',
     '10/11/21, 6:55\u202fpm - ',
     '10/11/21, 7:38\u202fpm - ',
     '21/11/21, 12:41\u202fpm - ',
     '21/11/21, 5:16\u202fpm - ',
     '22/11/21, 6:56\u202fpm - ',
     '22/11/21, 6:56\u202fpm - ',
     '22/11/21, 7:29\u202fpm - ',
     '22/11/21, 7:47\u202fpm - ',
     '22/11/21, 7:53\u202fpm - ',
     '22/11/21, 7:53\u202fpm - ',
     '22/11/21, 7:53\u202fpm - ',
     '22/11/21, 7:53\u202fpm - ',
     '22/11/21, 7:53\u202fpm - ',
     '22/11/21, 7:53\u202fpm - ',
     '22/11/21, 7:54\u202fpm - ',
     '22/11/21, 7:54\u202fpm - ',
     '22/11/21, 7:54\u202fpm - ',
     '22/11/21, 7:54\u202fpm - ',
     '22/11/21, 7:54\u202fpm - ',
     '22/11/21, 7:55\u202fpm - ',
     '22/11/21, 7:55\u202fpm - ',
     '22/11/21, 7:55\u202fpm - ',
     '22/11/21, 7:56\u202fpm - ',
     '23/11/21, 10:03\u202fam - ',
     '23/11/21, 10:07\u202fam - ',
     '23/11/21, 10:08\u202fam - ',
     '23/11/21, 10:08\u202fam - ',
     '23/11/21, 10:08\u202fam - ',
     '23/11/21, 10:08\u202fam - ',
     '23/11/21, 10:09\u202fam - ',
     '23/11/21, 10:09\u202fam - ',
     '23/11/21, 10:09\u202fam - ',
     '23/11/21, 10:09\u202fam - ',
     '23/11/21, 11:08\u202fam - ',
     '23/11/21, 11:09\u202fam - ',
     '23/11/21, 11:09\u202fam - ',
     '23/11/21, 11:09\u202fam - ',
     '23/11/21, 11:09\u202fam - ',
     '23/11/21, 11:09\u202fam - ',
     '23/11/21, 11:10\u202fam - ',
     '23/11/21, 11:10\u202fam - ',
     '23/11/21, 11:10\u202fam - ',
     '23/11/21, 11:10\u202fam - ',
     '23/11/21, 11:11\u202fam - ',
     '23/11/21, 11:11\u202fam - ',
     '23/11/21, 11:11\u202fam - ',
     '23/11/21, 11:11\u202fam - ',
     '23/11/21, 11:11\u202fam - ',
     '23/11/21, 11:11\u202fam - ',
     '23/11/21, 11:11\u202fam - ',
     '23/11/21, 11:12\u202fam - ',
     '23/11/21, 11:12\u202fam - ',
     '23/11/21, 11:12\u202fam - ',
     '23/11/21, 5:19\u202fpm - ',
     '23/11/21, 6:36\u202fpm - ',
     '23/11/21, 6:43\u202fpm - ',
     '23/11/21, 6:46\u202fpm - ',
     '23/11/21, 6:47\u202fpm - ',
     '23/11/21, 7:00\u202fpm - ',
     '23/11/21, 7:00\u202fpm - ',
     '23/11/21, 8:13\u202fpm - ',
     '23/11/21, 8:14\u202fpm - ',
     '24/11/21, 6:55\u202fpm - ',
     '24/11/21, 7:05\u202fpm - ',
     '24/11/21, 7:30\u202fpm - ',
     '24/11/21, 7:40\u202fpm - ',
     '24/11/21, 7:43\u202fpm - ',
     '24/11/21, 7:44\u202fpm - ',
     '24/11/21, 7:44\u202fpm - ',
     '24/11/21, 7:44\u202fpm - ',
     '24/11/21, 7:44\u202fpm - ',
     '24/11/21, 7:46\u202fpm - ',
     '24/11/21, 7:47\u202fpm - ',
     '24/11/21, 7:47\u202fpm - ',
     '24/11/21, 8:38\u202fpm - ',
     '24/11/21, 8:39\u202fpm - ',
     '24/11/21, 8:39\u202fpm - ',
     '24/11/21, 8:39\u202fpm - ',
     '24/11/21, 8:39\u202fpm - ',
     '24/11/21, 8:40\u202fpm - ',
     '25/11/21, 7:21\u202fpm - ',
     '25/11/21, 7:23\u202fpm - ',
     '25/11/21, 7:24\u202fpm - ',
     '25/11/21, 7:24\u202fpm - ',
     '25/11/21, 7:24\u202fpm - ',
     '25/11/21, 7:25\u202fpm - ',
     '25/11/21, 7:25\u202fpm - ',
     '25/11/21, 7:25\u202fpm - ',
     '25/11/21, 7:25\u202fpm - ',
     '25/11/21, 7:25\u202fpm - ',
     '25/11/21, 7:25\u202fpm - ',
     '25/11/21, 7:25\u202fpm - ',
     '25/11/21, 7:25\u202fpm - ',
     '25/11/21, 7:26\u202fpm - ',
     '25/11/21, 7:26\u202fpm - ',
     '25/11/21, 7:26\u202fpm - ',
     '25/11/21, 7:27\u202fpm - ',
     '25/11/21, 7:28\u202fpm - ',
     '26/11/21, 7:04\u202fpm - ',
     '26/11/21, 7:29\u202fpm - ',
     '26/11/21, 7:45\u202fpm - ',
     '26/11/21, 7:46\u202fpm - ',
     '26/11/21, 7:46\u202fpm - ',
     '27/11/21, 6:53\u202fpm - ',
     '27/11/21, 6:55\u202fpm - ',
     '27/11/21, 6:55\u202fpm - ',
     '27/11/21, 7:01\u202fpm - ',
     '27/11/21, 7:01\u202fpm - ',
     '27/11/21, 7:01\u202fpm - ',
     '27/11/21, 7:01\u202fpm - ',
     '27/11/21, 7:02\u202fpm - ',
     '27/11/21, 7:02\u202fpm - ',
     '27/11/21, 7:02\u202fpm - ',
     '27/11/21, 7:02\u202fpm - ',
     '27/11/21, 7:02\u202fpm - ',
     '27/11/21, 7:02\u202fpm - ',
     '27/11/21, 7:02\u202fpm - ',
     '27/11/21, 7:02\u202fpm - ',
     '27/11/21, 7:02\u202fpm - ',
     '27/11/21, 7:03\u202fpm - ',
     '27/11/21, 7:03\u202fpm - ',
     '27/11/21, 7:08\u202fpm - ',
     '27/11/21, 7:18\u202fpm - ',
     '27/11/21, 7:19\u202fpm - ',
     '28/11/21, 1:45\u202fpm - ',
     '28/11/21, 1:45\u202fpm - ',
     '28/11/21, 1:46\u202fpm - ',
     '28/11/21, 2:24\u202fpm - ',
     '28/11/21, 2:25\u202fpm - ',
     '28/11/21, 2:26\u202fpm - ',
     '28/11/21, 2:26\u202fpm - ',
     '28/11/21, 2:27\u202fpm - ',
     '28/11/21, 2:28\u202fpm - ',
     '28/11/21, 2:30\u202fpm - ',
     '28/11/21, 2:30\u202fpm - ',
     '28/11/21, 2:30\u202fpm - ',
     '28/11/21, 2:30\u202fpm - ',
     '28/11/21, 2:31\u202fpm - ',
     '28/11/21, 2:31\u202fpm - ',
     '28/11/21, 6:29\u202fpm - ',
     '28/11/21, 7:03\u202fpm - ',
     '29/11/21, 7:01\u202fpm - ',
     '29/11/21, 7:02\u202fpm - ',
     '29/11/21, 7:02\u202fpm - ',
     '29/11/21, 7:02\u202fpm - ',
     '29/11/21, 7:02\u202fpm - ',
     '29/11/21, 7:06\u202fpm - ',
     '29/11/21, 7:53\u202fpm - ',
     '29/11/21, 7:53\u202fpm - ',
     '29/11/21, 7:54\u202fpm - ',
     '29/11/21, 7:55\u202fpm - ',
     '30/11/21, 7:08\u202fpm - ',
     '30/11/21, 7:12\u202fpm - ',
     '30/11/21, 7:12\u202fpm - ',
     '30/11/21, 7:12\u202fpm - ',
     '30/11/21, 7:16\u202fpm - ',
     '30/11/21, 7:16\u202fpm - ',
     '30/11/21, 7:16\u202fpm - ',
     '30/11/21, 7:16\u202fpm - ',
     '30/11/21, 7:17\u202fpm - ',
     '30/11/21, 7:17\u202fpm - ',
     '30/11/21, 7:17\u202fpm - ',
     '30/11/21, 7:17\u202fpm - ',
     '30/11/21, 7:29\u202fpm - ',
     '30/11/21, 7:44\u202fpm - ',
     '1/12/21, 9:32\u202fam - ',
     '1/12/21, 9:36\u202fam - ',
     '1/12/21, 9:40\u202fam - ',
     '1/12/21, 9:40\u202fam - ',
     '1/12/21, 9:43\u202fam - ',
     '1/12/21, 9:44\u202fam - ',
     '1/12/21, 9:45\u202fam - ',
     '1/12/21, 7:11\u202fpm - ',
     '2/12/21, 6:53\u202fpm - ',
     '2/12/21, 6:54\u202fpm - ',
     '2/12/21, 6:54\u202fpm - ',
     '2/12/21, 8:02\u202fpm - ',
     '2/12/21, 8:22\u202fpm - ',
     '2/12/21, 8:23\u202fpm - ',
     '3/12/21, 7:25\u202fpm - ',
     '3/12/21, 7:28\u202fpm - ',
     '3/12/21, 7:29\u202fpm - ',
     '3/12/21, 7:29\u202fpm - ',
     '3/12/21, 7:31\u202fpm - ',
     '4/12/21, 6:57\u202fpm - ',
     '4/12/21, 6:58\u202fpm - ',
     '4/12/21, 6:58\u202fpm - ',
     '4/12/21, 7:03\u202fpm - ',
     '4/12/21, 7:03\u202fpm - ',
     '6/12/21, 6:50\u202fpm - ',
     '6/12/21, 6:55\u202fpm - ',
     '6/12/21, 6:56\u202fpm - ',
     '6/12/21, 7:00\u202fpm - ',
     '7/12/21, 7:00\u202fpm - ',
     '7/12/21, 7:30\u202fpm - ',
     '7/12/21, 7:30\u202fpm - ',
     '8/12/21, 9:59\u202fam - ',
     '8/12/21, 10:18\u202fam - ',
     '8/12/21, 10:23\u202fam - ',
     '8/12/21, 10:23\u202fam - ',
     '8/12/21, 10:46\u202fam - ',
     '8/12/21, 11:40\u202fam - ',
     '8/12/21, 11:54\u202fam - ',
     '8/12/21, 7:26\u202fpm - ',
     '9/12/21, 7:32\u202fpm - ',
     '9/12/21, 7:34\u202fpm - ',
     '9/12/21, 7:35\u202fpm - ',
     '9/12/21, 7:35\u202fpm - ',
     '9/12/21, 7:35\u202fpm - ',
     '9/12/21, 7:36\u202fpm - ',
     '9/12/21, 7:36\u202fpm - ',
     '9/12/21, 7:36\u202fpm - ',
     '9/12/21, 7:37\u202fpm - ',
     '9/12/21, 7:37\u202fpm - ',
     '9/12/21, 7:37\u202fpm - ',
     '9/12/21, 7:37\u202fpm - ',
     '9/12/21, 7:38\u202fpm - ',
     '9/12/21, 7:38\u202fpm - ',
     '9/12/21, 7:39\u202fpm - ',
     '9/12/21, 7:39\u202fpm - ',
     '9/12/21, 7:39\u202fpm - ',
     '9/12/21, 7:39\u202fpm - ',
     '9/12/21, 7:40\u202fpm - ',
     '9/12/21, 7:40\u202fpm - ',
     '9/12/21, 7:40\u202fpm - ',
     '9/12/21, 7:40\u202fpm - ',
     '9/12/21, 7:40\u202fpm - ',
     '9/12/21, 7:41\u202fpm - ',
     '9/12/21, 7:41\u202fpm - ',
     '9/12/21, 7:41\u202fpm - ',
     '9/12/21, 7:41\u202fpm - ',
     '9/12/21, 7:41\u202fpm - ',
     '9/12/21, 7:42\u202fpm - ',
     '10/12/21, 7:22\u202fpm - ',
     '10/12/21, 7:26\u202fpm - ',
     '10/12/21, 7:26\u202fpm - ',
     '10/12/21, 7:27\u202fpm - ',
     '10/12/21, 7:30\u202fpm - ',
     '10/12/21, 7:32\u202fpm - ',
     '10/12/21, 7:33\u202fpm - ',
     '10/12/21, 7:33\u202fpm - ',
     '10/12/21, 7:34\u202fpm - ',
     '10/12/21, 7:34\u202fpm - ',
     '10/12/21, 7:34\u202fpm - ',
     '10/12/21, 7:34\u202fpm - ',
     '10/12/21, 7:35\u202fpm - ',
     '10/12/21, 7:35\u202fpm - ',
     '10/12/21, 7:35\u202fpm - ',
     '10/12/21, 7:36\u202fpm - ',
     '10/12/21, 7:37\u202fpm - ',
     '10/12/21, 7:38\u202fpm - ',
     '10/12/21, 7:38\u202fpm - ',
     '10/12/21, 7:38\u202fpm - ',
     '10/12/21, 7:38\u202fpm - ',
     '10/12/21, 7:38\u202fpm - ',
     '10/12/21, 7:46\u202fpm - ',
     '10/12/21, 8:00\u202fpm - ',
     '10/12/21, 8:06\u202fpm - ',
     '10/12/21, 8:06\u202fpm - ',
     '10/12/21, 8:06\u202fpm - ',
     '10/12/21, 8:07\u202fpm - ',
     '10/12/21, 8:07\u202fpm - ',
     '10/12/21, 8:07\u202fpm - ',
     '10/12/21, 8:07\u202fpm - ',
     '10/12/21, 8:07\u202fpm - ',
     '10/12/21, 8:08\u202fpm - ',
     '10/12/21, 8:08\u202fpm - ',
     '10/12/21, 8:09\u202fpm - ',
     '10/12/21, 8:09\u202fpm - ',
     '10/12/21, 8:09\u202fpm - ',
     '10/12/21, 8:09\u202fpm - ',
     '10/12/21, 8:10\u202fpm - ',
     '11/12/21, 1:40\u202fpm - ',
     '11/12/21, 1:42\u202fpm - ',
     '11/12/21, 6:56\u202fpm - ',
     '11/12/21, 7:14\u202fpm - ',
     '11/12/21, 7:15\u202fpm - ',
     '11/12/21, 7:15\u202fpm - ',
     '11/12/21, 7:16\u202fpm - ',
     '11/12/21, 7:16\u202fpm - ',
     '11/12/21, 7:17\u202fpm - ',
     '11/12/21, 7:17\u202fpm - ',
     '11/12/21, 7:17\u202fpm - ',
     '11/12/21, 7:17\u202fpm - ',
     '11/12/21, 7:18\u202fpm - ',
     '11/12/21, 7:18\u202fpm - ',
     '11/12/21, 7:18\u202fpm - ',
     '11/12/21, 7:18\u202fpm - ',
     '11/12/21, 7:18\u202fpm - ',
     '11/12/21, 7:19\u202fpm - ',
     '11/12/21, 7:19\u202fpm - ',
     '11/12/21, 7:20\u202fpm - ',
     '11/12/21, 7:20\u202fpm - ',
     '11/12/21, 7:21\u202fpm - ',
     '11/12/21, 7:22\u202fpm - ',
     '11/12/21, 7:22\u202fpm - ',
     '11/12/21, 7:22\u202fpm - ',
     '11/12/21, 7:23\u202fpm - ',
     '11/12/21, 7:23\u202fpm - ',
     '11/12/21, 7:23\u202fpm - ',
     '11/12/21, 7:24\u202fpm - ',
     '11/12/21, 7:24\u202fpm - ',
     '11/12/21, 7:25\u202fpm - ',
     '11/12/21, 7:27\u202fpm - ',
     '12/12/21, 4:22\u202fpm - ',
     '12/12/21, 4:27\u202fpm - ',
     '12/12/21, 4:27\u202fpm - ',
     '12/12/21, 4:31\u202fpm - ',
     '12/12/21, 5:08\u202fpm - ',
     '12/12/21, 5:29\u202fpm - ',
     '12/12/21, 5:29\u202fpm - ',
     '13/12/21, 6:26\u202fpm - ',
     '13/12/21, 6:33\u202fpm - ',
     '13/12/21, 6:35\u202fpm - ',
     '13/12/21, 6:39\u202fpm - ',
     '13/12/21, 6:39\u202fpm - ',
     '13/12/21, 6:39\u202fpm - ',
     '13/12/21, 6:41\u202fpm - ',
     '13/12/21, 6:42\u202fpm - ',
     '13/12/21, 6:42\u202fpm - ',
     '13/12/21, 6:43\u202fpm - ',
     '13/12/21, 6:43\u202fpm - ',
     '13/12/21, 6:46\u202fpm - ',
     '13/12/21, 6:46\u202fpm - ',
     '13/12/21, 6:47\u202fpm - ',
     '13/12/21, 6:49\u202fpm - ',
     '13/12/21, 7:08\u202fpm - ',
     '13/12/21, 7:08\u202fpm - ',
     '13/12/21, 7:08\u202fpm - ',
     '13/12/21, 7:40\u202fpm - ',
     '13/12/21, 7:40\u202fpm - ',
     '13/12/21, 7:41\u202fpm - ',
     '13/12/21, 7:43\u202fpm - ',
     '13/12/21, 7:44\u202fpm - ',
     '13/12/21, 7:45\u202fpm - ',
     '13/12/21, 7:45\u202fpm - ',
     '13/12/21, 7:52\u202fpm - ',
     '13/12/21, 7:52\u202fpm - ',
     '13/12/21, 7:52\u202fpm - ',
     '13/12/21, 7:52\u202fpm - ',
     '13/12/21, 7:53\u202fpm - ',
     '13/12/21, 7:53\u202fpm - ',
     '13/12/21, 7:53\u202fpm - ',
     '13/12/21, 7:53\u202fpm - ',
     '13/12/21, 7:54\u202fpm - ',
     '13/12/21, 7:54\u202fpm - ',
     '13/12/21, 7:54\u202fpm - ',
     '13/12/21, 7:54\u202fpm - ',
     '13/12/21, 7:54\u202fpm - ',
     '13/12/21, 7:54\u202fpm - ',
     '13/12/21, 7:54\u202fpm - ',
     '13/12/21, 7:54\u202fpm - ',
     '13/12/21, 7:54\u202fpm - ',
     '13/12/21, 7:55\u202fpm - ',
     '13/12/21, 7:55\u202fpm - ',
     '13/12/21, 7:55\u202fpm - ',
     '13/12/21, 7:55\u202fpm - ',
     '13/12/21, 7:55\u202fpm - ',
     '13/12/21, 7:56\u202fpm - ',
     '16/12/21, 9:56\u202fam - ',
     '16/12/21, 10:45\u202fam - ',
     '17/12/21, 5:55\u202fpm - ',
     '17/12/21, 5:55\u202fpm - ',
     '17/12/21, 6:43\u202fpm - ',
     '17/12/21, 6:43\u202fpm - ',
     '17/12/21, 6:44\u202fpm - ',
     '17/12/21, 6:44\u202fpm - ',
     '17/12/21, 6:44\u202fpm - ',
     '17/12/21, 6:44\u202fpm - ',
     '17/12/21, 6:45\u202fpm - ',
     '17/12/21, 6:45\u202fpm - ',
     '17/12/21, 6:45\u202fpm - ',
     '17/12/21, 6:45\u202fpm - ',
     '17/12/21, 6:45\u202fpm - ',
     '17/12/21, 6:45\u202fpm - ',
     '17/12/21, 6:46\u202fpm - ',
     '17/12/21, 6:46\u202fpm - ',
     '17/12/21, 6:46\u202fpm - ',
     '17/12/21, 6:46\u202fpm - ',
     '17/12/21, 6:46\u202fpm - ',
     '17/12/21, 6:46\u202fpm - ',
     '17/12/21, 6:47\u202fpm - ',
     '17/12/21, 6:47\u202fpm - ',
     '17/12/21, 6:47\u202fpm - ',
     '17/12/21, 6:47\u202fpm - ',
     '17/12/21, 6:47\u202fpm - ',
     '17/12/21, 6:48\u202fpm - ',
     '17/12/21, 6:48\u202fpm - ',
     '17/12/21, 6:48\u202fpm - ',
     '17/12/21, 6:48\u202fpm - ',
     '17/12/21, 6:48\u202fpm - ',
     '17/12/21, 6:48\u202fpm - ',
     '17/12/21, 6:49\u202fpm - ',
     '17/12/21, 6:49\u202fpm - ',
     '17/12/21, 6:49\u202fpm - ',
     '17/12/21, 6:49\u202fpm - ',
     '17/12/21, 6:49\u202fpm - ',
     '17/12/21, 6:49\u202fpm - ',
     '17/12/21, 6:50\u202fpm - ',
     '17/12/21, 6:50\u202fpm - ',
     '17/12/21, 6:50\u202fpm - ',
     '17/12/21, 6:50\u202fpm - ',
     '17/12/21, 6:50\u202fpm - ',
     '17/12/21, 6:50\u202fpm - ',
     '19/12/21, 11:22\u202fam - ',
     '19/12/21, 11:23\u202fam - ',
     '19/12/21, 11:23\u202fam - ',
     '19/12/21, 11:23\u202fam - ',
     '19/12/21, 11:24\u202fam - ',
     '19/12/21, 11:24\u202fam - ',
     '19/12/21, 11:24\u202fam - ',
     '19/12/21, 11:24\u202fam - ',
     '19/12/21, 12:00\u202fpm - ',
     '20/12/21, 6:55\u202fpm - ',
     '20/12/21, 7:11\u202fpm - ',
     '20/12/21, 7:36\u202fpm - ',
     '20/12/21, 7:36\u202fpm - ',
     '20/12/21, 7:36\u202fpm - ',
     '20/12/21, 7:37\u202fpm - ',
     '20/12/21, 7:38\u202fpm - ',
     '20/12/21, 7:38\u202fpm - ',
     '20/12/21, 7:39\u202fpm - ',
     '20/12/21, 7:42\u202fpm - ',
     '20/12/21, 7:43\u202fpm - ',
     '20/12/21, 7:44\u202fpm - ',
     '20/12/21, 7:44\u202fpm - ',
     '20/12/21, 7:44\u202fpm - ',
     '20/12/21, 7:45\u202fpm - ',
     '20/12/21, 7:45\u202fpm - ',
     '20/12/21, 7:45\u202fpm - ',
     '20/12/21, 7:46\u202fpm - ',
     '20/12/21, 7:46\u202fpm - ',
     '20/12/21, 7:47\u202fpm - ',
     '20/12/21, 7:47\u202fpm - ',
     '20/12/21, 7:48\u202fpm - ',
     '20/12/21, 7:48\u202fpm - ',
     '20/12/21, 7:48\u202fpm - ',
     '20/12/21, 7:49\u202fpm - ',
     '20/12/21, 7:50\u202fpm - ',
     '20/12/21, 7:50\u202fpm - ',
     '20/12/21, 7:50\u202fpm - ',
     '20/12/21, 7:50\u202fpm - ',
     '20/12/21, 7:50\u202fpm - ',
     '20/12/21, 7:51\u202fpm - ',
     '20/12/21, 7:51\u202fpm - ',
     '20/12/21, 7:51\u202fpm - ',
     '20/12/21, 7:53\u202fpm - ',
     '20/12/21, 7:52\u202fpm - ',
     '20/12/21, 7:56\u202fpm - ',
     '20/12/21, 7:56\u202fpm - ',
     '20/12/21, 7:56\u202fpm - ',
     '20/12/21, 7:57\u202fpm - ',
     '20/12/21, 8:03\u202fpm - ',
     '20/12/21, 8:04\u202fpm - ',
     '20/12/21, 8:05\u202fpm - ',
     '20/12/21, 8:05\u202fpm - ',
     '20/12/21, 8:05\u202fpm - ',
     '20/12/21, 8:06\u202fpm - ',
     '20/12/21, 8:07\u202fpm - ',
     '20/12/21, 8:07\u202fpm - ',
     '20/12/21, 8:07\u202fpm - ',
     '20/12/21, 8:08\u202fpm - ',
     '20/12/21, 8:08\u202fpm - ',
     '20/12/21, 8:29\u202fpm - ',
     '20/12/21, 8:36\u202fpm - ',
     '20/12/21, 8:40\u202fpm - ',
     '20/12/21, 8:41\u202fpm - ',
     '20/12/21, 8:41\u202fpm - ',
     '20/12/21, 8:42\u202fpm - ',
     '20/12/21, 8:42\u202fpm - ',
     '20/12/21, 8:42\u202fpm - ',
     '20/12/21, 8:43\u202fpm - ',
     '20/12/21, 8:43\u202fpm - ',
     '20/12/21, 8:43\u202fpm - ',
     '20/12/21, 8:44\u202fpm - ',
     '20/12/21, 8:45\u202fpm - ',
     '20/12/21, 8:45\u202fpm - ',
     '20/12/21, 8:46\u202fpm - ',
     '20/12/21, 8:47\u202fpm - ',
     '20/12/21, 8:47\u202fpm - ',
     '20/12/21, 8:49\u202fpm - ',
     '20/12/21, 8:49\u202fpm - ',
     '20/12/21, 8:50\u202fpm - ',
     '20/12/21, 8:50\u202fpm - ',
     '20/12/21, 8:51\u202fpm - ',
     '20/12/21, 8:51\u202fpm - ',
     '20/12/21, 8:51\u202fpm - ',
     '20/12/21, 8:52\u202fpm - ',
     '20/12/21, 8:52\u202fpm - ',
     '20/12/21, 8:53\u202fpm - ',
     '20/12/21, 8:54\u202fpm - ',
     '20/12/21, 8:54\u202fpm - ',
     '20/12/21, 8:55\u202fpm - ',
     '20/12/21, 8:55\u202fpm - ',
     '20/12/21, 8:55\u202fpm - ',
     '20/12/21, 8:55\u202fpm - ',
     '20/12/21, 8:56\u202fpm - ',
     '20/12/21, 8:56\u202fpm - ',
     '21/12/21, 7:03\u202fpm - ',
     '22/12/21, 6:47\u202fpm - ',
     '22/12/21, 7:25\u202fpm - ',
     '22/12/21, 7:26\u202fpm - ',
     '22/12/21, 7:26\u202fpm - ',
     '22/12/21, 7:26\u202fpm - ',
     '22/12/21, 7:29\u202fpm - ',
     '22/12/21, 7:30\u202fpm - ',
     '22/12/21, 7:31\u202fpm - ',
     '22/12/21, 7:32\u202fpm - ',
     '22/12/21, 7:32\u202fpm - ',
     '22/12/21, 7:32\u202fpm - ',
     '22/12/21, 7:32\u202fpm - ',
     '22/12/21, 7:32\u202fpm - ',
     '22/12/21, 7:32\u202fpm - ',
     '22/12/21, 7:33\u202fpm - ',
     '22/12/21, 7:33\u202fpm - ',
     '22/12/21, 7:34\u202fpm - ',
     '22/12/21, 7:37\u202fpm - ',
     '24/12/21, 2:10\u202fpm - ',
     ...]




```python
df = pd.DataFrame({'user_message':messages,'message_date':dates})
# convert message_date to DateTime type
df['message_date'] = pd.to_datetime(df['message_date'], format = '%d/%m/%y, %I:%M %p - ')
df.rename(columns={'message_date':'date'}, inplace=True)
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
</div>




```python
df['month'] = df['date'].dt.month_name()
```


```python
 df['day']= df['date'].dt.day
```


```python
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
</div>




```python
df['hour'] = df['date'].dt.hour
df['minute'] = df['date'].dt.minute
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
</div>




```python
df[df['user'] == 'Zara CR'].shape[0]
```




    0




```python

```

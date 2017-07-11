Test Win7 Browsers
# Observing IME behavior in different browsers and different languages

[Test page https://output.jsbin.com/rezuyuq/1](https://output.jsbin.com/rezuyuq/1)
tested on this site: https://rawgit.com/viller239/b64d5ae3ff110b3536779b5e69e730f4/raw/3e525a1b3fdb473143c7afe17d3010afa3bd00e1/input%2520log.html

## Scenario 1. Win7. Chinese(Simplified, Microsoft Pinyin New Experience Input Style). Z -> Space
Given text `1234` place cursor after `2`
<details><summary>Chrome</summary>

```1.   MutationObserver         'link  print log \n\n \n\[]        <br />
2.   selectionchange          'link  print log \n\n \n\[0,0]     <br />
3.   selectionchange          '1234'                   [2,2]     
1.   keydown                  '1234'                   [2,2]     {"keyCode":229,"key":"Process","code":"KeyZ"}<br />
2.   compositionstart         '1234'                   [2,2]     {"data":""}<br />
3.   compositionupdate        '1234'                   [2,2]     {"data":"z"}<br />
4.   input                    '12z34'                  [2,3]     <br />
5.   MutationObserver         '12z34'                  [2,3]     <br />
6.   selectionchange          '12z34'                  [3,3]     <br />
7.   selectionchange          '12z34'                  [3,3]     <br />
8.   keyup                    '12z34'                  [3,3]     {"keyCode":90,"key":"z","code":"KeyZ"}<br />
1.   keydown                  '12z34'                  [3,3]     {"keyCode":229,"key":"Process","code":"Space"}<br />
2.   compositionupdate        '12z34'                  [2,3]     {"data":"在"}<br />
3.   input                    '12在34'                  [2,3]     <br />
4.   MutationObserver         '12在34'                  [2,3]     <br />
5.   selectionchange          '12在34'                  [3,3]     <br />
6.   selectionchange          '12在34'                  [3,3]     <br />
7.   selectionchange          '12在34'                  [3,3]     <br />
8.   keyup                    '12在34'                  [3,3]     {"keyCode":32,"key":" ","code":"Space"}<br />
9.   compositionend           '12在34'                  [3,3]     {"data":"在"}```<br />
</details>
<details><summary>Firefox</summary>

```1.   MutationObserver         'link print log\n\n\n\n\n[1,1]     <br />
2.   selectionchange          '1234'                   [2,2]     <br />
3.   compositionstart         '1234'                   [2,2]     {"data":"","locale":""}<br />
4.   compositionupdate        '1234'                   [2,2]     {"data":"z","locale":""}<br />
5.   input                    '12z34'                  [3,3]     <br />
6.   MutationObserver         '12z34'                  [3,3]     <br />
7.   selectionchange          '12z34'                  [3,3]     <br />
8.   compositionupdate        '12z34'                  [3,3]     {"data":"在","locale":""}<br />
9.   input                    '12在34'                  [3,3]     <br />
10.  MutationObserver         '12在34'                  [3,3]     <br />
11.  compositionend           '12在34'                  [3,3]     {"data":"在","locale":""}<br />
12.  input                    '12在34'                  [3,3]     <br />
13.  MutationObserver         '12在34'                  [3,3]     <br />```
</details>
<details><summary>IE11</summary>

```1.   MutationObserver         'undefined'              []       <br /> 
2.   selectionchange          'link print log \n\n \n\n[0,0]     <br />
3.   selectionchange          '1234'                   [2,2]     <br />
1.   keydown                  '1234'                   [2,2]     {"keyCode":229,"key":"z"}<br />
2.   compositionstart         '1234'                   [2,2]     {"data":"","locale":"zh-CN"}<br />
3.   compositionupdate        '12z34'                  [3,3]     {"data":"z","locale":"zh-CN"}<br />
4.   MutationObserver         '12z34'                  [3,3]     <br />
5.   keyup                    '12z34'                  [3,3]     {"keyCode":90,"key":"z"}<br />
1.   keydown                  '12z34'                  [3,3]     {"keyCode":229,"key":"Spacebar"}<br />
2.   compositionupdate        '12在34'                  [3,3]     {"data":"在","locale":"zh-CN"}<br />
3.   MutationObserver         '12在34'                  [3,3]     <br />
4.   keyup                    '12在34'                  [3,3]     {"keyCode":32,"key":"Spacebar"}<br />
5.   compositionend           '12在34'                  [3,3]     {"data":"在","locale":"zh-CN"}<br />
6.   selectionchange          '12在34'                  [3,3]     <br />```
</details>

## Scenario 2. Win7. Chinese(Simplified, Microsoft Pinyin New Experience Input Style). R -> E -> Click on the first suggestion
Given text `1234` place cursor after `1`
<details><summary>Chrome</summary>

```1.   MutationObserver         'link  print log \n\n \n\[]        <br />
2.   selectionchange          '1234'                   [1,1]     <br />
1.   keydown                  '1234'                   [1,1]     {"keyCode":229,"key":"Process","code":"KeyR"}<br />
2.   compositionstart         '1234'                   [1,1]     {"data":""}<br />
3.   compositionupdate        '1234'                   [1,1]     {"data":"r"}<br />
4.   input                    '1r234'                  [1,2]     <br />
5.   MutationObserver         '1r234'                  [1,2]     <br />
6.   selectionchange          '1r234'                  [2,2]     <br />
7.   selectionchange          '1r234'                  [2,2]     <br />
8.   keyup                    '1r234'                  [2,2]     {"keyCode":82,"key":"r","code":"KeyR"}<br />
1.   keydown                  '1r234'                  [2,2]     {"keyCode":229,"key":"Process","code":"KeyE"}<br />
2.   compositionupdate        '1r234'                  [1,2]     {"data":"re"}<br />
3.   input                    '1re234'                 [1,3]     <br />
4.   MutationObserver         '1re234'                 [1,3]     <br />
5.   selectionchange          '1re234'                 [3,3]     <br />
6.   selectionchange          '1re234'                 [3,3]     <br />
7.   selectionchange          '1re234'                 [3,3]     <br />
8.   selectionchange          '1re234'                 [3,3]     <br />
9.   keyup                    '1re234'                 [3,3]     {"keyCode":69,"key":"e","code":"KeyE"}<br />
10.  compositionupdate        '1re234'                 [1,3]     {"data":"热"}<br />
11.  input                    '1热234'                  [1,2]     <br />
12.  MutationObserver         '1热234'                  [1,2]     <br />
13.  selectionchange          '1热234'                  [2,2]     <br />
14.  selectionchange          '1热234'                  [2,2]     <br />
15.  selectionchange          '1热234'                  [2,2]     <br />
16.  compositionend           '1热234'                  [2,2]     {"data":"热"}<br />```
</details>
<details><summary>Firefox</summary>

```1.   MutationObserver         'link print log\n\n\n\n\n[1,1]     <br />
2.   selectionchange          '1234'                   [1,1]     <br />
3.   compositionstart         '1234'                   [1,1]     {"data":"","locale":""}<br />
4.   compositionupdate        '1234'                   [1,1]     {"data":"r","locale":""}<br />
5.   input                    '1r234'                  [2,2]     <br />
6.   MutationObserver         '1r234'                  [2,2]     <br />
7.   selectionchange          '1r234'                  [2,2]     <br />
8.   compositionupdate        '1r234'                  [2,2]     {"data":"re","locale":""}<br />
9.   input                    '1re234'                 [3,3]     <br />
10.  MutationObserver         '1re234'                 [3,3]     <br />
11.  selectionchange          '1re234'                 [3,3]     <br />
12.  compositionupdate        '1re234'                 [3,3]     {"data":"热","locale":""}<br />
13.  input                    '1热234'                  [2,2]     <br />
14.  MutationObserver         '1热234'                  [2,2]     <br />
15.  selectionchange          '1热234'                  [2,2]     <br />
16.  compositionend           '1热234'                  [2,2]     {"data":"热","locale":""}<br />
17.  input                    '1热234'                  [2,2]     
18.  MutationObserver         '1热234'                  [2,2]   <br />```  
</details>
<details><summary>IE11</summary>

```1.   MutationObserver         'undefined'              []        <br />
2.   selectionchange          'link print log \n\n \n\n[0,0]     <br />
3.   selectionchange          '1234'                   [1,1]     <br />
1.   keydown                  '1234'                   [1,1]     {"keyCode":229,"key":"r"}<br />
2.   compositionstart         '1234'                   [1,1]     {"data":"","locale":"zh-CN"}<br />
3.   compositionupdate        '1r234'                  [2,2]     {"data":"r","locale":"zh-CN"}<br />
4.   MutationObserver         '1r234'                  [2,2]     <br />
5.   keyup                    '1r234'                  [2,2]     {"keyCode":82,"key":"r"}<br />
1.   keydown                  '1r234'                  [2,2]     {"keyCode":229,"key":"e"}<br />
2.   compositionupdate        '1re234'                 [3,3]     {"data":"re","locale":"zh-CN"}<br />
3.   MutationObserver         '1re234'                 [3,3]     <br />
4.   keyup                    '1re234'                 [3,3]     {"keyCode":69,"key":"e"}<br />
5.   compositionupdate        '1热234'                  [2,2]     {"data":"热","locale":"zh-CN"}<br />
6.   MutationObserver         '1热234'                  [2,2]     <br />
7.   compositionend           '1热234'                  [2,2]     {"data":"热","locale":"zh-CN"}<br />
8.   selectionchange          '1热234'                  [2,2]     <br />```
</details>

## Scenario 3. Win7. Korean. Z -> Space -> Z -> Space
Given text `1234` place cursor after `1`
<details><summary>Chrome</summary>

```1.   MutationObserver         'link  print log \n\n \n\[]        <br />
2.   selectionchange          '1234'                   [1,1]     <br />
1.   keydown                  '1234'                   [1,1]     {"keyCode":229,"key":"Process","code":"KeyZ"}<br />
2.   compositionstart         '1234'                   [1,1]     {"data":""}<br />
3.   compositionupdate        '1234'                   [1,1]     {"data":"ㅋ"}<br />
4.   input                    '1ㅋ234'                  [1,2]     <br />
5.   MutationObserver         '1ㅋ234'                  [1,2]     <br />
6.   keyup                    '1ㅋ234'                  [1,1]     {"keyCode":90,"key":"z","code":"KeyZ"}<br />
7.   selectionchange          '1ㅋ234'                  [1,1]     <br />
8.   selectionchange          '1ㅋ234'                  [1,1]     <br />
1.   keydown                  '1ㅋ234'                  [1,1]     {"keyCode":229,"key":"Process","code":"Space"}<br />
2.   compositionupdate        '1ㅋ234'                  [1,2]     {"data":"ㅋ"}<br />
3.   input                    '1ㅋ234'                  [2,2]     <br />
4.   compositionend           '1ㅋ234'                  [2,2]     {"data":"ㅋ"}<br />
1.   keydown                  '1ㅋ234'                  [2,2]     {"keyCode":32,"key":" ","code":"Space"}<br />
2.   keypress                 '1ㅋ234'                  [2,2]     {"charCode":32,"keyCode":32,"key":" ","code":"Space"}<br />
3.   input                    '1ㅋ 234'                 [3,3]     <br />
4.   MutationObserver         '1ㅋ 234'                 [3,3]     <br />
5.   selectionchange          '1ㅋ 234'                 [3,3]     <br />
6.   selectionchange          '1ㅋ 234'                 [3,3]     <br />
7.   selectionchange          '1ㅋ 234'                 [3,3]     <br />
8.   keyup                    '1ㅋ 234'                 [3,3]     {"keyCode":32,"key":" ","code":"Space"}<br />
1.   keydown                  '1ㅋ 234'                 [3,3]     {"keyCode":229,"key":"Process","code":"KeyZ"}<br />
2.   compositionstart         '1ㅋ 234'                 [3,3]     {"data":""}<br />
3.   compositionupdate        '1ㅋ 234'                 [3,3]     {"data":"ㅋ"}<br />
4.   input                    '1ㅋ ㅋ234'                [3,4]     <br />
5.   MutationObserver         '1ㅋ ㅋ234'                [3,4]     <br />
6.   selectionchange          '1ㅋ ㅋ234'                [3,3]     <br />
7.   selectionchange          '1ㅋ ㅋ234'                [3,3]     <br />
8.   keyup                    '1ㅋ ㅋ234'                [3,3]     {"keyCode":90,"key":"z","code":"KeyZ"}<br />
1.   keydown                  '1ㅋ ㅋ234'                [3,3]     {"keyCode":229,"key":"Process","code":"Space"}<br />
2.   compositionupdate        '1ㅋ ㅋ234'                [3,4]     {"data":"ㅋ"}<br />
3.   input                    '1ㅋ ㅋ234'                [4,4]     <br />
4.   compositionend           '1ㅋ ㅋ234'                [4,4]     {"data":"ㅋ"}<br />
1.   keydown                  '1ㅋ ㅋ234'                [4,4]     {"keyCode":32,"key":" ","code":"Space"}<br />
2.   keypress                 '1ㅋ ㅋ234'                [4,4]     {"charCode":32,"keyCode":32,"key":" ","code":"Space"}<br />
3.   input                    '1ㅋ ㅋ 234'               [5,5]     <br />
4.   MutationObserver         '1ㅋ ㅋ 234'               [5,5]     <br />
5.   selectionchange          '1ㅋ ㅋ 234'               [5,5]     <br />
6.   selectionchange          '1ㅋ ㅋ 234'               [5,5]     <br />
7.   selectionchange          '1ㅋ ㅋ 234'               [5,5]     <br />
8.   keyup                    '1ㅋ ㅋ 234'               [5,5]     {"keyCode":32,"key":" ","code":"Space"}<br />```
</details>
<details><summary>Firefox</summary>

```1.   MutationObserver         'link print log\n\n\n\n\n[1,1]     <br />
2.   selectionchange          '1234'                   [1,1]     <br />
3.   compositionstart         '1234'                   [1,1]     {"data":"","locale":""}<br />
4.   compositionupdate        '1234'                   [1,1]     {"data":"ㅋ","locale":""}<br />
5.   input                    '1ㅋ234'                  [2,2]     <br />
6.   MutationObserver         '1ㅋ234'                  [2,2]     <br />
7.   selectionchange          '1ㅋ234'                  [2,2]     <br />
8.   input                    '1ㅋ234'                  [2,2]     <br />
9.   MutationObserver         '1ㅋ234'                  [2,2]     <br />
10.  MutationObserver         '1ㅋ234'                  [2,2]     <br />
11.  compositionend           '1ㅋ234'                  [2,2]     {"data":"ㅋ","locale":""}<br />
12.  input                    '1ㅋ234'                  [2,2]     <br />
1.   keydown                  '1ㅋ234'                  [2,2]     {"keyCode":32,"key":" ","code":"Space"}<br />
2.   keypress                 '1ㅋ234'                  [2,2]     {"charCode":32,"keyCode":0,"key":" ","code":"Space"}<br />
3.   input                    '1ㅋ 234'                 [3,3]     <br />
4.   MutationObserver         '1ㅋ 234'                 [3,3]     <br />
5.   selectionchange          '1ㅋ 234'                 [3,3]     <br />
6.   keyup                    '1ㅋ 234'                 [3,3]     {"keyCode":32,"key":" ","code":"Space"}<br />
7.   compositionstart         '1ㅋ 234'                 [3,3]     {"data":"","locale":""}<br />
8.   compositionupdate        '1ㅋ 234'                 [3,3]     {"data":"ㅋ","locale":""}<br />
9.   input                    '1ㅋ ㅋ234'                [4,4]     <br />
10.  MutationObserver         '1ㅋ ㅋ234'                [4,4]     <br />
11.  selectionchange          '1ㅋ ㅋ234'                [4,4]     <br />
12.  input                    '1ㅋ ㅋ234'                [4,4]     <br />
13.  MutationObserver         '1ㅋ ㅋ234'                [4,4]     <br />
14.  MutationObserver         '1ㅋ ㅋ234'                [4,4]     <br />
15.  compositionend           '1ㅋ ㅋ234'                [4,4]     {"data":"ㅋ","locale":""}<br />
16.  input                    '1ㅋ ㅋ234'                [4,4]     <br />
1.   keydown                  '1ㅋ ㅋ234'                [4,4]     {"keyCode":32,"key":" ","code":"Space"}<br />
2.   keypress                 '1ㅋ ㅋ234'                [4,4]     {"charCode":32,"keyCode":0,"key":" ","code":"Space"}<br />
3.   input                    '1ㅋ ㅋ 234'               [5,5]     <br />
4.   MutationObserver         '1ㅋ ㅋ 234'               [5,5]     <br />
5.   selectionchange          '1ㅋ ㅋ 234'               [5,5]     <br />
6.   keyup                    '1ㅋ ㅋ 234'               [5,5]     {"keyCode":32,"key":" ","code":"Space"}<br />```
</details>
<details><summary>IE11</summary>

```1.   MutationObserver         'undefined'              []        <br />
2.   selectionchange          'link print log \n\n \n\n[0,0]     <br />
3.   selectionchange          '1234'                   [1,1]     <br />
1.   keydown                  '1ㅋ234'                  [2,2]     {"keyCode":229,"key":"z"}<br />
2.   compositionstart         '1ㅋ234'                  [2,2]     {"data":"ㅋ","locale":"ko-KR"}<br />
3.   selectionchange          '1ㅋ234'                  [1,2]     <br />
4.   compositionupdate        '1ㅋ234'                  [1,2]     {"data":"ㅋ","locale":"ko-KR"}<br />
5.   MutationObserver         '1ㅋ234'                  [1,2]     <br />
6.   keyup                    '1ㅋ234'                  [1,2]     {"keyCode":90,"key":"z"}<br />
1.   keydown                  '1ㅋ234'                  [1,2]     {"keyCode":229,"key":"Spacebar"}<br />
2.   selectionchange          '1ㅋ234'                  [2,2]     <br />
3.   compositionend           '1ㅋ234'                  [2,2]     {"data":"ㅋ","locale":"ko-KR"}<br />
1.   keydown                  '1ㅋ234'                  [2,2]     {"keyCode":32,"key":"Spacebar"}<br />
2.   keypress                 '1ㅋ234'                  [2,2]     {"charCode":32,"keyCode":32,"key":"Spacebar"}<br />
3.   MutationObserver         '1ㅋ 234'                 [3,3]     <br />
4.   keyup                    '1ㅋ 234'                 [3,3]     {"keyCode":32,"key":"Spacebar"}<br />
5.   keyup                    '1ㅋ 234'                 [3,3]     {"keyCode":32,"key":"Spacebar"}<br />
1.   keydown                  '1ㅋ ㅋ234'                [4,4]     {"keyCode":229,"key":"z"}<br />
2.   compositionstart         '1ㅋ ㅋ234'                [4,4]     {"data":"ㅋ","locale":"ko-KR"}<br />
3.   selectionchange          '1ㅋ ㅋ234'                [3,4]     <br />
4.   compositionupdate        '1ㅋ ㅋ234'                [3,4]     {"data":"ㅋ","locale":"ko-KR"}<br />
5.   MutationObserver         '1ㅋ ㅋ234'                [3,4]     <br />
6.   keyup                    '1ㅋ ㅋ234'                [3,4]     {"keyCode":90,"key":"z"}<br />
1.   keydown                  '1ㅋ ㅋ234'                [3,4]     {"keyCode":229,"key":"Spacebar"}<br />
2.   selectionchange          '1ㅋ ㅋ234'                [4,4]     <br />
3.   compositionend           '1ㅋ ㅋ234'                [4,4]     {"data":"ㅋ","locale":"ko-KR"}<br />
1.   keydown                  '1ㅋ ㅋ234'                [4,4]     {"keyCode":32,"key":"Spacebar"}<br />
2.   keypress                 '1ㅋ ㅋ234'                [4,4]     {"charCode":32,"keyCode":32,"key":"Spacebar"}<br />
3.   MutationObserver         '1ㅋ ㅋ 234'               [5,5]     <br />
4.   keyup                    '1ㅋ ㅋ 234'               [5,5]     {"keyCode":32,"key":"Spacebar"}<br />
5.   keyup                    '1ㅋ ㅋ 234'               [5,5]     {"keyCode":32,"key":"Spacebar"}<br />
6.   selectionchange          '1ㅋ ㅋ 234'               [5,5]    <br />```
</details>

## Scenario 4. Win7. Korean. V -> B -> V -> Click outside
Given text `1234` place cursor after `1`
<details><summary>Chrome</summary>

```1.   MutationObserver         'link  print log \n\n \n\[]        <br />
2.   selectionchange          '1234'                   [1,1]     <br />
1.   keydown                  '1234'                   [1,1]     {"keyCode":229,"key":"Process","code":"KeyV"}<br />
2.   compositionstart         '1234'                   [1,1]     {"data":""}<br />
3.   compositionupdate        '1234'                   [1,1]     {"data":"ㅍ"}<br />
4.   input                    '1ㅍ234'                  [1,2]     <br />
5.   MutationObserver         '1ㅍ234'                  [1,2]     <br />
6.   selectionchange          '1ㅍ234'                  [1,1]     <br />
7.   selectionchange          '1ㅍ234'                  [1,1]     <br />
8.   keyup                    '1ㅍ234'                  [1,1]     {"keyCode":86,"key":"v","code":"KeyV"}<br />
1.   keydown                  '1ㅍ234'                  [1,1]     {"keyCode":229,"key":"Process","code":"KeyB"}<br />
2.   compositionupdate        '1ㅍ234'                  [1,2]     {"data":"퓨"}<br />
3.   input                    '1퓨234'                  [1,2]     <br />
4.   MutationObserver         '1퓨234'                  [1,2]     <br />
5.   selectionchange          '1퓨234'                  [1,1]     <br />
6.   selectionchange          '1퓨234'                  [1,1]     <br />
7.   selectionchange          '1퓨234'                  [1,1]     <br />
8.   keyup                    '1퓨234'                  [1,1]     {"keyCode":66,"key":"b","code":"KeyB"}<br />
1.   keydown                  '1퓨234'                  [1,1]     {"keyCode":229,"key":"Process","code":"KeyV"}<br />
2.   compositionupdate        '1퓨234'                  [1,2]     {"data":"픂"}<br />
3.   input                    '1픂234'                  [1,2]     <br />
4.   MutationObserver         '1픂234'                  [1,2]     <br />
5.   selectionchange          '1픂234'                  [1,1]     <br />
6.   selectionchange          '1픂234'                  [1,1]     <br />
7.   selectionchange          '1픂234'                  [1,1]     <br />
8.   keyup                    '1픂234'                  [1,1]     {"keyCode":86,"key":"v","code":"KeyV"}<br />
9.   compositionupdate        '1픂234'                  [1,2]     {"data":""}<br />
10.  input                    '1234'                   [1,1]     <br />
11.  MutationObserver         '1234'                   [1,1]     <br />
12.  compositionend           '1234'                   [1,1]     {"data":""}<br />
13.  input                    '1픂234'                  [2,2]     <br />
14.  MutationObserver         '1픂234'                  [2,2]     <br />
15.  selectionchange          'link  print log \n\n \n\[0,0]     <br />
16.  selectionchange          'link  print log \n\n \n\[0,0]     <br />
17.  selectionchange          'link  print log \n\n \n\[0,0] <br />```
</details>
<details><summary>Firefox</summary>

```1.   MutationObserver         'link print log\n\n\n\n\n[1,1]     <br />
2.   selectionchange          '1234'                   [0,0]     <br />
3.   selectionchange          '1234'                   [1,1]     <br />
4.   compositionstart         '1234'                   [1,1]     {"data":"","locale":""}<br />
5.   compositionupdate        '1234'                   [1,1]     {"data":"ㅍ","locale":""}<br />
6.   input                    '1ㅍ234'                  [2,2]     <br />
7.   MutationObserver         '1ㅍ234'                  [2,2]     <br />
8.   selectionchange          '1ㅍ234'                  [2,2]     <br />
9.   compositionupdate        '1ㅍ234'                  [2,2]     {"data":"퓨","locale":""}<br />
10.  input                    '1퓨234'                  [2,2]     <br />
11.  MutationObserver         '1퓨234'                  [2,2]     <br />
12.  compositionupdate        '1퓨234'                  [2,2]     {"data":"픂","locale":""}<br />
13.  input                    '1픂234'                  [2,2]     <br />
14.  MutationObserver         '1픂234'                  [2,2]     <br />
15.  compositionend           '1픂234'                  [2,2]     {"data":"픂","locale":""}<br />
16.  input                    '1픂234'                  [2,2]     <br />
17.  MutationObserver         '1픂234'                  [2,2]     <br />
18.  selectionchange          'link print log\n\n\n\n\n[5,5]     <br />```
</details>
<details><summary>IE11</summary>

```1.   MutationObserver         'undefined'              []        <br />
2.   selectionchange          'link print log \n\n \n\n[0,0]     <br />
3.   selectionchange          '1234'                   [1,1]     <br />
1.   keydown                  '1ㅍ234'                  [2,2]     {"keyCode":229,"key":"v"}<br />
2.   compositionstart         '1ㅍ234'                  [2,2]     {"data":"ㅍ","locale":"ko-KR"}<br />
3.   selectionchange          '1ㅍ234'                  [1,2]     <br />
4.   compositionupdate        '1ㅍ234'                  [1,2]     {"data":"ㅍ","locale":"ko-KR"}<br />
5.   MutationObserver         '1ㅍ234'                  [1,2]     <br />
6.   keyup                    '1ㅍ234'                  [1,2]     {"keyCode":86,"key":"v"}<br />
1.   keydown                  '1ㅍ234'                  [1,2]     {"keyCode":229,"key":"b"}<br />
2.   selectionchange          '1퓨234'                  [1,2]     <br />
3.   compositionupdate        '1퓨234'                  [1,2]     {"data":"퓨","locale":"ko-KR"}<br />
4.   MutationObserver         '1퓨234'                  [1,2]     <br />
5.   keyup                    '1퓨234'                  [1,2]     {"keyCode":66,"key":"b"}<br />
1.   keydown                  '1퓨234'                  [1,2]     {"keyCode":229,"key":"v"}<br />
2.   selectionchange          '1픂234'                  [1,2]     <br />
3.   compositionupdate        '1픂234'                  [1,2]     {"data":"픂","locale":"ko-KR"}<br />
4.   MutationObserver         '1픂234'                  [1,2]     <br />
5.   keyup                    '1픂234'                  [1,2]     {"keyCode":86,"key":"v"}<br />
6.   selectionchange          '1픂234'                  [2,2]     <br />
7.   compositionupdate        '1픂234'                  [2,2]     {"data":"","locale":"ko-KR"}<br />
8.   selectionchange          '1픂234'                  [2,2]     <br />
9.   compositionend           'link print log \n\n \n\n[5,5]     {"data":"","locale":"ko-KR"}<br />```
</details>

## Scenario 5. Win7. Korean. Q -> W -> E -> Enter
Given text `1234` place cursor after `4`
<details><summary>Chrome</summary>

```1.   MutationObserver         'link  print log \n\n \n\[]        <br />
2.   selectionchange          '1234'                   [4,4]     <br />
1.   keydown                  '1234'                   [4,4]     {"keyCode":229,"key":"Process","code":"KeyQ"}<br />
2.   compositionstart         '1234'                   [4,4]     {"data":""}<br />
3.   compositionupdate        '1234'                   [4,4]     {"data":"ㅂ"}<br />
4.   input                    '1234ㅂ'                  [4,5]     <br />
5.   MutationObserver         '1234ㅂ'                  [4,5]     <br />
6.   selectionchange          '1234ㅂ'                  [4,4]     <br />
7.   selectionchange          '1234ㅂ'                  [4,4]     <br />
8.   keyup                    '1234ㅂ'                  [4,4]     {"keyCode":81,"key":"q","code":"KeyQ"}<br />
1.   keydown                  '1234ㅂ'                  [4,4]     {"keyCode":229,"key":"Process","code":"KeyW"}<br />
2.   compositionupdate        '1234ㅂ'                  [4,5]     {"data":"ㅂ"}<br />
3.   input                    '1234ㅂ'                  [5,5]     <br />
4.   compositionend           '1234ㅂ'                  [5,5]     {"data":"ㅂ"}<br />
5.   compositionstart         '1234ㅂ'                  [5,5]     {"data":""}<br />
6.   compositionupdate        '1234ㅂ'                  [5,5]     {"data":"ㅈ"}<br />
7.   input                    '1234ㅂㅈ'                 [5,6]     <br />
8.   MutationObserver         '1234ㅂㅈ'                 [5,6]     <br />
9.   selectionchange          '1234ㅂㅈ'                 [5,5]     <br />
10.  selectionchange          '1234ㅂㅈ'                 [5,5]     <br />
11.  selectionchange          '1234ㅂㅈ'                 [5,5]     <br />
12.  selectionchange          '1234ㅂㅈ'                 [5,5]     <br />
13.  keyup                    '1234ㅂㅈ'                 [5,5]     {"keyCode":87,"key":"w","code":"KeyW"}<br />
1.   keydown                  '1234ㅂㅈ'                 [5,5]     {"keyCode":229,"key":"Process","code":"KeyE"}<br />
2.   compositionupdate        '1234ㅂㅈ'                 [5,6]     {"data":"ㅈ"}<br />
3.   input                    '1234ㅂㅈ'                 [6,6]     <br />
4.   compositionend           '1234ㅂㅈ'                 [6,6]     {"data":"ㅈ"}<br />
5.   compositionstart         '1234ㅂㅈ'                 [6,6]     {"data":""}<br />
6.   compositionupdate        '1234ㅂㅈ'                 [6,6]     {"data":"ㄷ"}<br />
7.   input                    '1234ㅂㅈㄷ'                [6,7]     <br />
8.   MutationObserver         '1234ㅂㅈㄷ'                [6,7]     <br />
9.   selectionchange          '1234ㅂㅈㄷ'                [6,6]     <br />
10.  selectionchange          '1234ㅂㅈㄷ'                [6,6]     <br />
11.  selectionchange          '1234ㅂㅈㄷ'                [6,6]     <br />
12.  selectionchange          '1234ㅂㅈㄷ'                [6,6]     <br />
13.  keyup                    '1234ㅂㅈㄷ'                [6,6]     {"keyCode":69,"key":"e","code":"KeyE"}<br />
1.   keydown                  '1234ㅂㅈㄷ'                [6,6]     {"keyCode":229,"key":"Process","code":"Enter"}<br />
2.   compositionupdate        '1234ㅂㅈㄷ'                [6,7]     {"data":"ㄷ"}<br />
3.   input                    '1234ㅂㅈㄷ'                [7,7]     <br />
4.   compositionend           '1234ㅂㅈㄷ'                [7,7]     {"data":"ㄷ"}<br />
1.   keydown                  '1234ㅂㅈㄷ'                [7,7]     {"keyCode":13,"key":"Enter","code":"Enter"}<br />
2.   keypress                 '1234ㅂㅈㄷ'                [7,7]     {"charCode":13,"keyCode":13,"key":"Enter","code":"Enter"}<br />
3.   input                    '1234ㅂㅈㄷ\n\n'            [0,0]     <br />
4.   MutationObserver         '1234ㅂㅈㄷ\n\n'            [0,0]     <br />
5.   selectionchange          '1234ㅂㅈㄷ\n\n'            [0,0]     <br />
6.   selectionchange          '1234ㅂㅈㄷ\n\n'            [0,0]     <br />
7.   selectionchange          '1234ㅂㅈㄷ\n\n'            [0,0]     <br />
8.   keyup                    '1234ㅂㅈㄷ\n\n'            [0,0]     {"keyCode":13,"key":"Enter","code":"Enter"}<br />```
</details>
<details><summary>Firefox</summary>

```1.   MutationObserver         'link print log\n\n\n\n\n[1,1]     <br />
2.   selectionchange          '1234'                   [4,4]     <br />
3.   compositionstart         '1234'                   [4,4]     {"data":"","locale":""}<br />
4.   compositionupdate        '1234'                   [4,4]     {"data":"ㅂ","locale":""}<br />
5.   input                    '1234ㅂ'                  [5,5]     <br />
6.   MutationObserver         '1234ㅂ'                  [5,5]     <br />
7.   selectionchange          '1234ㅂ'                  [5,5]     <br />
8.   input                    '1234ㅂ'                  [5,5]     <br />
9.   MutationObserver         '1234ㅂ'                  [5,5]     <br />
10.  MutationObserver         '1234ㅂ'                  [5,5]     <br />
11.  compositionend           '1234ㅂ'                  [5,5]     {"data":"ㅂ","locale":""}<br />
12.  input                    '1234ㅂ'                  [5,5]     <br />
13.  compositionstart         '1234ㅂ'                  [5,5]     {"data":"","locale":""}<br />
14.  compositionupdate        '1234ㅂ'                  [5,5]     {"data":"ㅈ","locale":""}<br />
15.  input                    '1234ㅂㅈ'                 [6,6]     <br />
16.  MutationObserver         '1234ㅂㅈ'                 [6,6]     <br />
17.  selectionchange          '1234ㅂㅈ'                 [6,6]     <br />
18.  input                    '1234ㅂㅈ'                 [6,6]     <br />
19.  MutationObserver         '1234ㅂㅈ'                 [6,6]     <br />
20.  MutationObserver         '1234ㅂㅈ'                 [6,6]     <br />
21.  compositionend           '1234ㅂㅈ'                 [6,6]     {"data":"ㅈ","locale":""}<br />
22.  input                    '1234ㅂㅈ'                 [6,6]     <br />
23.  compositionstart         '1234ㅂㅈ'                 [6,6]     {"data":"","locale":""}<br />
24.  compositionupdate        '1234ㅂㅈ'                 [6,6]     {"data":"ㄷ","locale":""}<br />
25.  input                    '1234ㅂㅈㄷ'                [7,7]     <br />
26.  MutationObserver         '1234ㅂㅈㄷ'                [7,7]     <br />
27.  selectionchange          '1234ㅂㅈㄷ'                [7,7]     <br />
28.  input                    '1234ㅂㅈㄷ'                [7,7]     <br />
29.  MutationObserver         '1234ㅂㅈㄷ'                [7,7]     <br />
30.  MutationObserver         '1234ㅂㅈㄷ'                [7,7]     <br />
31.  compositionend           '1234ㅂㅈㄷ'                [7,7]     {"data":"ㄷ","locale":""}<br />
32.  input                    '1234ㅂㅈㄷ'                [7,7]     <br />
1.   keydown                  '1234ㅂㅈㄷ'                [7,7]     {"keyCode":13,"key":"Enter","code":"Enter"}<br />
2.   keypress                 '1234ㅂㅈㄷ'                [7,7]     {"charCode":0,"keyCode":13,"key":"Enter","code":"Enter"}<br />
3.   input                    '1234ㅂㅈㄷ\n\n'            [2,2]     <br />
4.   MutationObserver         '1234ㅂㅈㄷ\n\n'            [2,2]     <br />
5.   selectionchange          '1234ㅂㅈㄷ\n\n'            [2,2]     <br />
6.   keyup                    '1234ㅂㅈㄷ\n\n'            [2,2]     {"keyCode":13,"key":"Enter","code":"Enter"}```<br />
</details>
<details><summary>IE11</summary>

```1.   MutationObserver         'undefined'              []        <br />
2.   selectionchange          'link print log \n\n \n\n[0,0]     <br />
3.   selectionchange          '1234'                   [4,4]     <br />
1.   keydown                  '1234ㅂ'                  [5,5]     {"keyCode":229,"key":"q"}<br />
2.   compositionstart         '1234ㅂ'                  [5,5]     {"data":"ㅂ","locale":"ko-KR"}<br />
3.   selectionchange          '1234ㅂ'                  [4,5]     <br />
4.   compositionupdate        '1234ㅂ'                  [4,5]     {"data":"ㅂ","locale":"ko-KR"}<br />
5.   MutationObserver         '1234ㅂ'                  [4,5]     <br />
6.   keyup                    '1234ㅂ'                  [4,5]     {"keyCode":81,"key":"q"}<br />
1.   keydown                  '1234ㅂ'                  [4,5]     {"keyCode":229,"key":"w"}<br />
2.   selectionchange          '1234ㅂ'                  [5,5]     <br />
3.   compositionend           '1234ㅂㅈ'                 [6,6]     {"data":"ㅂ","locale":"ko-KR"}<br />
4.   compositionstart         '1234ㅂㅈ'                 [6,6]     {"data":"ㅈ","locale":"ko-KR"}<br />
5.   selectionchange          '1234ㅂㅈ'                 [5,6]     <br />
6.   compositionupdate        '1234ㅂㅈ'                 [5,6]     {"data":"ㅈ","locale":"ko-KR"}<br />
7.   MutationObserver         '1234ㅂㅈ'                 [5,6]     <br />
8.   keyup                    '1234ㅂㅈ'                 [5,6]     {"keyCode":87,"key":"w"}<br />
1.   keydown                  '1234ㅂㅈ'                 [5,6]     {"keyCode":229,"key":"e"}<br />
2.   selectionchange          '1234ㅂㅈ'                 [6,6]     <br />
3.   compositionend           '1234ㅂㅈㄷ'                [7,7]     {"data":"ㅈ","locale":"ko-KR"}<br />
4.   compositionstart         '1234ㅂㅈㄷ'                [7,7]     {"data":"ㄷ","locale":"ko-KR"}<br />
5.   selectionchange          '1234ㅂㅈㄷ'                [6,7]     <br />
6.   compositionupdate        '1234ㅂㅈㄷ'                [6,7]     {"data":"ㄷ","locale":"ko-KR"}<br />
7.   MutationObserver         '1234ㅂㅈㄷ'                [6,7]     <br />
8.   keyup                    '1234ㅂㅈㄷ'                [6,7]     {"keyCode":69,"key":"e"}<br />
1.   keydown                  '1234ㅂㅈㄷ'                [6,7]     {"keyCode":229,"key":"Enter"}<br />
2.   selectionchange          '1234ㅂㅈㄷ'                [7,7]     <br />
3.   compositionend           '1234ㅂㅈㄷ'                [7,7]     {"data":"ㄷ","locale":"ko-KR"}<br />
1.   keydown                  '1234ㅂㅈㄷ'                [7,7]     {"keyCode":13,"key":"Enter"}<br />
2.   keypress                 '1234ㅂㅈㄷ'                [7,7]     {"charCode":13,"keyCode":13,"key":"Enter"}<br />
3.   MutationObserver         '1234ㅂㅈㄷ'                [0,0]     <br />
4.   keyup                    '1234ㅂㅈㄷ'                [0,0]     {"keyCode":13,"key":"Enter"}<br />
5.   keyup                    '1234ㅂㅈㄷ'                [0,0]     {"keyCode":13,"key":"Enter"}<br />
6.   selectionchange          '1234ㅂㅈㄷ'                [0,0]    <br />```

</details>

## Scenario 6. Win7. JP Google IME. S -> A -> K -> U -> R -> A -> Space -> Click outside
Given text `1234` place cursor after `4`
<details><summary>Chrome</summary>

```1.   MutationObserver         'link  print log \n\n \n\[]        <br />
2.   selectionchange          '1234'                   [4,4]     <br />
1.   keydown                  '1234'                   [4,4]     {"keyCode":229,"key":"Process","code":"KeyS"}<br />
2.   compositionstart         '1234'                   [4,4]     {"data":""}<br />
3.   compositionupdate        '1234'                   [4,4]     {"data":"ｓ"}<br />
4.   input                    '1234ｓ'                  [4,5]     <br />
5.   MutationObserver         '1234ｓ'                  [4,5]     <br />
6.   selectionchange          '1234ｓ'                  [5,5]     <br />
7.   selectionchange          '1234ｓ'                  [5,5]     <br />
8.   keyup                    '1234ｓ'                  [5,5]     {"keyCode":83,"key":"s","code":"KeyS"}<br />
1.   keydown                  '1234ｓ'                  [5,5]     {"keyCode":229,"key":"Process","code":"KeyA"}<br />
2.   compositionupdate        '1234ｓ'                  [4,5]     {"data":"さ"}<br />
3.   input                    '1234さ'                  [4,5]     <br />
4.   MutationObserver         '1234さ'                  [4,5]     <br />
5.   selectionchange          '1234さ'                  [5,5]     <br />
6.   selectionchange          '1234さ'                  [5,5]     <br />
7.   selectionchange          '1234さ'                  [5,5]     <br />
8.   keyup                    '1234さ'                  [5,5]     {"keyCode":65,"key":"a","code":"KeyA"}<br />
1.   keydown                  '1234さ'                  [5,5]     {"keyCode":229,"key":"Process","code":"KeyK"}<br />
2.   compositionupdate        '1234さ'                  [4,5]     {"data":"さｋ"}<br />
3.   input                    '1234さｋ'                 [4,6]     <br />
4.   MutationObserver         '1234さｋ'                 [4,6]     <br />
5.   selectionchange          '1234さｋ'                 [6,6]     <br />
6.   selectionchange          '1234さｋ'                 [6,6]     <br />
7.   selectionchange          '1234さｋ'                 [6,6]     <br />
8.   selectionchange          '1234さｋ'                 [6,6]     <br />
9.   keyup                    '1234さｋ'                 [6,6]     {"keyCode":75,"key":"k","code":"KeyK"}<br />
1.   keydown                  '1234さｋ'                 [6,6]     {"keyCode":229,"key":"Process","code":"KeyU"}<br />
2.   compositionupdate        '1234さｋ'                 [4,6]     {"data":"さく"}<br />
3.   input                    '1234さく'                 [4,6]     <br />
4.   MutationObserver         '1234さく'                 [4,6]     <br />
5.   selectionchange          '1234さく'                 [6,6]     <br />
6.   selectionchange          '1234さく'                 [6,6]     <br />
7.   selectionchange          '1234さく'                 [6,6]     <br />
8.   keyup                    '1234さく'                 [6,6]     {"keyCode":85,"key":"u","code":"KeyU"}<br />
1.   keydown                  '1234さく'                 [6,6]     {"keyCode":229,"key":"Process","code":"KeyR"}<br />
2.   compositionupdate        '1234さく'                 [4,6]     {"data":"さくｒ"}<br />
3.   input                    '1234さくｒ'                [4,7]     <br />
4.   MutationObserver         '1234さくｒ'                [4,7]     <br />
5.   selectionchange          '1234さくｒ'                [7,7]     <br />
6.   selectionchange          '1234さくｒ'                [7,7]     <br />
7.   selectionchange          '1234さくｒ'                [7,7]     <br />
8.   selectionchange          '1234さくｒ'                [7,7]     <br />
9.   keyup                    '1234さくｒ'                [7,7]     {"keyCode":82,"key":"r","code":"KeyR"}<br />
1.   keydown                  '1234さくｒ'                [7,7]     {"keyCode":229,"key":"Process","code":"KeyA"}<br />
2.   compositionupdate        '1234さくｒ'                [4,7]     {"data":"さくら"}<br />
3.   input                    '1234さくら'                [4,7]     <br />
4.   MutationObserver         '1234さくら'                [4,7]     <br />
5.   selectionchange          '1234さくら'                [7,7]     <br />
6.   selectionchange          '1234さくら'                [7,7]     <br />
7.   selectionchange          '1234さくら'                [7,7]     <br />
8.   selectionchange          '1234さくら'                [7,7]     <br />
9.   keyup                    '1234さくら'                [7,7]     {"keyCode":65,"key":"a","code":"KeyA"}<br />
1.   keydown                  '1234さくら'                [7,7]     {"keyCode":229,"key":"Process","code":"Space"}<br />
2.   compositionupdate        '1234さくら'                [4,7]     {"data":"桜"}<br />
3.   input                    '1234桜'                  [4,5]     <br />
4.   MutationObserver         '1234桜'                  [4,5]     <br />
5.   selectionchange          '1234桜'                  [5,5]     <br />
6.   selectionchange          '1234桜'                  [5,5]     <br />
7.   selectionchange          '1234桜'                  [5,5]     <br />
8.   keyup                    '1234桜'                  [5,5]     {"keyCode":32,"key":" ","code":"Space"}<br />
9.   compositionend           '1234桜'                  [5,5]     {"data":"桜"}<br />
10.  selectionchange          'link  print log \n\n \n\[0,0]   <br />```
</details>
<details><summary>Firefox</summary>

```1.   MutationObserver         'link print log\n\n\n\n\n[1,1]     <br />
2.   selectionchange          '1234'                   [4,4]     <br />
3.   compositionstart         '1234'                   [4,4]     {"data":"","locale":""}<br />
4.   compositionupdate        '1234'                   [4,4]     {"data":"ｓ","locale":""}<br />
5.   input                    '1234ｓ'                  [5,5]     <br />
6.   MutationObserver         '1234ｓ'                  [5,5]     <br />
7.   selectionchange          '1234ｓ'                  [5,5]     <br />
8.   compositionupdate        '1234ｓ'                  [5,5]     {"data":"さ","locale":""}<br />
9.   input                    '1234さ'                  [5,5]     <br />
10.  MutationObserver         '1234さ'                  [5,5]     <br />
11.  compositionupdate        '1234さ'                  [5,5]     {"data":"さｋ","locale":""}<br />
12.  input                    '1234さｋ'                 [6,6]     <br />
13.  MutationObserver         '1234さｋ'                 [6,6]     <br />
14.  selectionchange          '1234さｋ'                 [6,6]     <br />
15.  compositionupdate        '1234さｋ'                 [6,6]     {"data":"さく","locale":""}<br />
16.  input                    '1234さく'                 [6,6]     <br />
17.  MutationObserver         '1234さく'                 [6,6]     <br />
18.  compositionupdate        '1234さく'                 [6,6]     {"data":"さくｒ","locale":""}<br />
19.  input                    '1234さくｒ'                [7,7]     <br />
20.  MutationObserver         '1234さくｒ'                [7,7]     <br />
21.  selectionchange          '1234さくｒ'                [7,7]     <br />
22.  compositionupdate        '1234さくｒ'                [7,7]     {"data":"さくら","locale":""}<br />
23.  input                    '1234さくら'                [7,7]     <br />
24.  MutationObserver         '1234さくら'                [7,7]     <br />
25.  compositionupdate        '1234さくら'                [7,7]     {"data":"桜","locale":""}<br />
26.  input                    '1234桜'                  [5,5]     <br />
27.  MutationObserver         '1234桜'                  [5,5]     <br />
28.  selectionchange          '1234桜'                  [5,5]     <br />
29.  compositionend           '1234桜'                  [5,5]     {"data":"桜","locale":""}<br />
30.  input                    '1234桜'                  [5,5]     <br />
31.  MutationObserver         '1234桜'                  [5,5]     <br />```
</details>
<details><summary>IE11</summary>

```1.   MutationObserver         'undefined'              []        <br />
2.   selectionchange          'link print log \n\n \n\n[0,0]     <br />
3.   selectionchange          '1234'                   [4,4]     <br />
1.   keydown                  '1234'                   [4,4]     {"keyCode":229,"key":"s"}<br />
2.   compositionstart         '1234'                   [4,4]     {"data":"","locale":"ja-JP"}<br />
3.   selectionchange          '1234ｓ'                  [5,5]     <br />
4.   compositionupdate        '1234ｓ'                  [5,5]     {"data":"ｓ","locale":"ja-JP"}<br />
5.   MutationObserver         '1234ｓ'                  [5,5]     <br />
6.   keyup                    '1234ｓ'                  [5,5]     {"keyCode":83,"key":"s"}<br />
1.   keydown                  '1234ｓ'                  [5,5]     {"keyCode":229,"key":"a"}<br />
2.   compositionupdate        '1234さ'                  [5,5]     {"data":"さ","locale":"ja-JP"}<br />
3.   MutationObserver         '1234さ'                  [5,5]     <br />
4.   keyup                    '1234さ'                  [5,5]     {"keyCode":65,"key":"a"}<br />
1.   keydown                  '1234さ'                  [5,5]     {"keyCode":229,"key":"k"}<br />
2.   compositionupdate        '1234さｋ'                 [6,6]     {"data":"さｋ","locale":"ja-JP"}<br />
3.   MutationObserver         '1234さｋ'                 [6,6]     <br />
4.   keyup                    '1234さｋ'                 [6,6]     {"keyCode":75,"key":"k"}<br />
1.   keydown                  '1234さｋ'                 [6,6]     {"keyCode":229,"key":"u"}<br />
2.   compositionupdate        '1234さく'                 [6,6]     {"data":"さく","locale":"ja-JP"}<br />
3.   MutationObserver         '1234さく'                 [6,6]     <br />
4.   keyup                    '1234さく'                 [6,6]     {"keyCode":85,"key":"u"}<br />
1.   keydown                  '1234さく'                 [6,6]     {"keyCode":229,"key":"r"}<br />
2.   compositionupdate        '1234さくｒ'                [7,7]     {"data":"さくｒ","locale":"ja-JP"}<br />
3.   MutationObserver         '1234さくｒ'                [7,7]     <br />
4.   keyup                    '1234さくｒ'                [7,7]     {"keyCode":82,"key":"r"}<br />
1.   keydown                  '1234さくｒ'                [7,7]     {"keyCode":229,"key":"a"}<br />
2.   compositionupdate        '1234さくら'                [7,7]     {"data":"さくら","locale":"ja-JP"}<br />
3.   MutationObserver         '1234さくら'                [7,7]     <br />
4.   keyup                    '1234さくら'                [7,7]     {"keyCode":65,"key":"a"}<br />
1.   keydown                  '1234さくら'                [7,7]     {"keyCode":229,"key":"Spacebar"}<br />
2.   compositionupdate        '1234桜'                  [5,5]     {"data":"桜","locale":"ja-JP"}<br />
3.   MutationObserver         '1234桜'                  [5,5]     <br />
4.   keyup                    '1234桜'                  [5,5]     {"keyCode":32,"key":"Spacebar"}<br />
5.   compositionend           '1234桜'                  [5,5]     {"data":"桜","locale":"ja-JP"}<br />
6.   selectionchange          '1234桜'                  [5,5]     <br />```
</details>

test win7 browsers
# Observing IME behavior in different browsers and different languages

[Test page https://output.jsbin.com/rezuyuq/1](https://output.jsbin.com/rezuyuq/1)



## Scenario 1. Win10. Chinese(Simplified, China). Z -> Space
Given text `1234` place cursor after `1`

<details><summary>Chrome</summary>

```
1.   selectionchange          '1234'                   [1,1]     
1.   keydown                  '1234'                   [1,1]     {"keyCode":229,"key":"Process","code":"KeyZ"}
2.   compositionstart         '1234'                   [1,1]     {"data":""}
3.   compositionupdate        '1234'                   [1,1]     {"data":"z"}
4.   input                    '1z234'                  [1,2]     
5.   MutationObserver         '1z234'                  [1,2]     
5.   selectionchange          '1z234'                  [2,2]     
6.   selectionchange          '1z234'                  [2,2]     
7.   compositionupdate        '1z234'                  [1,2]     {"data":"z"}
8.   input                    '1z234'                  [1,2]     
9.   selectionchange          '1z234'                  [2,2]     
10.  selectionchange          '1z234'                  [2,2]     
11.  selectionchange          '1z234'                  [2,2]     
12.  selectionchange          '1z234'                  [2,2]     
13.  keyup                    '1z234'                  [2,2]     {"keyCode":229,"key":"Process","code":"KeyZ"}
1.   keydown                  '1z234'                  [2,2]     {"keyCode":229,"key":"Process","code":"Space"}
2.   compositionupdate        '1z234'                  [1,2]     {"data":"在"}
3.   input                    '1在234'                  [1,2]     
4.   MutationObserver         '1在234'                  [1,2]     
4.   selectionchange          '1在234'                  [2,2]     
5.   selectionchange          '1在234'                  [2,2]     
6.   selectionchange          '1在234'                  [2,2]     
7.   compositionupdate        '1在234'                  [1,2]     {"data":"在"}
8.   input                    '1在234'                  [1,2]     
9.   compositionupdate        '1在234'                  [1,2]     {"data":"在"}
10.  input                    '1在234'                  [2,2]     
11.  compositionend           '1在234'                  [2,2]     {"data":"在"}
12.  selectionchange          '1在234'                  [2,2]     
13.  selectionchange          '1在234'                  [2,2]     
14.  selectionchange          '1在234'                  [2,2]     
15.  selectionchange          '1在234'                  [2,2]     
16.  selectionchange          '1在234'                  [2,2]     
17.  selectionchange          '1在234'                  [2,2]     
18.  keyup                    '1在234'                  [2,2]     {"keyCode":229,"key":"Process","code":"Space"}
```
</details>
<details><summary>Firefox</summary>

```
1.   selectionchange          '1234'                   [1,1]     
2.   compositionstart         '1234'                   [1,1]     {"data":"","locale":""}
3.   compositionupdate        '1234'                   [1,1]     {"data":"z","locale":""}
4.   input                    '1z234'                  [2,2]     
5.   MutationObserver         '1z234'                  [2,2]     
5.   selectionchange          '1z234'                  [2,2]     
6.   compositionupdate        '1z234'                  [2,2]     {"data":"在","locale":""}
7.   input                    '1在234'                  [2,2]     
8.   MutationObserver         '1在234'                  [2,2]     
8.   MutationObserver         '1在234'                  [2,2]     
8.   compositionend           '1在234'                  [2,2]     {"data":"在","locale":""}
9.   input                    '1在234'                  [2,2]     
10.  keyup                    '1在234'                  [2,2]     {"keyCode":32,"key":" ","code":"Space"}
```
</details>
<details><summary>Edge</summary>

```
6.   selectionchange          '1234'                   [1,1]     
1.   keydown                  '1234'                   [1,1]     {"keyCode":229,"key":"Unidentified"}
2.   compositionstart         '1234'                   [1,1]     {"data":"","locale":"zh-Hans-CN"}
3.   compositionupdate        '1z234'                  [2,2]     {"data":"z","locale":"zh-Hans-CN"}
4.   MutationObserver         '1z234'                  [2,2]     
4.   input                    '1z234'                  [2,2]     
5.   selectionchange          '1z234'                  [2,2]     
6.   keyup                    '1z234'                  [2,2]     {"keyCode":90,"key":"z"}
7.   compositionupdate        '1在234'                  [2,2]     {"data":"在","locale":"zh-Hans-CN"}
8.   MutationObserver         '1在234'                  [2,2]     
8.   input                    '1在234'                  [2,2]     
9.   selectionchange          '1在234'                  [2,2]     
10.  compositionend           '1在234'                  [2,2]     {"data":"在","locale":"zh-Hans-CN"}
11.  input                    '1在234'                  [2,2]     
```
</details>
<details><summary>IE11</summary>

```
2.   selectionchange          '1234'                   [1,1]     
1.   keydown                  '1234'                   [1,1]     {"keyCode":229,"key":"z"}
2.   compositionstart         '1234'                   [1,1]     {"data":"","locale":"zh-Hans-CN"}
3.   compositionupdate        '1z234'                  [2,2]     {"data":"z","locale":"zh-Hans-CN"}
4.   MutationObserver         '1z234'                  [2,2]     
4.   keyup                    '1z234'                  [2,2]     {"keyCode":90,"key":"z"}
5.   compositionupdate        '1在234'                  [2,2]     {"data":"在","locale":"zh-Hans-CN"}
6.   MutationObserver         '1在234'                  [2,2]     
6.   compositionend           '1在234'                  [2,2]     {"data":"在","locale":"zh-Hans-CN"}
7.   selectionchange          '1在234'                  [2,2]     
```
</details>



## Scenario 2. Win10. Chinese(Simplified, China). R -> E -> Click on the first suggestion
Given text `1234` place cursor after `1`

<details><summary>Chrome</summary>

```
1.   selectionchange          '1234'                   [1,1]
1.   keydown                  '1234'                   [1,1]     {"keyCode":229,"key":"Process","code":"KeyR"}
2.   compositionstart         '1234'                   [1,1]     {"data":""}
3.   compositionupdate        '1234'                   [1,1]     {"data":"r"}
4.   input                    '1r234'                  [1,2]
5.   MutationObserver         '1r234'                  [1,2]
5.   compositionupdate        '1r234'                  [1,2]     {"data":"r"}
6.   input                    '1r234'                  [1,2]
7.   selectionchange          '1r234'                  [2,2]
8.   selectionchange          '1r234'                  [2,2]
9.   selectionchange          '1r234'                  [2,2]
10.  selectionchange          '1r234'                  [2,2]
11.  selectionchange          '1r234'                  [2,2]
12.  selectionchange          '1r234'                  [2,2]
13.  keyup                    '1r234'                  [2,2]     {"keyCode":229,"key":"Process","code":"KeyR"}
1.   keydown                  '1r234'                  [2,2]     {"keyCode":229,"key":"Process","code":"KeyE"}
2.   compositionupdate        '1r234'                  [1,2]     {"data":"re"}
3.   input                    '1re234'                 [1,3]
4.   MutationObserver         '1re234'                 [1,3]
4.   selectionchange          '1re234'                 [3,3]
5.   selectionchange          '1re234'                 [3,3]
6.   selectionchange          '1re234'                 [3,3]
7.   selectionchange          '1re234'                 [3,3]
8.   compositionupdate        '1re234'                 [1,3]     {"data":"re"}
9.   input                    '1re234'                 [1,3]
10.  compositionupdate        '1re234'                 [1,3]     {"data":"re"}
11.  input                    '1re234'                 [1,3]
12.  selectionchange          '1re234'                 [3,3]
13.  selectionchange          '1re234'                 [3,3]
14.  selectionchange          '1re234'                 [3,3]
15.  selectionchange          '1re234'                 [3,3]
16.  selectionchange          '1re234'                 [3,3]
17.  selectionchange          '1re234'                 [3,3]
18.  selectionchange          '1re234'                 [3,3]
19.  selectionchange          '1re234'                 [3,3]
20.  keyup                    '1re234'                 [3,3]     {"keyCode":229,"key":"Process","code":"KeyE"}
21.  compositionupdate        '1re234'                 [1,3]     {"data":"热"}
22.  input                    '1热234'                  [1,2]
23.  MutationObserver         '1热234'                  [1,2]
23.  selectionchange          '1热234'                  [2,2]
24.  selectionchange          '1热234'                  [2,2]
25.  selectionchange          '1热234'                  [2,2]
26.  compositionupdate        '1热234'                  [1,2]     {"data":"热"}
27.  input                    '1热234'                  [1,2]
28.  compositionupdate        '1热234'                  [1,2]     {"data":"热"}
29.  input                    '1热234'                  [2,2]
30.  compositionend           '1热234'                  [2,2]     {"data":"热"}
31.  selectionchange          '1热234'                  [2,2]
32.  selectionchange          '1热234'                  [2,2]
33.  selectionchange          '1热234'                  [2,2]
34.  selectionchange          '1热234'                  [2,2]
35.  selectionchange          '1热234'                  [2,2]
36.  selectionchange          '1热234'                  [2,2]
```
</details>
<details><summary>Firefox</summary>

```
1.   selectionchange          '1234'                   [1,1]
2.   compositionstart         '1234'                   [1,1]     {"data":"","locale":""}
3.   compositionupdate        '1234'                   [1,1]     {"data":"r","locale":""}
4.   input                    '1r234'                  [2,2]
5.   MutationObserver         '1r234'                  [2,2]
5.   selectionchange          '1r234'                  [2,2]
6.   compositionupdate        '1r234'                  [2,2]     {"data":"re","locale":""}
7.   input                    '1re234'                 [3,3]
8.   MutationObserver         '1re234'                 [3,3]
8.   selectionchange          '1re234'                 [3,3]
9.   compositionupdate        '1re234'                 [3,3]     {"data":"热","locale":""}
10.  input                    '1热234'                  [2,2]
11.  MutationObserver         '1热234'                  [2,2]
11.  MutationObserver         '1热234'                  [2,2]
11.  compositionend           '1热234'                  [2,2]     {"data":"热","locale":""}
12.  input                    '1热234'                  [2,2]
13.  selectionchange          '1热234'                  [2,2]
```
</details>
<details><summary>Edge</summary>

```
8.   selectionchange          '1234'                   [1,1]
1.   keydown                  '1234'                   [1,1]     {"keyCode":229,"key":"Unidentified"}
2.   compositionstart         '1234'                   [1,1]     {"data":"","locale":"zh-Hans-CN"}
3.   compositionupdate        '1r234'                  [2,2]     {"data":"r","locale":"zh-Hans-CN"}
4.   MutationObserver         '1r234'                  [2,2]
4.   input                    '1r234'                  [2,2]
5.   selectionchange          '1r234'                  [2,2]
6.   keyup                    '1r234'                  [2,2]     {"keyCode":82,"key":"r"}
1.   keydown                  '1r234'                  [2,2]     {"keyCode":229,"key":"Unidentified"}
2.   compositionupdate        '1re234'                 [3,3]     {"data":"re","locale":"zh-Hans-CN"}
3.   MutationObserver         '1re234'                 [3,3]
3.   input                    '1re234'                 [3,3]
4.   selectionchange          '1re234'                 [3,3]
5.   keyup                    '1re234'                 [3,3]     {"keyCode":69,"key":"e"}
6.   compositionupdate        '1热234'                  [2,2]     {"data":"热","locale":"zh-Hans-CN"}
7.   MutationObserver         '1热234'                  [2,2]
7.   input                    '1热234'                  [2,2]
8.   selectionchange          '1热234'                  [2,2]
9.   compositionend           '1热234'                  [2,2]     {"data":"热","locale":"zh-Hans-CN"}
10.  input                    '1热234'                  [2,2]
```
</details>
<details><summary>IE11</summary>

```
3.   selectionchange          '1234'                   [1,1]
1.   keydown                  '1234'                   [1,1]     {"keyCode":229,"key":"r"}
2.   compositionstart         '1234'                   [1,1]     {"data":"","locale":"zh-Hans-CN"}
3.   compositionupdate        '1r234'                  [2,2]     {"data":"r","locale":"zh-Hans-CN"}
4.   MutationObserver         '1r234'                  [2,2]
4.   keyup                    '1r234'                  [2,2]     {"keyCode":82,"key":"r"}
1.   keydown                  '1r234'                  [2,2]     {"keyCode":229,"key":"e"}
2.   compositionupdate        '1re234'                 [3,3]     {"data":"re","locale":"zh-Hans-CN"}
3.   MutationObserver         '1re234'                 [3,3]
3.   keyup                    '1re234'                 [3,3]     {"keyCode":69,"key":"e"}
4.   compositionupdate        '1热234'                  [2,2]     {"data":"热","locale":"zh-Hans-CN"}
5.   MutationObserver         '1热234'                  [2,2]
5.   compositionend           '1热234'                  [2,2]     {"data":"热","locale":"zh-Hans-CN"}
6.   selectionchange          '1热234'                  [2,2]
```
</details>



## Scenario 3. Win10. Korean. Z -> Space -> Z -> Space
Given text `1234` place cursor after `1`

<details><summary>Chrome</summary>

```
1.   selectionchange          '1234'                   [1,1]
1.   keydown                  '1234'                   [1,1]     {"keyCode":229,"key":"Process","code":"KeyZ"}
2.   compositionstart         '1234'                   [1,1]     {"data":""}
3.   compositionupdate        '1234'                   [1,1]     {"data":"ㅋ"}
4.   input                    '1ㅋ234'                  [1,2]
5.   MutationObserver         '1ㅋ234'                  [1,2]
5.   selectionchange          '1ㅋ234'                  [1,1]
6.   selectionchange          '1ㅋ234'                  [1,1]
7.   keyup                    '1ㅋ234'                  [1,1]     {"keyCode":90,"key":"z","code":"KeyZ"}
1.   keydown                  '1ㅋ234'                  [1,1]     {"keyCode":229,"key":"Process","code":"Space"}
2.   compositionupdate        '1ㅋ234'                  [1,2]     {"data":"ㅋ"}
3.   input                    '1ㅋ234'                  [2,2]
4.   compositionend           '1ㅋ234'                  [2,2]     {"data":"ㅋ"}
1.   keydown                  '1ㅋ234'                  [2,2]     {"keyCode":32,"key":" ","code":"Space"}
2.   keypress                 '1ㅋ234'                  [2,2]     {"charCode":32,"keyCode":32,"key":" ","code":"Space"}
3.   input                    '1ㅋ 234'                 [3,3]
4.   MutationObserver         '1ㅋ 234'                 [3,3]
4.   selectionchange          '1ㅋ 234'                 [3,3]
5.   selectionchange          '1ㅋ 234'                 [3,3]
6.   selectionchange          '1ㅋ 234'                 [3,3]
7.   keyup                    '1ㅋ 234'                 [3,3]     {"keyCode":32,"key":" ","code":"Space"}
1.   keydown                  '1ㅋ 234'                 [3,3]     {"keyCode":229,"key":"Process","code":"KeyZ"}
2.   compositionstart         '1ㅋ 234'                 [3,3]     {"data":""}
3.   compositionupdate        '1ㅋ 234'                 [3,3]     {"data":"ㅋ"}
4.   input                    '1ㅋ ㅋ234'                [3,4]
5.   MutationObserver         '1ㅋ ㅋ234'                [3,4]
5.   selectionchange          '1ㅋ ㅋ234'                [3,3]
6.   selectionchange          '1ㅋ ㅋ234'                [3,3]
7.   keyup                    '1ㅋ ㅋ234'                [3,3]     {"keyCode":90,"key":"z","code":"KeyZ"}
1.   keydown                  '1ㅋ ㅋ234'                [3,3]     {"keyCode":229,"key":"Process","code":"Space"}
2.   compositionupdate        '1ㅋ ㅋ234'                [3,4]     {"data":"ㅋ"}
3.   input                    '1ㅋ ㅋ234'                [4,4]
4.   compositionend           '1ㅋ ㅋ234'                [4,4]     {"data":"ㅋ"}
1.   keydown                  '1ㅋ ㅋ234'                [4,4]     {"keyCode":32,"key":" ","code":"Space"}
2.   keypress                 '1ㅋ ㅋ234'                [4,4]     {"charCode":32,"keyCode":32,"key":" ","code":"Space"}
3.   input                    '1ㅋ ㅋ 234'               [5,5]
4.   MutationObserver         '1ㅋ ㅋ 234'               [5,5]
4.   selectionchange          '1ㅋ ㅋ 234'               [5,5]
5.   selectionchange          '1ㅋ ㅋ 234'               [5,5]
6.   selectionchange          '1ㅋ ㅋ 234'               [5,5]
7.   keyup                    '1ㅋ ㅋ 234'               [5,5]     {"keyCode":32,"key":" ","code":"Space"}
```
</details>
<details><summary>Firefox</summary>

```
1.   selectionchange          '1234'                   [1,1]
2.   compositionstart         '1234'                   [1,1]     {"data":"","locale":""}
3.   compositionupdate        '1234'                   [1,1]     {"data":"ㅋ","locale":""}
4.   input                    '1ㅋ234'                  [2,2]
5.   MutationObserver         '1ㅋ234'                  [2,2]
5.   selectionchange          '1ㅋ234'                  [2,2]
6.   input                    '1ㅋ234'                  [2,2]
7.   MutationObserver         '1ㅋ234'                  [2,2]
7.   MutationObserver         '1ㅋ234'                  [2,2]
7.   compositionend           '1ㅋ234'                  [2,2]     {"data":"ㅋ","locale":""}
8.   input                    '1ㅋ234'                  [2,2]
1.   keydown                  '1ㅋ234'                  [2,2]     {"keyCode":32,"key":" ","code":"Space"}
2.   keypress                 '1ㅋ234'                  [2,2]     {"charCode":32,"keyCode":0,"key":" ","code":"Space"}
3.   input                    '1ㅋ 234'                 [3,3]
4.   MutationObserver         '1ㅋ 234'                 [3,3]
4.   selectionchange          '1ㅋ 234'                 [3,3]
5.   keyup                    '1ㅋ 234'                 [3,3]     {"keyCode":32,"key":" ","code":"Space"}
6.   compositionstart         '1ㅋ 234'                 [3,3]     {"data":"","locale":""}
7.   compositionupdate        '1ㅋ 234'                 [3,3]     {"data":"ㅋ","locale":""}
8.   input                    '1ㅋ ㅋ234'                [4,4]
9.   MutationObserver         '1ㅋ ㅋ234'                [4,4]
9.   selectionchange          '1ㅋ ㅋ234'                [4,4]
10.  input                    '1ㅋ ㅋ234'                [4,4]
11.  MutationObserver         '1ㅋ ㅋ234'                [4,4]
11.  MutationObserver         '1ㅋ ㅋ234'                [4,4]
11.  compositionend           '1ㅋ ㅋ234'                [4,4]     {"data":"ㅋ","locale":""}
12.  input                    '1ㅋ ㅋ234'                [4,4]
1.   keydown                  '1ㅋ ㅋ234'                [4,4]     {"keyCode":32,"key":" ","code":"Space"}
2.   keypress                 '1ㅋ ㅋ234'                [4,4]     {"charCode":32,"keyCode":0,"key":" ","code":"Space"}
3.   input                    '1ㅋ ㅋ 234'               [5,5]
4.   MutationObserver         '1ㅋ ㅋ 234'               [5,5]
4.   selectionchange          '1ㅋ ㅋ 234'               [5,5]
5.   keyup                    '1ㅋ ㅋ 234'               [5,5]     {"keyCode":32,"key":" ","code":"Space"}
```
</details>
<details><summary>Edge</summary>

```
6.   selectionchange          '1234'                   [1,1]
1.   keydown                  '1234'                   [1,1]     {"keyCode":229,"key":"z"}
2.   compositionstart         '1234'                   [1,1]     {"data":"","locale":"ko"}
3.   compositionupdate        '1ㅋ234'                  [1,2]     {"data":"ㅋ","locale":"ko"}
4.   MutationObserver         '1ㅋ234'                  [1,2]
4.   input                    '1ㅋ234'                  [1,2]
5.   selectionchange          '1ㅋ234'                  [1,2]
6.   selectionchange          '1ㅋ234'                  [1,2]
7.   selectionchange          '1ㅋ234'                  [1,2]
8.   selectionchange          '1ㅋ234'                  [1,2]
9.   keyup                    '1ㅋ234'                  [1,2]     {"keyCode":90,"key":"z"}
1.   keydown                  '1ㅋ234'                  [1,2]     {"keyCode":229,"key":"Unidentified"}
2.   compositionend           '1ㅋ234'                  [2,2]     {"data":"ㅋ","locale":"ko"}
3.   input                    '1ㅋ234'                  [2,2]
1.   keydown                  '1ㅋ234'                  [2,2]     {"keyCode":32,"key":" "}
2.   selectionchange          '1ㅋ234'                  [2,2]
3.   keypress                 '1ㅋ234'                  [2,2]     {"charCode":32,"keyCode":32,"key":" "}
4.   MutationObserver         '1ㅋ 234'                 [3,3]
4.   input                    '1ㅋ 234'                 [3,3]
5.   selectionchange          '1ㅋ 234'                 [3,3]
6.   keyup                    '1ㅋ 234'                 [3,3]     {"keyCode":32,"key":" "}
1.   keydown                  '1ㅋ 234'                 [3,3]     {"keyCode":229,"key":"z"}
2.   compositionstart         '1ㅋ 234'                 [3,3]     {"data":"","locale":"ko"}
3.   compositionupdate        '1ㅋ ㅋ234'                [3,4]     {"data":"ㅋ","locale":"ko"}
4.   MutationObserver         '1ㅋ ㅋ234'                [3,4]
4.   input                    '1ㅋ ㅋ234'                [3,4]
5.   selectionchange          '1ㅋ ㅋ234'                [3,4]
6.   selectionchange          '1ㅋ ㅋ234'                [3,4]
7.   selectionchange          '1ㅋ ㅋ234'                [3,4]
8.   selectionchange          '1ㅋ ㅋ234'                [3,4]
9.   keyup                    '1ㅋ ㅋ234'                [3,4]     {"keyCode":90,"key":"z"}
1.   keydown                  '1ㅋ ㅋ234'                [3,4]     {"keyCode":229,"key":"Unidentified"}
2.   compositionend           '1ㅋ ㅋ234'                [4,4]     {"data":"ㅋ","locale":"ko"}
3.   input                    '1ㅋ ㅋ234'                [4,4]
1.   keydown                  '1ㅋ ㅋ234'                [4,4]     {"keyCode":32,"key":" "}
2.   selectionchange          '1ㅋ ㅋ234'                [4,4]
3.   keypress                 '1ㅋ ㅋ234'                [4,4]     {"charCode":32,"keyCode":32,"key":" "}
4.   MutationObserver         '1ㅋ ㅋ 234'               [5,5]
4.   input                    '1ㅋ ㅋ 234'               [5,5]
5.   selectionchange          '1ㅋ ㅋ 234'               [5,5]
6.   keyup                    '1ㅋ ㅋ 234'               [5,5]     {"keyCode":32,"key":" "}
```
</details>
<details><summary>IE11</summary>

```
2.   selectionchange          '1234'                   [1,1]
1.   keydown                  '1234'                   [1,1]     {"keyCode":229,"key":"z"}
2.   compositionstart         '1ㅋ234'                  [2,2]     {"data":"ㅋ","locale":"ko"}
3.   selectionchange          '1ㅋ234'                  [1,2]
4.   compositionupdate        '1ㅋ234'                  [1,2]     {"data":"ㅋ","locale":"ko"}
5.   MutationObserver         '1ㅋ234'                  [1,2]
5.   keyup                    '1ㅋ234'                  [1,2]     {"keyCode":90,"key":"z"}
1.   keydown                  '1ㅋ234'                  [1,2]     {"keyCode":229,"key":"Spacebar"}
2.   selectionchange          '1ㅋ234'                  [2,2]
3.   compositionend           '1ㅋ234'                  [2,2]     {"data":"ㅋ","locale":"ko"}
1.   keydown                  '1ㅋ234'                  [2,2]     {"keyCode":32,"key":"Spacebar"}
2.   keypress                 '1ㅋ234'                  [2,2]     {"charCode":32,"keyCode":32,"key":"Spacebar"}
3.   MutationObserver         '1ㅋ 234'                 [3,3]
3.   keyup                    '1ㅋ 234'                 [3,3]     {"keyCode":32,"key":"Spacebar"}
4.   keyup                    '1ㅋ 234'                 [3,3]     {"keyCode":32,"key":"Spacebar"}
1.   keydown                  '1ㅋ 234'                 [3,3]     {"keyCode":229,"key":"z"}
2.   compositionstart         '1ㅋ ㅋ234'                [4,4]     {"data":"ㅋ","locale":"ko"}
3.   selectionchange          '1ㅋ ㅋ234'                [3,4]
4.   compositionupdate        '1ㅋ ㅋ234'                [3,4]     {"data":"ㅋ","locale":"ko"}
5.   MutationObserver         '1ㅋ ㅋ234'                [3,4]
5.   keyup                    '1ㅋ ㅋ234'                [3,4]     {"keyCode":90,"key":"z"}
1.   keydown                  '1ㅋ ㅋ234'                [3,4]     {"keyCode":229,"key":"Spacebar"}
2.   selectionchange          '1ㅋ ㅋ234'                [4,4]
3.   compositionend           '1ㅋ ㅋ234'                [4,4]     {"data":"ㅋ","locale":"ko"}
1.   keydown                  '1ㅋ ㅋ234'                [4,4]     {"keyCode":32,"key":"Spacebar"}
2.   keypress                 '1ㅋ ㅋ234'                [4,4]     {"charCode":32,"keyCode":32,"key":"Spacebar"}
3.   MutationObserver         '1ㅋ ㅋ 234'               [5,5]
3.   keyup                    '1ㅋ ㅋ 234'               [5,5]     {"keyCode":32,"key":"Spacebar"}
4.   keyup                    '1ㅋ ㅋ 234'               [5,5]     {"keyCode":32,"key":"Spacebar"}
5.   selectionchange          '1ㅋ ㅋ 234'               [5,5]
```
</details>



## Scenario 4. Win10. Korean. V -> B -> V -> Click outside
Given text `1234` place cursor after `1`

<details><summary>Chrome</summary>

```
1.   selectionchange          '1234'                   [1,1]
1.   keydown                  '1234'                   [1,1]     {"keyCode":229,"key":"Process","code":"KeyV"}
2.   compositionstart         '1234'                   [1,1]     {"data":""}
3.   compositionupdate        '1234'                   [1,1]     {"data":"ㅍ"}
4.   input                    '1ㅍ234'                  [1,2]
5.   MutationObserver         '1ㅍ234'                  [1,2]
5.   selectionchange          '1ㅍ234'                  [1,1]
6.   selectionchange          '1ㅍ234'                  [1,1]
7.   keyup                    '1ㅍ234'                  [1,1]     {"keyCode":86,"key":"v","code":"KeyV"}
1.   keydown                  '1ㅍ234'                  [1,1]     {"keyCode":229,"key":"Process","code":"KeyB"}
2.   compositionupdate        '1ㅍ234'                  [1,2]     {"data":"퓨"}
3.   input                    '1퓨234'                  [1,2]
4.   MutationObserver         '1퓨234'                  [1,2]
4.   selectionchange          '1퓨234'                  [1,1]
5.   selectionchange          '1퓨234'                  [1,1]
6.   selectionchange          '1퓨234'                  [1,1]
7.   keyup                    '1퓨234'                  [1,1]     {"keyCode":66,"key":"b","code":"KeyB"}
1.   keydown                  '1퓨234'                  [1,1]     {"keyCode":229,"key":"Process","code":"KeyV"}
2.   compositionupdate        '1퓨234'                  [1,2]     {"data":"픂"}
3.   input                    '1픂234'                  [1,2]
4.   MutationObserver         '1픂234'                  [1,2]
4.   selectionchange          '1픂234'                  [1,1]
5.   selectionchange          '1픂234'                  [1,1]
6.   selectionchange          '1픂234'                  [1,1]
7.   keyup                    '1픂234'                  [1,1]     {"keyCode":86,"key":"v","code":"KeyV"}
8.   compositionupdate        '1픂234'                  [1,2]     {"data":""}
9.   input                    '1234'                   [1,1]
10.  MutationObserver         '1234'                   [1,1]
10.  compositionend           '1234'                   [1,1]     {"data":""}
11.  input                    '1픂234'                  [2,2]
12.  MutationObserver         '1픂234'                  [2,2]
```
</details>
<details><summary>Firefox</summary>

```
1.   selectionchange          '1234'                   [1,1]
2.   compositionstart         '1234'                   [1,1]     {"data":"","locale":""}
3.   compositionupdate        '1234'                   [1,1]     {"data":"ㅍ","locale":""}
4.   input                    '1ㅍ234'                  [2,2]
5.   MutationObserver         '1ㅍ234'                  [2,2]
5.   selectionchange          '1ㅍ234'                  [2,2]
6.   compositionupdate        '1ㅍ234'                  [2,2]     {"data":"퓨","locale":""}
7.   input                    '1퓨234'                  [2,2]
8.   MutationObserver         '1퓨234'                  [2,2]
8.   compositionupdate        '1퓨234'                  [2,2]     {"data":"픂","locale":""}
9.   input                    '1픂234'                  [2,2]
10.  MutationObserver         '1픂234'                  [2,2]
10.  compositionend           '1픂234'                  [2,2]     {"data":"픂","locale":""}
11.  input                    '1픂234'                  [2,2]
12.  MutationObserver         '1픂234'                  [2,2]
```
</details>
<details><summary>Edge</summary>

```
5.   selectionchange          '1234'                   [1,1]
1.   keydown                  '1234'                   [1,1]     {"keyCode":229,"key":"v"}
2.   compositionstart         '1234'                   [1,1]     {"data":"","locale":"ko"}
3.   compositionupdate        '1ㅍ234'                  [1,2]     {"data":"ㅍ","locale":"ko"}
4.   MutationObserver         '1ㅍ234'                  [1,2]
4.   input                    '1ㅍ234'                  [1,2]
5.   selectionchange          '1ㅍ234'                  [1,2]
6.   selectionchange          '1ㅍ234'                  [1,2]
7.   selectionchange          '1ㅍ234'                  [1,2]
8.   selectionchange          '1ㅍ234'                  [1,2]
9.   keyup                    '1ㅍ234'                  [1,2]     {"keyCode":86,"key":"v"}
1.   keydown                  '1ㅍ234'                  [1,2]     {"keyCode":229,"key":"Unidentified"}
2.   compositionupdate        '1퓨234'                  [1,2]     {"data":"퓨","locale":"ko"}
3.   MutationObserver         '1퓨234'                  [1,2]
3.   input                    '1퓨234'                  [1,2]
4.   selectionchange          '1퓨234'                  [1,2]
5.   selectionchange          '1퓨234'                  [1,2]
6.   keyup                    '1퓨234'                  [1,2]     {"keyCode":66,"key":"b"}
1.   keydown                  '1퓨234'                  [1,2]     {"keyCode":229,"key":"Unidentified"}
2.   compositionupdate        '1픂234'                  [1,2]     {"data":"픂","locale":"ko"}
3.   MutationObserver         '1픂234'                  [1,2]
3.   input                    '1픂234'                  [1,2]
4.   selectionchange          '1픂234'                  [1,2]
5.   selectionchange          '1픂234'                  [1,2]
6.   keyup                    '1픂234'                  [1,2]     {"keyCode":86,"key":"v"}
7.   compositionupdate        '1픂234'                  [2,2]     {"data":"","locale":"ko"}
8.   selectionchange          ''                       [0,0]
```
</details>
<details><summary>IE11</summary>

```
2.   selectionchange          '1234'                   [1,1]
1.   keydown                  '1234'                   [1,1]     {"keyCode":229,"key":"v"}
2.   compositionstart         '1ㅍ234'                  [2,2]     {"data":"ㅍ","locale":"ko"}
3.   selectionchange          '1ㅍ234'                  [1,2]
4.   compositionupdate        '1ㅍ234'                  [1,2]     {"data":"ㅍ","locale":"ko"}
5.   MutationObserver         '1ㅍ234'                  [1,2]
5.   keyup                    '1ㅍ234'                  [1,2]     {"keyCode":86,"key":"v"}
1.   keydown                  '1ㅍ234'                  [1,2]     {"keyCode":229,"key":"b"}
2.   selectionchange          '1퓨234'                  [1,2]
3.   compositionupdate        '1퓨234'                  [1,2]     {"data":"퓨","locale":"ko"}
4.   MutationObserver         '1퓨234'                  [1,2]
4.   keyup                    '1퓨234'                  [1,2]     {"keyCode":66,"key":"b"}
1.   keydown                  '1퓨234'                  [1,2]     {"keyCode":229,"key":"v"}
2.   selectionchange          '1픂234'                  [1,2]
3.   compositionupdate        '1픂234'                  [1,2]     {"data":"픂","locale":"ko"}
4.   MutationObserver         '1픂234'                  [1,2]
4.   keyup                    '1픂234'                  [1,2]     {"keyCode":86,"key":"v"}
5.   selectionchange          '1픂234'                  [2,2]
6.   compositionupdate        '1픂234'                  [2,2]     {"data":"","locale":"ko"}
7.   selectionchange          '1픂234'                  [0,0]
```
</details>



## Scenario 4. Win10. Korean. Q -> W -> E -> Enter
Given text `1234` place cursor after `4`


<details><summary>Chrome</summary>

```
2.   selectionchange          '1234'                   [4,4]
1.   keydown                  '1234'                   [4,4]     {"keyCode":229,"key":"Process","code":"KeyQ"}
2.   compositionstart         '1234'                   [4,4]     {"data":""}
3.   compositionupdate        '1234'                   [4,4]     {"data":"ㅂ"}
4.   input                    '1234ㅂ'                  [4,5]
5.   MutationObserver         '1234ㅂ'                  [4,5]
5.   selectionchange          '1234ㅂ'                  [4,4]
6.   selectionchange          '1234ㅂ'                  [4,4]
7.   keyup                    '1234ㅂ'                  [4,4]     {"keyCode":81,"key":"q","code":"KeyQ"}
1.   keydown                  '1234ㅂ'                  [4,4]     {"keyCode":229,"key":"Process","code":"KeyW"}
2.   compositionupdate        '1234ㅂ'                  [4,5]     {"data":"ㅂ"}
3.   input                    '1234ㅂ'                  [5,5]
4.   compositionend           '1234ㅂ'                  [5,5]     {"data":"ㅂ"}
5.   compositionstart         '1234ㅂ'                  [5,5]     {"data":""}
6.   compositionupdate        '1234ㅂ'                  [5,5]     {"data":"ㅈ"}
7.   input                    '1234ㅂㅈ'                 [5,6]
8.   MutationObserver         '1234ㅂㅈ'                 [5,6]
8.   selectionchange          '1234ㅂㅈ'                 [5,5]
9.   selectionchange          '1234ㅂㅈ'                 [5,5]
10.  selectionchange          '1234ㅂㅈ'                 [5,5]
11.  selectionchange          '1234ㅂㅈ'                 [5,5]
12.  keyup                    '1234ㅂㅈ'                 [5,5]     {"keyCode":87,"key":"w","code":"KeyW"}
1.   keydown                  '1234ㅂㅈ'                 [5,5]     {"keyCode":229,"key":"Process","code":"KeyE"}
2.   compositionupdate        '1234ㅂㅈ'                 [5,6]     {"data":"ㅈ"}
3.   input                    '1234ㅂㅈ'                 [6,6]
4.   compositionend           '1234ㅂㅈ'                 [6,6]     {"data":"ㅈ"}
5.   compositionstart         '1234ㅂㅈ'                 [6,6]     {"data":""}
6.   compositionupdate        '1234ㅂㅈ'                 [6,6]     {"data":"ㄷ"}
7.   input                    '1234ㅂㅈㄷ'                [6,7]
8.   MutationObserver         '1234ㅂㅈㄷ'                [6,7]
8.   selectionchange          '1234ㅂㅈㄷ'                [6,6]
9.   selectionchange          '1234ㅂㅈㄷ'                [6,6]
10.  selectionchange          '1234ㅂㅈㄷ'                [6,6]
11.  selectionchange          '1234ㅂㅈㄷ'                [6,6]
12.  keyup                    '1234ㅂㅈㄷ'                [6,6]     {"keyCode":69,"key":"e","code":"KeyE"}
1.   keydown                  '1234ㅂㅈㄷ'                [6,6]     {"keyCode":229,"key":"Process","code":"Enter"}
2.   compositionupdate        '1234ㅂㅈㄷ'                [6,7]     {"data":"ㄷ"}
3.   input                    '1234ㅂㅈㄷ'                [7,7]
4.   compositionend           '1234ㅂㅈㄷ'                [7,7]     {"data":"ㄷ"}
1.   keydown                  '1234ㅂㅈㄷ'                [7,7]     {"keyCode":13,"key":"Enter","code":"Enter"}
2.   keypress                 '1234ㅂㅈㄷ'                [7,7]     {"charCode":13,"keyCode":13,"key":"Enter","code":"Enter"}
3.   input                    '1234ㅂㅈㄷ\n\n'            [0,0]
4.   MutationObserver         '1234ㅂㅈㄷ\n\n'            [0,0]
4.   selectionchange          '1234ㅂㅈㄷ\n\n'            [0,0]
5.   selectionchange          '1234ㅂㅈㄷ\n\n'            [0,0]
6.   selectionchange          '1234ㅂㅈㄷ\n\n'            [0,0]
7.   keyup                    '1234ㅂㅈㄷ\n\n'            [0,0]     {"keyCode":13,"key":"Enter","code":"Enter"}
```
</details>
<details><summary>Firefox</summary>

```
1.   selectionchange          '1234'                   [4,4]
2.   compositionstart         '1234'                   [4,4]     {"data":"","locale":""}
3.   compositionupdate        '1234'                   [4,4]     {"data":"ㅂ","locale":""}
4.   input                    '1234ㅂ'                  [5,5]
5.   MutationObserver         '1234ㅂ'                  [5,5]
5.   selectionchange          '1234ㅂ'                  [5,5]
6.   input                    '1234ㅂ'                  [5,5]
7.   MutationObserver         '1234ㅂ'                  [5,5]
7.   MutationObserver         '1234ㅂ'                  [5,5]
7.   compositionend           '1234ㅂ'                  [5,5]     {"data":"ㅂ","locale":""}
8.   input                    '1234ㅂ'                  [5,5]
9.   compositionstart         '1234ㅂ'                  [5,5]     {"data":"","locale":""}
10.  compositionupdate        '1234ㅂ'                  [5,5]     {"data":"ㅈ","locale":""}
11.  input                    '1234ㅂㅈ'                 [6,6]
12.  MutationObserver         '1234ㅂㅈ'                 [6,6]
12.  selectionchange          '1234ㅂㅈ'                 [6,6]
13.  input                    '1234ㅂㅈ'                 [6,6]
14.  MutationObserver         '1234ㅂㅈ'                 [6,6]
14.  MutationObserver         '1234ㅂㅈ'                 [6,6]
14.  compositionend           '1234ㅂㅈ'                 [6,6]     {"data":"ㅈ","locale":""}
15.  input                    '1234ㅂㅈ'                 [6,6]
16.  compositionstart         '1234ㅂㅈ'                 [6,6]     {"data":"","locale":""}
17.  compositionupdate        '1234ㅂㅈ'                 [6,6]     {"data":"ㄷ","locale":""}
18.  input                    '1234ㅂㅈㄷ'                [7,7]
19.  MutationObserver         '1234ㅂㅈㄷ'                [7,7]
19.  selectionchange          '1234ㅂㅈㄷ'                [7,7]
20.  input                    '1234ㅂㅈㄷ'                [7,7]
21.  MutationObserver         '1234ㅂㅈㄷ'                [7,7]
21.  MutationObserver         '1234ㅂㅈㄷ'                [7,7]
21.  compositionend           '1234ㅂㅈㄷ'                [7,7]     {"data":"ㄷ","locale":""}
22.  input                    '1234ㅂㅈㄷ'                [7,7]
1.   keydown                  '1234ㅂㅈㄷ'                [7,7]     {"keyCode":13,"key":"Enter","code":"Enter"}
2.   keypress                 '1234ㅂㅈㄷ'                [7,7]     {"charCode":0,"keyCode":13,"key":"Enter","code":"Enter"}
3.   input                    '1234ㅂㅈㄷ\n\n'            [2,2]
4.   MutationObserver         '1234ㅂㅈㄷ\n\n'            [2,2]
4.   selectionchange          '1234ㅂㅈㄷ\n\n'            [2,2]
5.   keyup                    '1234ㅂㅈㄷ\n\n'            [2,2]     {"keyCode":13,"key":"Enter","code":"Enter"}
```
</details>
<details><summary>Edge</summary>

```
6.   selectionchange          '1234'                   [1,1]
1.   keydown                  '1234'                   [4,4]     {"keyCode":229,"key":"q"}
2.   compositionstart         '1234'                   [4,4]     {"data":"","locale":"ko"}
3.   compositionupdate        '1234ㅂ'                  [4,5]     {"data":"ㅂ","locale":"ko"}
4.   MutationObserver         '1234ㅂ'                  [4,5]
4.   input                    '1234ㅂ'                  [4,5]
5.   selectionchange          '1234ㅂ'                  [4,5]
6.   selectionchange          '1234ㅂ'                  [4,5]
7.   selectionchange          '1234ㅂ'                  [4,5]
8.   selectionchange          '1234ㅂ'                  [4,5]
9.   keyup                    '1234ㅂ'                  [4,5]     {"keyCode":81,"key":"q"}
1.   keydown                  '1234ㅂ'                  [4,5]     {"keyCode":229,"key":"Unidentified"}
2.   compositionend           '1234ㅂ'                  [5,5]     {"data":"ㅂ","locale":"ko"}
3.   input                    '1234ㅂ'                  [5,5]
4.   compositionstart         '1234ㅂ'                  [5,5]     {"data":"","locale":"ko"}
5.   compositionupdate        '1234ㅂㅈ'                 [5,6]     {"data":"ㅈ","locale":"ko"}
6.   MutationObserver         '1234ㅂㅈ'                 [5,6]
6.   selectionchange          '1234ㅂㅈ'                 [5,6]
7.   input                    '1234ㅂㅈ'                 [5,6]
8.   selectionchange          '1234ㅂㅈ'                 [5,6]
9.   selectionchange          '1234ㅂㅈ'                 [5,6]
10.  selectionchange          '1234ㅂㅈ'                 [5,6]
11.  selectionchange          '1234ㅂㅈ'                 [5,6]
12.  keyup                    '1234ㅂㅈ'                 [5,6]     {"keyCode":87,"key":"w"}
1.   keydown                  '1234ㅂㅈ'                 [5,6]     {"keyCode":229,"key":"Unidentified"}
2.   compositionend           '1234ㅂㅈ'                 [6,6]     {"data":"ㅈ","locale":"ko"}
3.   input                    '1234ㅂㅈ'                 [6,6]
4.   compositionstart         '1234ㅂㅈ'                 [6,6]     {"data":"","locale":"ko"}
5.   compositionupdate        '1234ㅂㅈㄷ'                [6,7]     {"data":"ㄷ","locale":"ko"}
6.   MutationObserver         '1234ㅂㅈㄷ'                [6,7]
6.   selectionchange          '1234ㅂㅈㄷ'                [6,7]
7.   input                    '1234ㅂㅈㄷ'                [6,7]
8.   selectionchange          '1234ㅂㅈㄷ'                [6,7]
9.   selectionchange          '1234ㅂㅈㄷ'                [6,7]
10.  selectionchange          '1234ㅂㅈㄷ'                [6,7]
11.  selectionchange          '1234ㅂㅈㄷ'                [6,7]
12.  keyup                    '1234ㅂㅈㄷ'                [6,7]     {"keyCode":69,"key":"e"}
1.   keydown                  '1234ㅂㅈㄷ'                [6,7]     {"keyCode":229,"key":"Unidentified"}
2.   compositionend           '1234ㅂㅈㄷ'                [7,7]     {"data":"ㄷ","locale":"ko"}
3.   input                    '1234ㅂㅈㄷ'                [7,7]
1.   keydown                  '1234ㅂㅈㄷ'                [7,7]     {"keyCode":13,"key":"Enter"}
2.   selectionchange          '1234ㅂㅈㄷ'                [7,7]
3.   keypress                 '1234ㅂㅈㄷ'                [7,7]     {"charCode":13,"keyCode":13,"key":"Enter"}
4.   MutationObserver         '1234ㅂㅈㄷ\n'              [0,0]
4.   keyup                    '1234ㅂㅈㄷ\n'              [0,0]     {"keyCode":13,"key":"Enter"}

```
</details>
<details><summary>IE11</summary>

```
2.   selectionchange          '1234'                   [4,4]
1.   keydown                  '1234'                   [4,4]     {"keyCode":229,"key":"q"}
2.   compositionstart         '1234ㅂ'                  [5,5]     {"data":"ㅂ","locale":"ko"}
3.   selectionchange          '1234ㅂ'                  [4,5]
4.   compositionupdate        '1234ㅂ'                  [4,5]     {"data":"ㅂ","locale":"ko"}
5.   MutationObserver         '1234ㅂ'                  [4,5]
5.   keyup                    '1234ㅂ'                  [4,5]     {"keyCode":81,"key":"q"}
1.   keydown                  '1234ㅂ'                  [4,5]     {"keyCode":229,"key":"w"}
2.   selectionchange          '1234ㅂ'                  [5,5]
3.   compositionend           '1234ㅂㅈ'                 [6,6]     {"data":"ㅂ","locale":"ko"}
4.   compositionstart         '1234ㅂㅈ'                 [6,6]     {"data":"ㅈ","locale":"ko"}
5.   selectionchange          '1234ㅂㅈ'                 [5,6]
6.   compositionupdate        '1234ㅂㅈ'                 [5,6]     {"data":"ㅈ","locale":"ko"}
7.   MutationObserver         '1234ㅂㅈ'                 [5,6]
7.   keyup                    '1234ㅂㅈ'                 [5,6]     {"keyCode":87,"key":"w"}
1.   keydown                  '1234ㅂㅈ'                 [5,6]     {"keyCode":229,"key":"e"}
2.   selectionchange          '1234ㅂㅈ'                 [6,6]
3.   compositionend           '1234ㅂㅈㄷ'                [7,7]     {"data":"ㅈ","locale":"ko"}
4.   compositionstart         '1234ㅂㅈㄷ'                [7,7]     {"data":"ㄷ","locale":"ko"}
5.   selectionchange          '1234ㅂㅈㄷ'                [6,7]
6.   compositionupdate        '1234ㅂㅈㄷ'                [6,7]     {"data":"ㄷ","locale":"ko"}
7.   MutationObserver         '1234ㅂㅈㄷ'                [6,7]
7.   keyup                    '1234ㅂㅈㄷ'                [6,7]     {"keyCode":69,"key":"e"}
1.   keydown                  '1234ㅂㅈㄷ'                [6,7]     {"keyCode":229,"key":"Enter"}
2.   selectionchange          '1234ㅂㅈㄷ'                [7,7]
3.   compositionend           '1234ㅂㅈㄷ'                [7,7]     {"data":"ㄷ","locale":"ko"}
1.   keydown                  '1234ㅂㅈㄷ'                [7,7]     {"keyCode":13,"key":"Enter"}
2.   keypress                 '1234ㅂㅈㄷ'                [7,7]     {"charCode":13,"keyCode":13,"key":"Enter"}
3.   MutationObserver         '1234ㅂㅈㄷ'                [0,0]
3.   keyup                    '1234ㅂㅈㄷ'                [0,0]     {"keyCode":13,"key":"Enter"}
4.   keyup                    '1234ㅂㅈㄷ'                [0,0]     {"keyCode":13,"key":"Enter"}
```
</details>



## Scenario 5. Win10. JP Google IME. S -> A -> K -> U -> R -> A -> Space -> Click outside
Given text `1234` place cursor after `4`

<details><summary>Chrome</summary>

```
1.   selectionchange          '1234'                   [4,4]
1.   keydown                  '1234'                   [4,4]     {"keyCode":229,"key":"Process","code":"KeyS"}
2.   compositionstart         '1234'                   [4,4]     {"data":""}
3.   compositionupdate        '1234'                   [4,4]     {"data":"ｓ"}
4.   input                    '1234ｓ'                  [4,5]
5.   MutationObserver         '1234ｓ'                  [4,5]
5.   selectionchange          '1234ｓ'                  [5,5]
6.   selectionchange          '1234ｓ'                  [5,5]
7.   keyup                    '1234ｓ'                  [5,5]     {"keyCode":83,"key":"s","code":"KeyS"}
1.   keydown                  '1234ｓ'                  [5,5]     {"keyCode":229,"key":"Process","code":"KeyA"}
2.   compositionupdate        '1234ｓ'                  [4,5]     {"data":"さ"}
3.   input                    '1234さ'                  [4,5]
4.   MutationObserver         '1234さ'                  [4,5]
4.   selectionchange          '1234さ'                  [5,5]
5.   selectionchange          '1234さ'                  [5,5]
6.   selectionchange          '1234さ'                  [5,5]
7.   keyup                    '1234さ'                  [5,5]     {"keyCode":65,"key":"a","code":"KeyA"}
1.   keydown                  '1234さ'                  [5,5]     {"keyCode":229,"key":"Process","code":"KeyK"}
2.   compositionupdate        '1234さ'                  [4,5]     {"data":"さｋ"}
3.   input                    '1234さｋ'                 [4,6]
4.   MutationObserver         '1234さｋ'                 [4,6]
4.   selectionchange          '1234さｋ'                 [6,6]
5.   selectionchange          '1234さｋ'                 [6,6]
6.   selectionchange          '1234さｋ'                 [6,6]
7.   selectionchange          '1234さｋ'                 [6,6]
8.   keyup                    '1234さｋ'                 [6,6]     {"keyCode":75,"key":"k","code":"KeyK"}
1.   keydown                  '1234さｋ'                 [6,6]     {"keyCode":229,"key":"Process","code":"KeyU"}
2.   compositionupdate        '1234さｋ'                 [4,6]     {"data":"さく"}
3.   input                    '1234さく'                 [4,6]
4.   MutationObserver         '1234さく'                 [4,6]
4.   selectionchange          '1234さく'                 [6,6]
5.   selectionchange          '1234さく'                 [6,6]
6.   selectionchange          '1234さく'                 [6,6]
7.   keyup                    '1234さく'                 [6,6]     {"keyCode":85,"key":"u","code":"KeyU"}
1.   keydown                  '1234さく'                 [6,6]     {"keyCode":229,"key":"Process","code":"KeyR"}
2.   compositionupdate        '1234さく'                 [4,6]     {"data":"さくｒ"}
3.   input                    '1234さくｒ'                [4,7]
4.   MutationObserver         '1234さくｒ'                [4,7]
4.   selectionchange          '1234さくｒ'                [7,7]
5.   selectionchange          '1234さくｒ'                [7,7]
6.   selectionchange          '1234さくｒ'                [7,7]
7.   selectionchange          '1234さくｒ'                [7,7]
8.   keyup                    '1234さくｒ'                [7,7]     {"keyCode":82,"key":"r","code":"KeyR"}
1.   keydown                  '1234さくｒ'                [7,7]     {"keyCode":229,"key":"Process","code":"KeyA"}
2.   compositionupdate        '1234さくｒ'                [4,7]     {"data":"さくら"}
3.   input                    '1234さくら'                [4,7]
4.   MutationObserver         '1234さくら'                [4,7]
4.   selectionchange          '1234さくら'                [7,7]
5.   selectionchange          '1234さくら'                [7,7]
6.   selectionchange          '1234さくら'                [7,7]
7.   selectionchange          '1234さくら'                [7,7]
8.   keyup                    '1234さくら'                [7,7]     {"keyCode":65,"key":"a","code":"KeyA"}
1.   keydown                  '1234さくら'                [7,7]     {"keyCode":229,"key":"Process","code":"Space"}
2.   compositionupdate        '1234さくら'                [4,7]     {"data":"桜"}
3.   input                    '1234桜'                  [4,5]
4.   MutationObserver         '1234桜'                  [4,5]
4.   selectionchange          '1234桜'                  [5,5]
5.   selectionchange          '1234桜'                  [5,5]
6.   selectionchange          '1234桜'                  [5,5]
7.   keyup                    '1234桜'                  [5,5]     {"keyCode":32,"key":" ","code":"Space"}
8.   compositionend           '1234桜'                  [5,5]     {"data":"桜"}
9.   selectionchange          '\n'                     [0,0]
```
</details>
<details><summary>Firefox</summary>

```
1.   selectionchange          '1234'                   [4,4]
2.   compositionstart         '1234'                   [4,4]     {"data":"","locale":""}
3.   compositionupdate        '1234'                   [4,4]     {"data":"ｓ","locale":""}
4.   input                    '1234ｓ'                  [5,5]
5.   MutationObserver         '1234ｓ'                  [5,5]
5.   selectionchange          '1234ｓ'                  [5,5]
6.   compositionupdate        '1234ｓ'                  [5,5]     {"data":"さ","locale":""}
7.   input                    '1234さ'                  [5,5]
8.   MutationObserver         '1234さ'                  [5,5]
8.   compositionupdate        '1234さ'                  [5,5]     {"data":"さｋ","locale":""}
9.   input                    '1234さｋ'                 [6,6]
10.  MutationObserver         '1234さｋ'                 [6,6]
10.  selectionchange          '1234さｋ'                 [6,6]
11.  compositionupdate        '1234さｋ'                 [6,6]     {"data":"さく","locale":""}
12.  input                    '1234さく'                 [6,6]
13.  MutationObserver         '1234さく'                 [6,6]
13.  compositionupdate        '1234さく'                 [6,6]     {"data":"さくｒ","locale":""}
14.  input                    '1234さくｒ'                [7,7]
15.  MutationObserver         '1234さくｒ'                [7,7]
15.  selectionchange          '1234さくｒ'                [7,7]
16.  compositionupdate        '1234さくｒ'                [7,7]     {"data":"さくら","locale":""}
17.  input                    '1234さくら'                [7,7]
18.  MutationObserver         '1234さくら'                [7,7]
18.  compositionupdate        '1234さくら'                [7,7]     {"data":"桜","locale":""}
19.  input                    '1234桜'                  [5,5]
20.  MutationObserver         '1234桜'                  [5,5]
20.  selectionchange          '1234桜'                  [5,5]
21.  compositionend           '1234桜'                  [5,5]     {"data":"桜","locale":""}
22.  input                    '1234桜'                  [5,5]
23.  MutationObserver         '1234桜'                  [5,5]
23.  selectionchange          '\n'                     [0,0]
```
</details>
<details><summary>Edge</summary>

```
Does not work
```
</details>
<details><summary>IE11</summary>

```
2.   selectionchange          '1234'                   [4,4]
1.   keydown                  '1234'                   [4,4]     {"keyCode":229,"key":"s"}
2.   compositionstart         '1234'                   [4,4]     {"data":"","locale":"ja"}
3.   selectionchange          '1234ｓ'                  [5,5]
4.   compositionupdate        '1234ｓ'                  [5,5]     {"data":"ｓ","locale":"ja"}
5.   MutationObserver         '1234ｓ'                  [5,5]
5.   keyup                    '1234ｓ'                  [5,5]     {"keyCode":83,"key":"s"}
1.   keydown                  '1234ｓ'                  [5,5]     {"keyCode":229,"key":"a"}
2.   compositionupdate        '1234さ'                  [5,5]     {"data":"さ","locale":"ja"}
3.   MutationObserver         '1234さ'                  [5,5]
3.   keyup                    '1234さ'                  [5,5]     {"keyCode":65,"key":"a"}
1.   keydown                  '1234さ'                  [5,5]     {"keyCode":229,"key":"k"}
2.   compositionupdate        '1234さｋ'                 [6,6]     {"data":"さｋ","locale":"ja"}
3.   MutationObserver         '1234さｋ'                 [6,6]
3.   keyup                    '1234さｋ'                 [6,6]     {"keyCode":75,"key":"k"}
1.   keydown                  '1234さｋ'                 [6,6]     {"keyCode":229,"key":"u"}
2.   compositionupdate        '1234さく'                 [6,6]     {"data":"さく","locale":"ja"}
3.   MutationObserver         '1234さく'                 [6,6]
3.   keyup                    '1234さく'                 [6,6]     {"keyCode":85,"key":"u"}
1.   keydown                  '1234さく'                 [6,6]     {"keyCode":229,"key":"r"}
2.   compositionupdate        '1234さくｒ'                [7,7]     {"data":"さくｒ","locale":"ja"}
3.   MutationObserver         '1234さくｒ'                [7,7]
3.   keyup                    '1234さくｒ'                [7,7]     {"keyCode":82,"key":"r"}
1.   keydown                  '1234さくｒ'                [7,7]     {"keyCode":229,"key":"a"}
2.   compositionupdate        '1234さくら'                [7,7]     {"data":"さくら","locale":"ja"}
3.   MutationObserver         '1234さくら'                [7,7]
3.   keyup                    '1234さくら'                [7,7]     {"keyCode":65,"key":"a"}
1.   keydown                  '1234さくら'                [7,7]     {"keyCode":229,"key":"Spacebar"}
2.   compositionupdate        '1234桜'                  [5,5]     {"data":"桜","locale":"ja"}
3.   MutationObserver         '1234桜'                  [5,5]
3.   keyup                    '1234桜'                  [5,5]     {"keyCode":32,"key":"Spacebar"}
4.   compositionupdate        '1234桜'                  [5,5]     {"data":"桜","locale":"ja"}
5.   compositionend           '1234桜'                  [5,5]     {"data":"桜","locale":"ja"}
6.   selectionchange          '1234桜'                  [0,0]

```
</details>





Template below

<details><summary>Chrome</summary>

```
copy me
```
</details>
<details><summary>Firefox</summary>

```
copy me
```
</details>
<details><summary>Edge</summary>

```
copy me
```
</details>
<details><summary>IE11</summary>

```
copy me
```
</details>

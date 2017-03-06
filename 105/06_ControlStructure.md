控制流程
========================================================
author: 曾意儒 Yi-Ju Tseng
date: 2017/03/13
autosize: true
font-family: 'Microsoft JhengHei'
navigation: slide

對應書本章節
========================================================
[3 控制流程](http://yijutseng.github.io/DataScienceRBook/controlstructure.html)

大綱
====================================
- 條件判斷
    - if-else敘述
    - if-else if-else
    - 巢狀if
    - ifelse() 
    
***

- 迴圈
    - for
    - while
    - break
    - next

條件判斷
====================================
type:section

- if-else敘述
- if-else if-else
- 巢狀if
- ifelse() 

if-else敘述
====================================
type:sub-section
![plot of chunk unnamed-chunk-1](figures/ifelse.png)

***
- 邏輯判斷
- 若**if**後所接邏輯判斷
    - 為**真(TRUE)**，就會執行if下方之程式碼
    - 若為**偽(FALSE)**，則執行**else**下方之程式碼
    - 若程式中沒有**else**片段，則不執行任何程式碼
    
if-else敘述
====================================
- 必須要使用**{ }**將程式碼包起來
- 若程式碼只有一行，可省略**{ }**
    - 建議不要省略**{ }**

若考試分數**大於等於60分**，則印出**及格**字樣，小於60分則印出**不及格**字樣


```r
score<-59
if(score>=60){
  print("及格")
}else{
  print("不及格")
}
```

```
[1] "不及格"
```

if-else敘述
====================================


```r
score<-80
if(score>=60){
  print("及格")
}else{
  print("不及格")
}
```

```
[1] "及格"
```

if-else if-else
====================================
type:sub-section 

- 多重邏輯判斷
- 在`if`和`else`間新增邏輯區段**else if**


```r
score<-95
if(score>=90){
  print("優秀")
}else if(score>=60){
  print("及格")
}else{
  print("不及格")
}
```

```
[1] "優秀"
```

巢狀if
====================================
type:sub-section 

在`if`區段程式碼內包含其他`if-else`判斷

```r
CHscore<-95 ##國文成績
ENscore<-55 ##英文成績
if(CHscore>=60){
  if(ENscore>=60){
    print("全部及格")
  }else{
    print("國文及格，英文再加油")
  }
}
```

```
[1] "國文及格，英文再加油"
```

if- else if - else 練習
====================================
type:alert
incremental:true

- 新增一個數值**price**，值設定為**199**
- 撰寫if- else if - else條件判斷式，依price變數數值判斷，邏輯如下
    - 小於100元，印出"不用考慮"
    - 大於等於100元，小於1000元，印出"需要考慮一分鐘"
    - 大於等於1000元，印出"買不起"


ifelse() 
====================================
type:sub-section 

- 用最短的方式取代`if-else`敘述
- `ifelse(邏輯判斷,判斷為真要執行的程式碼,判斷為偽要執行的程式碼)`


```r
score<-80
ifelse(score>=60,"及格","不及格")
```

```
[1] "及格"
```

ifelse() 
====================================
- 可判斷向量，一次**判斷多個元素**

```r
scoreVector<-c(30,90,50,60,80)
ifelse(scoreVector>=60,"及格", "不及格")
```

```
[1] "不及格" "及格"   "不及格" "及格"   "及格"  
```
- 其他條件判斷函數都不能判斷向量，且會有**Warning message**

```r
if(scoreVector>=60){
    print("及格")
}else{
    print("不及格")
}
```

```
[1] "不及格"
```


ifelse()  練習
====================================
type:alert
incremental:true

- 基於iris資料內的Sepal.Length欄位，新增一個Type欄位
- 邏輯:如果Sepal.Length大於5.5，Type設定為"長"，小於等於5.5，Type設定為短

迴圈
====================================
type:section

- for
- while
- break
- next

for
====================================
type:sub-section 
- 必須建立需要逐一執行的參數向量或序列，再使用`for`迴圈逐一執行
- `for (單一變數 in 參數向量){ 程式碼 }`

```r
for (n in 1:3){ #n為單一變數，1:3為需要逐一執行的參數向量
  print(n)
}
```

```
[1] 1
[1] 2
[1] 3
```

for + if-else
====================================
`for`迴圈也可和`if-else`函數合併使用

```r
for (n in 1:4){
  if(n%%2==0){ #偶數直接輸出數字
    print(n)
  }else{
    print("奇數") #奇數則輸出"奇數"
  }
}
```

```
[1] "奇數"
[1] 2
[1] "奇數"
[1] 4
```

for + if-else 練習
====================================
type:alert

用**ifelse()**函數改寫上述範例

```r
for (n in 1:4){
  if(n%%2==0){ #偶數直接輸出數字
    print(n)
  }else{
    print("奇數") #奇數則輸出"奇數"
  }
}
```

```
[1] "奇數"
[1] 2
[1] "奇數"
[1] 4
```

while
====================================
type:sub-section 
- 每次執行迴圈時檢查while邏輯判斷是否為真
    - 若邏輯判斷為**真**，就會執行區段程式碼
    - 若邏輯判斷為**偽**，則會結束迴圈執行

```r
x<-0
while(x<3){
  print(x)
  x<-x+1
}
```

```
[1] 0
[1] 1
[1] 2
```

break
====================================
type:sub-section 
若遇特殊情形想**結束**迴圈執行，可使用`break`指令

```r
for(n in 1:4){
  if(n==3){
    break ##一執行到3，跳出迴圈，不再執行之後的迴圈
  }
  print(n)
}
```

```
[1] 1
[1] 2
```

next
====================================
type:sub-section 
若遇特殊情形想**跳過**迴圈執行，可使用`next`指令

```r
for(n in 1:4){
  if(n==2){
    next ##跳過2，直接執行下一個迴圈
  }
  print(n)
}
```

```
[1] 1
[1] 3
[1] 4
```

for, while, break, next 練習
====================================
type:alert
incremental:true

- 新增一向量a，包含1~20的所有奇數
- 撰寫一個for迴圈，逐一印出向量a內的元素，但遇到3的倍數時，跳過不印
- 撰寫一個for迴圈，逐一印出向量a內的元素，但遇到13的倍數時，直接跳出迴圈，不繼續執行

#### HW2_hash_practice

# 讀取txt檔 並運用hash計算有幾種不同的單字和其出現次數

## 程式碼與執行結果
* [程式碼github網址<hw2_hash_practice.ipynb>](https://github.com/max1nehour/HW2_hash_practice/blob/main/HW2_hash_practice.ipynb)

## 程式碼解析：

 * 用while迴圈確保輸入的數字在0~255之間。

* 載入json模組
* 讀取txt檔
* 初始化一個空字典
```py
import json
with open('/content/hw2_data.txt', 'r') as data:
string_counts = {}
```

* 一行一行讀取，分割每一行變成單個文字
* stripe(): 去除首尾空格
* split(): 括號內為空格，代表以「一個空格」為分隔符
```py
    for line in data:
        words = line.strip().split()
```
* 一個單字一個單字讀取
* 如果單字不存在，將其加入字典中，令值=1
* 逐行列印單字和其出現次數，方便debug
```py
        for string in words:
            if string not in string_counts:  
                string_counts[string] = 1
                print(words, string_counts[string])  
```

* 如果單字已存在，將其在字典中的值加1
* 列印單字和其出現次數
```py    
            else:
                string_counts[string] += 1
                print(words, string_counts[string]) 
```

* 列印有多少字典的key和其對應value，利用json模組增加可讀性
* 列印有多少元素在字典中
```py                     
print("每一個單字出現次數：",json.dumps(string_counts, sort_keys=False, indent=4),"\n")
print("有幾種單字出現：",len(string_counts),"種")

```

* 記得關閉檔案

```py
data.close()
```


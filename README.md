#### HW2_hash_practice

# 讀取txt檔 並運用hash計算有幾種不同的單字和其出現次數

## 程式碼與執行結果
* [程式碼github網址<hw2_hash_practice.ipynb>](https://github.com/max1nehour/HW2_hash_practice/blob/main/HW2_hash_practice.ipynb)

## 程式碼解析：

 * 用while迴圈確保輸入的數字在0~255之間。


* 讀取txt檔
* 初始化一個空字典
```py
with open('/content/hw2_data.txt', 'r') as data:
string_counts = {}
```

* 一行一行讀取
* 分割每一行變成單個文字
* 一個單字一個單字讀取
```py
    for line in data:
        words = line.strip().split()
```

* 如果字串不存在，將其加入字典中，令值=1
* 逐行列印單字和其出現次數，方便debug
```py
        for string in words:
            if string not in string_counts:  
                string_counts[string] = 1
                print(words, string_counts[string])  
```

* 如果字串已存在，將其在字典中的值加1
* 列印單字和其出現次數
```py
            
            else:
                string_counts[string] += 1
                print(words, string_counts[string]) 
                
```

* 列印有多少字典的key和其對應value 
* 列印有多少元素在字典中
```py
             
print("每一個單字出現次數：",string_counts.items())
print("有幾種不同的單字：",len(string_counts))

```

* 記得關閉檔案

```py
data.close()
  
```


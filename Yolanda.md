---
timezone: Asia/Shanghai
---

> 请在上边的 timezone 添加你的当地时区，这会有助于你的打卡状态的自动化更新，如果没有添加，默认为北京时间 UTC+8 时区


---

# YourName

1. 自我介绍
有些許DeFi相關經驗，也學過wtf的solidity課程，這次決定參與共學，並藉此機會產出相關的學習筆記。

2. 你认为你会完成本次残酷学习吗？
   會！
   
## Notes

<!-- Content_START -->

### 2024.09.23
1. 完成了"hello web3!"
   (1)第一行：license
   (2)第二行：版本，會使用“^”表示
   (3)第三行後是合約內容
2. Solidity的變量類型包括三種：
   (1)value type:布爾、整型
   (2)reference type:數組
   (3)mapping type:
   (4)enum

### 2024.09.24
1. 聲明函數可見性的關鍵字有4種：public, private, external, internal
2. 聲明函數所擁有的權限：pure（不能讀寫鏈上狀態的變量）、view（能讀取但不能寫入狀態變量）、默認寫法（自由讀取和寫入狀態變量）
3. 引用pure和view：節省gas、控制函數權限


### 2024.09.25
1. 函數輸出：(1)returns加在函數名後面，聲明返回的變量類型和變量名；return用在函數主體，返回指定的變量
2. 命名式返回
3. 解構式返回：(1)讀取所有返回值（聲明變量），要賦值的變量用“,”隔開、(2)讀取部分返回值：不讀取的部分留白

<!-- Content_END -->

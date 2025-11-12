<div align="center">
  
# Array 輸出變數類型對照表

</div>

```yaml
輸出變數配置：

1. status
   類型: String
   說明: "success" 或 "error"

2. main_question  
   類型: String
   說明: 優化後的主要問題文字

3. formatted_output
   類型: String  
   說明: 格式化後的顯示文字

4. extended_questions_list
   類型: Array[String] ← 選這個
   說明: 延伸問題的字串陣列

5. parsed_data
   類型: Object
   說明: 完整的JSON物件

6. error_message (可選)
   類型: String
   說明: 錯誤訊息

7. raw_output (可選)
   類型: String
   說明: 原始輸出內容
```

---

## **如何判斷要選哪種 Array？**

### **看代碼中 return 的內容：**

#### **Array[String] - 字串陣列**
```python
# 範例
["問題1", "問題2", "問題3"]
["領域A", "領域B", "領域C"]

# 你的代碼中：
"extended_questions_list": ["...", "...", "..."]  ← 這個
```

#### **Array[Number] - 數字陣列**
```python
# 範例
[85, 90, 75, 88]
[1, 2, 3, 4, 5]
```

#### **Array[Object] - 物件陣列**
```python
# 範例
[
    {"name": "學生A", "score": 85},
    {"name": "學生B", "score": 90}
]

# 如果你想保留完整的延伸問題資訊：
"extended_questions_full": [
    {
        "perspective": "理論基礎",
        "question": "...",
        "learning_value": "..."
    },
    ...
]  ← 這種情況選 Array[Object]
```

#### **Array[File] - 檔案陣列**
```python
# 範例
[file1.pdf, file2.jpg]
# 通常用於檔案上傳/處理
```

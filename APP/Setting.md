<div align="center">
  
# ✨ Setting

</div>

## 1️⃣ 創建工作流
1. 進入 Dify 工作台
2. 點擊「創建空白應用」→ 選擇「工作流」

## 2️⃣ 設置開始節點
```YAML
節點名稱: Start
變數設置:
  - 變數名: user_question
  - 類型: text
  - 必填: 是
  - 提示文字: "請輸入你想了解的問題"
```
<div align="center">
  <img src="/APP/S1-1.png" width="70%">
</div>

## 3️⃣ 添加 LLM 節點（老師）
### 1. 變數設置
1. 上下文：加入開始的`user_question`變量

### 2. 基本配置
```YAML
節點類型: LLM
節點名稱: Teacher_Question_Optimizer
模型: gpt-5 (或 claude-3-opus)
```

### 系統提示詞 (System Prompt)
```MARKDOWN
你是一位資深的教育專家，專門將簡單的問題轉化為有深度的教學機會。你的角色是：
1. 分析問題的教育價值
2. 優化問題使其更具體、更有深度
3. 從多個角度延伸問題
4. 建立知識架構

回應必須是有效的JSON格式。
```

### 用戶提示詞 (User Prompt)

> [!CAUTION]
> 如果貼上去後 `{{start.user_question}}` 變量沒有自動套用，要點擊 `{x}` 手動套用
> 
> <img src="/APP/S1-2.png" width="30%">

```MARKDOWN
請分析並優化以下問題：

【原始問題】
{{start.user_question}}

【分析與優化要求】

請完成以下任務並以JSON格式輸出：

1. **問題診斷**
   - 識別問題的核心概念
   - 判斷問題的複雜度（初級/中級/高級）
   - 推測提問者的意圖

2. **問題重構**
   - 將問題改寫得更精確
   - 添加必要的背景脈絡
   - 明確界定討論範圍

3. **多維度延伸**（至少3個不同角度）
   - 理論基礎：相關的基本原理是什麼？
   - 實際應用：如何在現實中運用？
   - 比較分析：與類似概念有何異同？
   - 批判思考：有哪些限制或爭議？
   - 未來發展：未來趨勢如何？

4. **知識地圖**
   - 主要涉及的學科領域
   - 需要的前置知識
   - 可以延伸學習的進階主題

【輸出JSON格式】
{
  "problem_analysis": {
    "core_concept": "識別出的核心概念",
    "complexity_level": "初級/中級/高級",
    "learner_intent": "學習者可能的目的"
  },
  "optimized_question": {
    "refined_version": "優化後更精確的問題表述",
    "context": "補充的背景資訊",
    "scope": "明確的討論範圍"
  },
  "extended_questions": [
    {
      "perspective": "理論基礎",
      "question": "具體的延伸問題",
      "learning_value": "這個問題的教學價值"
    },
    {
      "perspective": "實際應用", 
      "question": "具體的延伸問題",
      "learning_value": "這個問題的教學價值"
    },
    {
      "perspective": "比較分析",
      "question": "具體的延伸問題", 
      "learning_value": "這個問題的教學價值"
    }
  ],
  "knowledge_structure": {
    "primary_domain": "主要知識領域",
    "related_fields": ["相關領域1", "相關領域2"],
    "prerequisites": ["前置知識1", "前置知識2"],
    "advanced_topics": ["進階主題1", "進階主題2"]
  }
}
```

## 4️⃣ 添加代碼節點 - 解析JSON

### 輸出變量
```YAML
輸出變數 1:
  變數名: status
  類型: String
  
輸出變數 2:
  變數名: main_question
  類型: String
  
輸出變數 3:
  變數名: formatted_output
  類型: String
  
輸出變數 4:
  變數名: extended_questions_list
  類型: Array
  
輸出變數 5:
  變數名: parsed_data
  類型: Object

輸出變數 6:
  變數名: error_message
  類型: String

輸出變數 7:
  變數名: raw_output
  類型: String
```

## 5️⃣ 添加結束節點

## 6️⃣ 

## 7️⃣ 

## 8️⃣ 








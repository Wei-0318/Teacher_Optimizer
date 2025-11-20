<div align="center">
  
# 👩‍🏫 Teacher_Optimizer
提問 --> 老師分析 --> 提取問題重心 & 解答

[![Built with](https://img.shields.io/badge/Built%20with-Stima%20API-blueviolet?logo=robot)](https://api.stima.tech)

</div>

## ✨ 提示詞
### 【分析與優化要求】
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

### 【輸出JSON格式】
```YAML
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

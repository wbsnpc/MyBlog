---
title: {{ title }}
tags: [{{ tag }}]
categories: 菜谱
index_img: {{ img }}
---

![{{ title }}]({{ img }})

> {{ description }}

---

### 📋 菜谱信息
- **难度**：{{ difficulty }}
- **准备时间**：{{ prepTime || '15 分钟' }}
- **烹饪时间**：{{ time }} 分钟
- **份量**：{{ servings }}

---

### 🛒 必备原料

#### 主料
{{ main }}

#### 配料
{{ extra }}

#### 调料
{{ seasoning }}

---

### 🍳 烹饪步骤
{{ steps }}

---

### 💡 小贴士
{{ tips }}
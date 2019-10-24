"# Music-recommendation-engine" 
"# 音乐推荐"
### 离线计算音乐推荐
---
#### 大致流程
1. 解析请求：userid，itemid
2. 加载模型：加载model.w ， model.b
3. 检索候选集合：分别用cb和cf去redis检索，得到item->item,item推荐候选
4. 获得用户特征：userid
5. 获得物品特征：itemid
6. 打分（sigmoid），排序： 1/（1 + exp（-wx）） / 1/（1 + exp（-wx + b））
7. top-n 截断
8. 数据包装：{itemid-name}
9. 验证


---
#### 

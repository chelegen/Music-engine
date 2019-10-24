"# Music-recommendation-engine" 
"# 音乐推荐"
# 离线计算音乐推荐


## 笔记：

#### **大致流程**
1. 解析请求：userid，itemid
2. 加载模型：加载 model.w ， model.b
3. 检索候选集合：分别用cb和cf去redis检索，得到 {item->item,item} 推荐候选
4. 获得用户特征：userid
5. 获得物品特征：itemid
6. 打分，排序： （sigmoid） => 1/（1 + exp（-wx）） / 1/（1 + exp（-wx + b））
7. 截取 top-n
8. 数据包装：{itemid-name}
9. 验证推荐


#### 数据
1. 用户：userId / sex / age / inCome / region
- user.profile.data
2. 物品：itemId / itemName / itemDesc /  duration(时长) / region / tag（标签)
- music_meta
3. 用户行为：userid / itemid / user_item_duration / time（点击时间）
- user_watch_pref.sml
4. 融合：pre_base_data / gen_base.py => merge_base.data


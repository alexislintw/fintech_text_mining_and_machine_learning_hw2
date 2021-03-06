# 「財經新聞的語意分析及對股價的影響」


### 實驗目的
- 分析財經新聞詞彙與股價變動的關係。
- 搜集財經類新聞與個股股價，比較正面消息見報後，5天後股價相較於見報前的表現。
- 以『台積電』為例


### 資料預處理
1. 撰寫爬蟲，以『台積電』為關鍵字，抓取Google Search的搜尋結果頁面。
2. 撰寫爬蟲，依據步驟1取得的新聞文章網址，抓取完整的新聞內容。
3. 將步驟2取得的文章內容進行人工標注，標注出財經或投資等專業用語。(人工進行NER)
4. 取出新聞發布後5天的股價資料。


### 以股價漲跌區分新聞中的高頻詞

##### 標注詞分群
1. 以股價漲跌閾值將新聞分群，取出標注詞。
2. 篩出漲幅超過1%的新聞，取出前10名高頻詞。
3. 篩出跌幅超過1%的新聞，取出前10名高頻詞。

##### 觀察結果
- 兩方都出現的詞為：營收, 市值
- 後勢為漲的詞為：'ADR', '創新高', '成長動能', '蘋果', '匯率', '先進製程'
- 後勢為跌的詞為：'跳槽', '降評', '營收季減'


### 財經新聞詞彙與股價漲跌之相關性驗證

##### 過濾出包含經濟詞彙的新聞
- 以"ADR"為例
- 共 12 篇新聞包含該財經詞彙

##### 觀察結果
- 5日後股價為漲(漲幅大於0)的，共有10篇新聞。其中，ADR上漲的有7篇，ADR下跌的有3篇，正確率(正相關性)為70%
- 5日後股價漲幅大於1%的，共有7篇新聞。其中，ADR上漲的有6篇，ADR下跌的有1篇，正確率(正相關性)為86%
- 反過來看，ADR上漲的新聞有8篇。其中，5日後股價上漲的有7篇，5日後股價下跌的有1篇，正確率(正相關性)為88%


### 資料來源
- 工商時報 (https://ctee.com.tw)


### 檔案說明
- 抓取Google Search的『台積電』搜尋結果。爬蟲程式請見[Google_Search_台積電.ipynb](./Google_Search_%E5%8F%B0%E7%A9%8D%E9%9B%BB.ipynb)
- 抓取完整的新聞內容。爬蟲程式請見[crawler_ctee_台積電.ipynb](./crawler_ctee_%E5%8F%B0%E7%A9%8D%E9%9B%BB.ipynb)
- 篩取標注詞與股價驗證。分析程式請見[analysis_news_terms_by_stock_price.ipynb](./analysis_news_terms_by_stock_price.ipynb)



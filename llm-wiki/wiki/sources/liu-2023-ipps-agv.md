# Liu 等人（2023）｜整合製程規劃、生產排程與 AGV 運輸

## 書目與版本

Qihao Liu、Cuiyu Wang、Xinyu Li、Liang Gao。*An improved genetic algorithm with modified critical path-based searching for integrated process planning and scheduling problem considering automated guided vehicle transportation task*. Journal of Manufacturing Systems, 70, 127–136。正式期刊版，依上傳 PDF 正文整理。[DOI](https://doi.org/10.1016/j.jmsy.2023.07.004) · [原始 PDF](../../raw/papers/paper1_261007_100350.pdf)

## 研究問題與方法

研究將製程路徑選擇、工序排序、機台指派與無人搬運車（automated guided vehicle, AGV）指派整合為同一個排程問題（IPPS_T），唯一目標是最小化最大完工時間（makespan）。作者用整合編碼把上述決策放進同一個個體，並在改良式基因演算法（IGA）的突變運算中加入改自 N8 的[關鍵路徑鄰域搜尋](../concepts/critical-path-search-in-ipps.md)，同時考量機台與 AGV 上的關鍵作業。見第 3、4 節。

## 實驗與結果

第 5 節以擴充的 Kim 基準測試 24 個案例，配置四種 AGV 數量與工件數量比例（0.25、0.50、0.75、1.00），各條件獨立執行 10 次，比較 IGA、無關鍵路徑搜尋的 GA、模擬退火（SA）及粒子群最佳化（PSO）。

| 方法 | 最小 makespan | 平均 makespan | 標準差 |
| --- | ---: | ---: | ---: |
| IGA | 527 | 537.9 | 6.0 |
| GA | 590 | 614.0 | 21.6 |
| SA | 584 | 607.1 | 17.0 |
| PSO | 558 | 577.3 | 12.1 |

上表為表 7 的第 1 個案例，AGV／工件比為 1.00（p. 135）。作者在第 5 節指出，整體而言 IGA 的最小值與平均值表現較好。就標準差而言，作者報告 IGA 於 96 組案例條件中有 52 組取得最佳值，PSO 有 45 組，其中有 2 組同列最佳。這些是描述統計。

## 限制與後續研究

加工與搬運一旦開始即不中斷，裝卸時間納入運輸時間（第 3 節）。實驗來自擴充基準。作者在第 6 節提出可探索耗能、機台負載等額外目標。Wiki 延伸問題見 [LLM 能否協助排程實驗與錯誤分析？](../questions/llm-assisted-scheduling.md)。這篇論文提供排程方法的比較基線，後續需另外蒐集 LLM 的實證研究。

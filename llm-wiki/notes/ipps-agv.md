# 如何同時最佳化製程路徑、機台作業及 AGV 運輸以縮短整體生產時間？

## 結論

以最大完工時間為共同目標，將製程路徑、工序順序、機台指派與無人搬運車（AGV）指派放在同一個候選解中，並用關鍵路徑鄰域搜尋調整可能影響整體完工時間的加工與搬運作業。[Liu 等人（2023），§3–4](../wiki/sources/liu-2023-ipps-agv.md)

## 目標與可行性

以 $C_j$ 表示工件 $j$ 的完工時間，$C_{\max}$ 是最晚完工的工件所對應的時間。

$$
\min C_{\max}, \qquad C_{\max}=\max_j C_j
$$

此式是 Wiki 所述 makespan 目標的簡記。候選排程須符合製程優先關係與資源限制。加工與搬運開始後不中斷，裝卸計入運輸時間。[來源頁，§3](../wiki/sources/liu-2023-ipps-agv.md)

## 求解方式

改良式基因演算法（IGA）以整合編碼表示四項決策，把改自 N8 的關鍵路徑鄰域搜尋放進突變。關鍵路徑是決定 makespan 的作業鏈，加工或 AGV 任務都可能在這條鏈上。調整後仍須符合製程優先關係及資源限制。[關鍵路徑概念，§3–4，圖 6–8](../wiki/concepts/critical-path-search-in-ipps.md)

## 實驗證據

擴充 Kim 基準共有 24 個案例，測試四種 AGV／工件比（0.25、0.50、0.75、1.00），各條件獨立執行 10 次。下表僅呈現表 7 案例 1，AGV／工件比為 1.00。[來源頁，§5，表 7，p. 135](../wiki/sources/liu-2023-ipps-agv.md)

| 方法 | 最小 makespan | 平均 makespan | 標準差 |
| --- | ---: | ---: | ---: |
| IGA | 527 | 537.9 | 6.0 |
| GA | 590 | 614.0 | 21.6 |
| SA | 584 | 607.1 | 17.0 |
| PSO | 558 | 577.3 | 12.1 |

案例 1 的平均 makespan，IGA 較無關鍵路徑搜尋的 GA 低約 12.4%（由表中 $(614.0-537.9)/614.0$ 換算）。穩定性則應看多組條件：作者報告 96 組條件中，IGA 有 52 組取得最佳標準差，PSO 有 45 組，含 2 組同列最佳。[來源頁，§5](../wiki/sources/liu-2023-ipps-agv.md)

## 使用範圍

這是擴充基準上的描述統計，可用來說明方法在該實驗設定下的表現。實際產線可達的改善幅度仍待驗證。論文只最佳化 makespan，耗能及機台負載可作為後續研究方向。[來源頁，§5–6](../wiki/sources/liu-2023-ipps-agv.md)

## 建議文獻｜待收錄

- Yang 等人（2025），*MILP Modeling and Optimization of Three-Stage Flexible Job Shop Scheduling Problem with Assembly and AGV Transportation*。可補足含組裝階段的 MILP 比較方法。[下載公開 PDF](https://link.springer.com/content/pdf/10.1186/s10033-025-01281-z.pdf)
- Stadtler、Stahmann 與 Janiesch（2026），*A Benchmark for Selecting Real-Time Scheduling Approaches for Fleets of Automated Guided Vehicles in Intralogistics*。可補足即時 AGV 車隊排程的評估設計。[下載公開 PDF](https://link.springer.com/content/pdf/10.1007/s12599-026-01003-2.pdf)

# Project Overview: Multidimensional Substance Synergy & the Gateway Myth / 專案總覽：多維物質協同與入門磚迷思剖析

Welcome to the official repository for our data science research project. This study utilizes empirical records from the Youth Risk Behavior Surveillance System (YRBSS) to investigate the context dependency of the marijuana gateway effect and polysubstance comorbidity structures in adolescent public health.
歡迎來到我們的資料科學研究專案官方倉庫。本研究利用青少年危險行為監測系統（YRBSS）的經驗紀錄，探討青少年公共衛生中大麻入門磚效應的背景依賴性與多重物質共用之成癮共病結構。

---

## 1. Administrative Information / 行政資訊
* **Project Type / 專案型態**: Individual Project / 個人獨立作業
* **Student Name / Student ID (學生姓名/學號)**: 
  * 鍾肇紘 113370240

---

## 2. Selected Research Question / 選定之研究問題
Our investigation is strictly dedicated to answering the structural intersection of the gateway drug controversy:
本研究全力聚焦於解答入門磚藥物爭議的結構性交會點：

> **"Does marijuana use independently accelerate adolescent progression to illicit hard drugs, or is this effect context-dependent and synergistic with alcohol and tobacco?"**
> **「大麻吸食是否會獨立物化並加速青少年涉入非法硬性毒品，亦或此效應高度取決於吸食背景，並與酒精、香菸產生協同加乘的催化作用？」**

---

## 3. Core Variables Taxonomy / 核心變數分類學

To isolate and test this query, the analytical workflow structures the data around two primary pillars across $N = 12,093$ valid fully-complying samples:
為了隔離並檢定此問題，分析流程圍繞兩個核心支柱展開資料工程，涵蓋 $N = 12,093$ 筆完全填答的黃金樣本池：

* **Grouping Variables (Independent Predictors) / 分組與全域自變項**: 
  * **`Substance_Group` (8-Group Mutually Exclusive Matrix / 8大互斥群體變數)**: Categorizes adolescents into 8 unique groups based on their binary consumption profile of Cigarettes (`Cig`), Alcohol (`Alc`), and Marijuana (`Mj`) to eliminate statistical confounding.
    由香菸、酒精與大麻的涉入狀態（0=無，1=有）交互交織衍生而得，藉此徹底根除統計混淆。
    * **Control Group (`G1: None`) / 完全清白對照組**: Completely unexposed control group. / 完全清白組。
    * **Single-Substance Groups (`G2`, `G3`, `G4`) / 單一物質涉入組**: Cig Only, Alc Only, Mj Only. / 單獨吸菸組、單獨飲酒組、單獨大麻組。
    * **Polysubstance Groups (`G5`, `G6`, `G7`, `G8`) / 多重物質多維並用組**: Cig+Alc, Cig+Mj, Alc+Mj, All Three. / 菸酒共用組、菸大麻共用組、酒大麻共用組、三者全面涉入組。
  * **`Cig_scaled` / `Alc_scaled` / `Mj_scaled`**: Continuous standard normal regressors transformed via Z-score for global coefficient comparison.
    全域標準化自變項，用以在多元線性模型中公平評估並排序獨立風險推力。
* **Response Variable (Dependent Metric) / 反應依變項**: 
  **`AnyHardDrug_Score` (Composite Hard Drug Index / 綜合硬性毒品總體得分)**
  * An adjusted continuous-like metric (0 to 5) established by capturing the maximum frequency score among five tracked illicit substances (Cocaine, Heroin, Inhalants, Methamphetamine, Ecstasy) and applying a minus-1 baseline translation.
    介於 0 至 5 之間的連續型衍生指標，橫向捕捉古柯鹼、海洛因、吸入劑、安非他命與搖頭丸這五項非法毒品的最高填答級分並減 1 轉換（0 分代表絕對清白）。

---

## 4. Statistical Methodology Deployed / 採用的統計方法學

The mathematical validation workflow relies on a multi-stage inferential framework:
本研究的數學驗證流程依賴於多階段推論架構：

1. **One-Way ANOVA & Tukey's HSD Post-Hoc Test (單因子變異數分析與事後比較檢定)**:
   Deployed to audit macro-level variance heterogeneities across the 8 exclusive groups, followed by micro-level pairwise multiple comparisons to formally verify the context dependency (e.g., matching G1 vs G4, and G5 vs G8).
   用以檢定 8 個互斥組別之間的全局巨觀異質性，並透過微觀成對事後比較，嚴謹驗證大麻引導效應的背景依賴性（如比對 G1 與 G4、G5 與 G8 的均值淨增幅）。
2. **Standardized Multiple Linear Regression (OLS) (全域標準化多元線性迴歸模型)**:
   Executed by scaling all baseline regressors into Z-scores, mathematically neutralizing compounding covariances to rank the true independent gateway weights ($\beta$) of tobacco, alcohol, and marijuana on hard drug escalation.
   透過將所有入門物質轉化為標準阻抗分數，在完全扣除彼此共變干擾的前提下，精確計算並排序香菸、酒精與大麻對硬性毒品涉入的獨立淨推力權重。

---

## 5. Short Final Conclusion / 最終簡短結論

*(Note: Below is a formal empirical summary derived from our global linear and post-hoc pipelines.)*
*(註：以下為基於本研究全域線性與事後比較管線所得之嚴謹實證總結。)*

The inferential architecture reveals that the global multiple regression model holds extreme statistical power ($R^2 = 24.6\%$, $F = 1315, p < 0.0001$), proving that entry substances collectively account for nearly a quarter of the total variance in adolescent hard drug engagement. More importantly, the micro-level Tukey HSD tests strongly support the **Common Liability Model** over the traditional independent gateway drug hypothesis. The risk increment from `G1 (Clean Control)` to `G4 (Marijuana Only)` is statistically **non-significant** ($p = 0.5614$). However, once an alcohol-consuming environment is present, introducing marijuana triggers a violent synergistic catalyst effect, generating a leap-forward risk surge from `G5` to `G8` ($\text{meandiff} = 0.6604, p < 0.0001$). Under the global OLS model, **Alcohol exhibits the highest standardized push weight ($\beta = 0.2182, p < 0.0001$)**, outperforming Cigarettes ($\beta = 0.2079$) and Marijuana ($\beta = 0.1945$). This implies that marijuana’s gateway risk is heavily conditional and background-dependent; alcohol acts as the primary pharmacological and behavioral disinhibition deconstructor that unbolts the gates to illicit hard drug abuse.

推論統計架構顯示，全域多元線性迴歸模型具備極強的統計解釋力（$R^2 = 24.6\%$，全域模型 $F = 1315, p < 0.0001$），證實入門物質共同解釋了青少年高中生將近四分之一的硬性毒品行為變異。更關鍵的是，微觀層面的 Tukey HSD 檢定結果強烈支持**「共同責任模型（Synergistic Model）」**並駁斥了傳統獨立的入門磚假說。數據顯示，從 `G1 完全清白組` 跨越至 `G4 單獨大麻組` 的硬毒品風險增幅在統計上**完全不顯著**（$p = 0.5614$）；然而，一旦背景中存在飲酒行為，大麻的加入便會觸發強烈的協同催化作用，引發 `G5` 到 `G8` 之間全表最高的跨越式飆升（$\text{meandiff} = 0.6604, p < 0.0001$）。在全域 OLS 模型中，**酒精展現出最強的獨立預測推力（$\beta = 0.2182, p < 0.0001$）**，排序高於香菸（$\beta = 0.2079$）與大麻（$\beta = 0.1945$）。這表明大麻的入門磚風險高度取決於涉入背景，酒精才是解鎖、並引導青少年走向重度非法毒品濫用的首要開拓物質。


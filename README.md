# 自動控制：原課程 MATLAB 程式的 Python 筆記本

「[自動控制 Automatic Control](https://yoshiagent.github.io/automaticControl/)」課程原本以 MATLAB 示範。這裡把原課程的 MATLAB 程式改寫成 Python 筆記本，可以直接在 Google Colab 執行，不需要安裝任何軟體。

| 筆記本 | 內容（原課程的檔案） | 對照的網頁 | 開啟 |
|---|---|---|---|
| [微分方程式的解析解](notebooks/AnalyticSolution.ipynb) | sys2ndfree.m（標準二階系統自由響應）、Osci1.m、nonOsc.m（自由響應例題）、TranSteady.m（暫態＋穩態）、Unstable.m（不穩定）、Resonance.m（共振）、noResonance.m、Osci.m | [網頁](https://yoshiagent.github.io/automaticControl/AS.html) | [![在 Colab 開啟](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yoshiagent/automaticControl-colab/blob/main/notebooks/AnalyticSolution.ipynb) |
| [頻域補償器設計](notebooks/LeadLag_Design.ipynb) | Leadtab.m（α 與最大相位領先角對照表）、mo2zeta2pm.m（超越量→阻尼比→相位邊限）；另驗算網頁上的 lead／lag 設計例 | [網頁](https://yoshiagent.github.io/automaticControl/FRD-Lead.html) | [![在 Colab 開啟](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yoshiagent/automaticControl-colab/blob/main/notebooks/LeadLag_Design.ipynb) |

* 每本筆記本都先列出原本的 MATLAB 程式，再給逐段對應的 Python 版本，並已實際執行（存有輸出與圖）。
* 只用 Colab 內建的 numpy、scipy、sympy 與 plotly。
* 解析解都用 sympy 的 `dsolve`（對應 MATLAB Symbolic Math Toolbox）與數值積分交叉驗證。

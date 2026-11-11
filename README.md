# 自動控制：原課程 MATLAB 程式與 Simulink 模型的 Python 筆記本

「[自動控制 Automatic Control](https://yoshiagent.github.io/automaticControl/)」課程原本以 MATLAB 與 Simulink 示範。這裡把原課程的 MATLAB 程式（`.m`）與 Simulink 模型（`.mdl`）改寫成 Python 筆記本，可以直接在 Google Colab 執行，不需要安裝任何軟體。

| 筆記本 | 內容（原課程的檔案） | 對照的網頁 | 開啟 |
|---|---|---|---|
| [微分方程式的解析解](notebooks/AnalyticSolution.ipynb) | sys2ndfree.m（標準二階系統自由響應）、Osci1.m、nonOsc.m（自由響應例題）、TranSteady.m（暫態＋穩態）、Unstable.m（不穩定）、Resonance.m（共振）、noResonance.m、Osci.m | [網頁](https://yoshiagent.github.io/automaticControl/AS.html) | [![在 Colab 開啟](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yoshiagent/automaticControl-colab/blob/main/notebooks/AnalyticSolution.ipynb) |
| [頻域補償器設計](notebooks/LeadLag_Design.ipynb) | Leadtab.m（α 與最大相位領先角對照表）、mo2zeta2pm.m（超越量→阻尼比→相位邊限）；另驗算網頁上的 lead／lag 設計例 | [網頁](https://yoshiagent.github.io/automaticControl/FRD-Lead.html) | [![在 Colab 開啟](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yoshiagent/automaticControl-colab/blob/main/notebooks/LeadLag_Design.ipynb) |
| [Simulink 模擬入門](notebooks/Simulink_Basics.ipynb) | TfSim.mdl、sssim.mdl、IntgratorM.mdl（同一系統三種建模）、Linearity.mdl（線性）、FreqResp.mdl（頻率響應） | [網頁](https://yoshiagent.github.io/automaticControl/SIM.html) | [![在 Colab 開啟](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yoshiagent/automaticControl-colab/blob/main/notebooks/Simulink_Basics.ipynb) |
| [回授控制與 PID](notebooks/Feedback_PID.ipynb) | OpenLP1TF、CloseLPTF、SensorDis、CloseLPPITF、PID_IESS、CloseLPPITFUStab、PID_Iover、PID_P_I_D、PID_P_I_D1、OpenCloseLPTF、OpenCloseLPPITF、CloseLPPDTF、OpenCloseLPPITFPV、OpenCloseLPPITFStab、OpenCloseLP、OpenCloseLPPI、PID_P、PID_PI、PID_PID（共 19 個 .mdl） | [網頁](https://yoshiagent.github.io/automaticControl/FBC-FeedBack.html) | [![在 Colab 開啟](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yoshiagent/automaticControl-colab/blob/main/notebooks/Feedback_PID.ipynb) |
| [穩態誤差](notebooks/SteadyState_Error.ipynb) | Ess_NoSpring、Ess_inf、Ess_Type1_2、Ess_Type2Step、Ess_Eliminate（系統型別與 P／I 控制，共 5 個 .mdl） | [網頁](https://yoshiagent.github.io/automaticControl/ESS.html) | [![在 Colab 開啟](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yoshiagent/automaticControl-colab/blob/main/notebooks/SteadyState_Error.ipynb) |
| [根軌跡與 P／I／D 控制器](notebooks/RootLocus_PID.ipynb) | DominantPole、Pcontrol、Icontrol、PDEffect、Dcontrol1、PDcontrol1（主極點與 P／I／D 控制，共 6 個 .mdl） | [網頁](https://yoshiagent.github.io/automaticControl/RL-RootLocusDesign.html) | [![在 Colab 開啟](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yoshiagent/automaticControl-colab/blob/main/notebooks/RootLocus_PID.ipynb) |

* MATLAB 程式：先列出原本的程式，再給逐段對應的 Python 版本；解析解用 sympy 的 `dsolve`（對應 MATLAB Symbolic Math Toolbox）與數值積分交叉驗證。
* Simulink 模型：方塊與參數直接從 `.mdl` 檔讀出（沒寫的用 Simulink 預設值），積分器寫成狀態變數、Transfer Fcn 轉成狀態空間，以 `scipy.integrate.solve_ivp`（RK45，對應 ode45）模擬，結果與理論值（穩態值、極點、解析解）比對。
* 每本都已實際執行（存有輸出與圖），只用 Colab 內建的 numpy、scipy、sympy 與 plotly。

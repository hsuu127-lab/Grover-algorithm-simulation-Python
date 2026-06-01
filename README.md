# Grover-algorithm-simulation-Python

這個專案是模擬量子演算法 Grover Algorithm。本研究聚焦於 Grover's Algorithm 的實作，並在數學上證明且在 Qiskit 上利用通用量子閘集合（Universal Gate Set）去合成並模擬套件未原生提供的特殊黑盒子（Oracle）與擴散器（Diffuser）。

- **通用量子閘合成證明（Universal Gate Synthesis）：** 理論上所有的量子匣都能Universal Gate 組合出來，本專案運用線性代數與么正矩陣（Unitary Matrix）分解，從數學上嚴謹證明：如何利用 Qiskit 原生提供的基礎量子閘（如 $X, H, CNOT$ 等），組裝出原本並未提供的特殊量子算子。
- **自定義 Oracle & Diffuser 實作：** 本專案將上述數學證明用小數字實作，在 Qiskit 框架下建構出專屬的黑盒子與相位放大的 Quantum Circuits。
- **NumPy 與 Qiskit 雙引擎驗證：** 
  1. 先用 NumPy 進行純矩陣乘法的底層數值模擬，確保數學邏輯與機率振幅（Probability Amplitude）的收斂正確。
  2. 再用 Qiskit 建立量子線路，驗證數學證明在真實量子計算架構下的可行性。
  3. 最後用 matplotlib 將演算法的收斂機率視覺化。

## 科學限制與實務考量
由於傳統硬體（CPU/GPU）在模擬量子疊加態時，矩陣維度會隨位元數（Qubits）呈指數型暴增（$2^n$），因此本專案聚焦於小規模位元數的**精準電路合成與邏輯驗證**。這符合量子計算研發的實務流程——先在小規模進行嚴謹的矩陣轉換證明，再推廣至高維度，並在最後將機率視覺化。

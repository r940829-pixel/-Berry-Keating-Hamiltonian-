# 優化Berry-Keating Hamiltonian的方法

---

[![DOI](https://zenodo.org/badge/1397884520.svg)](https://doi.org/10.5281/zenodo.23063486)

---

## (一) Berry-Keating 哈密頓量形式

$$\hat{H} = \frac{1}{2}(\hat{x}\hat{p} + \hat{p}\hat{x}) = -i\hbar \left( x \frac{\partial}{\partial x} + \frac{1}{2} \right)$$

(1)

---

## (二)本研究提出的轉換算符型式

### 位置座標 $x$

$$x = \sqrt{n \cot(\theta_r + i\theta_i)} = \sqrt{n \cot\theta}$$

(2)

---

### 共軛動量 $p$（即公式中的 $y$，在此對應動量算符）

$$p = \sqrt{n \tan(\theta_r + i\theta_i)} = \sqrt{n \tan\theta}$$

(3)

---

## (三)算符轉換過程

本研究透過透過微分鏈鎖律（Chain Rule），將對 $x$ 的微分算子轉化為對複相角 $\theta$ 的微分算子 $\frac{\partial}{\partial \theta}$

### 1.對位置 x 求解與 θ 的微分關係

因為 $x = \sqrt{n} (\cot\theta)^{1/2}$，對 $\theta$ 求導可得

$$\frac{\partial x}{\partial \theta} = \sqrt{n} \cdot \frac{1}{2} (\cot\theta)^{-1/2} \cdot (-\csc^2\theta) = -\frac{\sqrt{n}}{2} \frac{\csc^2\theta}{\sqrt{\cot\theta}}$$

---

### 2.利用倒數關係變換微分算子

$$\frac{\partial}{\partial x} = \left( \frac{\partial x}{\partial \theta} \right)^{-1} \frac{\partial}{\partial \theta} = -\frac{2 \sqrt{\cot\theta}}{\sqrt{n} \csc^2\theta} \frac{\partial}{\partial \theta} = -\frac{2}{\sqrt{n}} \sin\theta \cos\theta \sqrt{\tan\theta} \frac{\partial}{\partial \theta}$$

---

### 3.代入膨脹項 $x \frac{\partial}{\partial x}$

$$x \frac{\partial}{\partial x} = \left( \sqrt{n \cot\theta} \right) \cdot \left( -\frac{2}{\sqrt{n}} \sin\theta \cos\theta \sqrt{\tan\theta} \frac{\partial}{\partial \theta} \right)$$

由於 
$\sqrt{\cot\theta} \cdot \sqrt{\tan\theta} = 1$
，上式可簡化為：
$$x \frac{\partial}{\partial x} = -2 \sin\theta \cos\theta \frac{\partial}{\partial \theta} = -\sin(2\theta) \frac{\partial}{\partial \theta}$$

---

### 4.最終帶入算符得到 $\hat{H}_{\theta}$

將 $x \frac{\partial}{\partial x} = -\sin(2\theta) \frac{\partial}{\partial \theta}$ 代入量子哈密頓量

$$\hat{H} = -i\hbar \left( -\sin(2\theta) \frac{\partial}{\partial \theta} + \frac{1}{2} \right)$$

展開複相角 $\theta = \theta_r + i\theta_i$，我們得到複相空間下的 PT 對稱哈密頓量最終形式

$$\hat{H}_{\text{PT}} = i\hbar \sin(2\theta_r + 2i\theta_i) \frac{\partial}{\partial \theta} - \frac{i\hbar}{2}$$

利用複數三角函數展開 $\sin(A + iB) = \sin A \cosh B + i \cos A \sinh B$

$$\hat{H}_{\text{PT}} = i\hbar \left[ \sin(2\theta_r)\cosh(2\theta_i) + i \cos(2\theta_r)\sinh(2\theta_i) \right] \left( \frac{1}{2}\frac{\partial}{\partial \theta_r} - \frac{i}{2}\frac{\partial}{\partial \theta_i} \right) - \frac{i\hbar}{2}$$

---

## (四)最終算符型式

$$\hat{H} = -i\hbar \left( -\sin(2\theta) \frac{\partial}{\partial \theta} + \frac{1}{2} \right)$$

(4)

---

其PT對稱性完整系統型式

$$\hat{H}_{\text{PT}} = i\hbar \left[ \sin(2\theta_r)\cosh(2\theta_i) + i \cos(2\theta_r)\sinh(2\theta_i) \right] \left( \frac{1}{2}\frac{\partial}{\partial \theta_r} - \frac{i}{2}\frac{\partial}{\partial \theta_i} \right) - \frac{i\hbar}{2}$$

(5)

---

## (五)對最終算符(4)做FT變換

算子（哈密頓量）形式為

$$\hat{H} = -i\hbar \left( -\sin(2\theta) \frac{\partial}{\partial \theta} + \frac{1}{2} \right)$$

(4)

將對時間（或複數變數） $\theta$  的作用態向量進行頻域展開（傅立葉變換 Fourier Transform），並逐步推導其在頻域中的對應矩陣/算子表現與本徵方程。

### 一、 傅立葉變換的對映關係與算子替換規則

在時域 $\theta$ 與頻域 $\omega$ 之間，定義連續傅立葉變換（Fourier Transform）

$$\psi(\theta) = \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\infty} \tilde{\psi}(\omega) e^{i\omega\theta} d\omega$$

在頻域中，微商算子與複指數函數分別對應以下變換規則

---

微分算子 $\frac{\partial}{\partial \theta}$

$$\frac{\partial}{\partial \theta} \psi(\theta) \xrightarrow{\mathscr{F}} (i\omega) \tilde{\psi}(\omega)$$

---

三角函數項 $\sin(2\theta)$ 的展開

利用歐拉公式， $\sin(2\theta) = \frac{e^{2i\theta} - e^{-2i\theta}}{2i}$
在頻域中，乘以 $e^{\pm 2i\theta}$ 會引起頻域的平移（Shift Operator）

$$e^{\pm 2i\theta} \phi(\theta) \xrightarrow{\mathscr{F}} \tilde{\phi}(\omega \mp 2)$$

### 二、 過程詳細推導

將 $\hat{H}\psi(\theta)$ 帶入時域表達式並套用傅立葉變換

$$\hat{H}\psi(\theta) = i\hbar \sin(2\theta) \frac{\partial\psi(\theta)}{\partial\theta} - \frac{i\hbar}{2} \psi(\theta)$$

---

推導第一項 $i\hbar \sin(2\theta) \frac{\partial\psi(\theta)}{\partial\theta}$

利用 $\sin(2\theta) = \frac{e^{2i\theta} - e^{-2i\theta}}{2i}$

$$i\hbar \sin(2\theta) \frac{\partial\psi(\theta)}{\partial\theta} = i\hbar \left( \frac{e^{2i\theta} - e^{-2i\theta}}{2i} \right) \frac{\partial\psi(\theta)}{\partial\theta} = \frac{\hbar}{2} \left( e^{2i\theta} - e^{-2i\theta} \right) \frac{\partial\psi(\theta)}{\partial\theta}$$

對微分項 $\phi(\theta) = \frac{\partial\psi(\theta)}{\partial\theta}$ 做變換，其頻域形式為 $\tilde{\phi}(\omega) = i\omega \tilde{\psi}(\omega)$

接著乘以相移因子 $e^{\pm 2i\theta}$

$\mathscr{F} \left\lbrace e^{2i\theta} \frac{\partial\psi}{\partial\theta} \right\rbrace = i(\omega - 2) \tilde{\psi}(\omega - 2)$


$\mathscr{F} \left\lbrace e^{-2i\theta} \frac{\partial\psi}{\partial\theta} \right\rbrace= i(\omega + 2) \tilde{\psi}(\omega + 2)$

相減後乘以 $\frac{\hbar}{2}$，得到第一項在頻域的表示為：

$$\frac{i\hbar}{2} \left[ (\omega - 2)\tilde{\psi}(\omega - 2) - (\omega + 2)\tilde{\psi}(\omega + 2) \right]$$

---

推導第二項 $-\frac{i\hbar}{2}\psi(\theta)$

此項為標量乘法，頻域直接保持

$$\mathscr{F} \left\lbrace -\frac{i\hbar}{2}\psi(\theta) \right\rbrace = -\frac{i\hbar}{2}\tilde{\psi}(\omega)$$

### 三、 頻域下的最終哈密頓量表達式
將兩項組合，頻域作用算子 $\hat{H}_\omega \tilde{\psi}(\omega)$ 為

$$\hat{H}_\omega \tilde{\psi}(\omega) = -\frac{i\hbar}{2} \left[ (\omega + 2)\tilde{\psi}(\omega + 2) - (\omega - 2)\tilde{\psi}(\omega - 2) + \tilde{\psi}(\omega) \right]$$

(6)

---

If you find this project useful, please contact me at the following email address.

Contact Information(Email address)
```bash
r940829@gmail.com
```

---

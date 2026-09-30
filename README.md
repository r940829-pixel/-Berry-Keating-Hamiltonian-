# 優化Berry-Keating Hamiltonian的方法

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

If you find this project useful, please contact me at the following email address.

Contact Information(Email address)
```bash
r940829@gmail.com
```

---

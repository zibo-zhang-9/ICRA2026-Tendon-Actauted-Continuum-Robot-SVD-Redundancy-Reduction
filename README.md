# From Redundant Tendon Tensions to Low-Dimensional Actuation Coordinates: A SVD-Based Method for Tendon-Actuated Continuum Robots

[![Venue: ICRA 2026](https://img.shields.io/badge/Venue-IEEE%20ICRA%202026%20Workshop-blue.svg)](https://2026.ieee-icra.org/)
[![Thesis: Chapter 4](https://img.shields.io/badge/PhD%20Thesis-Chapter%204-red.svg)](https://github.com/zibo-zhang-9)

This repository hosts the core theoretical framework, analytical methods, and presentation materials for the **SVD-based actuation redundancy elimination method**. This work constitutes **Chapter 4** of my PhD dissertation (*Élimination et analyse de la redondance d'actionnement*) and was peer-reviewed and presented as a Workshop Poster at the **IEEE International Conference on Robotics and Automation (ICRA 2026)**, Vienna, Austria.

---

## 🖼️ Workshop Poster & Graphical Abstract
*(提示：请将您的 Poster PDF 转换为一张高分辨率的 poster.png，上传到这个仓库中，然后在这里展示。如果没有图片，可以先删掉这一行)*
![IEEE ICRA 2026 Poster](poster.png)

---

## 📌 Background & Research Motivation (PhD Thesis Ch. 4)
Tendon-Actuated Continuum Robots (TACRs) are inherently **over-actuated**. Due to the routing mechanics, the same spatial bending configuration or trajectory can be produced by an infinite combination of internal tendon tensions. This severe actuation redundancy leads to:
1. **Mathematical Ill-posedness:** Hard to predict unique tendon inputs for shape control.
2. **Computational Inefficiency:** Extreme overhead in multi-segment and multi-routing forward/inverse kinematic simulations.

While historical methods (such as Clarke-based reduction) work well for symmetric 2D planar robots, they **completely fail when handling 3D complex torsion, large multi-segment deformations, or non-symmetric routings**.

---

## 🚀 Core Contributions & Methodology
To bridge this gap, this work introduces a unified mathematical framework leveraging **Singular Value Decomposition (SVD)** integrated with **Cosserat Rod Theory** and Lie groups ($SE(3)$):

1. **Exact Dimension Reduction:** The highly redundant, high-dimensional physical tendon tension space is projectively mapped into a minimal, non-redundant, low-dimensional virtual actuation coordinate system.
2. **3D Torsion Compatibility:** Proven mathematically and experimentally to seamlessly capture 3D multi-axial deformations (bending + twisting), unlocking capabilities where classical methods fail.
3. **~5x Computational Speedup:** By eliminating internal tension redundancies during iterative solver steps, the simulation speed is accelerated by approximately **500%**, facilitating real-time closed-loop force/position control.
4. **Multi-Segment Scalability:** Demonstrated versatile performance on multi-routing, multi-segment continuum systems under intense physical boundaries.

---

## 📊 Key Results (Sim2Real Validation)
* **Example 1 (Planar Bending):** Achieved sub-millimeter tip tracking precision with unified coordinates.
* **Example 2 (3D Spiral Torsion):** Traditional Clarke reduction yielded a **22.33% Max Tip Error** due to missing torsional constraints. Our **SVD Method reduced the Max Tip Error to 0.36%**.
* **Real-Time Efficiency:** Forward modeling time reduced drastically, allowing high-frequency embedding.

---

## 📂 Repository Structure
```text
├── README.md               # This project overview
├── doc/
│   └── ICRA2026_Poster.pdf # High-quality PDF of the presented workshop poster
└── src/                    # (提示：后续如果您打算开源算法，可以在此文件夹放置MATLAB/Python核心矩阵转换代码)
    └── svd_reduction.m     # Core SVD reduction function snippet


If you find this theory or method helpful for your continuum/soft robotics research, please cite our workshop paper or the corresponding PhD dissertation chapter:

@inproceedings{zhang2026svd,
  author    = {Zhang, Zibo and Chikhaoui, M. Taha and Lebastard, Vincent and Boyer, Fr{\'e}d{\'e}ric},
  title     = {From Redundant Tendon Tensions to Low-Dimensional Actuation Coordinates: A SVD-Based Method for Tendon-Actuated Continuum Robots},
  booktitle = {IEEE International Conference on Robotics and Automation (ICRA 2026) Workshop on AI-Driven Soft Robotics: Innovations, Challenges, and Future Directions},
  address   = {Vienna, Austria},
  month     = {June},
  year      = {2026}
}

@phdthesis{zhang2025modelisation,
  author  = {Zhang, Zibo},
  title   = {Mod{\'e}lisation, pr{\'e}diction de forme et {\'e}limination de la redondance d'actionnement dans les robots continus actionn{\'e}s par c{\^a}bles},
  school  = {IMT Atlantique / Universit{\'e} Grenoble Alpes},
  year    = {2025},
  note    = {Chapter 4: {\'E}limination et analyse de la redondance d'actionnement}
}

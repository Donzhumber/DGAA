# Identifying Rational Types in Unknown Environments under an Indirect Dynamic Mechanism

[![Target Journal: Dynamic Games and Applications](https://img.shields.io/badge/Journal-Dynamic%20Games%20and%20Applications-blue.svg)](https://link.springer.com/journal/13235)
[![Publisher: Springer Nature](https://img.shields.io/badge/Publisher-Springer%20Nature%20%2F%20Birkh%C3%A4user-orange.svg)](https://www.springer.com)
[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://7kkgn4sfscykkfvv5794qw.streamlit.app/)
[![Lean 4 Verified](https://img.shields.io/badge/Formal%20Verification-Lean%204-brightgreen.svg)](https://leanprover.github.io/)
[![Python 3.9+](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://www.python.org/)
[![Stata](https://img.shields.io/badge/Empirical-Stata%2012%E2%80%9319-lightblue.svg)](https://www.stata.com/)

**Author:** Prof. Humberto Bernal, Ph.D.  
**Repository:** [https://github.com/Donzhumber/DGAA.git](https://github.com/Donzhumber/DGAA.git)  
**Target Journal:** *Dynamic Games and Applications* (Springer Nature / Birkhäuser)  
**ISSN:** 2153-0785 (print) / 2153-0793 (electronic)  
**Submission Fee:** $0 (Free Submission)  
**Peer Review Model:** Single-Blind  

---

## Abstract

This paper develops an indirect dynamic mechanism design framework to identify rational types in unknown, non-stationary environments where the principal faces asymmetric information, unobserved private types, and strategic learning. By combining dynamic mechanism design with Bayesian belief updating, active entropy exploration subsidies, and deep neural network value approximations, the mechanism induces incentive-compatible screening and dynamic identification.

The theoretical framework is empirically calibrated using micro-level competing-hazards duration data from kidnappings in Colombia (Centro Nacional de Memoria Histórica - CNMH / SIEVCAC). Key mathematical derivations and asymptotic identification lemmas are machine-checked using the **Lean 4 Interactive Theorem Prover**. The backward induction curse of dimensionality is solved via Multilayer Perceptrons (MLPs) implemented in **PyTorch**, deployed through an interactive **Streamlit** simulation portal.

---

## Interactive Simulation Portal

The dynamic mechanism simulation engine can be explored live without local installation:
- **Interactive Web App:** [https://7kkgn4sfscykkfvv5794qw.streamlit.app/](https://7kkgn4sfscykkfvv5794qw.streamlit.app/)

---

## Repository Structure

```text
DGAA/
├── README.md                      # Primary documentation (this file)
├── main/                          # Main manuscript LaTeX source & compiled PDF
│   ├── Bernal_H_DGAA.tex          # Primary article (Springer sn-jnl class)
│   ├── Bernal_H_DGAA.pdf          # Compiled single-blind manuscript (55 pages)
│   ├── references.bib             # Complete bibliography database
│   ├── sn-jnl.cls                 # Springer Nature document class
│   ├── sn-mathphys-ay.bst         # Springer bibliography style
│   └── Figures/                   # Vector graphics (110 figures in PDF/PNG)
├── appendix_A_micro/              # Appendix A: Microeconometric Empirical Calibration
│   ├── Appendix_A_Micro.tex       # LaTeX source for Appendix A
│   ├── Appendix_A_Micro.pdf       # Compiled PDF for Appendix A
│   └── scripts/                   # Stata replication package (run_all.do, data, outputs)
├── appendix_B_proofs/             # Appendix B: Formal Mathematical Proofs & Lean 4
│   ├── Appendix_B_Proofs.tex      # LaTeX source for Appendix B
│   ├── Appendix_B_Proofs.pdf      # Compiled PDF for Appendix B
│   ├── replicate.sh               # Shell script for Lean 4 formal verification
│   └── lean/                      # Lean 4 project (AppendixBProofs.lean, lakefile.lean)
├── Appendix_C_Streamlit/          # Appendix C: Simulation Engine & Deep Learning
│   ├── Appendix_C_Streamlit.tex   # LaTeX source for Appendix C
│   ├── Appendix_C_Streamlit.pdf   # Compiled PDF for Appendix C
│   ├── app_DL.py                  # Streamlit simulation web app
│   ├── train_captor_value_net.py  # PyTorch value approximation neural networks
│   ├── captor_value_net_T10.pt    # Pre-trained state continuation value network
│   ├── captor_true_type_value_net_T10.pt # Pre-trained agent optimal response network
│   ├── run_app.command            # Double-click launcher for macOS
│   ├── run_app.bat                # Double-click launcher for Windows
│   └── requirements.txt           # Python package dependencies
├── additional_documents/          # Administrative & submission declarations
│   ├── cover_letter.tex / .pdf    # Cover letter to the DGAA Editorial Board
│   ├── highlights.tex / .pdf      # 4 core research highlights
│   └── declaration_of_interest.tex / .pdf # Conflict of interest declaration
└── UPLOAD_FILES/                  # Pre-packaged archives ready for editorial submission
    ├── 01_MANUSCRIPT_DGAA.zip     # Complete LaTeX bundle for main manuscript
    ├── 02_Supplementary_Appendix_A.zip # Appendix A bundle (Stata scripts + data)
    ├── 03_Supplementary_Appendix_B.zip # Appendix B bundle (Lean 4 project + proofs)
    ├── 04_Supplementary_Appendix_C.zip # Appendix C bundle (Streamlit code + models)
    ├── Bernal_H_DGAA.pdf          # Full compiled manuscript
    ├── cover_letter.pdf           # Submission cover letter
    ├── highlights.pdf             # Highlights document
    └── declaration_of_interest.pdf# Competing interest disclosure
```

---

## Replication Instructions

### 1. Appendix A: Microeconometric Calibration (Stata)
- **Software:** Stata 12 or newer (optimized for Stata 19).
- **Execution:**
  ```stata
  cd "appendix_A_micro/scripts"
  do run_all.do
  ```
- **Outputs:** Generates all Multinomial Logit and cause-specific Cox competing-hazards models in `appendix_A_micro/scripts/outputs/`.

### 2. Appendix B: Formal Proofs (Lean 4)
- **Software:** Lean 4 (via `elan`).
- **Execution:**
  ```bash
  cd appendix_B_proofs
  chmod +x replicate.sh
  ./replicate.sh
  ```
- **Outputs:** Formally verifies all lemmas, dependency graphs, and asymptotic propositions against Mathlib (`AppendixBProofs.lean`), logging confirmation in `lean/build.log`.

### 3. Appendix C: Interactive Simulation & PyTorch Value Networks (Python)
- **Software:** Python 3.9+.
- **Quick Launch:**
  - **macOS:** Double-click `Appendix_C_Streamlit/run_app.command`.
  - **Windows:** Double-click `Appendix_C_Streamlit/run_app.bat`.
- **Manual Launch:**
  ```bash
  cd Appendix_C_Streamlit
  python3 -m venv venv
  source venv/bin/activate  # On Windows: venv\Scripts\activate
  pip install -r requirements.txt
  streamlit run app_DL.py
  ```

---

## Submission Guide for Springer Nature / Editorial System

When uploading files to the *Dynamic Games and Applications* submission portal:

| Item | File / Package | Recommended Submission Category |
| :--- | :--- | :--- |
| **1** | `UPLOAD_FILES/01_MANUSCRIPT_DGAA.zip` (or `Bernal_H_DGAA.pdf`) | **Manuscript** |
| **2** | `UPLOAD_FILES/cover_letter.pdf` | **Cover Letter** |
| **3** | `UPLOAD_FILES/highlights.pdf` | **Highlights** |
| **4** | `UPLOAD_FILES/declaration_of_interest.pdf` | **Declaration of Interest** |
| **5** | `UPLOAD_FILES/02_Supplementary_Appendix_A.zip` | **Supplementary Material** |
| **6** | `UPLOAD_FILES/03_Supplementary_Appendix_B.zip` | **Supplementary Material** |
| **7** | `UPLOAD_FILES/04_Supplementary_Appendix_C.zip` | **Supplementary Material** |

---

## Citation

```bibtex
@article{bernal2026dynamic,
  title   = {Identifying Rational Types in Unknown Environments under an Indirect Dynamic Mechanism},
  author  = {Bernal, Humberto},
  journal = {Dynamic Games and Applications},
  year    = {2026},
  note    = {Under review}
}
```

---

## License & Contact

- **Author:** Prof. Humberto Bernal, Ph.D.
- **Repository:** [https://github.com/Donzhumber/DGAA.git](https://github.com/Donzhumber/DGAA.git)

# Pricing European Options via Martingales

**From the binomial model to Girsanov's theorem and the Black-Scholes formula**

Bachelor's thesis in Mathematics — University of Oviedo, Faculty of Science, September 2026.

[![PDF (English)](https://img.shields.io/badge/PDF-English-blue.svg)](en/thesis_en.pdf)
[![PDF (Español)](https://img.shields.io/badge/PDF-Espa%C3%B1ol-blue.svg)](es/tfg_es.pdf)
[![License: CC BY-NC-ND 4.0](https://img.shields.io/badge/License-CC%20BY--NC--ND%204.0-lightgrey.svg)](LICENSE)

## About this work

This repository contains my *Trabajo de Fin de Grado* (bachelor's thesis) for the Degree in Mathematics at the University of Oviedo, written as part of the double degree in Mathematics and Physics and supervised by **José Santos Domínguez Menchero**. The thesis was written and defended in Spanish; an English version is provided so that the work is accessible to a wider audience (see the note on the translation below).

The thesis is a self-contained, rigorous development of the theory of European option pricing, from the one-period binary model up to the proof of the Black-Scholes formula, built entirely on the **martingale approach** rather than the classical PDE route. Its guiding thread is the correspondence between the discrete and the continuous settings: every tool of stochastic calculus introduced in the second half (Itô integral, Itô's formula, Girsanov's theorem, martingale representation) is presented as the continuous-time counterpart of an elementary object already met in the binomial model.

## Abstract

This work develops, in a self-contained and mathematically rigorous manner, the theory of European option pricing, culminating in the proof of the Black-Scholes formula for the European call option. The approach adopted is carried out in a unified way: we first formulate the problem in the discrete setting of the multi-period binomial model, where the central conceptual ideas (no-arbitrage principle, replication, risk-neutral measure, martingale representation) are accessible with elementary probability tools; we then translate the problem and its resolution to the continuous setting of the Black-Scholes model, developing along the way the necessary apparatus of stochastic calculus. The chosen approach, via martingales rather than the classical route of partial differential equations, makes transparent the translation of the ideas from the discrete case to the continuous case, and allows the Black-Scholes formula to be presented as the natural limit of the multi-period binomial formula when the time steps become infinitely small. Thus, the development requires introducing and constructing in detail a substantial part of the stochastic calculus needed for the continuous setting: the Itô integral, Girsanov's theorem and the martingale representation theorem. These tools are not only necessary for the purposes of this work, but also play a central role in the theory of stochastic processes. The dissertation also includes the derivation of the classical Black-Scholes PDE from the formula obtained via martingales, thus showing the consistency between the two formulations.

**Keywords:** no-arbitrage, martingale, Itô integral, Girsanov's theorem, martingale representation, Black-Scholes formula.

## Contents

| Chapter | Content |
|---|---|
| 1. Introduction | Motivation, historical context, objectives, sources and own contribution, structure. |
| 2. Option pricing in discrete time | No-arbitrage principle and replication; the forward as a warm-up; one-period binary model, emergence of the risk-neutral measure, trinomial model and incompleteness; multi-period binomial model with the full probabilistic machinery (filtrations, conditional expectation, discrete-time martingales, predictable processes, discrete stochastic integral, binomial representation theorem); the three-step pricing recipe; heuristic passage to continuous time. |
| 3. Brownian motion | Definition and existence; nowhere differentiability, unbounded variation and quadratic variation of the paths (with full proof); the augmented Brownian filtration and continuous martingales. |
| 4. Stochastic calculus | Why a new integral is needed (a no-arbitrage argument); construction of the Itô integral on simple processes, the Itô isometry, extension to $\mathcal{H}^2$ by density, the indefinite integral as a continuous martingale; Itô's formula (with proof for $f(W_t)$); change of measure, Novikov's condition and Girsanov's theorem (with proof via Lévy's characterization); the Brownian martingale representation theorem; synthesis of the discrete–continuous correspondence. |
| 5. The Black-Scholes model | Market assumptions, portfolios and the self-financing condition in continuous time; the three-step recipe in the continuous setting (Girsanov, the $\mathbb{Q}$-martingale of the discounted payoff, representation and replication); the Black-Scholes formula for the European call; derivation of the Black-Scholes PDE and the Feynman–Kac connection. |
| 6. Conclusions | Summary, convergence of the binomial formula to Black-Scholes, reflection on the approach, further directions. |

Some proofs that the standard references present in summary form or at a higher level of generality have been developed in full detail and adapted to the Brownian setting: the Itô isometry step by step, the extension of the integral to $\mathcal{H}^2$ and the continuity of the indefinite integral, Itô's formula for functions of Brownian motion, Girsanov's theorem, and the verification that the replicating strategy in the Black-Scholes model is self-financing.

## Repository structure

```
option-pricing-via-martingales/
├── README.md
├── LICENSE
├── .gitignore
├── en/
│   ├── thesis_en.tex      English version (LaTeX source)
│   ├── thesis_en.pdf      English version (compiled)
│   └── logo_uniovi.png
└── es/
    ├── tfg_es.tex         Spanish original (LaTeX source)
    ├── tfg_es.pdf         Spanish original (compiled)
    └── logo_uniovi.png
```

## Building from source

Both versions compile with a standard TeX Live distribution (`pdflatex` + `latexmk`). Required packages: `babel`, `amsmath`, `amssymb`, `amsthm`, `mathtools`, `bm`, `geometry`, `setspace`, `tikz`, `enumitem`, `booktabs`, `caption`, `hyperref`, `xcolor`.

```bash
cd en && latexmk -pdf thesis_en.tex     # English version
cd es && latexmk -pdf tfg_es.tex        # Spanish version
```

## On the English translation

The thesis was written and defended in Spanish. The English version was produced by the author with the assistance of AI translation tools (Anthropic's Claude) and then revised in full by the author. The mathematical content, structure and numbering of results are identical in both versions; the Spanish text remains the reference version, and any remaining infelicities in the English are the author's responsibility.

## Continuation of this work

The natural next step after this thesis is to move from theory to numerical practice and beyond the Black-Scholes assumptions. That is the purpose of my companion repository [**quant-finance-portfolio**](https://github.com/indexxxxbraker/quant-finance-portfolio): a derivative pricing library implemented in parallel in Python and C++, covering analytical Black-Scholes pricing and Greeks, Monte Carlo methods with variance reduction and quasi-Monte Carlo, finite-difference PDE schemes and lattices, and the Heston stochastic volatility model with Fourier, Monte Carlo (Andersen QE) and ADI-PDE pricers, calibration, and exotic options — each method cross-validated against independent ones.

## Main references

- A. Etheridge, *A Course in Financial Calculus*, Cambridge University Press, 2002.
- I. Karatzas and S. E. Shreve, *Brownian Motion and Stochastic Calculus*, 2nd ed., Springer, 1991.
- S. E. Shreve, *Stochastic Calculus for Finance II: Continuous-Time Models*, Springer, 2004.
- D. Williams, *Probability with Martingales*, Cambridge University Press, 1991.
- B. Øksendal, *Stochastic Differential Equations: An Introduction with Applications*, 6th ed., Springer, 2003.
- F. Black and M. Scholes, "The pricing of options and corporate liabilities", *Journal of Political Economy* 81 (1973), 637–654.
- R. C. Merton, "Theory of rational option pricing", *Bell Journal of Economics and Management Science* 4 (1973), 141–183.

## Author

**Roberto Cepeda Rocandio** — Mathematics & Physics undergraduate, University of Oviedo.

LinkedIn: [linkedin.com/in/robertocepedarocandio](https://www.linkedin.com/in/robertocepedarocandio) · Email: robertocepedarocan@gmail.com

## License

The text of this thesis is licensed under [CC BY-NC-ND 4.0](LICENSE): you may share it with attribution, but not modify it or use it commercially.

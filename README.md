# Quantitative Credit Risk Modelling in Python

A Jupyter notebook that implements the main building blocks of credit risk measurement, from the Basel IRB capital formula to counterparty credit risk, using Monte Carlo simulation and numerical calibration. Notation and benchmark examples follow chapter 3 (*Credit Risk*) of Roncalli, *Handbook of Financial Risk Management* (CRC Press, 2020).

**Notebook:** [`credit_risk_modelling.ipynb`](credit_risk_modelling.ipynb) (outputs and plots are saved, so it renders directly on GitHub)

## What is inside

| Section | Topics | Techniques |
|---|---|---|
| **1. Basel IRB model** | Vasicek one-factor model, loss quantile as a function of the confidence level α, PD, LGD and asset correlation ρ | Closed-form IRB formula, sensitivity analysis |
| **2. LGD estimation** | Beta distribution calibrated with method of moments and maximum likelihood; portfolio VaR under empirical, Beta and constant (granular) LGD | Moment matching, MLE (`scipy.stats.beta.fit`), Monte Carlo with 10⁶ scenarios |
| **3. Default probability** | Merton structural model; CIR intensity model and CDS fair premium; hazard rates (exponential, Gompertz, piecewise exponential); hazard rates from a rating migration matrix | Non-linear root finding, least-squares calibration, matrix powers of a Markov chain |
| **4. Default correlation** | Gaussian one-factor copula, loss distribution, VaR and Expected Shortfall for ρ = 0, 0.2, 0.5 | Monte Carlo with common random numbers |
| **5. Counterparty credit risk** | Exposure profile of a long call position, expected exposure, potential future exposure, CVA | Risk-neutral simulation, Monte Carlo vs closed-form check |

## Selected results

| Analysis |
|---|---|
| Beta calibration of 13 observed LGDs |
| Portfolio of 10 loans, VaR 99% / 99.5% / 99.9% |
| Merton model (equity 15,500, debt face value 40,000, σ_E = 18%) |
| CDS on a CIR intensity (λ₀ = 0.25), 5-year protection |
| One-factor copula, VaR 99% (ρ = 0 / 0.2 / 0.5) |
| Long call position (100 options, strike 100, S(t₀) = 114.77) |


## References

- T. Roncalli, *Handbook of Financial Risk Management*, CRC Press, 2020 (chapter 3, Credit Risk).
- O. Vasicek, *Probability of Loss on Loan Portfolio*, KMV, 1987.
- R. C. Merton, *On the Pricing of Corporate Debt: The Risk Structure of Interest Rates*, Journal of Finance, 29(2), 1974.

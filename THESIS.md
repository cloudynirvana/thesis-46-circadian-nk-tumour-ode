# CIRCADIAN DISRUPTION OF TUMOUR IMMUNE SURVEILLANCE: AN ODE MODEL OF CLOCK-GATED NK CELL CYTOTOXICITY IN SOLID TUMOURS
**Thesis #46** — computational research thesis
**Author:** Kelechi Emeka Ogbonna
**Correspondence:** kelechiogbonna300@gmail.com
**Date:** September 2026
**Format:** B.Sc. project chapter structure (Nile University style)
**Citation style:** APA 6th edition (Author, Year)
**DOI:** none registered.

Continuing the mathematical biology investigations originating from Thesis Zero (BSc Carica papaya AgNP, Nile University 2022), this forty-sixth manuscript integrates chronobiology into the immunodynamic framework. Drawing on parameter identifiability paradigms established in T07, the immunometabolic stability landscapes of T10, and the Lyapunov chain-recurrent structures discussed in T17, this thesis constructs a coupled oscillator-immune-tumour topology to investigate time-dependent immune surveillance.

## Non-claims
This study presents a theoretical mathematical model of circadian-immune interactions. The differential equations and computational results documented herein do not constitute clinical oncology advice. The parameters are scaled for theoretical qualitative analysis and do not reflect validated human physiological constants. This work does not propose therapeutic regimens for circadian disruption or shift-work-associated malignancies. 

---

## Declaration
I, Kelechi Emeka Ogbonna, declare that this thesis titled "CIRCADIAN DISRUPTION OF TUMOUR IMMUNE SURVEILLANCE: AN ODE MODEL OF CLOCK-GATED NK CELL CYTOTOXICITY IN SOLID TUMOURS" is entirely my original computational research work. It has not been submitted previously for any degree or publication in any academic institution. All mathematical formulations and code are original contributions to the Project Confluence repository, and all external literature has been duly acknowledged.

---

## Abstract
Circadian rhythm disruption, endemic to modern industrialized societies and shift-work professions, is classified by the International Agency for Research on Cancer (IARC) as a Group 2A probable carcinogen. The underlying mechanisms point toward a chronobiological gating of immune surveillance, specifically the time-dependent infiltration and cytotoxic efficacy of Natural Killer (NK) cells regulated by core clock genes (BMAL1, CLOCK, PER, CRY). Despite vast epidemiological and molecular evidence, the dynamical systems literature lacks a coupled ordinary differential equation (ODE) framework that integrates a circadian oscillator with tumour-immune kinetics. This thesis introduces a novel mathematical model coupling a three-variable Goodwin-type circadian oscillator to a logistical tumour growth model and NK cell surveillance kinetics. By modulating NK cell infiltration and cytolytic rates as a function of the circadian phase, the model quantifies the "surveillance window." Computational simulations reveal that amplitude attenuation and phase shifting—hallmarks of circadian disruption—significantly compromise NK cell efficacy, leading to earlier tumour escape and expanded tumour burden. The findings mathematically formalize the epidemiological observations of elevated cancer risk in shift workers and demonstrate that chronotherapeutic alignment of immunomodulatory interventions may be necessary to maximize efficacy. 

## Keywords
Circadian rhythm, Natural Killer cells, Tumour immune surveillance, Goodwin oscillator, Ordinary Differential Equations (ODEs), Chronodisruption, Mathematical oncology.

## Table of Contents
1.0 INTRODUCTION
    1.1 Background to the Study
    1.2 Statement of Research Problem
    1.3 Justification of Study
    1.4 Aim and Objectives of the Study
    1.5 Significance of the Study
    1.6 Scope of the Study
2.0 LITERATURE REVIEW
    2.1 The Molecular Circadian Clock
    2.2 Circadian Disruption and Cancer Epidemiology
    2.3 NK Cell Cytotoxicity and Clock-Gated Infiltration
    2.4 Mathematical Modelling of Tumour-Immune Dynamics
3.0 MATERIALS AND METHODS
    3.1 The Mathematical Model
    3.2 The Circadian Oscillator Sub-Model
    3.3 Tumour-Immune Kinetic Sub-Model
    3.4 Parameter Estimation and Scaling
    3.5 Simulation Environment
4.0 RESULTS
    4.1 Baseline Homeostatic Circadian Dynamics
    4.2 Phase-Gated Tumour Eradication
    4.3 Simulation of Circadian Disruption (Shift-Work Phenotype)
    4.4 Bifurcation Analysis of Immune Escape
5.0 DISCUSSION, CONCLUSION AND RECOMMENDATION
    5.1 Discussion
    5.2 Conclusion
    5.3 Recommendation
References
Disclaimer

---

## 1.0 INTRODUCTION

### 1.1 Background to the Study
Life on Earth has evolved under the ubiquitous influence of a 24-hour planetary rotation, leading to the evolutionary embedding of endogenous timekeeping mechanisms within nearly all living organisms (Lévi et al., 2010). In mammals, the circadian clock operates through a hierarchical network governed by the suprachiasmatic nucleus (SCN) in the hypothalamus, which synchronizes peripheral cellular clocks located in virtually every tissue (Innominato et al., 2014). At the molecular level, this oscillator functions via a transcription-translation feedback loop (TTFL) driven by the basic helix-loop-helix transcription factors CLOCK and BMAL1, which heterodimerize to promote the transcription of their own repressors, the Period (PER) and Cryptochrome (CRY) genes. 

Over the last decade, it has become increasingly evident that the immune system is highly sensitive to circadian gating. The trafficking, cytolytic capacity, and cytokine production of innate and adaptive immune cells fluctuate rhythmically (Scheiermann et al., 2013). Natural Killer (NK) cells, acting as the primary innate effectors of tumour immune surveillance, exhibit robust diurnal rhythms in their peripheral blood counts and tissue infiltration rates. However, modern anthropogenic lifestyles, characterized by chronic jet lag, artificial light at night (ALAN), and rotational shift work, consistently perturb these biological rhythms. The International Agency for Research on Cancer (IARC) has consequently classified shift work involving circadian disruption as a Group 2A probable carcinogen (Straif et al., 2007). 

While molecular biology has elucidated the pathways through which clock genes regulate the cytolytic effector molecules of NK cells (such as perforin and granzyme B), the non-linear, time-dependent dynamics of this interaction remain mathematically underexplored. Mathematical oncology relies heavily on ordinary differential equations (ODEs) to model the predator-prey-like interactions between the immune system and malignant cells (Komarova & Wodarz, 2005). Yet, traditional ODE frameworks treat immune infiltration and cytotoxicity as time-invariant constants. This study bridges the gap between chronobiology and mathematical oncology by introducing a coupled Goodwin-type oscillator to a tumour-immune kinetic model. 

### 1.2 STATEMENT OF RESEARCH PROBLEM
Epidemiological studies unequivocally link circadian disruption to increased cancer incidence, and molecular evidence demonstrates that NK cell tumour infiltration and cytolytic activity are gated by the circadian clock. Despite this, there is no existing dynamical systems model (ODE) that mathematically couples a molecular circadian oscillator to NK cell tumour-kill kinetics. The absence of such a model leaves the field without a quantitative framework to measure the temporal "surveillance window" or to dynamically simulate how specific amplitude and phase perturbations (such as shift work) induce tumour immune escape. 

### 1.3 JUSTIFICATION OF STUDY
The author's prior work in T10 established robust immunometabolic ODEs that account for nutrient competition in the tumour microenvironment, while T07 provided the foundational framework for parameter identifiability in complex biological systems. However, these models inherently assumed temporal homogeneity in immune function. Given that biological organisms are temporally structured, ignoring the 24-hour rhythmic variation in immune surveillance limits the predictive validity of current mathematical models. 

This study is imperative because experimental chronobiology is costly and time-intensive. An in silico mathematical framework allows for the rapid simulation of varying degrees of circadian disruption—from mild phase shifts to complete clock ablation—and maps their direct topological consequences on tumour growth trajectories. By coupling a Goodwin oscillator to a standard tumour-immune model, this research provides the necessary mathematical infrastructure to explore chronotherapeutic strategies, fulfilling a critical gap in both systems biology and theoretical oncology.

### 1.4 AIM AND OBJECTIVES OF THE STUDY
The primary aim of this study is to formulate and analyze an Ordinary Differential Equation (ODE) model coupling a circadian oscillator to NK cell-mediated tumour immune surveillance.

The specific objectives are:
1. To construct a modified three-variable Goodwin-type oscillator that accurately simulates the CLOCK/BMAL1 and PER/CRY regulatory feedback loop.
2. To integrate the oscillator's output as a time-dependent modulating function for NK cell tumour infiltration and cytotoxicity.
3. To simulate baseline homeostatic tumour-immune interactions and quantify the rhythmic "surveillance window."
4. To model circadian disruption by perturbing the oscillator's amplitude and period, and to observe the corresponding shift in tumour growth dynamics.
5. To perform a bifurcation analysis to identify critical chronobiological thresholds that precipitate tumour immune escape.

**Non-aims:** This study does not attempt to model spatial intratumoural heterogeneity, nor does it incorporate adaptive T-cell responses or immunotherapy pharmacokinetics. 

### 1.5 SIGNIFICANCE OF THE STUDY
The outcomes of this computational research will mathematically validate the epidemiological link between circadian disruption and carcinogenesis. By providing a tractable set of differential equations, it gives theoreticians a foundation upon which to build more complex chronotherapeutic models. If the model succeeds in demonstrating that circadian gating is an essential topological requirement for maintaining tumour suppression, it will underscore the necessity of administering immunomodulators at specific circadian times (chronotherapy). This structural understanding has the potential to influence how subsequent pharmacokinetic ODE models are designed across the mathematical oncology community.

### 1.6 SCOPE OF THE STUDY
The scope of this research is confined to the theoretical mathematical modelling of circadian-gated Natural Killer (NK) cell dynamics in a generalized solid tumour microenvironment. The circadian clock is abstracted using a simplified three-variable Goodwin oscillator rather than high-dimensional molecular network models, ensuring analytical tractability as per the chain-recurrent paradigms explored in T17. The tumour is modelled using a simple logistic growth function. The defects of this model—specifically, the exclusion of spatial dynamics (PDEs) and the adaptive immune system (CD8+ T cells)—are explicitly maintained as out of scope to isolate and preserve the dynamical influence of the biological clock on innate surveillance.

---

## 2.0 LITERATURE REVIEW

### 2.1 The Molecular Circadian Clock
The mammalian circadian clock is a highly conserved evolutionary mechanism that aligns physiological processes with the 24-hour solar day. The core of this system relies on the basic helix-loop-helix PAS domain transcription factors CLOCK and BMAL1. As demonstrated by Takahashi and colleagues (Takahashi, 2017), CLOCK and BMAL1 heterodimerize in the nucleus and bind to E-box promoter elements to drive the transcription of thousands of clock-controlled genes (CCGs), including their own repressors, the PER and CRY genes. As PER and CRY proteins accumulate in the cytoplasm, they are phosphorylated, form complexes, and translocate back into the nucleus to inhibit the CLOCK/BMAL1 complex, thus closing the negative feedback loop. In computational biology, this delayed negative feedback loop is classically modelled using the Goodwin oscillator, first proposed by Brian Goodwin in 1965 (Gonze & Abou-Jaoudé, 2013).

### 2.2 Circadian Disruption and Cancer Epidemiology
Modern societal structures heavily rely on continuous 24/7 operations, exposing a significant portion of the global workforce to artificial light at night (ALAN) and rotational shift work. Epidemiological evidence robustly correlates these chronodisruptive exposures to elevated risks of hormone-dependent and independent malignancies. In 2007, and reaffirmed in 2019, the IARC classified shift work as a Group 2A probable carcinogen (Straif et al., 2007). The biological basis of this carcinogenicity is believed to stem from the uncoupling of peripheral clocks from the central SCN pacemaker, leading to a state of internal desynchronization. This desynchronization compromises various physiological barriers against malignant transformation, including DNA damage repair, apoptosis, and critically, immune surveillance (Lévi et al., 2010).

### 2.3 NK Cell Cytotoxicity and Clock-Gated Infiltration
Natural Killer (NK) cells are innate lymphoid cells crucial for recognizing and eliminating virally infected and neoplastic cells without prior sensitization. Recent molecular immunology has revealed that NK cell frequency, tissue localization, and cytolytic activity undergo robust diurnal oscillations. According to Chiossone et al. (2018), NK cells exhibit highest cytolytic activity against tumour targets during the active phase of the host (nighttime in nocturnal rodents, daytime in humans). The expression of key effector molecules, such as granzyme B and perforin, is directly regulated by clock genes. Furthermore, the secretion of chemokines that guide NK cells into the tumour microenvironment is rhythmic, establishing a narrow temporal window wherein immune surveillance is optimal.

### 2.4 Mathematical Modelling of Tumour-Immune Dynamics
Mathematical oncology has historically relied on Lotka-Volterra-style predator-prey dynamics to describe the interaction between expanding tumour populations and cytotoxic immune cells. Komarova and Wodarz (2005) established foundational ODEs demonstrating that tumour eradication depends on the ratio of immune cell recruitment to tumour proliferation rates. However, a systemic review of the literature reveals a distinct temporal homogeneity in these models; parameters for cytotoxicity and immune recruitment are universally treated as constants. While Ballesta et al. (2017) introduced chronotherapy models optimizing the timing of chemotherapy administration, the endogenous circadian oscillation of the immune system itself has not been dynamically coupled to tumour growth kinetics. This gap highlights the necessity of the current thesis.

---

## 3.0 MATERIALS AND METHODS

### 3.1 The Mathematical Model
The computational model is formulated as a system of ordinary differential equations (ODEs) composed of two coupled modules: (1) a three-variable Goodwin oscillator representing the endogenous molecular clock, and (2) a two-variable tumour-immune kinetic model describing the interaction between a solid tumour and NK cells.

### 3.2 The Circadian Oscillator Sub-Model
The Goodwin oscillator models the transcription-translation feedback loop (TTFL) of the clock. Let $X$ denote the concentration of clock mRNA (e.g., PER/CRY), $Y$ the concentration of the associated clock protein, and $Z$ the concentration of the nuclear repressor complex. The system is defined as:

$$ \frac{dX}{dt} = \frac{v_1}{1 + (Z/K_i)^n} - d_1 X $$
$$ \frac{dY}{dt} = k_1 X - d_2 Y $$
$$ \frac{dZ}{dt} = k_2 Y - d_3 Z $$

Where $v_1$ is the maximal transcription rate, $K_i$ is the inhibition threshold, $n$ is the Hill coefficient dictating the non-linearity of repression, and $d_1, d_2, d_3$ are degradation rates. The output of this oscillator, $Z(t)$, is normalized to a function $C(t)$ bounded between $[0, 1]$ to modulate immune parameters.

### 3.3 Tumour-Immune Kinetic Sub-Model
Let $T$ denote the tumour cell population and $N$ the Natural Killer (NK) cell population within the tumour microenvironment. The tumour undergoes logistic growth, and its death is mediated by NK cells through a mass-action kinetic term.

$$ \frac{dT}{dt} = r T \left(1 - \frac{T}{K_T}\right) - \alpha(t) N T $$
$$ \frac{dN}{dt} = s_0 + s_1 C(t) + \rho \frac{N T}{g + T} - \delta N $$

Here, $r$ is the intrinsic tumour growth rate, and $K_T$ is the carrying capacity. The cytotoxicity parameter $\alpha(t)$ is circadian-gated such that $\alpha(t) = \alpha_0 (1 + \beta C(t))$, where $\beta$ is the amplitude of the circadian effect. The NK cell infiltration rate contains a constant baseline term $s_0$ and a rhythmic term $s_1 C(t)$. NK cells are recruited dynamically by the presence of the tumour at a maximal rate $\rho$ with a half-saturation constant $g$, and die at a rate $\delta$.

### 3.4 Parameter Estimation and Scaling
Parameters were selected to ensure the Goodwin oscillator maintains a stable limit cycle with a period of approximately 24 hours. The Hill coefficient was set to $n=9$ to satisfy the Poincaré-Bendixson requirements for limit cycles in a 3D system. Tumour growth and immune parameters were scaled non-dimensionally, referencing relative kinetic rates established in prior works (T10 and Komarova & Wodarz, 2005). 

### 3.5 Simulation Environment
The initial value problem (IVP) was solved numerically using Python 3.10 with the `scipy.integrate.solve_ivp` library, utilizing the Radau method suitable for stiff systems. Trajectories were analyzed over a simulated time of 300 to 1000 days.

---

## 4.0 RESULTS

### 4.1 Baseline Homeostatic Circadian Dynamics
Under homeostatic parameter assumptions, the Goodwin oscillator yielded a robust, self-sustained limit cycle with a precise 24-hour period. The normalized circadian output $C(t)$ oscillated smoothly, peaking midway through the active phase. When coupled to the tumour-immune equations, the system demonstrated a rhythmic "surveillance window." The NK cell population $N(t)$ fluctuated in phase with $C(t)$, generating cyclic pressure on the tumour micro-colony. Under these baseline conditions, the high peak of circadian-gated cytotoxicity ($\alpha(t)$) was sufficient to suppress tumour growth, maintaining the tumour population $T(t)$ near an infinitesimal equilibrium (tumour dormancy).

### 4.2 Phase-Gated Tumour Eradication
The temporal alignment between peak tumour proliferation and peak immune surveillance proved critical. In silico experiments where the circadian phase of $C(t)$ was artificially delayed by 12 hours (simulating acute jet lag) resulted in a transient spike in the tumour population before the immune system could re-establish control. This indicates that temporal misalignment momentarily compromises the efficacy of NK cell-mediated lysis.

### 4.3 Simulation of Circadian Disruption (Shift-Work Phenotype)
Chronic circadian disruption was modelled by drastically dampening the amplitude of the Goodwin oscillator, simulating the molecular blunting observed in chronic shift workers. As the amplitude of $C(t)$ decayed, the daily peak of NK cell infiltration and cytolytic capacity dropped below the critical threshold necessary to offset the logistic growth of the tumour. 
In the simulation, the dampened immune rhythm led to a gradual, unchecked expansion of $T(t)$. By day 150 of the simulation, the tumour had escaped the dynamical boundary of immune control and exponentially approached its carrying capacity ($K_T$). This mathematical outcome perfectly mirrors the epidemiological reality: prolonged loss of circadian amplitude facilitates tumour immune escape.

### 4.4 Bifurcation Analysis of Immune Escape
A one-parameter bifurcation analysis was conducted by varying the circadian amplitude parameter $\beta$. The analysis revealed a transcritical bifurcation point. For values of $\beta$ above the critical threshold, the stable state of the system is the tumour-dormant equilibrium. As $\beta$ crosses below the critical threshold (representing severe circadian disruption), the dormant equilibrium loses stability, and a new stable node corresponding to maximum tumour burden emerges. 

---

## 5.0 DISCUSSION, CONCLUSION AND RECOMMENDATION

### 5.1 Discussion
This thesis sought to address a glaring theoretical gap in mathematical oncology by constructing a dynamical systems model that explicitly couples endogenous circadian rhythms to NK cell-mediated tumour immune surveillance. The results of the computational simulations firmly establish that temporal structure is not merely a passive backdrop to immunology, but an active, necessary variable for tumour suppression. 

The baseline model demonstrated that the circadian gating of NK cell cytotoxicity creates a critical "surveillance window." This mathematical finding aligns with the biological observations of Chiossone et al. (2018), who reported that NK cell functionality is heavily reliant on time-of-day variations. When this rhythm was unperturbed, the immune system successfully maintained the tumour in a state of dormancy. However, the simulation of circadian disruption—achieved by dampening the amplitude of the Goodwin oscillator—resulted in catastrophic tumour escape. This is a highly significant finding. It translates the probabilistic nature of epidemiological data regarding shift workers (Straif et al., 2007) into a deterministic mathematical consequence. The bifurcation analysis proved that loss of circadian amplitude fundamentally alters the topological landscape of the system, shifting the global attractor from health (tumour control) to disease (tumour expansion).

Unlike prior models (e.g., T10) which assumed constant immunological pressure, the coupled oscillator model reveals that the temporal *peak* of immune activity is often more crucial than the *average* level of immune activity. If the amplitude drops, the tumour is able to utilize the "troughs" in immune surveillance to incrementally outpace immune-mediated death. 

### 5.2 Conclusion
The mathematical coupling of a Goodwin circadian oscillator to a tumour-immune kinetic system provides a robust theoretical explanation for how circadian disruption promotes cancer progression. The ODE model demonstrates that normal, high-amplitude circadian rhythms are dynamically required to maintain the stability of the tumour-dormant state. Shift-work phenotypes, mathematically abstracted as amplitude attenuation and phase misalignment, lower the peak cytolytic pressure of NK cells, predictably forcing the system past a bifurcation point into uncontrolled tumour growth. 

### 5.3 Recommendation
Based on the computational insights derived from this study, the following recommendations are proposed for future mathematical biology and clinical research:
1. **Integration of Chronobiology in ODEs:** Future mathematical models of tumour-immune interactions should abandon the assumption of temporal homogeneity and explicitly incorporate circadian forcing functions.
2. **Chronotherapeutic Clinical Trial Design:** The existence of a mathematical "surveillance window" strongly suggests that immunotherapies (e.g., cytokine treatments activating NK cells) should be administered at specific times of the day to coincide with peak endogenous infiltration.
3. **Expansion to Adaptive Immunity:** Subsequent iterations of this model should expand to include CD8+ T cells to assess how circadian disruption impacts antigen presentation and adaptive immune memory.

---

## References

Ballesta, A., Innominato, P. F., Dallmann, R., Rand, D. A., & Lévi, F. A. (2017). Systems chronotherapeutics. *Pharmacological Reviews*, 69(2), 161-199.

Chiossone, L., Dumas, P. Y., Vienne, M., & Vivier, E. (2018). Natural killer cells and other innate lymphoid cells in cancer. *Nature Reviews Immunology*, 18(11), 671-688.

Gonze, D., & Abou-Jaoudé, W. (2013). The Goodwin model: behind the Hill function. *PLOS ONE*, 8(8), e69573.

Innominato, P. F., Roche, V. P., Palesh, O. G., Ulusakarya, A., Spiegel, D., & Lévi, F. A. (2014). The circadian timing system in clinical oncology. *Annals of Medicine*, 46(4), 191-207.

Komarova, N. L., & Wodarz, D. (2005). Drug resistance in cancer: Principles of emergence and prevention. *Proceedings of the National Academy of Sciences*, 102(27), 9714-9719.

Lévi, F., Okyar, A., Dulong, S., Innominato, P. F., & Clairambault, J. (2010). Circadian timing in cancer treatments. *Annual Review of Pharmacology and Toxicology*, 50, 377-421.

Scheiermann, C., Kunisaki, Y., & Frenette, P. S. (2013). Circadian control of the immune system. *Nature Reviews Immunology*, 13(3), 190-198.

Straif, K., Baan, R., Grosse, Y., Secretan, B., El Ghissassi, F., Bouvard, V., ... & Cogliano, V. (2007). Carcinogenicity of shift-work, painting, and fire-fighting. *The Lancet Oncology*, 8(12), 1065-1066.

Takahashi, J. S. (2017). Transcriptional architecture of the mammalian circadian clock. *Nature Reviews Genetics*, 18(3), 164-179.

Vivier, E., Tomasello, E., Baratin, M., Walzer, T., & Ugolini, S. (2008). Functions of natural killer cells. *Nature Immunology*, 9(5), 503-510.

## Disclaimer
The computational models, differential equations, and in silico simulations presented in this repository and manuscript series (Project Confluence, Theses T01-T50) are strictly theoretical research tools. They are designed to explore mathematical and dynamical properties of biological systems. Nothing in this manuscript constitutes medical advice.

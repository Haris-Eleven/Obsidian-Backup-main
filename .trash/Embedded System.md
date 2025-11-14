# RTOS Numerical and Formula Summary (Obsidian Ready)

  

This document includes **only numerical and formula-based** RTOS concepts formatted for **Obsidian** compatibility.  

All equations are wrapped in `$$` blocks for direct rendering.

  

---

  
## 1. Task Parameters and Definitions

Each real-time task **Tᵢ** is defined by three main parameters:

  

$$

T_i = (C_i, P_i, D_i)

$$

  

where:

- $C_i$: Computation (execution) time

- $P_i$: Period of the task

- $D_i$: Relative deadline

  

### Derived Values

**Utilization of each task:**

  

$$

U_i = \frac{C_i}{P_i}

$$

  

**Total CPU Utilization:**

  

$$

U = \sum_{i=1}^{n} U_i = \sum_{i=1}^{n} \frac{C_i}{P_i}

$$

  

---

  

## 2. Frame Size Selection in Cyclic Scheduling

**Goal:** Choose frame size $F$ such that all tasks meet their deadlines.

  

### Constraints

$$

\begin{aligned}

F &\geq \max(C_i) \\

2F - \gcd(P_i, F) &\leq D_i \\

F &\text{ divides LCM}(P_1, P_2, \dots, P_n)

\end{aligned}

$$

  

### Example

For tasks: $A = (1,6,6)$ and $B = (2,8,8)$

  

Major cycle: $LCM(6,8) = 24$

  

Candidate frame sizes: $F = 2, 3, 4, 6, 12, 24$

  

For $F = 2$:

$$

2F - \gcd(F,6) = 4 - 2 = 2 \leq 6 \quad \text{and} \quad 2F - \gcd(F,8) = 4 - 2 = 2 \leq 8

$$

✅ Frame size of 2 ms is acceptable.

  

---

  

## 3. Rate Monotonic Analysis (RMA)

### Utilization Bound Test (Liu & Layland, 1971)

$$

\sum_{i=1}^{n} \frac{C_i}{P_i} \leq n(2^{1/n} - 1)

$$

  

For large $n$,

$$

\lim_{n \to \infty} n(2^{1/n} - 1) = \ln(2) \approx 0.693

$$

  

So, for many tasks, total utilization ≤ 69.3% guarantees schedulability.

  

### Example

Tasks: $T_1 = (2,4), T_2 = (1,8)$

$$

U = \frac{2}{4} + \frac{1}{8} = 0.5 + 0.125 = 0.625 \leq 0.828

$$

✅ Task set is schedulable under RMA.

  

---

  

## 4. Completion Time Theorem (Liu & Lehoczky, 1989)

If each task meets its first deadline when all tasks start at time zero (zero phasing),  

then it is **RMA schedulable** for all phase offsets.

  

**Worst-case response time (Rᵢ):**

$$

R_i = C_i + \sum_{k=1}^{i-1} \left\lceil \frac{R_i}{P_k} \right\rceil C_k

$$

  

Schedulable if $R_i \leq D_i$ for all i.

  

---

  

## 5. Earliest Deadline First (EDF) Scheduling

**Schedulability Criterion:**

$$

\sum_{i=1}^{n} \frac{C_i}{P_i} \leq 1

$$

  

This condition is **both necessary and sufficient** for EDF.  

If total utilization ≤ 1, all deadlines can be met.

  

### Example

$T_1 = (1,3,3), T_2 = (8,12,12)$

$$

U = \frac{1}{3} + \frac{8}{12} = 0.33 + 0.67 = 1.0

$$

✅ Task set is schedulable under EDF.

  

---

  

## 6. Context Switching Overhead

Each task may incur **two context switches**: one at preemption, one at completion.

  

If each context switch takes $c$ ms, then:  

Effective execution time:

$$

C'_i = C_i + 2c

$$

Schedulability must be checked using $C'_i$ instead of $C_i$.

  

---

  

## 7. Voltage and Frequency Scaling (DVFS)

Dynamic power consumption:

$$

P = C_{eff} \times V^2 \times f

$$

  

Execution time inversely depends on frequency:

$$

T \propto \frac{1}{f}

$$

  

### Energy per task:

$$

E = P \times T = C_{eff} \times V^2 \times N_{op}

$$

  

Energy depends quadratically on voltage.

  

### Example

Task runs 4 ms at 3V.  

At 2V, it runs 8 ms. Deadline = 8 ms → 2V is acceptable.

  

Energy ratio:

$$

\frac{E_{2V}}{E_{3V}} = \left( \frac{2}{3} \right)^2 = 0.44

$$

≈ 56% energy saved.

  

---

  

## 8. Parallel Power Efficiency

When splitting workload across $\beta$ cores at reduced frequency $f/\beta$:  

Each runs at lower voltage $V'$, achieving same throughput.

  

$$

E_{total} = \alpha C V'^2 N_{op}

$$

  

If $V' = 0.7V$ and $\beta = 4$, then normalized energy:

$$

E_{new} = (0.7)^2 = 0.49

$$

≈ 50% energy savings compared to single-core.

  

---

  

**End of Numerical and Formula Summary**
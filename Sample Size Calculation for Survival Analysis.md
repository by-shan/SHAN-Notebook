## Sample Size Calculation for Survival Analysis

### Components in Sample Size Calculations
1. Null hypothesis to be tested
2. Test Statistic
3. Assumed effect size
4. Size of the test (significance level $\alpha = 0.05; z_{\alpha/2} = 1.96$)
5. Desired Power (level $\beta$)
6. Number of Events
7. Probability of an event during study
8. Expected rate of loss
9. Sample size
10. Adjustemtns for interim analyses

### Null Hypothesis

#### Log-rank test

#### proportional hazards

* Assume proportional hazards
* $HR = h_1(t) / h_2 (t)$ ;  use HR=Median.CO / Median.TR as fixed HR for fix global effect scenario
* HR = 1 implies no difference between treatments
* HR > 1 implies "survival" longer on treatment 2
* HR < 1 implies "survival" longer on treatment 1

HR = 0.7, maybe 30% reduction in incidence means clinicall meaningful

### Power
The **power** of a hypothesis test is nothing more than 1 minus the probability of a **Type II error**. Basically the power of a test is the probability that we make the right decision when the null is not correct (i.e. we correctly reject it).

Power: typicall desier power of  80%, 90%, 95%
- REcall: for means & proportions, power is a function of sample size
- for survival data, power is entirely driven by **number of event**

| Power | beta | Z-beta |
| ----- | ---- | ------ |
| 80%   | 0.20 | 0.842  |
| 90%   | 0.10 | 1.282  |
| 95%   | 0.05 | 1.645  |

### Number of Events

$$Events = \frac{(Z_{\alpha/2} + Z_{\beta})^2}{\pi_1\pi_2(logHR)^2} $$

### Probability of an event during study

* Need to consider probability of event
* $$ n = \frac{events}{Pr\{event\}} $$
* ignoring loss at this moment

#### Probability of an Event

$$ Pr\{event\} = 1 - (\pi_1S_1(T) + \pi_2S_2(T)) $$

> for equal allocation between treatments $\pi_1 = \pi_2 = 1/2$
> How to get $S_1(t) , S_2(t)$ ?  Assume Exponential Survival Times Distribution
> $ S(t) = exp\{-\lambda t\} $

### Loss
$$ n_{adj} = n / (1 - loss) $$















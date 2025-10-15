---
title: Hacking research results
---


_Linus Szillat, 2025-03-25_

_Collecting Data in research is expensive. Optional Stopping is believed to be a cheaper way of gathering data without increasing the risk of false decisions in the subsequent data analysis. A deep dive into Optional Stopping shows that it can lead to severe mistakes in the interpretations of data._

Assume there is a god who knows the underlying truth of the world. We don‘t know this underlying truth because the uncertainty we face through random influences draws a veil about this „true“ world. We use statistics to enable us to approximate the truth and to make statements about the world with a permissable percentage of uncertainty.

Taking the relation between body weight and body height as an example, we could measure every human being and assign each a weight and a height. Our hypothesis would be that height and weight do correlate. That means that an effect exist: the higher the height, the higher the weight. To test our hypothesis, we would measure 200 randomly selected human beings.

In statistics there are two influential theories abut how this problem can be solved. The Frequentists think that by repetitions of one experiment (in this case measuring weight and height of one randomly selected person) the truth and the probability of the world can be concluded. The Bayesians select certain beliefs about the truth across different worlds before the experiment and update after the experiment this belief by looking at the observed results.

Using the Frequentist approach we only test one direction: if we can disprove that height and weight of a person do not correlate. If we can disprove that there is no correlation, then that proves the hypothesis that there is a correlation.

Using the Bayesian approach we test two directions: not only do we select our belief about the world for the case that height and weight of a person correlate but we also select the belief about the world for the case that there is no correlation. The relation between these two beliefs in the light of the observed measurements is called Bayes Factors.

In this case both perspectives assume a fixed number of measurements. Only after 200 repetitions will we test if one of these two hypotheses are correct. This is the most common way to prove or disprove hypotheses. However, because repeating many measurements is often expensive there is another, more controversial method.

While collecting data we can check after each measurement if we have gathered enough evidence to decide for one or the other hypothesis. After we have gathered enough evidence, we stop collecting data immediately and decide for one of the two hypotheses. This method is called Optional Stopping. This is especially problematic for Frequentists. Frequentists only test if there is enough evidence to disprove the hypothesis without effect. As a result of Optional Stopping we wrongly decide for a true effect even though this effect does not exist in the real world.

![[ressources/hbf1.png]]

_Figure 1. Schematic Procedure for one of the 20000 repetitions until we stop for one of the two hypotheses. $BF_{crit}$ is the critical threshold that has to be reached for a decision._

Bayesians however claim that Optional Stopping works for them. One argument that they use is the two-sided testing of the hypotheses. By using Bayes Factors as decision thresholds a correct decision should be possible either for the hypothesis without an effect (= $H_0$) or the hypotheses with the  effect (= $H_1$).

What motivated me personally was finding out if it is possible hacking the Bayesian hypothesis test with Optional Stopping. Or to be more precise: how often does Optional Stopping led to a decision for a hypothesis without an effect, although a true effect does exist? 

Assuming now that we are god and we can change what the real world is made of. Then we could define the strength of the correlation of height and weight or choose not to correlate them. This means that height could have almost no influence on weight or maybe even way more. I varied this effect size from $\delta = 0$ (no effect) to $\delta = 1$ (very strong effect). Then I used Bayesian Optional Stopping to stop with a decision via the Bayes Factors for one of the two hypotheses (see Figure 1).

For every effect size I repeated the Optional Stopping procedure 20000 times in total and counted the decisions for the hypothesis without effect. These decisions were divided by the number of repetitions to yield the probability for deciding for the hypothesis without effect $(= P('H_0'))$.

![[ressources/hbf2.png]]

_Figure 2. Results of the simulations of Bayesian Optional Stopping with the effect size $\delta$._

Results of the simulation show that the probability of deciding for the wrong hypthesis is very high especially for small effect sizes. For a small effect size like $\delta = 0.1$ will lead to a decision for the hypothesis without an effect even though a true effect does exist approximately $80\%$ of the time. Only large effect sizes like $\delta = 0.8$ will lead to a high probability of deciding for the hypothesis with an effect.

Based on these results we see that Optional Stopping can be problematic for Bayesians. The two-sided property of the Bayesian test does not ensure that the results are congruent with the "true" world. Similar to the Frequentist perspective there might be a fundamental trade-off between the efficient, cheaper collection of data (fewer data points) and the correct decision for a hypothesis which is congruent with the true world.

<!-- {{#endtab }}
{{#tab name="More advanced and technical"}}_
{{#endtab }}
{{#endtabs }} -->


# References:
- Rouder, J. N. (2014). Optional stopping: No problem for bayesians. Psychonomic
Bulletin & Review, 21 (2), 301–308. https://doi.org/10.3758/s13423-
014-0595-4
- de Heide, R., & Grünwald, P. D. (2021). Why optional stopping can be a problem
for bayesians. Psychonomic Bulletin & Review, 28 (3), 795–812. https:
//doi.org/10.3758/s13423-020-01803-x
- Also see my bachelor thesis at https://linus-szillat.de/thesis



# Google ML Fairness Reflections 

## Important stuff, there are some pitfalls to be aware of

Fairness is a generic concept not restricted to AI. Any decision-making system can exhibit bias towards certain factors and thus, needs to be evaluated for fairness. Fairness here is tested by verifying if the bias is valid as per pre-established ethical principles.
The legal definition of fairness is around the disparate treatment of and disparate impact to certain unpledged groups based on protected attributes like gender, race, religion, color, age, and more.

## Four-Fifths Rule
It occurs when a protected group is discriminated against during a selection process, like a hiring or promotion decision. The legal approach to measure disparate impact is the Four-Fifths Rule which states that if the selection rate for a certain group is less than 80 percent of that of the group with the highest selection rate, there is an adverse impact on that group.
Fairness may also be evaluated at an individual level where similar individuals are not treated in the same manner due to some unethical reason.

## Human cognitive bias.
Bias is something that our human brain exhibits when taking mental shortcuts or making assumptions to make decisions faster. Examples are confirmation bias where we focus on preconceived notions that certain fact is true. We often show a bandwagon effect and get influenced by decisions many others have made or we could fall for the gambler’s fallacy and get convinced that future probabilities are affected by past events. These are examples of human cognitive bias.

## Machines decision bias
Machines also exhibit bias while making decisions. For a rule-based system, it is easy to look at the steps of the algorithm and understand how decisions are made. It is easy to find any existence of unwanted bias here since these systems are intrinsically explainable.
When it comes to AI/ML systems the bias becomes difficult to find and explain since these systems usually learn patterns by finding correlations in the training data provided. The common source of bias for AI/ML systems in presence of bias in training data that flows into the ML model or there may be implementation issues while building the model that may cause bias to be induced.

## Two types of machine bias of AI
I-II Data Bias
Data bias can exist in training data usually due to historical bias in the system that flows directly in the collected data. For example, if historically male applicants have a greater selection rate for a job this bias will reflect directly in the data.
Bias is not always due to historical reasons - sometimes depending on the way training data is sampled from the population some sampling bias may be induced- like confirmation bias named above. Confirmation bias is when we collect data specifically with a predetermined assumption in mind. For example, if we want to prove that a treatment works for disease and only collect samples where it has worked of if we only select samples where male applicants were successful and females were not, then the trained model may incorrectly incorporate this bias

## II-II Algorithmic Bias
Not all bias is due to data, correlation fallacy is an algorithmic bias where we see a correlation in data and assume causation. Here there may be the presence of confounding factors that cause a condition and also affect the observed factors we collect. Hence the experimenter may incorrectly attribute the observed factors to cause the effect seen. Another example of algorithmic bias is labeling errors causing the model to learn incorrect patterns.


More to read:
https://ai.google/responsibilities/responsible-ai-practices/


Sources:
AI Fairness 360: An Extensible Toolkit for Detecting, Understanding, and Mitigating Unwanted Algorithmic Bias – Bellamy et al.


Harvard Business Review
 Corporate social responsibility
AI Fairness Isn’t Just an Ethical Issue
by
    Greg Satell and Yassmin Abdel-Magied 
https://hbr.org/2020/10/ai-fairness-isnt-just-an-ethical-issue


v1.1

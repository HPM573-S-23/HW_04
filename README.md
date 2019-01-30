# Homework Assignment 4

**Overview**. 
Atrial fibrillation is a major public health problem, as it is the cause of 10-15% of all stokes. 
It is an irregularity of the heart rhythm that can lead to the formation of small blood clots (emboli) 
in the circulation. If these clots reach the brain, then a stroke occurs. Several trials have 
demonstrated that anticoagulation dramatically reduces this risk of stroke. 
The dilemma is that it also increases the risk of bleeding, 
the most serious form of which is a bleed into the brain (i.e., a hemorrhagic stroke). 
Thus, the decision problem is whether the reduced risk of embolic 
stroke from using anticoagulation is worth the increase risk of bleeding. 
Clearly, this depends on the risk of emboli – the higher the risk, the greater 
the payoff from anticoagulation. Note that a stroke or bleed can occur 
repeatedly during the lifetime of the patient, so we must model the entire uncertain 
life span of the patient, and allow for repeated uncertain events. 
Similarly, we must allow for death to occur at any point in time. 

**Problem 1: Markov Model (Weight 1)**.
We would like to formulate this problem as a Markov model with the following mutually-exclusive states:
1. **Well**: Representing patients who are asymptomatic but in whom atrial fibrillation continues. 
We assume they have a normal quality of life in spite of the increased risk of stoke.
2. **Post-Stroke**: Representing patients who have survived a stroke. They have a reduced quality of life
and an increase probability of further stroke (and hence require treatment with anticoagulation).
3. **Dead**: An absorbing state to represent patients who died due to stroke. 

Draw a Markov diagram (using any software you wish) with the three health states described above and 
directed arrows that represent the possibility of transition between states. Name your graph as 'MarkovModel' 
and make sure to push it with your submission. 


**Problem 2: Probability Transition Matrix (Weight 2)**.
In many situations, the probability transition matrix is not readily available and we need to calculate
it using estimates available to us. Use the following estimates to calculate the 
transition probability matrix of the Markov model you draw for Problem 1:

1. For patients in health state 'Well', the annual probability of stroke is 5%. If they have a stroke, 
they will survive with 70% probability (and move to 'Post-Stoke'). 
2. For patients in health state 'Post-Stroke', the annual probability of stroke is 20%. If they have a stroke, 
they will survive with 60% probability (and move back to 'Post-Stroke')

_Hint_: To calculate transition probabilities out of 'Well', imagine you start today with 100 patients in 'Well', 
by the end of the year, how many would you expect to be still in 'Well', 
how many in 'Post-Stroke'm and how many in 'Dead'? 
Try to answer the same questions when you start today with 100 patients in 'Post-Stroke' and 'Dead'.


**Problem 3: Simulation (Weight 4)**. 
Develop a model to simulate 2,000 patients over 50 years to estimate the expected life-years of 
a patient who is in state “Well” at the beginning of the simulation period. 

**Problem 4: Survival Curves and Histogram of Survival Times (Weight 2)**: 
Produce the survival curve of patients who start in state “Well” and the histogram of patient survival times.

**Problem 5: Temporary State (Weight 1)**. 
Can you think of a way to count the number of strokes that a patient experiences throughout their lifetime
in this Markov model? With only 3 states, the number of strokes cannot be properly counted. 
Note that in this model, a patient who is in “Post-Stroke” state could continue to stay in 
this state under two scenarios: 
1. If a patient experience a stroke but survives, or
2. If a patient does not experience a stroke and keeps her post-stroke status. 

Under scenario 1, we should increment the number of strokes by 1 but with only 3 states, 
we cannot tell if scenario 1 has occurs during a time-step. 

One popular approach to resolve this problem is to add a **temporary state** “Stroke” to model 
the actual event (here stoke) that causes transition from one state to another state.  
This temporary state is characterized by having transitions from it only to other 
states and not to itself. Therefore, a patient can stay in this state for one 
cycle only and must move to another state for the next cycle. 
The presence of temporary “Stroke” enables the calculation of stroke episodes.










 

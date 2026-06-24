# Causal Machine Learning
## History
- `< 1990s`: Establishment of Tranditional Causal Inference (e.g. Causal Digrams, Potential Outcome Framework) Thanks to the Judea Pearl, Donald Rubin
- `2000s`: Machine Learning and deep learning technology evolved rapidly with the increase in data volume
- `2010s`: Fusion of Causal Inference and Machine Learning
    - New Methods such as `Causal Forest`
    - `EconML` and `CausalML` package got introduced

## Machine Learning Vs Causal ML
- `Supervised Machine Learning`/`SML` focuses on *prediction*, while `Causal Machine Learning` / `Causal Inference` / `CML/CI` focuses on *causality*.
- `purpose`: SML does **prediction based on correlation** while CML does **estimation of treatment effect**
- `Question`: SML answers questions like *What will customer buy next?* *What is the probability?* while CML answers questions like *Did the coupon increase sales?* *How much was its impact?*
- `Variables`: SML maps X (Features: age, gender, coupon availablity) with the Target variable like sales while CML works with X (control variables: age, gender), Z (Treatment Variable: Coupon availablity) and Y (Outcome variable: Sales uplift)


## Quick Reads
- `Causal Inference`: The process of determining whether a cause-and-effect relationship exists between `Treatment` and `Outcome`.
- `Treatment`: Coupons, Advertisement, direct mails, or any other activities.
- `Outcome`: Purchase, Brand Lift, Conversion Lift
- `Selection Bias`: Occurs when the participants or data chosen for a study do not properly represent the intended target population. eg in `Use Case 1` there there might be pitfall of selection bias like Customers who received coupons might have purchased anyway. 
- `Counter Factual`: We can only observe one outcome from the same individual. so the reality is observed world. and Counterfectual is the Hypothetical world. 
- `Simpson's Paradox`: A statistical phenomenon where a trend or relationship between two variables reverses or disappears when the data is combined (aggregated) into a single group, but appears in the opposite direction when the data is broken down into smaller groups.
- `Confounding Variable`: An unmeasured outside factor that influences both the independent and dependent variables. It distorts the true relationship between them, making it falsely appear that one variable causes another when it does not.

## Treatment Effect
- `Treatment Effect` = `Potential outcome with treatment` - `Potential outcome without treatment`
- This is represented by greek letter $\tau$
- There are 3 Types of Treatment effects.
    - `Average Treatment Effect` aka ATE 
    - $$ \tau ATE = \mathbb{E}[Y(1) - Y(0)] = \mathbb{E}[Y(1)] - \mathbb{E}[Y(0)] $$
    - `Conditional Average Treatment Effect` aka CATE 
    - $$ \tau CATE = \mathbb{E}[Y(1) - Y(0)]|X = \mathbb{E}[Y(1)] - \mathbb{E}[Y(0)|X] $$
    - `Individual Treatment Effect` aka i 
    - $$ \tau i = \mathbb{E}[Yi(1) - Yi(0)] = \mathbb{E}[Yi(1)] - \mathbb{E}[Yi(0)] $$

## we have two grups then Why we are not doing [split test](https://alokvermaotw.github.io/marketing_science/split_test/)  
- Because of limitations or RCT
- Because of Simpson's paradox where Overall and subgroups trends different.
- Because of Confounding variables

## Techniques
### 1. [Meta Learners]()
### 2. [Uplift Modeling]()


## Useful libraries
### EconML
#### Features 
- Covers a wide range of algorithms, strong in economics
- Part of a bigger DoWhy ecosystem
- Developed by Microsoft Research

### CausalML
#### Features
- Focus on Uplift modeling and Meta Learners
- Designed as a standalone tool
- Developed by Uber

## Evaluation: Refutation
### Add a commmon Cause
- Ok if new effect remains similar to the orignal and p-value exceeds 0.05
### Use a placebo treatment
- OK if the new Effect is close to 0



# Reference
## Libraries
- [CausalML]()
- [EconML]()

## Books
- [Causal Inference and Discovery in Python]()
- ["The Book of Why" by Judea Pearl and Dana MacKenzie]()
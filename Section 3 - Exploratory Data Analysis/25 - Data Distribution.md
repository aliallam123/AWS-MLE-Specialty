# Data Distributions - MUST KNOW for MLE exam

- **Probability Density Function (PDF)**  
  - For continuous data (infinite possible values)  
  - Gives probability of data falling *within a range* (not exact value)  
  - Example: Normal distribution (bell curve)  
    - ~68% data within 1 std dev of mean  
    - ~95% within 2 std devs  
    - Prob outside 3 std devs very small (<1%)  
 
- **Probability Mass Function (PMF)**  
  - For discrete data (countable values)  
  - Gives probability of exact discrete values occurring  
  - Looks like histogram  
  - Example: Poisson distribution (discrete events over time)  
    - Models # of events (e.g. sales per day)  
    - Lambda = expected avg # events  
    - Only integer counts make sense (no fractional events)  
  
- **Other discrete distributions:**  
  - Binomial distribution: # of successes in N independent yes/no trials  
  - Bernoulli distribution: special case of Binomial with N=1 trial (single yes/no)  

*Why care?*  
Choose correct distribution type (PDF vs PMF) based on data type (continuous vs discrete).  
Understand key distributions & examples (Normal, Poisson, Binomial, Bernoulli) for modeling.

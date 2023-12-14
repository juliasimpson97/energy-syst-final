# Energy Systems Final Project
## EEEL 4220 Fall 2023 
## Project Prompt \#1: Wind Integration in ISO New England

### Objective
We took the position of a policy maker to provide policy suggestions to decarbonize ISO New England. We were provided with one week (168 hours) of data including wind generation capacity factors and demand. This report summarizing how to best integrate up to 12,000 MW of wind generation into the system and how the wind generation would impact the system operating cost. We compared how a carbon tax and wind incentive tax credits impacted the system perforance over operating cost, average price of electricity, wind curtailment, and revenue. 

### Code
final-project.ipynb: Initial formulation of the UC problem   
baseline-simulation-seven-days.ipynb: Full week simulation with no additions
carbon-tax-simulation-seven-days.ipynb: Full week simulation with carbon tax
wind-tax-simulation-seven-days.ipynb: Full week simulation with wind tax incentives
combination-simulation-seven-days.ipynb: Full week simulation with carbon tax and wind tax incentives

### Formulation 

Baseline Policy Scenario  
$Gen. Cost_d  = min⁡∑_t[∑_i(QC_i g_{i,t}^2+LC_i g_{i,t} +NLC_i u_{i,t}+SUC_i v_{i,t})+9000s_t]$ 

Carbon Tax Policy Scenario     
$Gen. Cost_d  = min⁡∑_t[∑_i(QC_i g_{i,t}^2+(LC_i + EF_i)g_{i,t} +NLC_i u_{i,t}+SUC_i v_{i,t})+9000s_t]$ 

Wind Tax Incentive Policy Scenario    
$Gen. Cost_d  = min⁡∑_t[∑_i(QC_i g_{i,t}^2+LC_ig_{i,t} +NLC_i u_{i,t}+SUC_i v_{i,t})+9000s_t - 26w_t]$   

Combination Policy Scenario    
$Gen. Cost_d  = min⁡∑_t[∑_i(QC_i g_{i,t}^2+(LC_i + EF_i)g_{i,t} +NLC_i u_{i,t}+SUC_i v_{i,t})+9000s_t - 26w_y]$   

Generator Revenue    
$Revenue = ∑_{t=1}^{168}(λ_t D_t)$    

Total Profit  
$Profit = ∑_{t=1}^{168}(λ_t D_t)- ∑_{d=1}^7Gen.Cost_d 〗$


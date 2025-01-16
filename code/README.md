This folder contains the code used to generate figures in `../figures`, as well as the output data in `../data`.

Briefly, the code in `viability_selection_model.ipynb` simulates the evolution of malathion resistance in our mesocosm experiments under the viability selection model. It also estimates the fitness costs and dominance of malathion resistance that are consistend with the frequency dynamics observed in both populations. 

#### Viability selection model 

Within our model, the population frequencies of the resistant alleles change only due to selection that acts on viability. We further assume that the effects of other forces (mutation, recombination, and genetic drift) are negligible in comparison over the timescales that we considered ($\sim10$ generations). Under these assumptions, the frequency dynamics of sensitive ($f_{i=0}$) and resistant ($f_{i>0}$) alleles follow from  
```math
f_i (t+1) = f_i (t) \sum_j w_{ij} f_j(t) / \sum_{i,j}f_i f_j w_{ij},
```
where $t$ is time measured in generations and $w_ij$ is the viability of an individual carrying both $i$ and $j$ alleles. To map between time measured in days in the orchard and time measured in generations within our model, we applied the phenology model described in `degree_day_model.Rmd`.  
  

To estimate the fitness cost and dominance of malathion resistance, we analyzed the empirical frequency trajectories of these alleles in untreated populations and malathion-untreated populations in the absence of malathion. Assuming that resistant alleles share the selection ($s$) and dominance ($h$) coefficients, their frequency dynamics obey
```math
    \partial_t f_1 = sf_1(1-f_1)(f_1+h(1-2f_1)) / (1+sf_1^2+2hsf_1(1-f_1)), 
```
```math
s \equiv w_{11}/w_{00} - 1, \quad sh \equiv w_{01}/w_{00} - 1,
```
which allows us to find $h$ and $s$ that would be consistent with the observed slope $\partial_t f_1$ of the frequency trajectory. For more details, please refer to the methods section of our manuscript.   

#### System requirements
Running this code requires the web-based interactive computational environment `jupyter notebook`, `python 3.8.3` or above, as well as the following libraries: `numpy 1.23.1`, `scipy 1.10.1`, `pandas 2.0.2`, `sklearn 1.2.2`, `matplotlib 3.7.1`, `seaborn 0.12.2`, which can be installed on any operation system. To launch the notebook, simply type 
```
jupyter notebook viability_selection_model.ipynb
```
from the command line. Running the code in this notebook should take about half an hour. 

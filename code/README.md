This folder contains the code used to generate figures in `../figures`, as well as the output data in `../data`.

Briefly, the code in `viability_selection_model.ipynb` simulates the evolution of malathion resistance in our mesocosm experiments under the viability selection model<sup>1,2</sup>. It also estimates the fitness costs and dominance of malathion resistance that are consistend with the frequency dynamics observed in both populations. 

#### Viability selection model 

Within our model, the population frequencies of the resistant alleles in the populations change only due to selection that acts on viability. We further assume that the effects of other forces (mutation, recombination, and genetic drift) are negligible in comparison over the timescales that we considered ($\sim10$ generations). Under these assumptions, the frequency dynamics of the sensitive ($f_0$) and resistant ($f_1$, $f_2$, $f_3$) alleles follow from  
```math
f_i (t+1) = \frac{f_i (t) \sum_j w_{ij} f_j(t)}{\sum_{i,j}f_i f_j w_{ij}},
```
where $t$ is time measured in generations and $w_ij$ is the viability of an individual carrying both $i$ and $j$ alleles. To map between time measured in days in the orchard and time measured in generations within our model, we applied the phenology model described in `degree_day_model.Rmd`.  
  

To estimate the fitness cost and dominance of malathion resistance, we analyzed the empirical frequency trajectories of these alleles in malathion-treated populations and untreated populations in the absence of malathion. Assuming that resistant alleles share the selection ($s$) and dominance ($h$) coefficients, their frequencies obey
```math
    \partial_t f = sf(1-f)(f+h(1-2f)),
```
which allows us to find $s$ that would be consistent with the observed slope $\partial_t f$ of the frequency trajectory for a given $h$.  

-------------
<sup>1</sup> Gillespie J. H. Population genetics: A concise guide. Second edition. _Johns Hopkins University Press_, 2004.  
<sup>2</sup> Ewens W. J. Mathematical population genetics: I. A theoretical introduction. Second edition. _Springer_, 2004.

This folder contains all of the input data required to generate figures in `../figures`, as well as the output data that can be used to make figures directly without running simulations.

#### Required input data:
- `haplotype_freqs.csv` contains the haplotype frequencies from the mesocosm experiment;  
- `generation_start_July13.csv` contains the mapping between time in days and time in generations, estimated based on daily temperature (see `../code/degree_day_model.Rmd`); - `2021_orchard_weather_data.csv` contains the weather data used to estimate generations;   
- `viability_values_simulations.csv` contains genotype viabilities, estimated by fitting logistic dose-response curves to laboratory measurements;  
- `resistance_cage.csv` contains population malathion resistance data for both malathion-treated and untreated populations.  

#### Output data, used to generate figures in the manuscript:
- `sim_allele_freqs_treated_cages.csv` and `sim_allele_freqs_untreated_cages.csv` contain haplotype frequencies simulated under the viability selection model in malathion-treated and untreated populations;    
- `sim_resistance_data.csv` contains population malathion resistance data simulated under the viability selection model;    
- `bootstrapped_slope_treated_cages.csv` and `bootstrapped_slope_untreated_cages.csv` contain the bootstrap realizations for the slope of resistant allele frequency in malathion-treated and untreated populations;   
- `inferred_s_treated_cages.csv` and `inferred_s_untreated_cages.csv` contain selection coefficients inferred for a range of dominance coefficients from the mean and the bounds corresponding to the 0.95 confidence interval of the slope distributions;
- `likelihoods.csv` contains joint likelihoods for observing the slopes of resistant allele frequency in both populations as a function of dominance and selection coefficients;  
- `freq_dynamics_h.csv` contains resistant allele frequencies simulated under the viability selection model for a range of dominance coefficients.  

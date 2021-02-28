# uciml_data_analysis

## Companies dataset
This dataset I had been collecting on the side for the past few weeks and haven't had a chance to dive deep into it. This project looked like a perfect opportunity to combine the statistical techniques we've learned in class with a sideproject of mine. A little background: The Universal Scalability Law is a new theory of how systems scale. I'm trying to apply it to technology companies. On page 18 of this pdf: https://cdn2.hubspot.net/hubfs/498921/eBooks/scalability_new.pdf there is a statistical technique used that I wanted to replicate. I implemented nonlinear least-squares regression in my notebook, because I thought it'd be useful. I know it's not a mixture model - ignore it if it won't count for this project.


#### Summary of the dataset: 
companies_dataset.csv
Revenue, gross profit, gross margin, user data, company classification, and various related metrics for ~17 different companies

#### Analysis
The file companies_analysis.ipynb contains a summary of the exploration into this dataset.
The file [companies_scratchpad.ipynb](https://github.com/kambielawski/uciml_data_analysis/blob/master/companies_scratchpad.ipynb) is a scratchpad and documentation of everything I did starting from loading the data from the .csv file. 
Quick summary:
I failed at implementing nonlinear least-squares regression on the dataset. Exploding gradients. Couldn't figure it out. Then, I wanted to actually *see* a mixture model in action, so I picked two variables from each entry (gross margin and revenue per user), and did a mixture model for just those two variables so I could visualize it. I classified the entries and visualized the Gaussians with a contour map.


## Drug consumption dataset
The file [Drug_Consumption_Scratchpad.ipynb](https://github.com/kambielawski/uciml_data_analysis/blob/master/Drug_Consumption_Scratchpad.ipynb) contains all of my exploration. 
The file drug_consumption_analysis.ipynb contains a summary of the exploration into this dataset.
#### Summary of the dataset:
drug_consumption.data
from: https://archive.ics.uci.edu/ml/datasets/Drug+consumption+%28quantified%29#
This dataset contains 1885 entries of Big 5 personality scores and their consumption levels of ~18 different drugs

#### Analysis
I dove into this early and without a clear plan to do something useful with this data. But I first looked at the dataset and did a bunch of bar charts to get a sense of the distributions that were in play here. I thought about being able to generate data, so I decided to find the conditional distributions of the entries: what is the distribution of X-drug-users? So I made a mixture model based on the 7 personality metrics (I ignored the other columns because they weren't Gaussian) GIVEN they've used drug X. So now I'm able to generate a "X-user" for any given drug X. Kind of cool. 

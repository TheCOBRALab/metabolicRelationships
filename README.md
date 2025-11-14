# metabolicRelationships
Welcome to the code for the paper "Evaluation of network inference algorithms for derivation of metabolic relationships from metabolomic data sets"

This repo demonstrates the steps in generating the data and analyzing the results, with a focus on visualization.

---
Sample Generation<br>
We begin with using the Arachadonic Acid metabolism model defined by Jahagirdar 2019 [link](https://www.semanticscholar.org/paper/Simulation-and-reconstruction-association-networks-Jahagirdar-Su%C3%A1rez-Diez/4b614e1ff9e25baf205fa1fad3f3b455fec02a29)
. The model is provided here: Models/AA_model Jahagirdar2019.xml.

500 samples were generated using MATLAB (the program code is "Models/HealthyBaseline.m").
The data generated for this project (as well as additional visualization of inferred networks) is available: [link](https://zenodo.org/records/17246740)

-----
Data Generation<br>
We then used these samples to infer the underlying network by various methods. "Notebooks/Generate Data.ipynb" demonstrates how these network inference algorithms (NIAs) were applied using a subset of the data, without replacement. (Note, the PCLRC algorithms sample with replacement from within their available subset of data).

-----
Analysis<br>
Association matrix data is compiled and evaluation methods are applied in "Notebooks/Data Analysis and Visualization.ipynb".

"Notebooks/Aspirational Evaluations.ipynb" looks at the best-case scenario network inference algorithm where an increasing number of samples is related to increasing signal. That is, noise caused by small sample sizes or inherent to the network inference algorithm are removed and we can focus on the evaluation metrics themselves.

The "Reference_Network.npz" contains information about the underlying network useful for evaluations and visualizations (the adjacency matrix, metabolite positions, and metabolite names)

----
State Differentiation<br>
"Notebooks/Steady State Init.ipynb" helps navigate the COPASI model to adjust initial concentrations. This steady-state initialization model is also provided, "Models/AA_model SteadyStateInit.xml"
This is used for attempting to differentiate the network from two states: 'young' and 'old'. These visualizations are done in "Notebooks/Differentiation Visualization.ipynb".



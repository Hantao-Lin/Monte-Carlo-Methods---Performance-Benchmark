# Monte Carlo Methods - Performance-Benchmark
## Abstract 
Efficient management of fluid flow through orifices is fundamental in engineering disciplines, necessitating precise simulations to predict flow rates under varying operational conditions. This research presents a comparative study employing both Python and R programming environments to simulate and analyze the impact of critical parameters—discharge coefficient (Cd), orifice diameter (dia), pressure drop (dP), and specific gravity (Sg)—on the flow rate (Q) through an orifice. Utilizing a Monte Carlo simulation framework, we generated 100,000 scenarios in each programming environment, where the parameters were allowed to vary within predefined limits, thereby mimicking real-world variability and uncertainties.

The study meticulously calculates the flow rates based on established fluid dynamics equations, subsequently analyzing the distribution of these rates through histogram visualization to assess the probabilistic distribution, variability, and sensitivity of the flow rate to the input parameters. The comparative analysis not only sheds light on the nuances of implementing statistical simulations across different software platforms but also evaluates the efficiency, usability, and result accuracy of Python versus R in conducting such complex simulations.

Our findings reveal that both environments are capable of providing comprehensive insights into fluid flow dynamics, yet they offer distinct advantages in terms of data manipulation, visualization capabilities, and execution times. This research contributes to the engineering field by not only enhancing the understanding of fluid flow through orifices but also by offering a critical evaluation of the tools available to engineers and researchers for performing such simulations. The comparison underscores the importance of selecting the appropriate computational tool based on the specific requirements of the study, thereby guiding the design, optimization, and operational planning of systems involving fluid flow.
## Introduction

In the evolving landscape of engineering and computational fluid dynamics, the ability to accurately predict and analyze fluid flow through orifices plays a crucial role in the design and optimization of various mechanical and environmental systems. Orifices, being fundamental components in controlling and measuring fluid flow, are ubiquitous in engineering applications—from hydraulic systems and chemical reactors to water treatment and irrigation systems. The flow rate through an orifice, influenced by parameters such as discharge coefficient, orifice diameter, pressure drop, and fluid specific gravity, determines the efficiency and functionality of these systems. Thus, understanding the interplay between these parameters and flow rate is essential for engineers and designers.

Traditional approaches to studying fluid flow often rely on physical experiments and empirical formulas, which, while effective, can be time-consuming, costly, and limited by the feasibility of creating the desired conditions. With the advent of computational simulations, it has become possible to model and analyze complex fluid dynamics scenarios with greater flexibility and accuracy. Among the tools available for such simulations, Python and R stand out for their extensive libraries, ease of use, and strong support for statistical analysis and visualization.

This study embarks on a comparative exploration of Python and R in simulating fluid flow through orifices, aiming to leverage the Monte Carlo simulation technique to generate a vast array of scenarios. By varying key parameters within realistic ranges, the study seeks to model the probabilistic distribution of flow rates and analyze the sensitivity of the flow rate to changes in each parameter. The goal is not only to enhance the understanding of fluid dynamics in practical engineering contexts but also to evaluate the capabilities of Python and R in handling complex simulations. This comparison may offer valuable insights into the selection of computational tools for engineering applications, considering factors such as simulation efficiency, ease of implementation, and the clarity and utility of resulting visualizations.

In doing so, this research contributes to the broader field of computational fluid dynamics by providing a detailed analysis of flow through orifices under varied conditions, thereby informing the design and optimization of related engineering systems. Furthermore, by comparing the simulation processes and outcomes in Python and R, the study sheds light on the practical considerations of conducting such analyses, including the implications for engineering education, research, and practice.
## Literature Review 
A research project done by Prabhu Ramachandran of IIT-Madras in Chennai India looked at the effectiveness of python in computational fluid dynamic problems. Although, it was not the comparison of R and Python within this set of problems, the study did find a conclusion on the effectiveness of Python. Prabhu explained how the "number crunching code" was implemented in C++ but the analysis and management of the data was run using Python. After demonstrating his work he arrived at the conclusion that Python is "extremely well suited for scientific computations''. He explains how the built in packages make it extremely efficient and along with its power make it extremely fast. This would align with our findings that Python was a superior performer in the sense of accuracy and speed. 

Another study done by Arturo Burgos of the Federal University of Uberlandia, tested the best programming language for Computational fluid dynamics between Matlab, Python, Fortran, and Julia. Although some of his work was hard to follow due to the advanced nature of the study he concluded that Python, although very effective, was actually the slowest out of these programming languages when it came to run time. That was interesting to read because we did not achieve these same results, but he added that because python was constantly improving their system and adding so many different libraries and modules it could be logical that Python has gotten faster since 2021. 

References: 
https://www.aero.iitb.ac.in/~prabhu/research/papers/pr_scipy04.pdf
https://repositorio.ufu.br/bitstream/123456789/32272/4/AssessmentProgrammingLanguages.pdf

### Simulation Framework
Our study aimed to simulate the flow rate (Q) of fluid through an orifice, influenced by four primary parameters: discharge coefficient (Cd), orifice diameter (dia), pressure drop(dP), and specific gravity (Sg). A Monte Carlo simulation approach was employed to generate a comprehensive dataset reflecting the variability of these parameters. This simulation was conducted independently in both Python and R to leverage and compare the capabilities of these programming languages.
### Parameter Definition and Randomization
In both Python and R, we defined the ranges for Cd, dia, dP, and Sg, and calculated their mean and standard deviation values. This setup facilitated the generation of 100,000 random values for each parameter, simulating real-world variability. Random values were drawn from normal distributions centered around the mean values with the calculated standard deviations, using Python's 'numpy.random.normal' and R's 'rnom' functions.
### Flow Rate Calculation
The flow rate (Q) for each set of parameters was calculated using the formula Q = 29.81 x Cd x (dia^2) x sqrt(dP/Sg). This formula incorporates the interplay between the parameters to determine the flow rate, providing insights into how variations in these parameters affect fluid flow.
### Visualization of Results
The distribution of the calculated Q values was visualized using histograms in both Python (using 'matplotlib') and R (using base plotting functions), allowing for the analysis of the probabilistic distribution of flow rates under varying conditions.
### Predictive Modeling Using Random Forest
Following the simulation, we applied machine learning techniques to predict flow rates based on the input parameters. A Random Forest regression model was trained using the generated dataset, split into training and test subsets to evaluate model performance.
### Model Training and Evaluation
- [Python Implementation](https://github.com/Hantao-Lin/Monte-Carlo-Methods---Performance-Benchmark/blob/main/Group%20assignment%204.ipynb): Utilized RandomForestRegressor from sklearn.ensemble to train the model. Model performance was evaluated using metrics such as RMSE (Root Mean Square Error), MAE (Mean Absolute Error), and R^2.
- [R Implementation](https://github.com/Hantao-Lin/Monte-Carlo-Methods---Performance-Benchmark/blob/main/Group%20assignment%204.Rmd): Employed the randomForest package to create and train the model, with similar evaluation metrics calculated for assessing model accuracy.
### Computational Efficiency
The execution time and memory usage were recorded in both Python (using time and psutil) and R (using Sys.time and pryr::mem_used), providing insights into the computational efficiency of the simulation and modeling processes across both programming environments.
## Results
- [Python](https://github.com/Hantao-Lin/Monte-Carlo-Methods---Performance-Benchmark/blob/main/results/python_results.txt): 
<img title="Python Distribution" alt="python histogram" src="https://github.com/Hantao-Lin/Monte-Carlo-Methods---Performance-Benchmark/blob/main/results/python_distribution.png">

- [R](https://github.com/Hantao-Lin/Monte-Carlo-Methods---Performance-Benchmark/blob/main/results/R_results.txt): 
<img title="Python Distribution" alt="python histogram" src="https://github.com/Hantao-Lin/Monte-Carlo-Methods---Performance-Benchmark/blob/main/results/R_distribution.png">

| Metric       | Python    | R |
|--------------|-----------|------------|
| Mean | 0.40269      | 0.40269       |
| RMSE      | 0.00053  | 0.00149       |
| MAE      | 0.00036  | 0.00095       |
| R^2      | 0.99790  | 0.98426       |
| Execution Time      | 2.67 sec | 31.82 sec     |
| Memory     | 269.58 MB  | 208.83  MB       |

This comparative study of Python and R for simulating fluid flow through orifices using the Monte Carlo simulation has yielded several key findings. The histograms representing the standard distribution of Q values display the simulated probability density of flow rates, show similar distributions with Python's simulation results indicating a slightly narrower peak around the mean value compared to R's results. The statistical analysis showed that Python had a lower root mean square error (RMSE) of 0.00053 compared to R's RMSE of 0.00149, and a lower mean absolute error (MAE) of 0.00036 against R's MAE of 0.00095, indicating a higher precision in Python's simulation results. Furthermore, the coefficient of determination (R^2) was higher in Python than in R, signifying that Python's model predictions were closer to the actual data.

In terms of computational performance, Python demonstrated a significant advantage with an execution time of approximately 2.67 seconds, which is notably faster than R's 31.82 seconds. However, R was more memory-efficient, consuming around 208.83 MB, whereas Python used approximately 269.58 MB.

## Conclusions
The findings of this study suggest that while both Python and R are capable tools for simulating fluid flow through orifices, Python has shown superior performance in terms of accuracy and speed. Python's faster execution time and higher precision make it a preferable choice for simulations where these factors are critical. This study enhances the understanding of the practical applications of fluid dynamics simulations and provides a basis for selecting appropriate computational tools based on the needs of the simulation.

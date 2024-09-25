# Reproducing a paper
## Paper for this exercise


- Muralidharan, Karthik, Abhijeet Singh, and Alejandro J. Ganimian. 2019. "Disrupting Education? Experimental Evidence on Technology-Aided Instruction in India." American Economic Review, 109 (4): 1426–60.

  - [Paper](https://www.aeaweb.org/articles?id=10.1257/aer.20171112)
  - [Online Appendix repository](https://assets.aeaweb.org/asset-server/files/9271.pdf)
  - [Data and R code](https://www.openicpsr.org/openicpsr/project/113192/version/V2/view)

## Overall goal
- The overall task is to replicate all exhibits from the paper and online appendix other than Figures E3 and E4. 
- This is an AER paper with a reproducibility score of [4/10](https://www.socialsciencereproduction.org/reproductions/1787/published/index).
  - The exercise will show you how failing to adhere to best reproducibility practices leads to an unnecessarily strenuous replication process. 
  - All exhibits are perfectly reproducible after making the right changes (with the one exception of Table A8). 
- This is the original reproducibility package downloaded from the AEA Data and Code repository. 

# Exercises

## Exercise 1: Set up
Edit the code so that it works on your computer. This includes:
1. Setting your working directory and changing file paths
> You may need to create folders (for exhibits) that don't exist. 
2. Installing packages
> Look at [this blogpost](https://blogs.worldbank.org/en/impactevaluations/how-make-user-written-stata-commands-really-reproducible) and [this code template](https://github.com/DevInnovationLab/dil-template-repo/blob/d9d3910c519173dd8fb7f965057b9c1a34e0d2b9/main.do#L41-L50) for examples of how to share exact version of community-contributed commands.
3. Re-setting globals that control which parts of the script are run
           
## Exercise 2: Bug fixes
Unlike the R code we saw yesterday, this code includes many bugs. Creating [issues](https://github.com/boothresearch/rep_disrupting_educ/issues) to identify bugs and share solutions will help you get through this part of the exercise faster.

- Common mistakes may include:
  1. misnaming a variable
  2. creating a variable that already exists
  3. misnaming a dataset
  4. incorrect merges
  5. failure to save an exhibit
- Many bugs can be pre-empted by using `assert` and `isid` statements, e.g., to assert what variable uniquely identifies an observation in a particular dataset (especially useful for merging). You are encouraged to use them as you try to run the code.
- If you find a bug, remember to document it as an issue as it may occur again.
- It may be useful to consult the paper, the file `data/Readme.pdf`, and to explore the datasets used in the script (e.g., using the `fre` command).

We recommend you work on the code in this order:
1. Replicate Tables 1-9
2. Replicate Tables A1-A5
3. Replicate Tables A6-A7
> This may be challenging, so create a GitHub issue and collaborate with others on it
4. Replicate Table A8
5. Replicate Tables A9-A10 and Figs 1-4
6. Replicate Fig 5
7. Replicate Fig 7, 6, and A1-A4
> Exploring the distribution of the variable `ms_id` may help solving bugs here
8. Replicate Fig A5
9. Reproduce Fig E1 

## Exercise 3: Reproducibility

Once you are able to run the full code, check if the outputs match the paper and if outputs are stable.
1. Run the full code once and commit any changes
2. Re-run the whole codebase and look at the diff to identify any instabilities in the outputs
> One exhibit does not replicate. Which exhibit is it? Document it in the issues
3. Stabilize the code.
  1. Describe which statistical objects of the unstable exhibit, differ from the table in the paper.
  2. Provide three candidate explanations for this difference and rank them by degree of plausibility according to your opinion.

## Exercise 4: Automation

How easy is it to compile the paper itself once the code runs?
1. Save the tables as `.tex` rather than `.xls`.
2. You want to produce Table A8 with a stricter confidence interval, 99% rather than 95%. Estimate how long it would take you to update this table in the paper.

## Exercise 5: Ease of use

How easy it is to understand what the code is doing? How easy is it to make changes to it?
1. Understand Table 3 in the paper.
2. You want to run two robustness checks:
   1. Re-run each specification (i.e., each column of Table 3) without controlling for `Baseline math score` for math-related competencies and for `Baseline Hindi score` for language-related competencies.
   2. Re-run each specification (i.e., each column of Table 3) when controlling for both `Baseline math score` and `Baseline Hindi score` in each specification.
3. Save the exhibits so that each exhibit name's suffix indicates the robustness check performed.
4. Look at the `git diff` to count how many lines of code you needed to change to achieve this fully.
5. Can you think of a way to re-structure the code so that such changes would be easier? (If you've already done this above, great!)

## Exercise 6: Testing

How can you build checks into the code to prevent changes from introducing errors?
1. Identify three operations performed in the code that are "risky". Create issues pointing to the lines of code that perform these operations.
> For example, operations that change the number of observations in the data, combine different datasets, aggregate data points, or that may be sensitive to the presence of missing values
2. Discuss with your group how to build checks into the code to prevent errors from being introduced when these operations are performed.
> Two particularly useful commands here are `assert`, `isid`. You may also want to explore the help file for `merge` to look for options that test the results of this command.



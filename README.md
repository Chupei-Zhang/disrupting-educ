# Reproducing a paper
## Paper for this exercise


- Muralidharan, Karthik, Abhijeet Singh, and Alejandro J. Ganimian. 2019. "Disrupting Education? Experimental Evidence on Technology-Aided Instruction in India." American Economic Review, 109 (4): 1426–60.

  - [Paper](https://www.aeaweb.org/articles?id=10.1257/aer.20171112)
  - [Online Appendix repository](https://assets.aeaweb.org/asset-server/files/9271.pdf)
  - [Data and R code](https://www.openicpsr.org/openicpsr/project/113192/version/V2/view)

## Overall goal
- The overall task is to replicate all exhibits from the paper and online appendix other than Figures E3 and E4. 
- This is an AER paper with a reproducibility score of [4/10](https://www.socialsciencereproduction.org/reproductions/1787/published/index). An AER with a reproducibility score of 10/10 is better.
  - The exercise will show you how failing to adhere to best reproducibility practices leads to an unnecessarily strenuous replication process. 
  - All exhibits are perfectly reproducible after making the right changes (with the one exception of Table A8). 
- This is the original repkit. 

# Exercises

## Exercise 1: Set up
1. Edit the code so that it works on your computer. This includes:
   1. setting your working directory and changing file paths
         - You may need to create folders (for exhibits) that don't exist. 
   3. installing packages
         - Add a chunk of code to the top of the script that deals with packages, so that future users don't have to face the same problem. (You may need to use `net install` rather than `ssc install` for some packages.)
   4. re-setting globals that control which parts of the script are run correctly so that you can re-run all tables and figures other than Figures E3 and E4
     
## Exercise 2: Bug fixes
- Common mistakes may include:
  1. misnaming a variable
  2. creating a variable that already exists
  3. misnaming a dataset
  4. incorrect merges
  5. failure to save an exhibit
- Many bugs can be pre-empted by using `assert` and `isid` statements, e.g., to assert what variable uniquely identifies an observation in a particular dataset (especially useful for merging). You are encouraged to use them as you try to run the code.
- If you find a bug, remember it as it may occur again.
- If you find a bug and cannot fix it in 10 minutes, then create a GitHub issue for the bug that contains its error message. Work with others by adding comments with solutions you've tried that work or don't work. Do the same for recurring bugs.
- It may be useful to consult the paper, the file `data/Readme.pdf`, and to explore the datasets used in the script (e.g., using the `fre` user-written command).

1. Replicate Tables 1-9.
2. Replicate Tables A1-A5.
3. Replicate Tables A6-A7. (If this is challenging for you, create a GitHub issue and collaborate with others.)
4. Replicate Table A8. 
5. Replicate Tables A9-A10 and Figs 1-4.
6. Replicate Fig 5.
7. Replicate Fig 7, 6, and A1-A4.
8. Explore the distribution of the variable `ms_id`.
9. Replicate Fig A5.
10. Reproduce Fig E1. 
11. Re-run the whole codebase to check code stability.

## Exercise 3: Reproducibility
- Check if outputs match the paper and if outputs are stable.
1. One exhibit does not replicate. Which exhibit is it?
2. Describe which statistical objects of this exhibit, if any, differ from the table in the paper.
3. Provide three candidate explanations for this difference and rank them by degree of plausibility according to your opinion.

## Exercise 4: Automation
- How easy is it to compile the paper itself once the code runs?
1. Save the tables as `.tex` rather than `.xls`.
2. You want to produce Table A8 with a stricter confidence interval, 99% rather than 95%. Estimate how long it would take you to update this table in the paper.

## Exercise 5: Ease of use
- How easy it is to understand what the code is doing? How easy is it to make changes to it?
1. Understand Table 3 in the paper.
2. You want to run two robustness checks:
   1. Re-run each specification (i.e., each column of Table 3) without controlling for `Baseline math score` for math-related competencies and for `Baseline Hindi score` for language-related competencies.
   2. Re-run each specification (i.e., each column of Table 3) when controlling for both `Baseline math score` and `Baseline Hindi score` in each specification.
3. Save the exhibits so that each exhibit name's suffix indicates the robustness check performed.
4. Look at the `git diff` to count how many lines of code you needed to change to achieve this fully.
5. Can you think of a way to re-structure the code so that such changes would be easier? (If you've already done this above, great!)

## Exercise 6: Testing
- How can you build checks into the code to prevent changes from introducing errors?
1. Propose three checks that you deem most important for this code. Argue why. 



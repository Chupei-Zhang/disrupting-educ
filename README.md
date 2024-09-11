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

## Exercises
### General
- No packages are specified. As you run the code, install necessary packages. Add a chunk of code to the top of the script that deals with packages, so that future users don't have to face the same problem. (You may need to use `net install` rather than `ssc install` for some packages.)
- The word "replicate" below means i) produce an exhibit, and ii) compare it to the one in the paper to make sure they're identical. 
- If you find a type of mistake in the script -- e.g., misnaming a variable or a dataset, creating variables that already exist, merging with a dataset that has already been merged implicitly (not in the script) -- remember the mistake as it may occur again. 

### Chronological
1. Set globals controlling which parts of the script are run correctly so that you can re-run all tables and figures other than Figures E3 and E4.
2. Set up your directory and set paths. You may need to create folders (for exhibits) that don't exist. 
3. Replicate Tables 1-6.
4. Make sure that variables are named correctly in the script. 
  - Consult `data/Readme.pdf` for variable names and the paper for what the exhibits want to show. The script and the `Readme.pdf` file are from the authors -- if they disagree, you need to find out which one is correct. 
5. Replicate Tables 8-9.
6. Make sure that the datasets are named correctly in the script. 
  - To figure this out, consulting `data/Readme.pdf`, and looking at the datasets available in the repo is helpful. 
7. Replicate Tables A1-A5.
8. Make sure the script doesn't try to create variables that already exist. 
9. Make sure the script doesn't try to merge which datasets that don't exist. Check that the variables necessary are actually already present (so the datasets are already merged implicitly -- not in the script). 
10. Replicate Tables A6-A7.
11. Replicate Table A8. 
  - Make sure the table is saved.
  - Describe which statistical objects of this table, if any, differ from the table in the paper.
  - Provide three candidate explanations for this difference and rank them by degree of plausibility according to your opinion.
12. Replicate Tables A9-A10 and Figs 1-4.
13. Replicate Fig 5 using your knowledge of common mistakes from above.
14. Use `isid` statements to assert what variable uniquely identifies an observation. This is useful for merging. 
15. Replicate Fig 7, 6, A1-A4 using your knowledge of common mistakes from above.
16. Look at the distribution of the variable `ms_id`.
17. Replicate Fig A5.
18. Reproduce Fig E1. (Hint: look at `data/Readme.pdf` for variable names.)
19. Re-run the whole codebase to check code stability.
20. When you code your own code, please remember to always adhere to best reproducibility practices. (You should no longer wonder why it's useful to use `assert` and `isid` statements in your code!)

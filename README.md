# Analyze-Death-Age-Difference-of-Right-Handers-with-Left-Handers
## Description
 A 1991 study reported that left-handed people die on average nine years earlier than right-handed people. Nine years! Could this really be true?

 In this notebook, we will explore this phenomenon using age distribution data to see if we can reproduce a difference in average age at death purely from the changing rates of left-handedness over time, refuting the claim of early death for left-handers. This notebook uses pandas and Bayesian statistics to analyze the probability of being a certain age at death given that you are reported as left-handed or right-handed.

 A National Geographic survey in 1986 resulted in over a million responses that included age, sex, and hand preference for throwing and writing. Researchers Avery Gilbert and Charles Wysocki analyzed this data and noticed that rates of left-handedness were around 13% for people younger than 40 but decreased with age to about 5% by the age of 80. They concluded based on analysis of a subgroup of people who throw left-handed but write right-handed that this age-dependence was primarily due to changing social acceptability of left-handedness. This means that the rates aren't a factor of age specifically but rather of the year you were born, and if the same study was done today, we should expect a shifted version of the same distribution as a function of age. Ultimately, we'll see what effect this changing rate has on the apparent mean age of death of left-handed people, but let's start by plotting the rates of left-handedness as a function of age.

 This notebook uses two datasets: [death distribution data](https://www.cdc.gov/nchs/data/statab/vs00199_table310.pdf) for the United States from the year 1999 (source website [here](https://www.cdc.gov/nchs/nvss/mortality_tables.htm)) and rates of left-handedness digitized from a figure in this [1992 paper by Gilbert and Wysocki](https://www.ncbi.nlm.nih.gov/pubmed/1528408).


## Datasets
1. [Death distribution data](https://www.cdc.gov/nchs/data/statab/vs00199_table310.pdf) for the United States from the year 1999 (source website [here](https://www.cdc.gov/nchs/nvss/mortality_tables.htm))

2. Rates of left-handedness digitized from a figure in this [1992 paper by Gilbert and Wysocki.](https://www.ncbi.nlm.nih.gov/pubmed/1528408)

3. [Project data](https://drive.google.com/uc?export=download&id=1gSjYHJ8OPM9HMd3prr7XuhvSWWGKYZNE)


 ## Contents
 1. **Where are the old left-handed people?**: Load the handedness data from the National Geographic survey and create a scatter plot.Where are the old left-handed people?: Load the handedness data from the National Geographic survey and create a scatter plot.

 2. **Rates of left-handedness over time**: Add two new columns, one for birth year and one for mean left-handedness, then plot the mean as a function of birth year.

 3. **Applying Bayes' rule**: Create a function that will return P(LH | A) for particular ages of death in a given study year.

 4. **When do people normally die?**: Load death distribution data for the United States and plot it.

 5. **The overall probability of left-handedness**: Create a function called P_lh() which calculates the overall probability of left-handedness in the population for a given study year.

 6. **Putting it all together: dying while left-handed (i)**: Write a function to calculate P_A_given_lh().

 7. **Putting it all together: dying while left-handed (ii)**: Write a function to calculate P_A_given_rh().

 8. **Plotting the distributions of conditional probabilities**: Plot the probability of being a certain age at death given that you're left- or right-handed for a range of ages.

 9. **Moment of truth: age of left and right-handers at death**: Find the mean age at death for left-handers and right-handers.

 10. **Final comments**: Redo the calculation from Task 8, setting the study_year parameter to 2018.

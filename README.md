# PK analysis of AUC & Cmax from a drug and its metabolite with R
(English) Language: R // Author: Aramis Adriana Rojas Mena & Elisabet Castro Blanco

## Description
The database chosen is the blood pharmacokinetic values for an undetermined drug P and one of the metabolites M that are generated endogenously in the body of a person (without specifying the physiognomy or pathology that he/she may have).
It has been obtained from this server from a repository of databases from different phases of drug research, provided by the researcher Thomas E. Bradstreet, from the School of Mathematics at John Carroll University (USA) (http://webserv.jcu.edu/math//faculty/TShort/Bradstreet/index.html).
The pharmacokinetic values studied are the AUC (area under the curve), which gives an idea of the bioavailability of a substance in blood, either discrete (a specific point in time can be considered) or continuous (from time 0 to infinity), and the Cmax (maximum concentration in blood), for that substance.
Both values are used to characterise the kinetic behaviour of the substance in the body, i.e. the speed with which the drug P diffuses through the body with the blood and could reach the therapeutic targets, more or less non-specifically (a factor that depends on the type of drug and target cells, but is a broader concept), as well as the speed and amount of drug remaining once the elimination of the drug from the body is initiated.
In the database used, both values are presented as discrete, taken at an unspecified point in time, presumably to facilitate data processing. This is not the form that can provide the most pharmacokinetic information, but it is an assumption that is considered correct in the scientific community.
The reason for choosing such a database is due to the common interest of both authors in the behaviour of a drug/substance in a living animal organism, thus bringing together two separate scientific fields, with Elisabet as a biologist and Aramis as a pharmacist.

We checked within each of the following proposed comparisons whether the assumptions for parametric statistical tests based on a normal - Gaussian distribution are met (Shapiro Test). 
In general, these are usually criteria of fit to a normal distribution and homoscedasticity (equality of variances). 
Here it is not correct to perform parametric tests, since the assumptions of normality and homoscedasticity weren't met. Running parametric tests according to a normal distribution, without first testing these assumptions, would be a serious statistical error, which would lead to extrapolating erroneous conclusions.

### Comparisons
- For drug P and metabolite M (separately), for any dose in Panel 1, which are the lowest doses available (10, 20 or 40 mg), is there a correlation between the corresponding AUC and Cmax?
- For the pharmacokinetic (PK) AUC value, with drug P and metabolite M separately, check whether a correlation can be said to exist between any two low doses (10, 20 or 40 mg).
- For the pharmacokinetic (PK) AUC value, with drug P and metabolite M separately, check whether a correlation can be said to exist between any two doses, with one dose being high (from Panel 4) and the other low (Panel 1).
- For the PK AUC value of a high and a low dose (either and each as a variable), perform a test to test the null hypothesis of equality of means between the two factor levels (as applicable depending on the results of correlation between variables and normality/homoscedasticity).
- For the pharmacokinetic (PK) AUC values of drug P, with the doses of one of the panels (1,2,3,4), check together if both 3 variables would follow a normal distribution. What happens? Can we know if there is correlation in the AUC behaviour of the three doses of the panel we choose simultaneously? What kind of analysis are these? What kind of analysis would we have to make?
- Probability issues and a brief simulation model.
- Regression analysis (TBC)

### Discussion
From the analyses carried out in the previous sections, conclusions can be drawn which, although they are quite robust, suggest the need to carry out statistical analyses on a larger number and dimension (of variables).

With respect to sections 3.1 to 3.4 
The previous assumptions of normality and homoscedasticity (equality of variances) are not fulfilled, and therefore non-parametric tests must be performed to study the correlation between the variables we are interested in studying. 

Only Shapiro's test is performed, without the F test of the variance, because it is sufficient not to meet one of the two criteria for no parametric test to be performed (those that correspond to a certain statistical distribution). It is proposed to use Spearman's test, but it is also correct to perform Kendall's test, both indicated for these contexts.

We can see that the relationship between the pharmacokinetic parameters AUC and Cmax, for the dose and factor studied, is almost nil, but it is advisable to see what happens with the rest of the doses and/or factors, as for the 20/80/300 mg dose, with the metabolite, the correlation is statistically significant, as well as for others with the P drug.

There seems to be no correlation between low doses for the PK AUC parameter (neither P nor M factor), nor between low and high doses (neither P nor M factor). For all of them, the **p-value > 0.05** is higher than the significance level established for the test, which does not allow us to reject the null hypothesis established for each test.

With respect to section 3.5:
From the test regarding the equality of means between the factors P and M of a low dose and another high dose, the result obtained for both gives a **p-value < 0.05**, lower than the significance level set for the test, which allows us to reject the null hypothesis of equality of means between both factors.

With regard to section 3.6:
The analysis of the variables in isolation or in pairs ("pairwise") is a practical and mild resource of theory, but **does not allow to establish a complete picture with all the variables exposed at the same time**, which is what is really happening in any biological/chemical/physical process, so that the readings that could be made from these analyses should be considered as quite limited (however mathematically correct they may be).

Ideally, in addition to the univariate or pairwise tests seen during this course, we would like to continue with multivariate analysis, but the basic requirement for any such test (especially multivariate analysis of variance, MANOVA) is that all the variables studied simultaneously must comply with normality and be independent among themselves (uncorrelated). The multivariate normality test cannot be performed because the matrix introduced is of a singular type (without solution), most probably due to the correlation tested between the variables studied. 

Regarding the linear regression analysis in question 6:_ _
The reading can be made from the graphs, which are generated from the linear model lm budget. What we wanted to know is whether this model is the one that best fits the behaviour experimentally followed by the two variables chosen (AUC 80 mg and Cmax 80 mg for the M factor), a fact that we can find from the graph of residuals vs fitted points, whose representation reflects that the linear fit is not good, and it is not the best-fitting model; **its graph deviates quite a lot from a straight line** , which would be what would be obtained in the case of a linear relationship between variables. It would be convenient to generate another linear model with the P factor, in order to contrast results and to be able to make a more robust reading.

**In general, and as a conclusion, it is advisable to carry out a large part of this study with a larger sample size, to be able to see if, given normality, when studying the variance, there is homoscedasticity and thus be able to carry out parametric tests. It would provide some additional information to the study as a whole, although these tests should not show statistically different results to those obtained with the non-parametric tests.**

It seems to be a drug with a peculiar pharmacokinetic behaviour, very irregular and heterogeneous for the drug P and somewhat less so for its metabolite M, although with notable exceptions ("influential cases") in both factors (AUC 20 mg for M, AUC high doses for P.)** **.

## Repository content
- Panel1.txt
- Panel2.txt
- Panel3.txt
- Panel4.txt
- PK_different_doses.Rmd

## How to use
The data are structured in 4 panels with 8 individuals each, for each of which plasma samples are collected before and after treatment. The treatment consists of the administration of a given drug (P) in different increasing doses.
The column Panel refers to the panel number, Sub is the identifier for each of the subjects, Cpd refers to what we are measuring in the plasma, it can be the concentration of the drug (P) or the concentration of one of the metabolites produced from it. The next 6 columns are grouped in threes, with the first group of 3 corresponding to the measurements for the Area Under the Curve (AUC), and the second group of columns referring to the measurement of the maximum concentration (Cmax).

## Contact
If you find a bug in the code or you want to make a comment, write to: aramisrojas.farmacia@gmail.com

Translated with www.DeepL.com/Translator

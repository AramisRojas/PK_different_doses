# PK (AUC & Cmax) with different doses
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

## Repository content
- Panel1.txt
- Panel2.txt
- Panel3.txt
- Panel4.txt
- 

## How to use
The data are structured in 4 panels with 8 individuals each, for each of which plasma samples are collected before and after treatment. The treatment consists of the administration of a given drug (P) in different increasing doses.
The column Panel refers to the panel number, Sub is the identifier for each of the subjects, Cpd refers to what we are measuring in the plasma, it can be the concentration of the drug (P) or the concentration of one of the metabolites produced from it. The next 6 columns are grouped in threes, with the first group of 3 corresponding to the measurements for the Area Under the Curve (AUC), and the second group of columns referring to the measurement of the maximum concentration (Cmax).

## Contact
If you find a bug in the code or you want to make a comment, write to: aramisrojas.farmacia@gmail.com

Translated with www.DeepL.com/Translator

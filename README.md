# Missing-RD-Patent-Relation-in-Fixed-Effects-Models
The repository provides the detailed examples and codes following the paper Chuang, H.C., Hsu, P.H., Kuan, C.M., Yang, J.C., 2022. *Throw the baby out with the bathwater: The missing RD-patent relation in firm fixed effects models*. The paper is available at SSRN.

In this set of code, we demonstrate how users can implement the following four ways for the potential bias from fixed effects regressions: 
  1. Within Between Variation: check if within-firm variation dominates between-firm variation or vice versa 
  2. Regression without firm FEs
  3. Hausman_Taylor_Estimates
  4. Post-regularization and DML LASSO methods (note that you may need to use STATA v17)

## Data and Code Availability:
We have prepared the following three documents:
  1. `Replicate_code_MissingRDPatent_ML.do` contains the STATA code that produces all our results in the paper;
  2. `Replicate_data_MissingRDPatent_ML.dta` contains the dataset (in STATA format) of the randomly selected 200 firms from our full sample.
  3. `Replicate_log_MissingRDPatent_ML.sml` contains the log file for running the the replicate do file on the sample data. 



**Sample Data Construction**
* We randomly pick up 200 firms from our sample in this replicate exercise. PERMCO here is a pseudo firm identifier for illustration purposes.
* Variables definitions are as follows, and interested readers are referred to our paper and the original data sources to collect them.
  - patent:     Number of patent (data from USPTO PatentsView)
  - lnnpatent:  The logarithm of one plus the number of patents (data from USPTO PatentsView)
  - RDAT:       Research and development (R&D) expenses scaled by the total asset (data from Compustat)
  - lnME:       The logarithm of market equity (data from CRSP)  
  - RD_missing: A binary variable indicating that R&D expenses are missing (data from Compustat)
  - lnAge:      The logarithm of years where a firm exists in Compustat (data from Compustat)
  - lnK2L:      The logarithm of net property, plant, and equipment divided by the number of employees(data from Compustat)
  - Tobin:      The market value of a firm divided by its replacement cost(data from Compustat and CRSP)
  - ROA:        Return on assets (data from Compustat)
  - Leverage:   Long-term debt plus current debt, divided by total assets (data from Compustat)
  - CASH AT:    Cash to the total asset  (data from Compustat)
  - KZidx:      The financial constrain index (data from Compustat)
  - Instown:    The total institutional ownership from 13f filings divided by the total number of shares outstanding (data from CRSP and Thomson/Refinitiv)
  - oms_HHidx:  One minus the Herfindahl-Hirschman index (HHI) based on three-digit industry classification (data from Compustat)
  - oms_HHidx_square: Square of oms_HHidx (data from Compustat)


**Results for Sample Data**
* Depends on computer capacity; we also provide results using the sample data.
  - "Fixed_Effects_Linear_Model_Estimates.csv" contains the results of the estimation for OLS with and without FEs (Table 3--8).
  - "Within_Between_Variation.smcl" contains the log file for running the Between and Within variations of the key variables (Table 9).  
  - "Hausman_Taylor_Estimates.csv" contains the results of the estimation for Hausman and Taylor with and without FEs (Table 10--11).
  - "Post_regularization_LASSO_Linear_Model_Estimates.csv" contains the results of the estimation for the Post-regularization LASSO linear model with and without FEs (Table 12--17).	
  - "DML_LASSO_Linear_Model_Estimates.csv" contains the results of the estimation for the double machine learning (DML) LASSO linear model with and without FEs (Table 12--17).	
  - "Fixed_Effects_Poisson_Model_Estimates.csv" contains the results of the estimation for the Poisson model with and without FEs (Table 18--21).
  - "Post_regularization_LASSO_Poisson_Model_Estimates.csv" contains the results of the estimation for the Post-regularization LASSO Poisson model with and without FEs (Table 22--25).		
  - "DML_LASSO_Poisson_Model_Estimates.csv" contains the results of the estimation for DML LASSO Poisson model with and without FEs (Table 22--25).	


**Software**
- The STATA version to fully implement the replicate_code is: STATA 17.
- The LASSO inference approaces: `poregress`, `xporegress`, `popoisson`, and `xpopoisson` are available since STATA 16.
  The cluster standard error for those methods are only available since STATA 17. 
  The robust standard error can still be used for those methods in STATA 16.
 - The following commands may need to be installed on STATA to run the repicate code: `reghdfe`, `ppmlhdfe`, and `esttab`.
  
## Contact
Please contact Po-Hsuan Hsu (pohsuanhsu@mx.nthu.edu.tw) or Hui-Ching Chuang (hcchuang@saturn.yzu.edu.tw) for any questions regarding the data.
**Please see the paper for more information. If you use these data sets, please CITE this paper as the data source**.

## Citation
```
Chuang, H.C., Hsu, P.H., Kuan, C.M., Yang, J.C., 2022. Throw the baby out with the bathwater: The missing
RD-patent relation in firm fixed effects models. Available at SSRN.
```
```
@article{chuang2022throw, 
         title={Throw the Baby Out with the Bathwater: {T}he Missing {R&D}-Patent Relation in Firm Fixed Effects Models},
         author={Chuang, Hui-Ching and Hsu, Po-Hsuan and Kuan, Chung-Ming and Yang, Jui-Chung},
         journal={Available at SSRN},
         year={2022}
}
```

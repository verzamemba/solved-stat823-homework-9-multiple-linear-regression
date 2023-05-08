Download Link: https://assignmentchef.com/product/solved-stat823-homework-9-multiple-linear-regression
<br>



The primary objective of the Study on the E cacy of Nosocomial Infection Control (SENIC Project) wasdetermine whether infection surveillance and control programs have reduced the rates of nosocomial(hospital-acquired) infection in United States hospitals. The dataset consists of a random sample of 113 hospitals selected from the original 338 hospitals surveyed. Each record in the dataset has an identification number and provides information on 11 other variables for a single hospital. The 12 variables are:

<img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2022/03/946.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

 <noscript>

  <img decoding="async" src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2022/03/946.png?w=980&amp;ssl=1" data-recalc-dims="1">

 </noscript>

The average length of stay in a hospital (Y) is assumed to be related to infection risk, available facilities and services, and routine chest X-ray ratio.

<ol>

 <li>Run three separate regression models for each of the three potential predictors (i.e., your first model is Y = <em><sub>—</sub></em><sub>0 </sub>+<em><sub>—</sub></em><sub>1</sub><em><sub>X</sub></em><sub>1 </sub>where <em><sub>X</sub></em><sub>1 </sub>= infection risk). Plot the three estimated regression functions over the data in three separate graphs. Does a linear relationship appear to provide a good fit for each of the three predictor variables?</li>

 <li>Which predictor leads to the smallest MSE (a.k.a., unexplained (error) variation)? Which predictor variable has the highest <em><sub>R</sub></em><sup>2</sup>? So, which of the three accounts for the largest reduction in</li>

</ol>




variability of the average length of stay?

<strong>Predictor                                     MSE        </strong><em>R</em>2

<strong>Infection risk</strong>




<strong>Facilities and Services Chest X-ray ratio</strong>

<ol start="3">

 <li>Obtain model residuals and use them for model diagnostics. Do you identify any issues with model assumptions? Refer to the last lesson for a review of the approach.</li>

</ol>

Testing linearity and constant variance by plotting fitted value against against residuals.

<ol start="4">

 <li>Delete cases 47 (<em><sub>X </sub></em>=6<em><sub>.</sub></em>5, <em><sub>Y </sub></em>=19<em><sub>.</sub></em>56) and 112 (<em><sub>X </sub></em>=5<em><sub>.</sub></em>9, <em><sub>Y </sub></em>=17<em><sub>.</sub></em>94) and refit the model for length of stay and infection risk. From this fitted model, obtain prediction intervals for new Y observations at X = 6.5 and X = 5.9. Does what was observed (i.e., <em><sub>Y </sub></em>=19<em><sub>.</sub></em>56<em><sub>,</sub></em>17<em><sub>.</sub></em>94) fall into the bounds of the respective prediction intervals? Discuss the significance of this.</li>

 <li>Build the “best” regression model for Y. Begin first with variable selection using the regsubsets function. Justify your final choice of model using criterion-based methods such as BIC and adjusted <em>R</em><sup>2</sup>, all of which can be extracted from the regsubsets model object using the summary function.</li>

 <li>Once you have identified your final model, check for and comment on any issues with:

  <ul>

   <li>Multicollinearity between predictors</li>

   <li>Outliers and influential points</li>

   <li>Appropriateness of predictors (i.e., is any transformation of predictors necessary?)</li>

   <li>Normality of residuals</li>

   <li>Constant variance of residuals. Calculate the variance inflation factor.</li>

  </ul></li>

</ol>

<em># Normality of residuals</em>

<strong>par</strong>(mfrow = <strong>c</strong>(1, 2))

<strong>shapiro.qqnorm</strong>(<strong>residuals</strong>(lmBM), cex = 2) <strong>shapiro.qqnorm</strong>(<strong>residuals</strong>(lmBMsub), cex = 2)

<ol start="7">

 <li>Provide an intuitive interpretation of your final model. In other words, explain your findings to me as if I have a minimal working knowledge of statistics. <strong>Extra Plots (Not Required)</strong></li>

</ol>

<strong>library</strong>(car)

<strong>marginalModelPlots</strong>(lmBMsub)

<h1>Marginal Model Plots</h1>

chestxray                                                             Fitted values

<strong>avPlots</strong>(lmBMsub, id = <strong>list</strong>(n = 2, cex = 0.6))

<h1>Added−Variable Plots</h1>

infection | others                                                        facil | others

chestxray | others
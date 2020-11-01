# Quantifying bias in mortality estimates when ignoring imperfect detection

In this repo, you will find a [flexdashboard](https://garrettgman.github.io/rmarkdown/flexdashboard/index.html) that allows exploring interactively the amount of bias in mortality estimates when imperfect detection is ignored. In details, we simulate data in R then fit and compare two models to these data: a conditional model that was used by [De Pascalis et al. (2020) in a recent paper](https://www.sciencedirect.com/science/article/abs/pii/S000632072030851X) and a joint capture-mark-recapture-recovery (CMRR) model à la Burnham with constant parameters. 

You can run the app locally on your computer from RStudio. To do so, download the file `index.Rmd`, open it in RStudio, click on `Run Document`, and the app should pop up. 

We use package `RMark` to fit a CMRR model to the simulated data. This package calls the `Mark` standalone computer program from `R`. Unfortunately, it makes it impossible to deploy the app on GitHub or shinyapps.io because we would need to have the `mark.exe` installed there. 

An alternative would be to use the [`marked` package](https://github.com/jlaake/marked) developed by Jeff Laake. This package uses `TMB` to fit capture-recapture models. It offers the option to fit the CMRR model with multiple states, check out `?Paradise_shelduck`. 

Another alternative would be to write the likelihood of the CMRR model entirely in R, without relying on `RMark`. I have [some code](https://github.com/oliviergimenez/multievent_jags_R) that I could adapt. See also [this recent paper](https://peerj.com/articles/9382/) for some inspiration.


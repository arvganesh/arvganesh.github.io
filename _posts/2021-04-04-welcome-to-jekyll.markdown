---
layout: post
title:  "Introduction – GSoC '21"
date:   2021-04-04 22:10:13 -0500
categories: GSOC time-series 
---
Hi! Over the next few months, I'll be posting updates of my work on Pythia, a library for time-series forecasting in Julia, inspired by [fable](https://fable.tidyverts.org/) in R, and [sktime](https://www.sktime.org/en/latest/) in Python. I want to use this post to briefly describe the motivation and overarching goals of the project. To learn more, check out my [proposal](https://docs.google.com/document/d/1PPBPF0ZWney-bK3XLIOo76HGcqaLp5rlQmeWVeC354s/edit?usp=sharing).

### Motivation

Time-series forecasting is quickly becoming an important tool in many fields. From finance¹, to epidemiology², to sales³, understanding the future is critical for making optimal decisions in the present.

While libraries with robust time-series forecasting capability exist in languages like [R](https://cran.r-project.org/web/packages/forecast/index.html) and [Python](https://www.statsmodels.org/stable/index.html), one with similar ease-of-use and functionality does not exist in Julia. The goal of this project is to develop and extend Pythia, a Julia library for time-series forecasting. Specifically, the focus of this summer will be to extend Pythia to include common forecasting algorithms, evaluation metrics, and plotting capabilities. Additionally, Pythia will be compatible with the [MLJ ecosystem](https://github.com/alan-turing-institute/MLJ.jl#the-mlj-universe). Furthermore, unit tests, documentation, and tutorials will be written.

Inspired by [forecast](https://cran.r-project.org/web/packages/forecast/index.html), [fable](https://fable.tidyverts.org/), [statsmodels](https://www.statsmodels.org/stable/index.html), and [sktime](https://www.sktime.org/en/latest/), Pythia will compile a variety of important functions for time series forecasting into **one unified interface**.

### Goals

To compartmentalize development, Pythia development will be separated into a few different blocks.

#### Algorithms
I plan on implementing these algorithms:
- Croston's + Croston's Adjusted Method
- Exponetial Smoothing Algorithms (ETS)
  - Simple Exponential Smoothing (implemented here)
  - Holt's Linear Methods
  - Dampted Trend Methods
  - Holt-Winter's Method
- ARMA Models – (p, q)
- Mean Forecasts
- Theta Method Forecasts

Both seasonal and non-seasonal models will be supported.

#### Evaluation Metrics
To evaluate forecasts, the following methods will be included:
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- Scaled Errors⁴
- Prediction Intervals

#### Visualization
To visualize forecasts, users will be able to:
- Plot observed and predicted observations vs. time
- Plot Prediction Intervals

#### MLJ Integration
First, Pythia will be written as a standalone library. After the forecasting algorithms have been written, a wrapper for Pythia will be written in MLJ.

Additionally, tests, documentation, and tutorials will be written.

### Conclusion

Thanks for reading! Please reach out to me via the [Julia Slack](https://julialang.org/slack/) (@arvganesh) if you have any questions or are interested in contributing. Finally, I'd like to thank my mentors [Sebastian Vollmer](https://www.turing.ac.uk/people/researchers/sebastian-vollmer), [Andrii Babii](https://ababii.github.io/), and [Markus Löning](https://www.turing.ac.uk/people/former-enrichment-students/markus-loning) for their feedback and advice on my proposal.

#### References
1. Kim, K. 2003. “Financial Time Series Forecasting Using Support Vector Machines.” Neurocomputing.
2. Maleki, Mohsen, Mohammad Reza Mahmoudi, Darren Wraith, and Kim-Hung Pho. 2020. “Time Series Modelling to Forecast the Confirmed and Recovered Cases of COVID-19.” Travel Medicine and Infectious Disease 37 (September): 101742.
3. Willemain, Thomas R., Charles N. Smart, Joseph H. Shockor, and Philip A. DeSautels. 1994. “Forecasting Intermittent Demand in Manufacturing: A Comparative Evaluation of Croston’s Method.” International Journal of Forecasting 10 (4): 529–38.
4. Hyndman, Rob J., and Anne B. Koehler. 2006. “Another Look at Measures of Forecast Accuracy.” International Journal of Forecasting. https://doi.org/10.1016/j.ijforecast.2006.03.001.

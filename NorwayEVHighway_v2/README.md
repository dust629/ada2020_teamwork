# Title:

Google Trends insight in understanding what drives Norwegians into purchasing an electric vehicle

# Abstract:

Norway is well advanced compared to other countries in the expansion of its electric vehicle (EV) fleet thanks to strong incentives (100% tax for combustion vehicles which are exempted for EV). It has even reached the top place in total EV sales despite its country size. Understanding the evolution of EV car sales in Norway could help predicting future sales in other countries. 

Now that we have a working model to assess the predictive power of Google Trends on a certain output, we will then extend this on investigating which set of indicators best improve the short-term prediction of a Norway EV sales. The indicators will be grouped in categories such as environment, car models, infrastructure or policy related. Additionally, we will assess the impact of corner-stone events such as the Paris Climate Accord, the release of the Tesla model 3 as well as the implementation of tax-cuts for EVs in Norway on car sales. All of this will help us assess which category of indicators/events influence most the consumer propensity to switch from combustion to electric.

# Research Questions:

- Which category of indicators influence most EV market penetration in Norway?  Is it environment, car models, infrastructure (charging stations) or government policies?
- Which event influenced most EV sales in Norway (the Paris Climate Accord, the release of the Tesla model 3 or the increase of carbon pricing on petrol products due to extra fees (climate settlement 2012))?
- Is there a coherent correlation between the answers of both questions above? 

# Proposed dataset:

1) Opplysningsrådet for Veitrafikk - Road Traffic Information Council

- https://ofv.no/ 
- The data should be bought but as students we managed to request it for free
- We have not accessed the data yet, so we do not know the full content of it and cannot infer its size yet. Most probably it would be at around 100 rows (1 per month for 10 years).

2) Google Trends:

- https://trends.google.com/trends
- We will pick several indicators and investigate which ones help us best in predicting. Indicators will be grouped in these categories:
  - Environment
  - Car models
  - Infrastructure (charging stations)
  - Government policies

# Methods:

We will: 

- use market share of EV versus other vehicles instead of as a proxy for sales as our prediction output. Economical factors and policies are meant to drive consumers aways from combustion vehicles and towards EV. If EV sales increase but combustion vehicule sales keep on increasing just as much then the policies are in vain. The true interesting metric is therefore market share instead of pure sales. 
- use the same method in the paper for Motor Vehicles and Parts,  select relevant terms for google trends

- do several experiments to find a suitable match
- use the expanding window to train the data and make prediction

The models will be:

- Base model features: log(mkt_share) = log(mkt_share_1monthlag) + log(mkt_share_12monthslag) 
- Indicators model features: 
  - Base + each keyword individually (totalling 20 models)
  - Base + Best model (found by experimental combinations)
  
- Indicators and events model features (Discontinuous regression model): 
  - Base + car model related key dates
  - Base + range anxiety related key dates
  - Base + environment related key dates
  
Unfortunately an economic event could not be found because they happened before the dataset from OFV begins. 

# Key findings:
From the discontinuous regression analysis we can see an intercept shift upwards for the release of the Nissan Leaf, as well as the beginning of the Tesla supercharging infrastructure project. 
For the prediction models keywords relating to economic considerations and EV-model interest are provides the best improvements to the model, as much as 3.68%.
Finally, the merits of using purely these metrics to evaluate what motivates a buyer is discussed
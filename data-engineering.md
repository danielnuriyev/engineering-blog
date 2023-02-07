# What is Data Engineering versus Data Analytics and Data Science

This should clarify the confusion of terms

## Data Engineers 

Data Engineer is a software engineer who 
- creates connectors to external data sources
- creates infrastructure for piping data from external data sources into a "place" 
where the data can be used by Data Analysts and Data Scientists for analytics.
- backs the data up. Creates mechanisms for restoring the data.
- protects the data
- creates infrastructure for Data Analysts and Data Scientists to explore, analyse, transform, present, document and share data
- creates infrastructure for data validation/verification
- creates infrastructure for Data Scientists to train models during development, to run models in production (ML Ops)

In other words, a Data Engineer provides Analysts and Data Scientists infrastructure to pipe data and work with it.

Data Engineers are not familiar with the data.

Data Engineers should be good in cloud infratructure, security, software development, data storage formats and technologies, SQL, 
ML Ops, statistics and ML for data validation, user support.

## Data Analysts

Data Analysts use the infrastructure provided by the Data Engineers to connect to data sources, pipe data, analyze it 
and present the analyses.

Analysts are familiar with the data and its meaning but they require Data Engineering direction when they come across technical roadblocks.

Analysts should be good at
- data exploration and presentation tools such as Tableau.
- SQL
- Python for data analysis (pandas etc.)
- statistics

## Data Scientists

Data Scientists use the infrastructure provided by the Data Engineers to connect to data sources, pipe data, analyze it using
Machine Learning and present the analyses.

Data Scientists are familiar with the data and its meaning 
but they require Data Engineering direction when they come across technical roadblocks.

Data Scientists should be good at
- all steps of ML development lifecycle
- tools used during ML development such as Jupyter
- statistics
- ML algorithm types, their uses, math behind them

ML work has a longer and interative lifecycle than data/software engineering and data analytics.

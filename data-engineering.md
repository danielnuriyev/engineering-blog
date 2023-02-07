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
ML Ops, statistics and ML for data validation, user support. It is a broad skillset and therefore hard to find. Non Data Engineers, i.e. other types of backend and cloud engineers, are not necessairy familira well enough with these technologies. 

## Data Analysts

Data Analysts use the infrastructure provided by the Data Engineers to connect to data sources, pipe data, analyze it 
and present the analyses.

Analysts are familiar with the data and its meaning but they require Data Engineering direction when they come across technical roadblocks.

Analysts should be good at
- data exploration and presentation tools such as Tableau.
- SQL
- Python for data analysis (pandas etc.)
- statistics

It is hard to find an analyst with the full technical skill set because a person interested in tech skills is less interested in analytics.

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

## Data Org

Data Scientists and Data Analysts know what they want but they do not have technical skills to pick technologies and
set up the development and production infrastructure, to fetch data etc.

Data Analysts are not familiar with ML development and math.

Data Engineers can do anything but are not interested in looking at the data or working on the relatively lengthy and interative ML development.

To achieve good analytics, a company should hire for the 3 roles and find a way for them to work together.

I find it useful to organize the work along several parallel tracks:
- long term projects, such as infrastructure development, new model development
- current projects
- user interaction: 
  - engineering support for analysts and data scientists
  - interaction of analysts and data scientists with business stakeholders
  - production alerts

Without the parallel tracks, it is only possible to work on the current top priority for the business 
which sounds efficient but every good engineer knows that a bad infratructure is a short term gain that exponentially drops with the size
of data and complexity of analysis. Dropping includes good people leaving.

It is important to rotate people over the tracks. This makes every engineer, analyst, scientist familiar with everything. 
It is good when someone decides to leave and it prevents people from leaving because they grow professionaly.

It is good to organize the analytics and data science work not only into the 3 tracks but also by focus areas, such as marketing, finance etc. Imagine a table having 3 horizontal track and N vertical areas. And, then create both rotation over the track and over focus areas to prevent atrition and siloing.

It is important to proactively bring all team members to the level of good technical/analytics/ML decisions/design.

A good size of a Data Engineering Team is at least team lead + tech lead + senior + senior + any. This covers rotation over the tracks and people leaving. The role of the Team Lead is half inside the team and half interacting with the other teams and the business stakeholders, his/her focus is long term, whereas the Tech Lead can make daily decisions based on established roadmap, policies etc.

Analytics and Data Science Teams can have more people because in addition to the tracks, there can be focus areas.

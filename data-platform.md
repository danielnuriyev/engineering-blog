WIP

# How to build a data platform

## Requirements

### Pipelines

- It should be simple to add a custom data source, transformation and sink
- It should be possible control the throughput of a pipeline in order not to overload sources/destinations
- A data pipeline should allow conditions, branching, fanning out/in
- It should be possible to run data pipelines both on schedules and as dependencies on other pipelines
- It should be possible to provide custom logic for error handling
- It should be easy to deploy multiple copies of the platform for disaster recovery, testing and development
- Testing should be as close to production as possible in structure, resources and data
- The platform should be designed to scale X100 without a redesign
- Monitoring should be good enough to see the history, the current state, what runs next and should be helpful in debugging
  
### Storage

It is convenient to store data so that it will be possible to query it using standard SQL from common data tools.

### Tools

A platform should make it easy to:
- find data
- explore it
- visualize it

### Participants

A platform should support multiple types of users. Every company names them differently. I will give an example naming in the brackets.

- Creators of the platform (data platform engineers)
- Users who will participate in the development of the platform (data engineers)
- Users who will build pipelines (analytics engineers)
- Users who will explore data using Python (analytics engineers, data scientists)
- Users who will explore data using SQL (analysts)
- Users who will explore data using visual tools (business users)
- Legal team to help classify the data and access
- Security team to help monitor data security and access

### Monitoring

Pipelines should be monitored for:
- speed
- resources
- errors
- whether they start on time
- how the environment where they run scales up/down
- whether the amount of data statistically deviates from the usual
- whether the statistics of each data column/field deviates from the usual
- whether data is logically correct
- cost
- whether data contains PII

Storage should be monitored for:
- cost

Any element of the platform that can be hacked from outside, from within the code and by the users must be monitored.

### Processes

The following processes should be established:
- development of the platform from idea to deployment. In addition to the technical aspects such as code style and structure, documentation, testing, review, deployment, monitoring, performance, resilience, scale, disaster recovery but also cost and security.
- monitoring the platform and addressing production issues
- process for users who want to participate in the development of the platform and thus a process for each type of users
- processes to support each type of users
- data participants who are part of a single data organization there should be an established process for hiring and development for each type of data participant including not only purely professional aspects but also how people interact with each other to make the environment supportive and cooperative.

Each process should have the corresponding tooling and documentation.

IMPORTANT: process is a means, not the goal. Processes should be reviewed and adjusted

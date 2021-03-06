# Pivotal Real-Time Data Science: Scoring-as-a-Service
## moves

This application demonstrates real-time model scoring as a service using Pivotal Cloud Foundry (PCF), Pivotal Big Data Suite, Spring Cloud Data Flow, and Python-based open source machine learning. The pipeline applies broadly and would allow us to evaluate and score almost any feed of streaming data - from sensor data to unstructured text data - to drive real-time action.

Take a look at this [blog post](https://blog.pivotal.io/data-science-pivotal/products/scoring-as-a-service-to-operationalize-algorithms-for-real-time) and the [about page](https://test-dashboard-jyi.cfapps.io/about) for more information.

[![Alt text](https://img.youtube.com/vi/j6yiVhm9bhs/0.jpg)](https://www.youtube.com/watch?v=j6yiVhm9bhs)

## Pre-requisites

* Pivotal Cloud Foundry
    * Redis service

## Deploying the app on Pivotal Cloud Foundry

### 1. Update the 3 application names in manifest.yml

These app names will become part of the domain URLs, so change as desired.
 
    ...
    name: DASHBOARD-APP-NAME
    ...
    name: TRAINING-APP-NAME
    ...
    name: SCORING-APP-NAME
    ...

*Note that underscores are not allowed in the app names. Cloud Foundry automatically converts them to dashes, which disrupts URL routing.*

### 2. Update parameters in JavaScript

Edit file "moves-app/moves/static/js/movesParams.js" to reflect route 
names of training and scoring applications as specified in previous step. 

### 3. Create redis service and push application

    cf create-service p.redis cache-small moves-redis
    cf push

This has been tested using Pivotal Web Services [PWS](https://run.pivotal.io)

[http://docs.run.pivotal.io/devguide/deploy-apps/deploy-app.html](http://docs.run.pivotal.io/devguide/deploy-apps/deploy-app.html)
    
## Contact

Chris Rawles is the original author. 

For more information, please contact Scott Hajek (shajek@pivotal.io) and Jarrod Vawdrey (jvawdrey@pivotal.io)

# Overview
DataHem is a serverless real-time end-2-end ML pipeline built entirely on Google Cloud Platform services - AppEngine, PubSub, Dataflow, BigQuery and Cloud ML.

# Benefits
When building ML/Data products, your most valuable asset is your data. Hence, the purpose of DataHem is to give you:

1. full control and ownership of your data
2. unsampled data
3. data in real time
4. the ability to replay/reprocess your data unlimited times
5. data synergies -> collect once and use for multiple purposes (reporting, analytics and building data/ML products)
6. low cost of operations and maintenance
7. scalability
8. data as a stream and at rest
9. activation of data

# Target architecture

![Target architecture](https://github.com/mhlabs/datahem/raw/master/images/target_architecture.PNG)

# Use cases

## 1. Digital Analytics
The first use is to leverage your implementation of Google Analytics / Measurement Protocol. Google Analytics is awesome, but has some limitations worth to address in order to take reporting, analytics and machine learning to the next level. By adding a custom task to your Google Analytics tracker, DataHem eliminates many of the limitations of both the free and the premium version of Google Analytics and gives you:
- Unsampled data
- Real-time data
- Unlimited custom dimensions and metrics
- Unlimited data volume
- Enriched data as a stream
- Unlimited reprocessing of data
- No licensing fees (open source)

# License
DataHem is licensed under [MIT](https://opensource.org/licenses/MIT)

# DataHem ecosystem
The architecute of DataHem consists of loosely coupled parts to enable future replacements and extensions of parts.

* **[tracker](https://github.com/mhlabs/datahem.tracker):** Send data to the collector, currently supporting Google Analytics javascript tracker
* **[collector](https://github.com/mhlabs/datahem.collector):** Collect data sent from trackers and publish the data on pubsub, currently running on Google App Engine Standard (Java)
* **[processor](https://github.com/mhlabs/datahem.processor):** Process bounded and unbounded data and write to PubSub and BigQuery, currently using Google Dataflow (Apache Beam) and supports processing of Google Analytics hits and AWS Kinesis events
* **[serializer](https://github.com/mhlabs/datahem.serializer):** Serialize structured data, currently using protocol buffers
* **[infrastructor](https://github.com/mhlabs/datahem.infrastructor):** Infrastructure as code to easily setup API:s and services required, currently using Google Deployment Manager
* **predictor** (backlog) predictions made on streaming data
* **pseudonymizor** (backlog) pseudonymizing personal and/or sensitive data
* **ruler** (backlog) processing rules for personal data
* **activator** (backlog) serving predictions via REST/gRPC

# Setup
[Follow instructions in wiki how to set up the various parts in DataHem](https://github.com/mhlabs/datahem/wiki/Setup)

# Background
DataHem was started in June 2017 by [robertsahlin](https://github.com/robertsahlin) / [ML-engineer](https://github.com/ML-engineer). It was open sourced and officially brought under Mathem's mhlabs Github account and announced in May 2018.

The name DataHem is a play of words to resemble MatHem, the Swedish online grocery store where DataHem is developed. "Data" = "data". "Hem" = the swedish word for "Home".

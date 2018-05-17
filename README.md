# datahem
A serverless real-time end-2-end ML pipeline built entirely on Google Cloud Platform services - AppEngine, PubSub, Dataflow, BigQuery and Cloud ML

The architecute of datahem consists of loosely coupled parts to enable future replacements and extensions of parts.

datahem currently includes:
* **[tracker](https://github.com/mhlabs/datahem.tracker):** Trackers to send data to datahem collector, currently supporting Google Analytics javascript tracker
* **[collector](https://github.com/mhlabs/datahem.collector):** Collector to collect data sent from trackers and publish the data on pubsub, currently running on Google App Engine Standard (Java)
* **[processor](https://github.com/mhlabs/datahem.processor):** Processor to process bounded and unbounded data and write to PubSub and BigQuery, currently using Google Dataflow (Apache Beam) and supports processing of Google Analytics hits and AWS Kinesis events
* **[serializer](https://github.com/mhlabs/datahem.serializer):** Serializer to serialize structured data in datahem, currently using protocol buffers
* **[infrastructor](https://github.com/mhlabs/datahem.infrastructor):** Infrastructure as code to easily setup API:s and services necessary for datahem, currently using Google Deployment Manager

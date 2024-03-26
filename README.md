# Real-Time Truck Fleet Violation Prediction

## Overview
This project aims to predict violations in real-time for a fleet of trucks using a Kafka topic. The architecture facilitates the ingestion of streaming data from truck sensors, processes the data through Apache Spark, and uses machine learning models to predict potential violations.

## Architecture Diagram

![Real-Time Prediction Architecture](https://i.imgur.com/kAXZl6n.png)

## Components

### Data Sources
- **Truck Fleet Simulator:** Simulates real-time data from truck sensors and sends the data to Apache Kafka.

### Apache Kafka
- **Ingestion:** Kafka is used to ingest real-time streaming data from the Truck Fleet Simulator.
- **Prediction:** Kafka also acts as the sink for the predictions made by the machine learning model, allowing downstream systems to consume the prediction results.

### Apache Spark
- **Spark Streaming:** Processes the real-time streaming data from Kafka.
- **Spark MLlib:** Machine learning library used for training and inference of the predictive model.

### Hadoop (HDFS)
- **Training Data Storage:** Historical data used for training the machine learning model is stored in Hadoop Distributed File System (HDFS).

## Workflow
1. **Data Ingestion:** The Truck Fleet Simulator sends streaming data to Apache Kafka.
2. **Data Processing and Training:**
   - Spark Streaming processes the incoming data in real-time.
   - Spark MLlib utilizes the processed data to train the predictive model with historical data stored in HDFS.
3. **Prediction and Output:**
   - The trained model performs real-time inference on the streaming data.
   - Predictions (Violation/No Violation) are then sent to another Kafka topic.

## How to Run the Demo
To run this demo, follow these steps:
1. Ensure that Kafka, Hadoop, and Spark are correctly installed and configured on your system.
2. Start the Truck Fleet Simulator to begin data generation.
3. Launch Kafka to create the necessary topics for data ingestion and prediction output.
4. Run the Spark Streaming application to process incoming data.
5. Use Spark MLlib to train the model with the historical data.
6. Finally, monitor the Kafka topic for predictions and consume the data as needed for downstream processing or alerting.

## License
[MIT License](LICENSE)

## Acknowledgments
This project would not be possible without the contributions of our team members and the support from our instructors.

## Contact Information
For any inquiries regarding the project, please contact us at [juliovalenzuela.pavez@gmail.com](mailto:juliovalenzuela.pavez@gmail.com).

# Building-weather-data-pipeline-orchestration-with-apache-airflow
This project involves creating and monitoring  an ETL pipelines using Apache Airflow. A weather data was used in for this project and it is stored in postgres database using a docker-compose file. 

# Introduction
A weather data set gotten from .An ETL job/data set was extracted from the weather API, transformed into json and loaded into postgres database. portainer.io UI was used to visualize the data.

# Set up
Docker-compose.yml file was used to run the airflow dag. python operator was mainly used for the flow of the services. xcoms airflow services was used to share data between tasks as tasks uses xcoms to exchange data.

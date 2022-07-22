# Building-weather-data-pipeline-orchestration-with-apache-airflow
This project involves creating and monitoring  an ETL pipelines using Apache Airflow. A weather data was used in for this project and it is stored in postgres database using a docker-compose file. 

# Introduction
A weather data set gotten from [weatrhe API] {https://www.weatherapi.com}. An ETL job/data set was extracted from the weather API through query, create a dag transformed into json, schedule the dag and loaded into postgres database, portainer.io UI was used to visualize the data.
![portainer img 1](https://user-images.githubusercontent.com/41475769/180443243-8c587b68-ecf8-4a88-80a6-cb0f02a5bf2d.PNG)


# Set up
Docker-compose.yml file was used to run the airflow dag. python operator was mainly used for the flow of the services. xcoms airflow services was used to share data between tasks as tasks uses xcoms to exchange data. 4 dags were created in this project for orchestration:
1. dags\00_ETLWeatherPrintAirflow2 - A simple ETL data pipeline that fetch the data from an API and print it
2. dags\01-ETLWeatherPrint - A simple Transform task which takes in the API data and only extracts the location, wind, the temperature and time.
3. dags\02-ETLWeatherPostgres - A simple Load task which takes in the result of the Transform task and writes it to the postgres database.
4. dags\03-ETLWeatherPostgresAndPrint - This is a simple ETL data pipeline example which demonstrates the use of the TaskFlow API using three simple tasks for Extract, Transform, and Load.

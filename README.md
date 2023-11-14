## Prerequisites for the project

- Docker
- Astro CLI
- Soda
- GCS account

## Astro CLI
- The Astro CLI is a command-line interface for data orchestration. It allows you to get started with Apache Airflow,  It's the easiest way to get started with Apache Airflow. <br/>
- To install astro cli we need to make sure we have windows 10 and docker installed.

[Helpful vedio to download Astro CLI](https://www.youtube.com/results?search_query=download+astro+cli+on+windows)<br/>
[Helpful repo to download latest Astro CLI zip file](https://gist.github.com/andriisoldatenko/e351f5310d14c0270fad681bfd7c49d3) <br/><br/>
![image](https://github.com/sundas586/Retail-Project-An-end-to-end-Airflow-data-pipeline-with-BigQuery-dbt-Soda-and-more-/assets/33677647/0a9c581c-535e-4a8c-b098-1bbd09bf02d5)
![image](https://github.com/sundas586/Retail-Project-An-end-to-end-Airflow-data-pipeline-with-BigQuery-dbt-Soda-and-more-/assets/33677647/519811d6-9a17-4288-9f11-0f0c0fbaae56)
![image](https://github.com/sundas586/Retail-Project-An-end-to-end-Airflow-data-pipeline-with-BigQuery-dbt-Soda-and-more-/assets/33677647/9458b5ff-c460-4c91-ae58-9bb0ef86ecf5)


## Soda
Data quality framework (https://www.soda.io/) <br/><br/>

Soda is a platform that enables Data Engineers to test data for quality where and when they need to.
- Use Soda with GitHub Actions to test data quality during CI/CD development.
- Use it with Airflow to test data quality after ingestion and transformation in your pipeline.
- Integrate Soda with your on-call systems to get instant alerts when data quality issues surface.
- Integrate with the tools and workflows your data team is already using.

## Cosmos
- New way to integrate dbt with airflow <br/>
- In cosmos all your dbt models becomes a task in the data pipeline. <br/>
- **alternate** : BashOperater to execute dbt commands

## Kaggle DataSet Used
https://www.kaggle.com/datasets/tunguz/online-retail

## Design :
![image](https://github.com/sundas586/Retail-Project-An-end-to-end-Airflow-data-pipeline-with-BigQuery-dbt-Soda-and-more-/assets/33677647/37c3f620-08a7-43cd-a9ab-d34e6041e069)



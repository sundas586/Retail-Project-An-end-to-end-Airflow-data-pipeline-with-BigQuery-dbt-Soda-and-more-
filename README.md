## Prerequisites for the project

- Docker
- Astro CLI
- Soda
- GCS account

## Astro CLI
- The Astro CLI is a command-line interface for data orchestration. It allows you to get started with Apache Airflow,  It's the easiest way to get started with Apache Airflow. <br/>
- To install astro cli we need to make sure we have windows 10 and docker installed.

```diff
astro dev init
# to initiate development environment
# please make sure to restart the system, as otherwise, this command will not execute, even when I ran it, after restart, it executed
```  

[Helpful vedio to download Astro CLI](https://www.youtube.com/results?search_query=download+astro+cli+on+windows)<br/>
[official website to download latest Astro CLI zip file](https://docs.astronomer.io/astro/cli/install-cli?tab=windows#install-the-astro-cli)<br/>
[Helpful repo to download latest Astro CLI zip file](https://gist.github.com/andriisoldatenko/e351f5310d14c0270fad681bfd7c49d3) <br/><br/>
![image](https://github.com/sundas586/Retail-Project-An-end-to-end-Airflow-data-pipeline-with-BigQuery-dbt-Soda-and-more-/assets/33677647/0a9c581c-535e-4a8c-b098-1bbd09bf02d5)
![image](https://github.com/sundas586/Retail-Project-An-end-to-end-Airflow-data-pipeline-with-BigQuery-dbt-Soda-and-more-/assets/33677647/519811d6-9a17-4288-9f11-0f0c0fbaae56)
![image](https://github.com/sundas586/Retail-Project-An-end-to-end-Airflow-data-pipeline-with-BigQuery-dbt-Soda-and-more-/assets/33677647/9458b5ff-c460-4c91-ae58-9bb0ef86ecf5)
![image](https://github.com/sundas586/Retail-Project-An-end-to-end-Airflow-data-pipeline-with-BigQuery-dbt-Soda-and-more-/assets/33677647/9287c89f-aaa3-4305-a944-c136d242c876)

- Here astronomer CLI image in the docker file, behind the scenes, is just for airflow easy integration with docker.
  ![image](https://github.com/sundas586/Retail-Project-An-end-to-end-Airflow-data-pipeline-with-BigQuery-dbt-Soda-and-more-/assets/33677647/34df1eff-616f-426b-b3a0-7885c5614125)

- packages.txt to install operating system dependencies.<br/>
- requirements.txt to install python packages.<br/>
- dags directory to put our pipelines here.<br/>
- include dir to put things that are not pipelines (like CSV file)
![image](https://github.com/sundas586/Retail-Project-An-end-to-end-Airflow-data-pipeline-with-BigQuery-dbt-Soda-and-more-/assets/33677647/d9ada26e-9972-4a64-a881-290c0a93d11b)
<br/>
```diff
astro dev start
# just run this command after init command & you will see airflow up & running
```
<br/>
- url : localhost:8080/home (admin/admin)

### how to find the proper path for service account :

- Run the following command :
```diff
astro dev bash
# This command alow you to you Astro Cli in terminal
# also
# this command provides the path of where the airflow schedular is running
```
- Then :
- ![image](https://github.com/sundas586/Retail-Project-An-end-to-end-Airflow-data-pipeline-with-BigQuery-dbt-Soda-and-more-/assets/33677647/9ff22765-0e66-4697-bcd6-634ef3124dae)
- put this final address in airflow connection :
- ![image](https://github.com/sundas586/Retail-Project-An-end-to-end-Airflow-data-pipeline-with-BigQuery-dbt-Soda-and-more-/assets/33677647/16c90f85-edb5-4c2b-bf6b-254138479127)
 





## Soda
Data quality framework (https://www.soda.io/) <br/><br/>

Soda is a platform that enables Data Engineers to test data for quality where and when they need to.
- Use Soda with GitHub Actions to test data quality during CI/CD development.
- Use it with Airflow to test data quality after ingestion and transformation in your pipeline.
- Integrate Soda with your on-call systems to get instant alerts when data quality issues surface.
- Integrate with the tools and workflows your data team is already using.

```diff
pip install -i https://pypi.cloud.soda.io soda-postgres
pip install -i https://pypi.cloud.soda.io soda-mysql
```
![image](https://github.com/sundas586/Retail-Project-An-end-to-end-Airflow-data-pipeline-with-BigQuery-dbt-Soda-and-more-/assets/33677647/ffc3c84b-e22d-45da-8f98-f3e4e4cd78aa)
![image](https://github.com/sundas586/Retail-Project-An-end-to-end-Airflow-data-pipeline-with-BigQuery-dbt-Soda-and-more-/assets/33677647/8f8ce6a4-924d-46ec-baea-13ec46b0b98b)

## Cosmos
- New way to integrate dbt with airflow <br/>
- In cosmos all your dbt models becomes a task in the data pipeline. <br/>
- **alternate** : BashOperater to execute dbt commands (but there will be no visual progress of models at the time )

## GCS account
- To load a file, one way is to create a bucket (You store objects in containers called buckets. All buckets are associated with a project).
- But as I used a free version of BigQuery web UI, I directly created a table of this csv file.
  
  ![image](https://github.com/sundas586/Retail-Project-An-end-to-end-Airflow-data-pipeline-with-BigQuery-dbt-Soda-and-more-/assets/33677647/1108b304-7334-4adb-81dd-1ace37261874)

- [a guide video for service account creation](https://www.youtube.com/watch?v=q9qHHEk5rVM)
- created a service account & generated a .json key, with the help of the above video
![image](https://github.com/sundas586/dbt-project/assets/33677647/8855f200-f5ca-42d7-8b4a-ad562c8b0cca)
- create a folder gcp as: OnlineRetail/include/gcp, inserted **datawarehouse-404612-8dd1b6e61781.json** service account file here and renamed it to service_account.json

![image](https://github.com/sundas586/Retail-Project-An-end-to-end-Airflow-data-pipeline-with-BigQuery-dbt-Soda-and-more-/assets/33677647/6ce39810-ea79-4ee7-ba21-31378738bca5)
  
  


## Kaggle DataSet Used
https://www.kaggle.com/datasets/tunguz/online-retail

## Design :
![image](https://github.com/sundas586/Retail-Project-An-end-to-end-Airflow-data-pipeline-with-BigQuery-dbt-Soda-and-more-/assets/33677647/37c3f620-08a7-43cd-a9ab-d34e6041e069)



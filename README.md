# Apache Airflow on Steroids with Java, Scala and Python Spark Jobs

This project orchestrates Spark jobs written in different programming languages using Apache Airflow, all within a Dockerized environment. The DAG `sparking_flow` is designed to submit Spark jobs written in Python, Scala, and Java, ensuring that data processing is handled efficiently and reliably on a daily schedule.

## Project Structure

The DAG `sparking_flow` includes the following tasks:

- `start`: A PythonOperator that prints "Jobs started".
- `python_job`: A SparkSubmitOperator that submits a Python Spark job.
- `scala_job`: A SparkSubmitOperator that submits a Scala Spark job.
- `java_job`: A SparkSubmitOperator that submits a Java Spark job.
- `end`: A PythonOperator that prints "Jobs completed successfully".

These tasks are executed in a sequence where the `start` task triggers the Spark jobs in parallel, and upon their completion, the `end` task is executed.

### The DAG will execute the following steps:
* Print "Jobs started" in the Airflow logs.
* Submit the Python Spark job to the Spark cluster.
* Submit the Scala Spark job to the Spark cluster.
* Submit the Java Spark job to the Spark cluster.
* Print "Jobs completed successfully" in the Airflow logs after all jobs have finished.

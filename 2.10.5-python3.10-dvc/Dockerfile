FROM apache/airflow:2.10.5-python3.10
USER root
RUN apt-get update \
  && apt-get install -y --no-install-recommends \
         git  \
		 postgresql \
		 libpq-dev \
		 curl \
  && apt-get autoremove -yqq --purge \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*
USER airflow
ADD requirements.txt .
RUN pip install apache-airflow==${AIRFLOW_VERSION} -r requirements.txt
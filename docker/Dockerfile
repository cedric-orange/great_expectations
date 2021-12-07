ARG PYTHON_DOCKER_TAG=3.9

FROM python:${PYTHON_DOCKER_TAG}

ARG GE_EXTRA_DEPS="spark,sqlalchemy,redshift,s3,gcp,snowflake"
ARG GE_VERSION="0.13.45"

RUN pip install --no-cache-dir great_expectations[${GE_EXTRA_DEPS}]=="${GE_VERSION}"

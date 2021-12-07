ARG PYTHON_DOCKER_TAG

FROM python:3.9

ARG GE_EXTRA_DEPS="spark,sqlalchemy,redshift,s3,gcp,snowflake"

ENV PYTHONIOENCODING utf-8
ENV LANG C.UTF-8
# Path where the root of the GE project will be expected
ENV GE_HOME /usr/app/great_expectations
#ENV GE_VERSION=${GITHUB_REF_NAME}
ENV GE_VERSION="0.13.45"

LABEL maintainer="great-expectations"
LABEL org.opencontainers.image.title="Great Expectations"
LABEL org.opencontainers.image.description="Great Expectations. Always know what to expect from your data."
LABEL org.opencontainers.image.version=${GE_VERSION}
LABEL org.opencontainers.image.created=${CREATED}
LABEL org.opencontainers.image.url="https://github.com/great-expectations/great_expectations"
LABEL org.opencontainers.image.documentation="https://github.com/great-expectations/great_expectations"
LABEL org.opencontainers.image.source="https://github.com/great-expectations/great_expectations"

# The interface to Great Expectations
# is a CLI, therefore we use root to
# avoid common permissioning pitfalls
USER root



RUN mkdir -p /usr/app/great_expectations && \    
    pip install great_expectations[${GE_EXTRA_DEPS}]==${GE_VERSION} && 
    
WORKDIR ${GE_HOME}

ENTRYPOINT ["great_expectations"]
CMD ["--help"]

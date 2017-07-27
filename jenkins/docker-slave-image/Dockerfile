FROM jenkins/jnlp-slave
MAINTAINER Vic Iglesias <viglesias@google.com>

ENV CLOUDSDK_CORE_DISABLE_PROMPTS 1
ENV PATH /opt/google-cloud-sdk/bin:$PATH

USER root

RUN apt-get update && apt-get install -y \
    jq \
    build-essential \
    libssl-dev \
    libffi-dev \
    python3-dev \
    python3-pip
RUN pip3 install --upgrade \
    cryptography \
    paramiko \
    ansible
RUN curl https://sdk.cloud.google.com | bash && mv google-cloud-sdk /opt
RUN gcloud components install kubectl

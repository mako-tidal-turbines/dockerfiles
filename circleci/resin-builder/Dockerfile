FROM circleci/buildpack-deps:latest

# install gcloud
RUN echo "deb http://packages.cloud.google.com/apt cloud-sdk-jessie main" | sudo tee -a /etc/apt/sources.list.d/google-cloud-sdk.list && \
    curl -sS https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add - && \
    sudo apt-get update -y -qq && \
    sudo apt-get install google-cloud-sdk -y && \
    sudo rm -rf /var/lib/apt/lists/*

# install resin-cli
ENV RESINCLI_VERSION 7.6.1
RUN sudo wget -q -O tmp.zip https://github.com/resin-io/resin-cli/releases/download/v${RESINCLI_VERSION}/resin-cli-v${RESINCLI_VERSION}-linux-x64.zip && \
    sudo unzip tmp.zip -d /usr/local/bin && \
    sudo rm -rf tmp.zip
ENV PATH="/usr/local/bin/resin-cli:${PATH}"

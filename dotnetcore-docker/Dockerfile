FROM jenkins/jenkins:lts

USER root

RUN apt-get update && apt-get install -y \
    wget \
    curl \
    libicu-dev

RUN curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin --channel 8.0 --install-dir /usr/local/bin

USER jenkins

RUN dotnet --version
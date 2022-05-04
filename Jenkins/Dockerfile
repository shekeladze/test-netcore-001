FROM jenkins/jenkins:lts

USER root

WORKDIR /dotnet
RUN curl https://download.visualstudio.microsoft.com/download/pr/c505a449-9ecf-4352-8629-56216f521616/bd6807340faae05b61de340c8bf161e8/dotnet-sdk-6.0.201-linux-x64.tar.gz -o dotnet.tar.gz
RUN tar zxf dotnet.tar.gz -C ./
RUN rm -rf dotnet.tar.gz
ENV PATH="${PATH}:/dotnet:/var/jenkins_home/.dotnet/tools"
ENV DOTNET_ROOT="/dotnet"
RUN apt update -y
RUN apt install icu-devtools vim zip unzip -y
RUN usermod -a -G root jenkins

# install docker
RUN apt-get update && apt-get install -y lsb-release
RUN curl -fsSLo /usr/share/keyrings/docker-archive-keyring.asc \
  https://download.docker.com/linux/debian/gpg
RUN echo "deb [arch=$(dpkg --print-architecture) \
  signed-by=/usr/share/keyrings/docker-archive-keyring.asc] \
  https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" > /etc/apt/sources.list.d/docker.list
RUN apt-get update && apt-get install -y docker-ce-cli


USER jenkins

RUN jenkins-plugin-cli --plugins "blueocean:1.25.3 docker-workflow:1.28"
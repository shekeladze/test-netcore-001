FROM jenkins/jenkins:lts

USER root


WORKDIR /dotnet
#RUN wget -O dotnet.tar.gz https:download.visualstudio.microsoft.com/download/pr/c505a449-9ecf-4352-8629-56216f521616/bd6807340faae05b61de340c8bf161e8/dotnet-sdk-6.0.201-linux-x64.tar.gz
RUN curl https://download.visualstudio.microsoft.com/download/pr/c505a449-9ecf-4352-8629-56216f521616/bd6807340faae05b61de340c8bf161e8/dotnet-sdk-6.0.201-linux-x64.tar.gz -o dotnet.tar.gz
RUN tar zxf dotnet.tar.gz -C ./
RUN rm -rf dotnet.tar.gz
ENV PATH="${PATH}:/dotnet:/var/jenkins_home/.dotnet/tools"
ENV DOTNET_ROOT="/dotnet"
RUN apt update -y
RUN apt install icu-devtools vim zip unzip -y
RUN usermod -a -G root jenkins


USER jenkins
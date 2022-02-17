FROM nginx:1.21

RUN apt-get clean
RUN apt-get update

#   安装常用的包
RUN apt-get install -y \
    vim \
    curl \
    net-tools \
    iputils-ping \
    procps
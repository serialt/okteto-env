ARG VERSION=3
ARG DEBIAN_VERSION="bookworm"
FROM python:${VERSION}-${DEBIAN_VERSION}

WORKDIR /usr/src/app

# setup okteto message
COPY bashrc /root/.bashrc

RUN apt-get update && apt-get install -y zip git

# set apt and pip source 
RUN sed -i 's/\w*.debian.org/mirrors.ustc.edu.cn/g' /etc/apt/sources.list.d/debian.sources 
ENV PIP_MIRROR=mirrors.aliyun.com
RUN echo -e "[global]\nindex-url=https://${PIP_MIRROR}/pypi/simple\n[install]\ntrusted-host=${PIP_MIRROR}" >  /etc/pip.conf 


CMD ["bash"]

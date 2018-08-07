
FROM centos:7

WORKDIR /
RUN yum -y install https://centos7.iuscommunity.org/ius-release.rpm && \
    yum makecache && \
    yum install -y python36u && \
    yum -y install python36u-pip && \
    yum -y install python36u-devel && \
    /usr/bin/python3.6  -V   && \
    /usr/bin/pip3.6 -V




RUN /usr/bin/pip3.6 install azure-batch  && \
    /usr/bin/pip3.6 install azure-mgmt-scheduler && \
    /usr/bin/pip3.6 install --pre azure-mgmt-compute && \
    /usr/bin/pip3.6 install azure && \
    /usr/bin/pip3.6 install --pre azure

COPY . .
RUN ls -l
ENV PYTHONUNBUFFERED=0
CMD /usr/bin/python3.6  -u ./ARM/azure-deployment.py --name=zihao-test --action create

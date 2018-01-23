FROM centos:7

MAINTAINER Al Faller

ADD ./run_cron /root/run_cron
ADD ./cron_job /root/cron_job

RUN yum -y update \
   && yum -y install epel-release \
   && yum -y install git cronie python-pip groff less \
   && pip install awscli \
   && yum -y clean all \
   && rm -rf /var/cache/yum \
   && chmod +x /root/run_cron /root/cron_job \
   && mkdir /root/.ssh \
   && chmod 700 /root/.ssh
   
CMD /root/run_cron
   



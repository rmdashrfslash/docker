FROM centos:7

ADD ./run.sh /root/run.sh

RUN yum -y update  && yum -y install epel-release  && yum -y install mod_auth_mellon mod_ssl && yum -y clean all  && rm -rf /var/cache/yum && rm -rf /var/cache/yum  && ln -sf /proc/self/fd/1 /var/log/httpd/access_log  && ln -sf /proc/self/fd/1 /var/log/httpd/error_log  && chmod +x /root/run.sh && echo -n > /etc/httpd/conf.d/welcome.conf

RUN sed -i '/<Directory "\/var\/www\/html">/,/<\/Directory>/ s/AllowOverride None/AllowOverride All/' /etc/httpd/conf/httpd.conf


CMD /root/run.sh

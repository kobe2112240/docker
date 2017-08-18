FROM FROM centos:6.6
MAINTAINER hexin<hexincloud@gmail.com>
RUN cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
RUN rpm -ivh http://nginx.org/packages/centos/6/noarch/RPMS/nginx-release-centos-6-0.el6.ngx.noarch.rpm
RUN yum install -y nginx

RUN mv /etc/nginx/nginx.conf /etc/nginx/nginx.conf.default
RUN mkdir -p /data/www  && chown -R nginx:nginx /data/www
RUN mv /etc/nginx/conf.d/default.conf /etc/nginx/conf.d/default.conf.save
RUN ADD ./includes/ /etc/nginx/
RUN ADD ./sites/   /etc/nginx/
RUN COPY nginx.conf /etc/nginx/
EXPOSE 80 443 8000

CMD ["nginx"]


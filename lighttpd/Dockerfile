FROM tclarke/supervisor

MAINTAINER Trevor R.H. Clarke <tclarke@ball.com> "https://github.com/tclarke"

RUN yum install -y lighttpd lighttpd-fastcgi

RUN mkdir -p /etc/lighttpd/apps.conf.d

ADD 10-lighttpd.supervisord.conf /etc/supervisord/conf.d/
ADD lighttpd.conf /etc/lighttpd/lighttpd.conf

# we'll have problems running django manage.py without a LANG set
ENV LANG en_US

EXPOSE 80

CMD ["supervisord"]

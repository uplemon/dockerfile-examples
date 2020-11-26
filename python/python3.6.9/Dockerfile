FROM uplemon/centos:centos7

ENV PYTHON_VERSION 3.6.9

COPY ./Python-3.6.9.tgz /usr/local/webserver/

RUN yum -y install gcc gcc-c++ make zlib zlib-devel openssl openssl-devel sqlite sqlite-devel \
	&& cd /usr/local/webserver \
	&& tar -zxvf Python-$PYTHON_VERSION.tgz \
	&& cd Python-$PYTHON_VERSION \
	&& ./configure --prefix=/usr/local/webserver/python --enable-optimizations \
	&& make \
	&& make install \
	&& cd /usr/local/webserver \
	&& rm -rf Python-$PYTHON_VERSION \
	&& rm -rf Python-$PYTHON_VERSION.tgz \
	&& cd /usr/local/bin \
	&& ln -sf /usr/local/webserver/python/bin/python3.6 python3.6 \
	&& ln -sf /usr/local/webserver/python/bin/pip3 pip3
	
CMD ["python3.6"]

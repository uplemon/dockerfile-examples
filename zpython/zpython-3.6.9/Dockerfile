FROM uplemon/python:3.6.9

LABEL maintainer="uplemon"

COPY ./pip.conf /root/.pip/
COPY ./.pydistutils.cfg /root/

RUN pip3 install --upgrade pip \
    && pip3 install virtualenv \
    && cd /usr/local/bin \
    && ln -sf /usr/local/webserver/python/bin/virtualenv virtualenv

CMD ["python3.6"]

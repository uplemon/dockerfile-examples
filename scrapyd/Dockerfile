FROM uplemon/python:3.6.9

COPY ./scrapyd.conf /etc/scrapyd/
COPY ./supervisord.conf /etc/supervisor/
COPY ./pip.conf /root/.pip/
COPY ./.pydistutils.cfg /root/
COPY ./twisted-18.9.0.tar.gz /root/

RUN pip3 install --upgrade pip \
    && pip3 install virtualenv \
    && cd /usr/local/bin \
    && ln -sf /usr/local/webserver/python/bin/virtualenv virtualenv \
    && mkdir -p /data/server/www \
    && cd /data/server/www \
    && virtualenv -p python3.6 scrapyd \
    && cd scrapyd \
    && source ./bin/activate \
    && mv /root/twisted-18.9.0.tar.gz . \
    && tar -zxvf twisted-18.9.0.tar.gz \
    && cd twisted-twisted-18.9.0 \
    && python setup.py install \
    && cd ../ \
    && rm -rf twisted-18.9.0.tar.gz \
    && rm -rf twisted-twisted-18.9.0 \
    && pip install scrapyd \
    && pip install supervisor \
    && mkdir -p /data/logs/supervisor

EXPOSE 6800

CMD /data/server/www/scrapyd/bin/supervisord -c /etc/supervisor/supervisord.conf && tail -f /data/logs/supervisor/supervisord.log

FROM uplemon/zpython:3.6.9

LABEL maintainer="uplemon"

RUN pip3 install --upgrade pip \
    && mkdir -p /data/server/www \
    && cd /data/server/www \ 
    && virtualenv -p python3.6 gerapy \
    && cd gerapy \
    && source ./bin/activate \
    && pip install gerapy \
    && mkdir -p /data/app

VOLUME ["/data/app/gerapy"]

CMD cd /data/app \
    && /data/server/www/gerapy/bin/gerapy init gerapy \
    && cd gerapy \
    && /data/server/www/gerapy/bin/gerapy migrate \
    && /data/server/www/gerapy/bin/gerapy runserver 0.0.0.0:8000

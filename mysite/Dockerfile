FROM ubuntu:18.04

RUN set -ex \
    \
    && apt-get update \
    && apt-get install -y --no-install-recommends \
    python3.8 python3.8-dev python3-virtualenv python3-cffi python3-pip

ENV VIRTUAL_ENV /app/venv

RUN python3 -m virtualenv --python=/usr/bin/python3.8 $VIRTUAL_ENV

ENV PATH $VIRTUAL_ENV/bin:$PATH

COPY ./requirements.txt /app/

RUN pip install --upgrade pip && pip install -r /app/requirements.txt

COPY . /app/

WORKDIR /app

CMD python manage.py runworker mqtt & daphne -b 0.0.0.0 -p 8000 mysite.asgi:application

FROM python:3.6.5

RUN mkdir -p /app
WORKDIR /app

# add requirements (to leverage Docker cache)
ADD ./flask-base-api/requirements.txt /app/requirements.txt

# install requirements
RUN pip install -r requirements.txt

ADD ./flask-base-api/ /app/

ENTRYPOINT celery -A project.celery worker --loglevel=INFO -E

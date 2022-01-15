FROM ubuntu:20.04

RUN apt-get update -y && \
    apt-get install -y python3-pip python3-dev && \
    pip install --upgrade pip setuptools

# Copy this file first to leverage docker cache
COPY ./requirements.txt /app/requirements.txt

WORKDIR /app

RUN pip install -r requirements.txt

COPY . /app
EXPOSE 8080

ENTRYPOINT [ "python3" ]

CMD [ "app.py" ]

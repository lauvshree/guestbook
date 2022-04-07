FROM ubuntu:20.04

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update -qq && \
    apt-get install -y -q --no-install-recommends \
    openssl python3.7 python3-pip

RUN pip3 install --upgrade pip setuptools
RUN pip3 install requests Flask Flask-Cache

ENV TONE_ANALYZER_API_KEY=CiVfMbYIslE0zmqNO9OPhu7VgOWPkvT7AQJ5Sa1HoQRj
ENV TONE_ANALYZER_SERVICE_API=https://api.eu-gb.natural-language-understanding.watson.cloud.ibm.com/instances/85429dfa-bd7e-4fec-8460-06eae1c52eee

RUN pip3 install pyopenssl
RUN pip3 install ibm-watson==5.2.1

# application source code including static files, templates, etc
ADD src /app/src

EXPOSE 5000

ENTRYPOINT ["python3", "/app/src/app.py"]

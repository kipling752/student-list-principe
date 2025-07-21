FROM python:3.11-slim

WORKDIR /

COPY requirements.txt ./

RUN apt-get update -y && apt-get install -y \
    python3-dev \
    libsasl2-dev \
    libldap2-dev \
    libssl-dev \
    build-essential \
    gcc \
    && rm -rf /var/lib/apt/lists/*

RUN pip3 install  -r requirements.txt

VOLUME ["/data"]

COPY student_age.json /data/student_age.json

COPY student_age.py /

EXPOSE 5000

CMD [ "python3", "./student_age.py" ]

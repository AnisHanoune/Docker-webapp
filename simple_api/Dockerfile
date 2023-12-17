FROM python:2.7-buster

# Install system dependencies
RUN apt-get update -y && apt-get install -y \
    python-dev \
    python3-dev \
    libsasl2-dev \
    libldap2-dev \
    libssl-dev


COPY . .


RUN mkdir /data

COPY student_age.json /data/student_age.json

RUN pip install --no-cache-dir -r req.txt


EXPOSE 5000

VOLUME /data

CMD ["python", "student_age.py"]


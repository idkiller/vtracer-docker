FROM python:3.9-slim
RUN apt update
RUN apt install git -y
RUN mkdir /opt/app
RUN git clone https://github.com/idkiller/vtracer-rest.git /opt/app
WORKDIR /opt/app
RUN git checkout azure
RUN python3 -m pip install -U pip
RUN python3 -m pip install setuptools-rust
RUN python3 -m pip install -r requirements.txt
RUN python3 ./mongodb_init.py
ENTRYPOINT ["run.sh"]
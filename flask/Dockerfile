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
RUN chmod +x /opt/app/run.sh
RUN echo $SSL_CERTIFICATE $SSL_PRIVATEKEY
COPY $SSL_CERTIFICATE /opt/app
COPY $SSL_PRIVATEKEY  /opt/app
ENTRYPOINT ["/bin/sh", "-c", "python3 ./mongodb_init.py && ./run.sh"]
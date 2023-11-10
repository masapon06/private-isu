FROM golang:1.21

# node_exporter
RUN wget https://github.com/prometheus/node_exporter/releases/download/v1.6.1/node_exporter-1.6.1.linux-amd64.tar.gz && \
    tar xvfz node_exporter-1.6.1.linux-amd64.tar.gz && \
    mv node_exporter-1.6.1.linux-amd64 /usr/local/bin/ && \
    rm node_exporter-1.6.1.linux-amd64.tar.gz
CMD /usr/local/bin/node_exporter-1.6.1.linux-amd64/node_exporter & ./app

RUN mkdir -p /home/webapp
WORKDIR /home/webapp
COPY . /home/webapp
RUN go build -o app
CMD ./app

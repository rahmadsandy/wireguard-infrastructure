FROM ubuntu
RUN apt update && \
    apt install curl vim net-tools iputils-ping -y
RUN mkdir /data
WORKDIR /app
COPY . /app
WORKDIR /app
EXPOSE 8888
CMD [ "./wg-gen-web" ]

FROM linux/amd64:stable

COPY . . 

WORKDIR /app

ARG applist1=nmap

RUN apt update && apt install iputils-ping -y

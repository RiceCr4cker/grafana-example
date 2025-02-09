FROM ubuntu:22.04
RUN apt update && apt upgrade -y
RUN apt install -y software-properties-common
RUN add-apt-repository ppa:oisf/suricata-stable
RUN apt install -y suricata jq
RUN apt install -y cron  multitail
COPY update-rules /etc/cron.d/update-rules
RUN chmod 0744 /etc/cron.d/update-rules
RUN crontab /etc/cron.d/update-rules
RUN touch /var/log/cron.log


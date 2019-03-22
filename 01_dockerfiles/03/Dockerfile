FROM ubuntu:18.04

RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install -y wget openssh-server ca-certificates vim postfix
RUN wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh && chmod +x script.deb.sh && ./script.deb.sh && apt-get install -y gitlab-ce

RUN apt-get install -y tzdata && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /script.deb.sh

EXPOSE 443 80 22

ENTRYPOINT service ssh start && (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl start && tail -f /dev/null

# Build
# docker build -t ex03 .
# Run
# docker run --rm -it -p 80:80 -p 443:443 -p 2222:22 -d ex03

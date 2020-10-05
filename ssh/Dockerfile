FROM ubuntu:20.04
RUN echo "deb http://mirrors.163.com/ubuntu/ focal main restricted universe multiverse" > /etc/apt/sources.list \ 
&& echo "deb http://mirrors.163.com/ubuntu/ focal-security main restricted universe multiverse" >> /etc/apt/sources.list \
&& echo "deb http://mirrors.163.com/ubuntu/ focal-updates main restricted universe multiverse" >> /etc/apt/sources.list \
&& echo "deb http://mirrors.163.com/ubuntu/ focal-proposed main restricted universe multiverse" >> /etc/apt/sources.list \
&& echo "deb http://mirrors.163.com/ubuntu/ focal-backports main restricted universe multiverse" >> /etc/apt/sources.list \
&& echo "deb-src http://mirrors.163.com/ubuntu/ focal main restricted universe multiverse" >> /etc/apt/sources.list \
&& echo "deb-src http://mirrors.163.com/ubuntu/ focal-security main restricted universe multiverse" >> /etc/apt/sources.list \
&& echo "deb-src http://mirrors.163.com/ubuntu/ focal-updates main restricted universe multiverse" >> /etc/apt/sources.list \
&& echo "deb-src http://mirrors.163.com/ubuntu/ focal-proposed main restricted universe multiverse" >> /etc/apt/sources.list \
&& echo "deb-src http://mirrors.163.com/ubuntu/ focal-backports main restricted universe multiverse" >>  /etc/apt/sources.list

RUN apt-get update && apt-get install -y openssh-server
RUN mkdir /var/run/sshd
RUN echo 'root:THEPASSWORDYOUCREATED' | chpasswd
RUN sed -i 's/#*PermitRootLogin prohibit-password/PermitRootLogin yes/g' /etc/ssh/sshd_config

# SSH login fix. Otherwise user is kicked off after login
RUN sed -i 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' /etc/pam.d/sshd

ENV NOTVISIBLE="in users profile"
RUN echo "export VISIBLE=now" >> /etc/profile

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]

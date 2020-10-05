Using Docker for Effective Linux

> https://docs.docker.com/engine/examples/running_ssh_service/

> vim .bash_profile
> alias sshcontainer="docker run -d -rm -p 50000:22 rastasheep/ubuntu-sshd && /usr/sbin/sshd -D"
> alias sshtestcontainer="docker run -it -rm  rastasheep/ubuntu-sshd /bin/bash"

function testcontainer() {
    docker run -it -d 22 $1 /bin/bash
}
alias containertest=testcontainer

containertest imagename

> https://cyberduck.io/


>`https://docs.docker.com/config/containers/multi-service_container/


> https://www.digitalocean.com/community/questions/how-to-start-docker-containers-automatically-after-a-reboot

disbale root login


adduser user1

adduser user1 sudo
login user1



auto ssh 


> ~/.ssh/config

Host Firstcontainer
Hostname  172.17.42.1
    user user1
    port 5000
    strictHostKeyChcking no


> https://github.com/meanjs/mean



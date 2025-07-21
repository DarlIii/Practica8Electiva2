FROM ubuntu:22.04 
 
ENV DEBIAN_FRONTEND=noninteractive 
 
 
RUN useradd -m -s /bin/bash ansible && echo "ansible:ansible" | chpasswd 
 
RUN usermod -aG sudo ansible && echo "ansible ALL=(ALL) NOPASSWD:ALL" >
 
RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config 
RUN sed -i 's@#PasswordAuthentication yes@PasswordAuthentication yes@' /etc/ssh/sshd_config 
 
EXPOSE 22 
 
CMD ["/usr/sbin/sshd", "-D"] 

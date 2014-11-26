FROM ubuntu:14.10
MAINTAINER tian <jia.tian@me.com>
RUN apt-get -qq update
RUN apt-get -qqy upgrade

RUN apt-get install -y openssh-server
RUN mkdir /var/run/sshd
RUN mkdir ~/.ssh/
RUN touch ~/.ssh/authorized_keys
RUN echo 'ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCuFV+3K2sEoSpITs3Opco3v6pRa/i55PCJRMaeEm4dFta/Y5KTRW+pc7phYIS7fl+JN1wZVOJxiNy/50yGSJ/i1plS5noohxJ4OaI7H2aanvOLLRs+6zcjyEQR4sTFGr0J5FJP5RaaxuDduxT7f4TkoENJ1c1Phl33hqVqglX+/jAaJX64GRpjB9axSEdxjYhwcf1iZPdzlGOEqtv8Ib9uq8MNvbhDU9eT3r+oykQR0fdL0mZaVNvf+3mS4ajNmrDauL25/mDvmHkFQY5uodAWojY2xVbTGcd6rluUZU49WFbW77fgRsR9eSAWbgpMIlfVJI4UYThF5UW5MA+n4z4t tian@tian-mac' > ~/.ssh/authorized_keys
RUN chmod -R 600 ~/.ssh
RUN wget -q -O - http://pkg.jenkins-ci.org/debian/jenkins-ci.org.key | apt-key add -
RUN echo "deb http://pkg.jenkins-ci.org/debian binary/" >> /etc/apt/sources.list
RUN apt-get -qq update
RUN apt-get install -y jenkins

EXPOSE 8080
EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]

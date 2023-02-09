FROM ubuntu:18.04

RUN sed 's/main$/main universe/' -i /etc/apt/sources.list && \
    apt-get update && apt-get install -y software-properties-common
RUN add-apt-repository ppa:webupd8team/java -y && \
    apt-get update && \
    echo openjdk-8-jdk shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections && \
    apt-get install -y openjdk-8-jdk libxext-dev libxrender-dev libxtst-dev wget && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf /tmp/*

# Install libgtk as a separate step so that we can share the layer above with
# the netbeans image
RUN apt-get update && apt-get install -y libgtk2.0-0 libcanberra-gtk-module libgtk-3-dev

RUN wget 'https://www.eclipse.org/downloads/download.php?file=/technology/epp/downloads/release/2022-03/R/eclipse-jee-2022-03-R-linux-gtk-x86_64.tar.gz&r=1' -O /tmp/eclipse.tar.gz&& \
    echo 'Installing eclipse' && \
    tar -xf /tmp/eclipse.tar.gz -C /bin && \
    rm /tmp/eclipse.tar.gz

ENV PATH="${PATH}:/bin/eclipse"
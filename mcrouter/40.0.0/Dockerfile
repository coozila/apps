# ----------------------------------------------------------------------------------#
#                                                                                   #
#   Copyright   (C) 2009 - 2024 Coozila! MIT Locense                                #
#   Coozila! Team    lab@coozila.com                                                #
#                                                                                   #
# ----------------------------------------------------------------------------------#

FROM ubuntu:bionic

ENV DEBIAN_FRONTEND noninteractive

# Adaugă surse alternative pentru APT
RUN echo "deb http://archive.ubuntu.com/ubuntu/ bionic main universe restricted multiverse" > /etc/apt/sources.list && \
    echo "deb http://security.ubuntu.com/ubuntu/ bionic-security main universe restricted multiverse" >> /etc/apt/sources.list && \
    echo "deb http://mirrors.kernel.org/ubuntu/ bionic main universe restricted multiverse" >> /etc/apt/sources.list && \
    echo "deb http://archive.ubuntu.com/ubuntu/ bionic-updates main universe restricted multiverse" >> /etc/apt/sources.list && \
    echo "deb http://archive.ubuntu.com/ubuntu/ bionic-backports main universe restricted multiverse" >> /etc/apt/sources.list

# Actualizează lista de pachete și instalează utilitare necesare
RUN apt-get update && apt-get install -y \
    wget \
    gnupg && \
    rm -rf /var/lib/apt/lists/*

# Adaugă cheia repository-ului
RUN wget -O - https://facebook.github.io/mcrouter/debrepo/bionic/PUBLIC.KEY | apt-key add - && \
    echo "deb https://facebook.github.io/mcrouter/debrepo/bionic bionic contrib" >> /etc/apt/sources.list

# Actualizează lista de pachete și instalează mcrouter
RUN apt-get update && apt-get install -y mcrouter && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Comandă implicită (opțional)
CMD ["mcrouter"]

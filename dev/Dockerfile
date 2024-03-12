# Base the image on the latest LTS version of Node.js
FROM node:lts

# Install Git
RUN apt-get update && \
    apt-get install -y git tzdata zsh ca-certificates vim curl make wget && \
    update-ca-certificates && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Set timezone to Asia/Tokyo
RUN cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

# Configure Git and Zsh
RUN sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"

# Set environment variables
ENV SHELL=/bin/zsh
ENV PNPM_HOME=/usr/local/bin

# Set the working directory inside the container
WORKDIR /usr/src/app


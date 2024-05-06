FROM ubuntu:latest

# Install dependencies
RUN apt update
RUN apt install -y xdg-utils

# Copy radiology images
RUN mkdir /images
COPY images /images 
# Copy deb package
COPY weasis_4.3.0-1_amd64.deb /tmp
# Make directory for xdg to avoid exit code 3 error
RUN mkdir /usr/share/desktop-directories
# Install weasis
RUN apt install -y /tmp/weasis_4.3.0-1_amd64.deb

# Needed to run GUI in container
RUN groupadd -g 1000 simspace
RUN useradd -d /home/simspace -s /bin/bash -m simspace -u 1000 -g 1000
USER simspace
ENV HOME /home/simspace

# Start the application
CMD /opt/weasis/bin/Weasis


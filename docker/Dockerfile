FROM ubuntu:bionic-20210118
ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update
RUN apt-get install -y curl git tree tmux

# Rose related
RUN apt-get install gpg software-properties-common -y
RUN add-apt-repository ppa:rosecompiler/rose-development -y
RUN apt-get install rose -y
RUN apt-get install rose-tools -y

WORKDIR /home/appuser

RUN groupadd -g 1000 appuser && \
    useradd -r -u 1000 -g appuser appuser
RUN chown appuser.appuser /home/appuser

USER appuser

# COPY executable_name .
# ENTRYPOINT ["/app/executable_name"]

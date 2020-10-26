FROM python:3.8
ENV PYTHONUNBUFFERED 1
RUN apt-get update && \
    apt-get install -y git build-essential cmake clang libssl-dev


WORKDIR /tmp/work
COPY requirements.txt ${PWD}
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

ENV TZ=Asia/Tokyo
ENV USER user1

RUN useradd -m ${USER} --uid 1000
RUN gpasswd -a ${USER} sudo
RUN echo "${USER}:password" | chpasswd

USER ${USER}
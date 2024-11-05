FROM debian:12.7-slim

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get remove w3m -y
RUN apt-get install -y \
	curl \
	git \
	gh \
	sudo \
	wget \
	nano \
	neovim \
	build-essential \
	gdb \
	python3 \
	python-is-python3 \
	black \
	cpplint \
	&& rm -rf /var/lib/apt/lists/*

ARG USER=coder
RUN useradd --groups sudo --no-create-home --shell /bin/bash ${USER} \
	&& echo "${USER} ALL=(ALL) NOPASSWD:ALL" >/etc/sudoers.d/${USER} \
	&& chmod 0440 /etc/sudoers.d/${USER}
USER ${USER}
WORKDIR /home/${USER}
RUN chown -R ${USER} /home/${USER}

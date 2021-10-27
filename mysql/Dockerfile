FROM mysql:5.7.36
LABEL maintainer="comdan66@gmail.com"

# apt 與 app
RUN apt-get -qq update
RUN apt-get -qq upgrade

RUN apt-get -qqy install nano
RUN apt-get -qqy install zsh
RUN apt-get -qqy install git-core

# zsh
RUN git clone https://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh \
    && cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc \
    && chsh -s /bin/zsh

RUN rm -rf /var/lib/apt/lists/*

EXPOSE 3306

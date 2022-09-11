FROM node:16

ARG UNAME=vscode
ARG GNAME=vscode
ARG UID=1000
ARG GID=1000

RUN groupadd --force -g  $GID $GNAME \
    && useradd -o -m -s /bin/bash -u $UID -g $GID $UNAME \
    && apt-get update -y && apt-get install -y sudo \
    && echo $UNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$UNAME \
    && chmod 0440 /etc/sudoers.d/$UNAME

RUN SNIPPET="export PROMPT_COMMAND='history -a' && export HISTFILE=/commandhistory/.bash_history" \
    && mkdir /commandhistory \
    && touch /commandhistory/.bash_history \
    && chown -R $UNAME /commandhistory \
    && echo $SNIPPET >> "/home/$UNAME/.bashrc"
USER $UNAME


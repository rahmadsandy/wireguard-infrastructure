FROM cmulk/wireguard-docker:buster
RUN apt update -y
RUN apt install python3 python3-pip cron -y
RUN pip3 install speedtest-cli
RUN touch /var/log/cron.log
RUN (crontab -l ; echo "*/70 * * * * /usr/local/bin/speedtest-cli >> /var/log/cron.log") | crontab
RUN service cron start
RUN apt install git dnsutils telnet zsh -y
RUN sh -c "$(wget -O- https://github.com/deluan/zsh-in-docker/releases/download/v1.1.2/zsh-in-docker.sh)" -- \
    -t https://github.com/denysdovhan/spaceship-prompt \
    -a 'SPACESHIP_PROMPT_ADD_NEWLINE="false"' \
    -a 'SPACESHIP_PROMPT_SEPARATE_LINE="false"' \
    -p git \
    -p https://github.com/zsh-users/zsh-autosuggestions \
    -p https://github.com/zsh-users/zsh-completions


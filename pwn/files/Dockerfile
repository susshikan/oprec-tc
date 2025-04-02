FROM ubuntu:18.04

RUN apt-get update && apt-get install -y \
    socat \
    && rm -rf /var/lib/apt/lists/*

RUN useradd -m compfest17

WORKDIR /home/compfest17

COPY . .

RUN chmod +x /home/compfest17/gema
RUN chown compfest17:compfest17 /home/compfest17/gema

USER compfest17

CMD ["socat", "TCP-LISTEN:4321,fork,reuseaddr", "EXEC:/home/compfest17/gema"]
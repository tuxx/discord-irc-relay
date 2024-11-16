# discord-irc-relay (1.0.3)
a better discord-irc relay that represents each discord user as a separate irc client connection on the server

### features
- each discord user joins the channel as a separate client (only if they chat)
- map irc channels to discord channels
- discord display name changes are reflected on irc
- ability to exclude certain irc nicknames from reaching discord (youtube/twitter/title bots)
- nicknames and messages are stripped of colours and control codes

### configuration

edit `config.json.example` and rename it to `config.json`

the `channels` section maps the irc channels to the discord text channels, e.g.,

```
    "channels": {
        "#sports": "237784782872424",
        "#music": "849429829924823"
    },
```

you can exclude specific nicknames from the relay by adding the nicknames to the `excludeNicks` array, in case they are youtube/twitter/title bots (discord already previews these)

### run

run `npm install`

run `node .`

### run with docker

```
docker build -t discord-irc-relay
docker run -d discord-irc-relay -v ./config.json:/home/node/app/config.json
```

### run with docker-compose
``` 
docker-compose build
docker-compose up -d
```

```
docker build -t discord-irc-relay
docker run -d discord-irc-relay -v ./config.json:/home/node/app/config.json
```

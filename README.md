# heroku-buildpack-stunnel
An stunnel buildpack for Heroku.

## testing

```
docker build -t lendup-stunnel .
touch bash_history
docker run --name=stunnel --rm -it -v ${PWD}/bash_history:/root/.bash_history lendup-stunnel
container$ app/bin/start-stunnel /bin/bash -c 'echo starting-app.......................... ; sleep 100000000'
```

# heroku-buildpack-stunnel
An stunnel buildpack for Heroku.

## testing

use either of these lines to simulate running a crashing stunnel:

```
# stunnel crashes after 2 seconds
aux-start stunnel SIGINT /bin/bash -c 'echo fake-stunnel-start ; sleep 2 ; echo fake-stunnel-crash ; exit 1'
# stunnel "runs" fine
aux-start stunnel SIGINT /bin/bash -c 'echo fake-stunnel-start ; sleep 1000 ; echo fake-stunnel-crash'
```

```
docker build -t lendup-stunnel .
touch bash_history
docker run --name=stunnel --rm -it -v ${PWD}/bash_history:/root/.bash_history lendup-stunnel
container$ app/bin/start-stunnel /bin/bash -c 'echo starting-app.......................... ; sleep 100000000'
```

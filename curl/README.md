# lwp-request
Alpine-based image with curl

## Usage

In your .bashrc:
```console
alias curl='docker run -it --rm --net host --log-driver none \
	-v ~/.ssh/known_hosts:/home/curl/.ssh/known_hosts:ro \
	-v ~/Downloads:/home/curl/Downloads:ro \
	drphlux/curl "$@"'
```
Then:
```console
$ curl -I https://www.google.no/
```

## License

No Copyright © 2017 DrPhlux

All contents licensed under the sun

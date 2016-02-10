# lwp-request
Alpine-based image with just lwp-request

## Usage

In your .bashrc:
```console
alias GET='docker run --rm -it --net host --log-driver none drphlux/lwp-request "$@"'
```
Then:
```console
$ GET -m HEAD www.google.com
```
With lwp-request "-m GET" is the default.

## License

No Copyright © 2016 DrPhlux

All contents licensed under the sun

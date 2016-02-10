# lwp-request
Alpine-based image with just lwp-request

## Usage

```In your .bashrc:
alias GET='docker run --rm -it --net host --log-driver none drphlux/lwp-request "$@"'
```Then:
$ GET -m HEAD www.google.com

## License

No Copyright © 2016 DrPhlux

All contents licensed under the sun

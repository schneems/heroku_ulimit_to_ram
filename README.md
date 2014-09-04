## Heroku Ulimit to Ram

### What?

Running on Heroku? Want to know how much ram you've got? Well too bad, you can't. But...you can guess. The `ulimit -u` return value is different for different size dynos.

### Seems bad

Ulimit is not a stable interface and may change. Yes, using this is pretty horrible, so don't.

### But...

If you do have to use this here's how. Run the script:

```
$ bin/heroku_ulimit_to_ram
```

If you're on heroku you'll get the memory limit in megabytes returned to the standard out

On a 1x dyno

```
$ bin/heroku_ulimit_to_ram
# => 512
```

On a 2x dyno

```
$ bin/heroku_ulimit_to_ram
# => 1024
```

On a PX dyno

```
$ bin/heroku_ulimit_to_ram
# => 8192
```

If you try to run this on any other system the process will exit with a status of 1

```
$ bin/heroku_ulimit_to_ram
# => nope
```

## License

MIT or something. Seriously though, please don't use this.
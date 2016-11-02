# Networking

## Tsung stress testing
if all you want to do is requesting a single URL in a loop, use **ab**


## ab stress testing

ab -n 100 -c 10 -C "COOKIE=VALUE" http://example.com/

##wrk - a HTTP benchmarking tool

  [https://github.com/wg/wrk](https://github.com/wg/wrk)

  wrk -H 'Cookie: uid=12345678901234567890;' -t12 -c400 -d30s http://127.0.0.1:8080/index.html

  This runs a benchmark for 30 seconds, using 12 threads, and keeping
  400 HTTP connections open.


## Use iperft to check connection between testing servers

 iperf -c SERVER_ADDRESS

## Simulate poor connection

* Create a pipe which adds 300ms delay
`dnctl pipe 1 config bw 10Kbit/s delay 300`

* Apply the pipe one to redis connection
```
echo "dummynet out proto tcp from any to any port 6379 pipe 1" |pfctl -f -
```

* Enable `pfctl`
```
pfctl -e
```
When you're done: `pfctl -F /etc/pf.conf and dnctl -q flush`


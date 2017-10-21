# Networking

## Stress testing

### ab

if all you want to do is requesting a single URL in a loop use **ab**.

```
  ab -n 100 -c 10 -C "COOKIE=VALUE" http://example.com/
```

### [wg/wrk](https://github.com/wg/wrk)

You can consider **wrk** if you want to build more complex HTTP tests like
a test with auth where you would need to describe test logic. Some Lua
script example can be found in https://github.com/wg/wrk/tree/master/scripts

```
  wrk -H 'Cookie: uid=12345678901234567890;' -t12 -c400 -d30s http://127.0.0.1:8080/index.html
```
### tsung stress testing

## Use iperft to check connection between testing servers

```
  iperf -c SERVER_ADDRESS
```

## Simulate poor connection

* Create a pipe with a 300ms delay
`dnctl pipe 1 config bw 10Kbit/s delay 300`

* Apply the pipe to redis connection running on `6379` port
```
echo "dummynet out proto tcp from any to any port 6379 pipe 1" |pfctl -f -
```

* Enable `pfctl`
```
pfctl -e
```
When you're done run: `pfctl -F /etc/pf.conf and dnctl -q flush`


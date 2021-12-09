# pymodbus-gm

## usage

### TCP client & server without GM

See `./examples/tcp_client.py` and `./examples/tcp_server.py`. The 2 examples are copied from `pymodbus`.

Run `python tcp_server.py` first to start the slaves. Then start a client by `python tcp_client.py` to send requests and get responses from the server. You may get server logger output like:

```sh
2021-12-09 13:39:47,410 MainThread      DEBUG    sync           :348      Started thread to serve client at ('127.0.0.1', 56767)
2021-12-09 13:39:47,410 Thread-1        DEBUG    sync           :46       Client Connected [127.0.0.1:56767]
2021-12-09 13:39:47,410 Thread-1        DEBUG    sync           :199      Handling data: 0x0 0x1 0x0 0x0 0x0 0x6 0x1 0x1 0x0 0x1 0x0 0x1
2021-12-09 13:39:47,410 Thread-1        DEBUG    socket_framer  :147      Processing: 0x0 0x1 0x0 0x0 0x0 0x6 0x1 0x1 0x0 0x1 0x0 0x1
2021-12-09 13:39:47,410 Thread-1        DEBUG    factory        :137      Factory Request[ReadCoilsRequest: 1]
2021-12-09 13:39:47,410 Thread-1        DEBUG    context        :64       validate: fc-[1] address-2: count-1
2021-12-09 13:39:47,410 Thread-1        DEBUG    context        :78       getValues fc-[1] address-2: count-1
2021-12-09 13:39:47,410 Thread-1        DEBUG    sync           :229      send: [ReadCoilsResponse(1)]- b'00010000000401010101'
2021-12-09 13:39:47,412 Thread-1        DEBUG    sync           :199      Handling data: 0x0 0x2 0x0 0x0 0x0 0x6 0x1 0x5 0x0 0x0 0xff 0x0
2021-12-09 13:39:47,412 Thread-1        DEBUG    socket_framer  :147      Processing: 0x0 0x2 0x0 0x0 0x0 0x6 0x1 0x5 0x0 0x0 0xff 0x0
2021-12-09 13:39:47,412 Thread-1        DEBUG    factory        :137      Factory Request[WriteSingleCoilRequest: 5]
2021-12-09 13:39:47,412 Thread-1        DEBUG    context        :64       validate: fc-[5] address-1: count-1
2021-12-09 13:39:47,412 Thread-1        DEBUG    context        :90       setValues[5] 1:1
2021-12-09 13:39:47,412 Thread-1        DEBUG    context        :78       getValues fc-[5] address-1: count-1
2021-12-09 13:39:47,412 Thread-1        DEBUG    sync           :229      send: [WriteCoilResponse(0) => 1]- b'00020000000601050000ff00'
```
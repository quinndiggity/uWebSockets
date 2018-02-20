<div align="center"><img src="misc/images/logo.png"/></div>

`µWS` ("[micro](https://en.wikipedia.org/wiki/Micro-)WS") is a WebSocket and HTTP server and client implementation. Focus lies on efficiency and per-connection memory footprint, while still keeping security an standards compliance a top priority.

## Simple & modern
The interface has been designed for simplicity and only requires you to write a few lines of code to get a working server:
```c++
#include <uWS/uWS.h>

int main() {
    uWS::Hub h;

    h.onMessage([](uWS::WebSocket<uWS::SERVER> *ws, char *message, size_t length, uWS::OpCode opCode) {
        ws->send(message, length, opCode);
    });

    h.onHttpRequest([](uWS::HttpResponse *res, uWS::HttpRequest req, char *data, size_t length, size_t remainingBytes) {
        res->end(const char *, size_t);
    });

    if (h.listen(3000)) {
        h.run();
    }
}
```
Get the sources of the uws.chat server [here](https://github.com/uWebSockets/website/blob/master/main.cpp). Learn from the tests [here](tests/main.cpp). Also do check the Wiki pages.

## Not your average server
µWS was designed to perform well across the board, not just in one specific dimension. With excellent memory usage paired with high throughput it outscales Socket.IO by 180x (Socket.IO 2 by 120x).

<div align="center"><img src="misc/images/overview.png"/></div>

*Benchmarks are run with default settings in all libraries, except for `ws` which is run with the native performance addons. Read more about the benchmarks [here](benchmarks).*

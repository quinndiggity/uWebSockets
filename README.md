<div align="center"><img src="misc/images/logo.png"/></div>

* Autobahn tests [all pass](http://htmlpreview.github.io/?https://github.com/uWebSockets/uWebSockets/blob/master/misc/autobahn/index.html) (including permessage-deflate & SSL tests).
* One million WebSockets require ~111mb of user space memory (104 bytes per WebSocket).
* Single-threaded throughput of up to 5 million HTTP req/sec or 20 million WebSocket echoes/sec.
* Linux, macOS & Windows support.

Read more

### Build optimized WebSocket & HTTP servers & clients in no time.
```c++
#include <uWS/uWS.h>

int main() {
    uWS::Hub h;
    std::string response = "Hello!";

    h.onMessage([](uWS::WebSocket<uWS::SERVER> *ws, char *message, size_t length, uWS::OpCode opCode) {
        ws->send(message, length, opCode);
    });

    h.onHttpRequest([&](uWS::HttpResponse *res, uWS::HttpRequest req, char *data, size_t length, size_t remainingBytes) {
        res->end(response.data(), response.length());
    });

    if (h.listen(3000)) {
        h.run();
    }
}
```

### Excel across the board.
<div align="center"><img src="misc/images/overview.png"/></div>

### Freely available.
Licensed Zlib

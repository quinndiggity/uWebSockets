<div align="center"><img src="misc/images/logo.png"/><br><i>Tiny WebSockets</i></div><br><br>

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
Non-profit open source. Permissive Zlib license.

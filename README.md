<div align="center"><img src="misc/images/logo.png"/></div>

## Simple.
```c++
#include <uWS/uWS.h>

int main() {
    uWS::Hub h;

    h.onMessage([](uWS::WebSocket<uWS::SERVER> *ws, char *message,
                   size_t length, uWS::OpCode opCode) {
        ws->send(message, length, opCode);
    });

    h.onHttpRequest([](uWS::HttpResponse *res, uWS::HttpRequest req,
                    char *data, size_t length, size_t remainingBytes) {
        res->end(const char *, size_t);
    });

    if (h.listen(3000)) {
        h.run();
    }
}
```

## Fast.
<div align="center"><img src="misc/images/overview.png"/></div>

## Open.

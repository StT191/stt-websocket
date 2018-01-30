

connect(url, callback[, settings])

* url <string>
    e.g. "ws://my-websocket.com/chat" | "wss://secure-websocket.com/login"

* callback <function> (client, error)
    will be called on connection or error
    * client <ws.WebSocket> ... will be null in case of error
    * error <Error> ... only in case of error, error.code = "ECONNECT", client will be null

* settings <Object>
    .maxMessage <number> ... disconnect on receiving a message bigger than .maxMessage (in bytes),
        default is 134217728 (128 MiB)
    .timeout <number> ... close pending connect or enforce pending close after timeout (in ms),
        default is 5000 (5 sec)
    .protocol <Array> ... a list of sub-protocols for handshake
    .headers <Object> ... a list of optional headers to be sent to the server
    .auth <string> ... Basic authentication i.e. "user:password" to compute an Authorization header
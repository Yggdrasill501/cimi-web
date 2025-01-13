# Cimi Web

A C/C++ micro framework for building web applications.

The idea is to create a minimalistic framework in c++ and CMake to make it as easy as possible.
The framework must handle Servers and Web Sockets.
And be as easy to use and possible with simple download to be used

## How to run in C++

To run server just execute [shell script](https://github.com/Yggdrasill501/cimi-web/blob/main/server.sh)

```
server.sh
```

If you're having a struggle running server.sh, remember to give it the correct permission.

```
chmod +x server.sh
```

### Examples

- Simple Server implementation

```c++
//// For Server listening
int main() {
    try {
        Server server;
        server.runServer();
    } catch (const std::runtime_error& e) {
        std::cerr << "Failed to start the server: " << e.what() << std::endl;
        return 1;
    }

    return 0;
}
```

- Simple Client connection

```c++
//// For Client connection
int main() {
    Client client;

    if (!client.connectToServer(8080, "127.0.0.1")) {
        std::cerr << "Connection to server failed." << std::endl;
        return 1;
    }

    std::cout << "Connected to the server successfully." << std::endl;

    client.sendMessage("Hello, server! This is the client.");


    return 0;
}
```

- For more Examples check [./examples/](https://github.com/Yggdrasill501/cimi-web/tree/main/examples)

## Motivation

You may ask where is the motivation coming from?
It's coming to understand and to handle the best way how to handle back-end and api development,
and since C/C++ is probably the most abstract way to do it your self.

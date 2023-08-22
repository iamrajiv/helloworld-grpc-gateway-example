<div align="center">
<img src="assets/helloworld-grpc-gateway-example.svg" height="auto" width="400" />
<br />
<h1>Hello World gRPC-Gateway Example</h1>
<p>

</p>
<a href="https://github.com/iamrajiv/helloworld-grpc-gateway-example/network/members"><img src="https://img.shields.io/github/forks/iamrajiv/helloworld-grpc-gateway-example?color=0969da&style=for-the-badge" height="auto" width="auto" /></a>
<a href="https://github.com/iamrajiv/helloworld-grpc-gateway-example/stargazers"><img src="https://img.shields.io/github/stars/iamrajiv/helloworld-grpc-gateway-example?color=0969da&style=for-the-badge" height="auto" width="auto" /></a>
<a href="https://github.com/iamrajiv/helloworld-grpc-gateway-example/blob/main/LICENSE"><img src="https://img.shields.io/github/license/iamrajiv/helloworld-grpc-gateway-example?color=0969da&style=for-the-badge" height="auto" width="auto" /></a>
</div>

## About

This repository contains an example of how to use the [gRPC-Gateway](https://github.com/grpc-ecosystem/grpc-gateway).

## Usage

#### Generating Protobuf and gRPC-Gateway Code

To generate the protobuf and gRPC-Gateway code, you can use the buf tool. The protobuf files are stored in the proto directory, and the generated code will be placed in the internal directory.

To generate the code, run the following command:

```shell
make generate
```

This will generate the necessary Go code for the protobuf files and the gRPC-Gateway files.

#### gRPC Requests and Responses

Once you've started both the gRPC and gRPC-Gateway servers using `go run main.go`, you can send gRPC requests and receive responses using a gRPC client.

Here's an example of how to send a gRPC request and receive a response using the `grpcurl` command-line tool:

1. Install `grpcurl` by following the instructions in the [official documentation](https://github.com/fullstorydev/grpcurl#installation).
2. Open a new terminal window or tab and run the following command to send a gRPC request to the `SayHello` RPC:

```shell
grpcurl -plaintext -d '{"name": "Rajiv"}' localhost:8080 helloworld.v1.GreeterService/SayHello
```

This sends a gRPC request to the `SayHello` RPC with the name "Rajiv" as a request parameter.

3. You should receive a response that looks like this:

```shell
{
  "message": "Hello, Rajiv!"
}
```

This is the response message returned by the `SayHello` RPC.

#### REST Requests and Responses

Once you've started both the gRPC and gRPC-Gateway servers using `go run main.go`, you can send REST requests and receive responses using a tool like `curl`.

Here's an example of how to send a REST request and receive a response using `curl`:

1. Open a new terminal window or tab and run the following command to send a REST request to the `/v1/helloworld` endpoint:

```shell
curl -X POST http://localhost:8081/v1/helloworld -H "Content-Type: application/json" -d '{"name": "Rajiv"}'
```

This sends a `POST` request to the `/v1/helloworld` endpoint with a JSON payload containing the name "Rajiv".

2. You should receive a response that looks like this:

```shell
{
  "message": "Hello, Rajiv!"
}
```

## License

[MIT](https://github.com/iamrajiv/helloworld-grpc-gateway-example/blob/main/LICENSE)

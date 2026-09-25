# Gzip HTTP Comparison

## Capture Source

The capture under investigation is `http_gzip.cap`, an official Wireshark sample capture.

Source: [Wireshark Sample Captures](https://wiki.wireshark.org/SampleCaptures)

## Request Evidence

The `http.request` display filter isolated the HTTP request.

- Request method: `GET`
- Request target: `/test/ethereal.html`
- HTTP version: `HTTP/1.1`
- Host: `cerberus`

## Response Evidence

TCP stream reconstruction shows the server response.

- Response status: `HTTP/1.1 200 OK`
- Server: `Apache/2.0.50 (Fedora)`
- `Vary: Accept-Encoding`
- `Content-Encoding: gzip`
- `Content-Length: 92`
- `Connection: close`
- `Content-Type: text/html; charset=UTF-8`

The exact observed content-encoding value is `gzip`.

## Differences from http.cap

- Request details differ: `http.cap` records `GET / HTTP/1.0` for host `cl-1985.ham-01.de.sixxs.net`, while `http_gzip.cap` records `GET /test/ethereal.html HTTP/1.1` for host `cerberus`.
- The response representation differs: `http_gzip.cap` explicitly records `Content-Encoding: gzip`, while the `http.cap` evidence does not record a `Content-Encoding` header.
- The observed response `Content-Length` differs: `http.cap` records `2121` bytes, while `http_gzip.cap` records `92` bytes.

## Limitation

These two training captures document differences between two specific HTTP exchanges. They cannot establish how content encoding behaves for all HTTP clients, servers, resources, or network conditions.

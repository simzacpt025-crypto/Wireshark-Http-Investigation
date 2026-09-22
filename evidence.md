# Evidence Log

## Source Metadata
- Capture filename: `http.cap`
- Official source page: https://wiki.wireshark.org/SampleCaptures

## Initial Observation
- Visible protocols: protocols you observed
- Protocol details inspected: protocol layer you expanded
- Packet-list observation: what the raw packet rows show

## Baseline Limitation
The unfiltered packet list shows individual traffic rows across protocol layers. By itself, this view does not explain the complete HTTP exchange.

## Packet Evidence

| Observed Field | Observed Value | Why It Matters |
| --- | --- | --- |
| Frame time | 	325.040411 | Places the request in the capture timeline. |
| Source address | 2001:6f8:102d:0:2d0:9fff:fee3:e8de | Identifies the sender shown in the packet. |
| Destination address | 2001:6f8:900:7c0::2 | Identifies the receiver shown in the packet. |
| Source port | 59201 | Identifies the sender-side TCP endpoint. |
| Destination port | 80 | Identifies the receiver-side TCP endpoint. |
| Request method | GET | Shows the action requested from the server. |
| Host | cl-1985.ham-01.de.sixxs.net| Identifies the requested host when visible. |
| Request target | / | Identifies the requested resource when visible. |

## Response Evidence

| Observed Field | Observed Value | Why It Matters |
| --- | --- | --- |
| Response status | HTTP/1.1 200 OK | Confirms how the server answered the request. |
| Relevant response headers | Date: Sun, 05 Aug 2007 19:16:44 GMT; Server: Apache; Content-Length: 2121; Connection: close; Content-Type: text/html | Records response metadata visible in the stream. |

## Event Sequence

1. Client request event:
The client sent a GET / HTTP/1.0 request to cl-1985.ham-01.de.sixxs.net on TCP port 80.

2. Server response event:
The server returned HTTP/1.1 200 OK with Server: Apache and Content-Type: text/html.
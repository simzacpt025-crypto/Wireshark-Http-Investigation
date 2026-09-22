# Wireshark-Http-Investigation

## Scenario

This case study documents a simulated security review of the public `http.cap` training capture. It demonstrates network analysis and incident reporting without claiming a real breach.

## Key Finding

The capture confirms an HTTP request and response transmitted without encryption. The sample does not confirm sensitive-data exposure or compromise.

## Tools

- Wireshark.
- Visual Studio Code.
- Git.
- GitHub.

## Investigation Workflow

1. Downloaded `http.cap` from [Wireshark Sample Captures](https://wiki.wireshark.org/SampleCaptures).
2. Stored the capture outside this repository.
3. Opened the capture without a display filter to establish a baseline.
4. Applied the `http.request` display filter to isolate the request.
5. Recorded only directly observed packet facts.
6. Used Follow TCP Stream to reconstruct the request and response.
7. Assessed the confirmed finding separately from its potential security risk.

## Evidence and Report

- [Review the packet evidence](evidence.md).
- [Read the incident report](incident-report.md).

## Assessment

Unencrypted HTTP is confirmed in the training capture. Sensitive-data exposure and compromise are not confirmed.

CWE-319 applies when sensitive or security-critical data is transmitted in cleartext. HTTPS with correctly implemented TLS is recommended. Correctly implemented TLS can protect confidentiality. It can protect integrity. It can provide server authentication.

## Skills Demonstrated

- Packet capture analysis.
- HTTP request filtering.
- TCP stream reconstruction.
- Evidence handling.
- Event timeline construction.
- Risk assessment.
- Scoped incident reporting.
- Version-controlled documentation.

## Limitation

This is a simulated review of a public training capture. It does not claim a real breach.
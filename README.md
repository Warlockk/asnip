
## Asnip
Asnip retrieves all IPs of a target organization&mdash;used for attack surface mapping in reconnaissance phases.

It uses the IP or domain name and looks up the Autonomous System Number (ASN), retrieves the Classless Inter-Domain Routing (CIDR) subnet masks and converts them to IPs.

_IP / Domain &rarr; ASN &rarr; CIDRs &rarr; IPs_

Please note that this technique only makes sense if the target has its own ASN. It is also advised to not perform tests on IP ranges that belong to multiple entities.

_This tool is work in progress, if you make optimization changes yourself, you are invited to create a pull request or check the GitHub issues page&mdash;help is always appreciated._

### Installation
`go get github.com/harleo/asnip`

_This tool requires [golang](https://golang.org/)_

### Update
`go get -u github.com/harleo/asnip`

### Options

```console
Usage:
  -t string
        Domain or IP address (Required)
  -p string
        Print results to console
```

### Example

```console
$ asnip -t google.com -p

[:] ASN: 15169 / GOOGLE - Google LLC, US
8.8.4.0/24
--- snip ---
[:] Writing 501 CIDRs to file...
[:] Converting to IPs...
8.8.8.1
--- snip ---
[:] Writing 14222870 IPs to file...
```

### Disclaimer
This tool must use an external API such as HackerTarget to retrieve relevant data. It will rate limit your requests if you send too many.

---

&copy; 2019 Leonid Hartmann
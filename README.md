# CTF Toolkit

A lightweight Bash toolkit that provides a collection of utilities commonly used during Capture The Flag (CTF) competitions and security labs. The toolkit is designed to be simple, dependency-light, and easy to use directly from your shell.

## Features

* **Base64 Encode / Decode**

  * Encode plain text to Base64.
  * Decode valid Base64 strings.

* **URL Encoder**

  * Percent-encode strings for use in URLs and HTTP requests.

* **ROT13**

  * Apply the ROT13 substitution cipher.

* **XOR Helper**

  * Perform bitwise XOR operations between two integer values.

* **Hash Identifier**

  * Identify common hash types based on hexadecimal format and length.
  * Supports detection of:

    * CRC32
    * MD5
    * NTLM
    * SHA-1
    * RIPEMD-160
    * SHA-224
    * SHA-256
    * SHA3-256
    * SHA-384
    * SHA-512
    * Whirlpool
    * bcrypt

* **Hex Conversion**

  * Convert hexadecimal data into ASCII.

* **Binary Conversion**

  * Convert binary data into ASCII.

* **HTTP Headers**

  * Send an HTTP `HEAD` request and display the response headers.

* **TCP Scan**

  * Scan a range of TCP ports on a target host to identify open services.

## Requirements

The toolkit uses standard Unix utilities available on most Linux systems.

Required:

* Bash
* `base64`
* `xxd`
* `perl`

Optional:

* `jq` (required only for the URL encoding feature)

## Installation

Clone the repository:

```bash
git clone <repository-url>
cd <repository-directory>
```

Since the toolkit is implemented as a collection of Bash functions, it must be **sourced**, not executed directly.

```bash
source toolkit.sh
```

or

```bash
. toolkit.sh
```

After sourcing the script, all toolkit functions become available in your current shell session.

## Usage

Examples:

```bash
base_64 "hello"

url_enc "hello world"

rot_13 "AttackAtDawn"

xor_helper 10 5

hash_id d41d8cd98f00b204e9800998ecf8427e

hex_conversion 48656c6c6f

binary_conversion 0100100001100101011011000110110001101111

http_headers example.com

tcp_scan example.com 1 1024
```

To display the built-in help menu:

```bash
help_page
```

## Notes

* HTTP header retrieval uses a plain TCP connection on port **80**.
* The TCP scanner performs a basic TCP connect scan using Bash's `/dev/tcp` interface.
* The toolkit is intended for educational purposes, CTF competitions, and authorized security testing only.

## License

This project is provided as-is for educational use.

# almide/base64

Base64 encoding and decoding for [Almide](https://github.com/almide/almide). Pure Almide implementation supporting standard (RFC 4648) and URL-safe variants.

## Install

```bash
almide add almide/base64
```

## Usage

```almide
import base64

// Encode / Decode (standard)
let encoded = base64.encode("Hello World")   // "SGVsbG8gV29ybGQ="
let decoded = base64.decode(encoded)!        // "Hello World"

// URL-safe (no padding, - and _ instead of + and /)
let url_encoded = base64.encode_url("Hello World")
let url_decoded = base64.decode_url(url_encoded)!
```

### Bytes API

```almide
import base64

let encoded = base64.encode_bytes([72, 101, 108, 108, 111])  // "SGVsbG8="
let bytes = base64.decode_bytes("SGVsbG8=")!                  // [72, 101, 108, 108, 111]
```

## API

| Function | Signature | Description |
|---|---|---|
| `base64.encode` | `(String) -> String` | Encode string to Base64 |
| `base64.decode` | `(String) -> Result[String, String]` | Decode Base64 to string |
| `base64.encode_url` | `(String) -> String` | Encode to URL-safe Base64 (no padding) |
| `base64.decode_url` | `(String) -> Result[String, String]` | Decode URL-safe Base64 |
| `base64.encode_bytes` | `(List[Int]) -> String` | Encode byte list to Base64 |
| `base64.decode_bytes` | `(String) -> Result[List[Int], String]` | Decode Base64 to byte list |
| `base64.encode_bytes_url` | `(List[Int]) -> String` | Encode bytes to URL-safe Base64 |
| `base64.decode_bytes_url` | `(String) -> Result[List[Int], String]` | Decode URL-safe Base64 to bytes |

## License

MIT

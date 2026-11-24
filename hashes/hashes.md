# HTTP object hashes (Appendix B)

Source: `docs/cw1-investigation-report.md` Appendix B.  
Bodies reassembled from TCP streams in `COMP3010HK_CW1.pcap`. “Transferred” = Content-Length bytes on the wire. Payload hash is **not** a plaintext `.exe` (body does not start with MZ).

| Object | Frame | Type | Bytes | Body | MD5 | SHA256 |
|---|---|---|---|---|---|---|
| RIG landing page | 14395 | text/html | 18840 | gzip as transferred | 3821d6acdf20a11d04bb8c0ebbc9a94c | d440f249d04817dcb402bd5144c25688ef329f0a51e5489a804901adae9a3b22 |
| RIG landing page | 14395 | text/html | 30212 | decompressed | d224396e69d2afea6a2df310efb3446f | f063798bac71434ec0bf5b9ce019e6b496971b1173e5eb34d1691c149b8533be |
| Flash | 14494 | application/x-shockwave-flash | 50368 | transferred (CWS SWF, no HTTP gzip) | 9d8a1f948a043dd7ee7b64154986513e | b95fa5beddf64653bf88456ed521a0b7226d4fb4f5e8983b85ca5d03d8621be5 |
| Payload | 15099 | application/x-msdownload | 490175 | transferred (not MZ) | 85f22cabd66f365a864b6e04cda85fa0 | 04a28df9620d722157cf629aa764eee408bcbd47fb6030f425efe0b13033e0a4 |

Do not execute the payload sample.

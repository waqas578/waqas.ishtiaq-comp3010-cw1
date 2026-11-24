# Wireshark filters — screenshots 1–8

UTC is authoritative. Map to Appendix B figures B1–B8.

| # | Screenshot | Display filter | Purpose |
|---|---|---|---|
| 1 | Endpoints / Ethernet (infected host) | `ip.addr == 10.14.106.192` | Confirm sole internal host `10.14.106.192` / MAC `00:05:31:c2:6f:b2`. |
| 2 | Frame 14055 — unwrappedphotos.com | `frame.number == 14055` | Jump to the Evil Redirector GET `http://unwrappedphotos.com/`. |
| 3 | Evil Redirector alert correlation | `http.host == "unwrappedphotos.com" && http.request.uri == "/"` | Isolate the redirector request matched to the Jul 12 2016 / dport 49450 alert. |
| 4 | Frame 14338 — RIG path | `http.host contains "kaghaan" && http.request` | Show GET to `rew.kaghaan.com` with referrer `unwrappedphotos.com`. |
| 5 | Frame 15099 — payload | `frame.number == 15099` | Show `application/x-msdownload` payload (490,175 bytes; not MZ). |
| 6 | Frame 15209 — Cerber check-in | `udp.dstport == 6892` | Show Cerber UDP check-in to port 6892. |
| 7 | Cerber infrastructure host | `http.host contains "le2brr.bid"` | Show access to `ffoqr3ug7m726zou.le2brr.bid`. |
| 8 | HTTP export objects / hash sources | `http.host contains "kaghaan"` | List RIG HTTP objects used for Appendix B landing/Flash/payload hashes. |

Optional related filters from Appendix A:

```
http.host contains "19jmfr.top" && http.request.uri contains "/intro"
```

# Other indicators (Appendix B)

Source: `docs/cw1-investigation-report.md` Appendix B / §3–§6.

## Victim / network

- Infected host: `10.14.106.192` / MAC `00:05:31:c2:6f:b2`
- Victim / payment id: `B558-E94E-6308-008C-1E79`
- Cerber check-in: UDP/`6892` (frame 15209; payload begins `hi008c1c4`)
- Bitcoin address: `17gd1msp5FnMcEMF1MitTNSsYs7w7AQyCt` (queried via `btc.blockr.io`)

## Hosts

- Compromised redirector: `unwrappedphotos.com` (`50.56.223.21`)
- RIG exploit-kit host: `rew.kaghaan.com` (`109.234.36.251`)
- Cerber infrastructure: `ffoqr3ug7m726zou.le2brr.bid` (also `ffoqr3ug7m726zou.19jmfr.top`)
- DNS resolver only (not victim): `10.4.29.3`

## Campaign / alert anchors

- Campaign (validation exercise): PseudoDarkleech
- Evil Redirector signature date field: `2016-07-12`; event timestamp: `2016-10-14 22:14:42` UTC; dport `49450`

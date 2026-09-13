# MikeTechSecurity Pi-hole Blocklists

A personal Pi-hole blocklist and filtering setup maintained by **MikeTechSecurity**.

This repository contains local copies of selected upstream DNS blocklists that can be subscribed to from Pi-hole using stable raw GitHub URLs. The upstream list contents remain the work of their respective maintainers; this repository does **not** claim authorship of those upstream lists.

## Recommended Pi-hole group layout

| Local list | Suggested Pi-hole group assignment | Purpose |
|---|---|---|
| `lists/pro.txt` | Default, LAN_Trusted, IoT, Kids, LAN3_Mining | Main ads, trackers and general protection |
| `lists/tif-medium.txt` | Default, LAN_Trusted, IoT, Kids, LAN3_Mining | Threat intelligence, malware and phishing |
| `lists/nsfw.txt` | Kids | Adult-content filtering |
| `lists/gambling-medium.txt` | Kids | Gambling filtering |
| `lists/social.txt` | Kids | Social-network filtering |
| `lists/nosafesearch.txt` | Kids | Blocks search services that do not support SafeSearch |
| `lists/doh-vpn-proxy-bypass.txt` | Kids, optional | Helps limit DNS/VPN/Tor/proxy bypass methods |
| `lists/stevenblack-hosts.txt` | Optional | StevenBlack hosts copy; usually redundant when using HaGeZi Pro |
| `lists/Mike-ow-list.txt` | Any group you choose | MikeTechSecurity custom network denylist |

Do **not** assign filtering lists to the `Bypass` group.

## Pi-hole subscription URLs

Use these URLs in **Pi-hole > Group Management > Lists**:

```text
https://raw.githubusercontent.com/MikeTechSecurity/pihole-blocklists/main/lists/pro.txt
https://raw.githubusercontent.com/MikeTechSecurity/pihole-blocklists/main/lists/tif-medium.txt
https://raw.githubusercontent.com/MikeTechSecurity/pihole-blocklists/main/lists/nsfw.txt
https://raw.githubusercontent.com/MikeTechSecurity/pihole-blocklists/main/lists/gambling-medium.txt
https://raw.githubusercontent.com/MikeTechSecurity/pihole-blocklists/main/lists/social.txt
https://raw.githubusercontent.com/MikeTechSecurity/pihole-blocklists/main/lists/nosafesearch.txt
https://raw.githubusercontent.com/MikeTechSecurity/pihole-blocklists/main/lists/doh-vpn-proxy-bypass.txt
https://raw.githubusercontent.com/MikeTechSecurity/pihole-blocklists/main/lists/stevenblack-hosts.txt
https://raw.githubusercontent.com/MikeTechSecurity/pihole-blocklists/main/lists/Mike-ow-list.txt
```

## Mike OW custom list

Edit `lists/Mike-ow-list.txt` to add your own network blocks. It includes a ready-to-use template plus a starter set of advertising and tracking domains.

Rules use Pi-hole-compatible ABP-style syntax:

```text
||example.com^
```

Lines beginning with `!` are comments. To activate one of the optional example blocks, remove the leading `!` from that rule.

After committing changes, run **Update Gravity** in Pi-hole so Pi-hole downloads the latest copy.

## Upstream sources

- HaGeZi DNS Blocklists: `https://github.com/hagezi/dns-blocklists`
- StevenBlack hosts: `https://github.com/StevenBlack/hosts`

See `SOURCES.md` for source URLs and attribution details.

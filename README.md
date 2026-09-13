# MikeTechSecurity Pi-hole Blocklists

A personal Pi-hole blocklist mirror and filtering setup maintained by **MikeTechSecurity**.

This repository mirrors selected upstream DNS blocklists into stable raw GitHub URLs that can be subscribed to from Pi-hole. The mirrored list contents are produced by their respective upstream projects; this repository does **not** claim authorship of those upstream lists.

## Recommended Pi-hole group layout

| Local mirror | Suggested Pi-hole group assignment | Purpose |
|---|---|---|
| `lists/pro.txt` | Default, LAN_Trusted, IoT, Kids, LAN3_Mining | Main ads, trackers and general protection |
| `lists/tif-medium.txt` | Default, LAN_Trusted, IoT, Kids, LAN3_Mining | Threat intelligence, malware and phishing |
| `lists/nsfw.txt` | Kids | Adult-content filtering |
| `lists/gambling-medium.txt` | Kids | Gambling filtering |
| `lists/social.txt` | Kids | Social-network filtering |
| `lists/nosafesearch.txt` | Kids | Blocks search services that do not support SafeSearch |
| `lists/doh-vpn-proxy-bypass.txt` | Kids, optional | Helps limit DNS/VPN/Tor/proxy bypass methods |
| `lists/stevenblack-hosts.txt` | Optional | StevenBlack hosts mirror; usually redundant when using HaGeZi Pro |
| `lists/miketechsecurity-custom.txt` | Any group you choose | Your own custom block entries |
Do **not** assign filtering lists to the `Bypass` group.

## Pi-hole subscription URLs

After the first successful GitHub Actions update, use these URLs in **Pi-hole > Group Management > Lists**:

```text
https://raw.githubusercontent.com/MikeTechSecurity/pihole-blocklists/main/lists/pro.txt
https://raw.githubusercontent.com/MikeTechSecurity/pihole-blocklists/main/lists/tif-medium.txt
https://raw.githubusercontent.com/MikeTechSecurity/pihole-blocklists/main/lists/nsfw.txt
https://raw.githubusercontent.com/MikeTechSecurity/pihole-blocklists/main/lists/gambling-medium.txt
https://raw.githubusercontent.com/MikeTechSecurity/pihole-blocklists/main/lists/social.txt
https://raw.githubusercontent.com/MikeTechSecurity/pihole-blocklists/main/lists/nosafesearch.txt
https://raw.githubusercontent.com/MikeTechSecurity/pihole-blocklists/main/lists/doh-vpn-proxy-bypass.txt
https://raw.githubusercontent.com/MikeTechSecurity/pihole-blocklists/main/lists/stevenblack-hosts.txt
```

## Automatic updates

The workflow in `.github/workflows/update-blocklists.yml` downloads fresh upstream copies every 6 hours and commits changes only when the mirrored content actually changes. It can also be run manually from the **Actions** tab.

## Upstream sources

The automated mirror currently follows:

- HaGeZi DNS Blocklists: `https://github.com/hagezi/dns-blocklists`
- StevenBlack hosts: `https://github.com/StevenBlack/hosts`

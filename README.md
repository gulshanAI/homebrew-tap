# Tether Homebrew tap

[Tether](https://ter.soiltonenatural.com) puts your dev machine in your pocket: browse files, run terminals, check git, preview dev servers and test APIs on your computer from your phone.

## Install

```sh
brew install gulshanAI/tap/tether
tether start
```

`tether start` runs Tether in the background (it restarts if it crashes and starts again at login), opens a free Cloudflare tunnel, and prints a link and a QR code. Open it on your phone. The first time, create your account with the setup code it shows.

| Command | |
|---|---|
| `tether start` | start in the background and print the link |
| `tether status` | is it running and reachable? |
| `tether url` | print the link |
| `tether open` | open the Tether app for this machine |
| `tether setup-code` | the one-time code for the first account |
| `tether logs -f` | follow the log |
| `tether stop` | stop it (and don't start at login) |

After `brew upgrade tether`, run `tether restart`.

Works on macOS (launchd) and Linux (systemd user service). On a Linux server, run `loginctl enable-linger $USER` so it keeps running when you're logged out.

## Uninstall

```sh
tether stop
brew uninstall tether
rm -rf ~/.tether     # your local account, projects and API collections
```

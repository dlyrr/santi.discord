# santi.discord

A Discord desktop client, the way I want it: [Equibop](https://github.com/Equicord/Equibop) (Equicord's Vesktop) with
[santi.discord-core](https://github.com/dlyrr/santi.discord-core) preinstalled, which is Equicord plus my own plugins:

- **BetterTyping**: cleans tracking parameters from links, rewrites them to embed-fixing mirrors (fxspotify, fxapplemusic, fxtwitter, ...),
  turns bare domains into links, polishes wording and restyles your typing.
- **TypingStyles**: lowercase, UPPERCASE, Title Case, Sentence case or aLtErNaTiNg for everything you send.

Everything else is Equibop: lighter and faster than the official app, Linux screenshare with sound, no Discord access to your system.

## How it fits together

| Repo | Role |
| --- | --- |
| [santi.discord](https://github.com/dlyrr/santi.discord) (this) | The desktop app. Fork of Equibop. |
| [santi.discord-core](https://github.com/dlyrr/santi.discord-core) | The client mod. Fork of Equicord with the plugins in `src/equicordplugins`. Every push rebuilds its `latest` release. |

On first launch the app downloads `equibop.asar` from santi.discord-core's `latest` release into its data folder, exactly the way
Equibop downloads Equicord's. Equibop's own updater keeps the app itself current from this repo's releases.

## Building

Needs [bun](https://bun.sh).

```sh
bun install
bun run start          # run from source
bun run package        # installers into dist/
```

Pushing a `v*` tag builds Windows and Linux installers on GitHub Actions and publishes them as a release.

## Upstream

`upstream` is Equicord/Equibop; merge it in to stay current. The only intentional differences are the branding, the download URL
in `src/main/utils/vencordLoader.ts`, and the removal of Equicord's release-side workflows.

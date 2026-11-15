# white-icons

Image assets referenced by URL from self-hosted containers — Unraid's Docker tab
fetches a container's icon over plain HTTP with no credentials.

**This repository must stay public.** That is the whole reason it exists and the
reason it holds nothing but images: the apps that point at it are private, and an
icon has nothing worth hiding. Making this private would break their icons with
no obvious cause.

Referenced as:

    https://raw.githubusercontent.com/Pallarran/white-icons/main/<file>.png

## What is here

| File | Containers |
| --- | --- |
| `steward.png` | `steward`, `steward-db` |
| `horizon.png` | `horizon`, `horizon-db`, `horizon-jobs` |
| `talos.png` | `talos`, `talos-voice`, `speaches` |
| `chronicle.png` | `adventurers-chronicle`, `adventurers-chronicle-db` |

512 × 512 PNG on transparency, so each one sits on Unraid's dark page rather than
in a pale box of its own.

## Replacing an icon

**Unraid caches the fetched icon by URL on its RAM disk**, so overwriting a file
here changes nothing on a running server until the next reboot. Bump the `?v=`
on the `net.unraid.docker.icon` label in that app's compose file in the same
change — a new URL is a new cache entry, and the icon arrives on the next
`up -d`.

That is why the labels read, for example:

    https://raw.githubusercontent.com/Pallarran/white-icons/main/steward.png?v=2

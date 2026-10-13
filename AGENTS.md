# Agent rules (private repo)

- **Visibility:** this repo stays private. It holds proprietary firmware and stock images. Never make it public, mirror it, or copy its files into `mia3-postmarketos`.
- **Use:** `mia3-postmarketos/deploy.sh` picks up `firmware/` from here (checked out next to it) and copies it to the phone with `cp -an`.
- **Large files:** `stock/images/*.img` are big. Add images only when they come from a new stock source.
- **Main rules:** see `mia3-postmarketos/AGENTS.md` (phone access, secrets, logging).

# Arch PKGBUILDs

Arch Linux package definitions for Rust projects maintained by
SisyphusAeolides. Each package directory is independently buildable with
`makepkg`.

## Build a package

Install the standard Arch build tools, then build from the package directory:

```bash
sudo pacman -S --needed base-devel rust cargo
cd ccze-rs
makepkg -si
```

## Add a Rust package

1. Create a directory named after the Arch package.
2. Add a `PKGBUILD` that downloads an immutable source archive, uses verified
   checksums, and builds with `cargo --locked`.
3. Run `makepkg --printsrcinfo > .SRCINFO` from that directory.
4. Build it locally with `makepkg -s`.

Package definitions should be self-contained. Do not commit built packages,
Cargo target directories, or package-manager caches.

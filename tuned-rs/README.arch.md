# tuned-rs

Rust implementation of the TuneD system tuning daemon.

## Installation

Build and install the package from this directory:

```bash
makepkg -si
```

The package conflicts with `tuned` and `power-profiles-daemon` because it
provides their D-Bus services. Enable the desired service after installation:

```bash
sudo systemctl enable --now tuned-rs.service
sudo systemctl enable --now tuned-rs-ppd.service
```

## Configuration

- `/etc/tuned/tuned-main.conf` configures the main tuning daemon.
- `/etc/tuned/ppd.conf` configures the power-profile compatibility service.
- Profiles are installed under `/usr/lib/tuned/profiles`.

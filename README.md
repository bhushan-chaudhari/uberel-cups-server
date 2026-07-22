# CUPS Server — Umbrel Community App Store

An [Umbrel](https://umbrel.com) community app store that packages the
[`anujdatar/cups`](https://hub.docker.com/r/anujdatar/cups) Docker image so you
can run a [CUPS](https://www.cups.org/) print server on your Umbrel and share
USB printers over your network.

## Apps

| App  | ID                | Image              | Port |
| ---- | ----------------- | ------------------ | ---- |
| CUPS | `cups-server-cups` | `anujdatar/cups`   | 631  |

## How to install

1. Open the umbrelOS dashboard.
2. Go to the **App Store**, click the **⋯** menu in the top right, and choose
   **Community App Stores**.
3. Add this repository's GitHub URL.
4. Install **CUPS** from the newly added store.

## Usage

- Open the app and sign in with the admin credentials to add and manage printers.
- Default admin username: `admin`
- Default admin password: `password`

Change these defaults by editing the `CUPSADMIN` and `CUPSPASSWORD` environment
variables in [`cups-server-cups/docker-compose.yml`](cups-server-cups/docker-compose.yml).

> **Note:** CUPS needs access to your device's USB bus (`/dev/bus/usb`) to detect
> printers. Make sure a supported USB printer is connected.

## Repository structure

```
.
├── umbrel-app-store.yml          # App store metadata (id + name)
├── README.md
└── cups-server-cups/             # The CUPS app (folder name == app id)
    ├── umbrel-app.yml            # App listing details shown in umbrelOS
    └── docker-compose.yml        # Services that run the app
```

## Credits

- Docker image by [Anuj Datar](https://github.com/anujdatar/cups-docker).
- App store pattern from [getumbrel/umbrel-community-app-store](https://github.com/getumbrel/umbrel-community-app-store).

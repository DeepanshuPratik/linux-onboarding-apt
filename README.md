# linux-onboarding apt repository

Prebuilt `.deb` packages, currently built for **Ubuntu 24.04 (noble), amd64**:

- **`linux-onboarding`** — the brand-agnostic base app. Installs no distro
  identity of its own.
- **`regolith-onboarding`** — Regolith Linux's branding (welcome page, theme,
  slides, practice workflows) for `linux-onboarding`. Depends on the base
  package and, once installed, makes Regolith the active branding on next
  launch. A reference implementation of the branding-package contract in
  [`docs/DISTRO-GUIDE.md`](https://github.com/DeepanshuPratik/Regolith_Onboarding/blob/main/docs/DISTRO-GUIDE.md) —
  other distros and desktops can copy this same shape.

## Add this repo

```bash
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://deepanshupratik.github.io/linux-onboarding-apt/linux-onboarding-archive-keyring.gpg \
    | sudo tee /etc/apt/keyrings/linux-onboarding-archive-keyring.gpg > /dev/null

echo "deb [signed-by=/etc/apt/keyrings/linux-onboarding-archive-keyring.gpg] https://deepanshupratik.github.io/linux-onboarding-apt noble main" \
    | sudo tee /etc/apt/sources.list.d/linux-onboarding.list > /dev/null

sudo apt-get update
sudo apt-get install linux-onboarding

# Optional: Regolith Linux's own branding
sudo apt-get install regolith-onboarding
```

## Verify the key fingerprint before trusting it

```
8297 A365 D602 5623 7C3F  6DFB 6DA9 DD17 0F87 78E9
```

## Removing the repo

```bash
sudo rm /etc/apt/sources.list.d/linux-onboarding.list
sudo rm /etc/apt/keyrings/linux-onboarding-archive-keyring.gpg
sudo apt-get update
```

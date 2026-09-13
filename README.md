# linux-onboarding apt repository

Prebuilt `.deb` packages for `linux-onboarding`, currently built for **Ubuntu 24.04 (noble), amd64**.

## Add this repo

```bash
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://deepanshupratik.github.io/linux-onboarding-apt/linux-onboarding-archive-keyring.gpg \
    | sudo tee /etc/apt/keyrings/linux-onboarding-archive-keyring.gpg > /dev/null

echo "deb [signed-by=/etc/apt/keyrings/linux-onboarding-archive-keyring.gpg] https://deepanshupratik.github.io/linux-onboarding-apt noble main" \
    | sudo tee /etc/apt/sources.list.d/linux-onboarding.list > /dev/null

sudo apt-get update
sudo apt-get install linux-onboarding
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

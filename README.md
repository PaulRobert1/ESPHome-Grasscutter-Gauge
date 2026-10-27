# Grasscutter Battery Gauge

ESP8266 battery-voltage monitor and PWM driver for a grasscutter analog gauge.

## What it does

Reads battery voltage through an ADC divider and maps it to a PWM-driven analog gauge. The source uses a 58.5 ADC scale factor and a 10.11–12.0 V gauge range; these installation-specific values require calibration.

## Hardware and configuration

- ESPHome entry point: [`grasscutter.yaml`](grasscutter.yaml).
- Board/profile: `nodemcuv2`.
- GPIO assignments, calibration constants and exposed entities are defined in the YAML. Match them to your hardware before use.

## Setup

1. Keep the repository directory structure when copying it to ESPHome Device Builder.
2. Copy `secrets.example.yaml` to `secrets.yaml`; enter your Wi-Fi settings, unique OTA password and API encryption key. Generate an API key with `openssl rand -base64 32`. Set any BSSID/static-network/web-login placeholders for your own installation.
3. Review pins, sensor calibration, network settings and any Home Assistant entity references.
4. Validate with `esphome config grasscutter.yaml`, then build with `esphome compile grasscutter.yaml`. Choose an ESPHome version compatible with the source; the publication check uses ESPHome 2026.9.1.
5. Flash only the intended board after checking its wiring and configuration.

`secrets.yaml` and build outputs are ignored by Git. Fonts referenced with `gfonts://` require download access during preparation/build.

## Source and publication notes

Snapshot of the stored Home Assistant ESPHome source taken on **2026-10-27**. This is not proof of which firmware is currently flashed. Creating this repository does not upload firmware or change a live device.

- Credentials and network settings moved to `!secret` references.

See [VALIDATION.md](VALIDATION.md) for the publication checks and their limits.

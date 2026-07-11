# Sentinel

**An off-grid perimeter monitoring system** — solar-friendly LoRa sensor nodes, a touchscreen base station, and an iPhone app for alerts.

Sentinel watches remote trails and approaches with battery-powered sensor nodes that passively detect nearby Bluetooth devices (phones, watches, earbuds carried by people). Detections travel by LoRa — no WiFi, no cellular, no internet — to a base station, which shows them on a touchscreen dashboard, plays audio alerts, and pushes notifications to your iPhone over Bluetooth.

## How it works

```
[Node 1..3]  ──LoRa──▶  [Base station]  ──BLE──▶  [iPhone app]
 XIAO ESP32-C6           ESP32-S3 2.8" LCD          this app
 passive BLE scan        LVGL dashboard             alerts + status
 deep-sleep cycle        audio alerts
                         (+ LED-only backup base)
```

- **Sensor nodes** — Seeed XIAO ESP32-C6 + RYLR998 LoRa radio. Passive BLE scanning (they transmit nothing detectable), multi-day battery life via deep sleep, external 2.4 GHz antenna for extended detection range.
- **Base station** — Waveshare ESP32-S3 2.8″ touch LCD. Dark "tactical" LVGL UI with per-node cards, detection ranges, mute timers, day/night themes, rolling event log, and RSSI-based distance estimation.
- **Backup base** — Heltec CubeCell, LED-only: heartbeat, per-node alert identification, button-configured range. Fully independent receiver.
- **iPhone app** — connects to the base over BLE, delivers time-sensitive notifications with node name and estimated distance, shows per-node status and battery, and can ping/silence/reset the base remotely.

## Screenshots

| Alerts | Status |
|---|---|
| *(coming soon)* | *(coming soon)* |

## Privacy

Sentinel collects **no data**. See [PRIVACY.md](PRIVACY.md).

## Availability

Currently in private testing via TestFlight. The firmware and app source live in a private repository.

## Contact

Max Botev — maxbotev@gmail.com

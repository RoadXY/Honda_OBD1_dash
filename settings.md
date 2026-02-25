# Configuration Settings (`settings.txt`)

This document explains the configuration parameters for the Civic Dash project. All settings can be adjusted by editing the `settings.txt` file on the SD card.

## Format
The file uses a `key=value` format. Lines before the `[SETTINGS]` header are ignored. For boolean values, use `1` for YES/ON and `0` for NO/OFF.

---

## 🛠 Basic Settings

| Key | Type | Description |
| :--- | :--- | :--- |
| `slaveName` | String | The Bluetooth name of the ECU module (e.g., `Z Fold7 van Robin`). |
| `trannyType` | Integer | Selects the gear ratio table for your transmission. (See [Transmission Types](#transmission-types)). |

### Transmission Types (`trannyType`)
The dashboard uses these values to calculate the correct gear display:
* `0`: Y21 / Y80
* `1`: S80J
* `2`: S80U
* `3`: Z6 / Y8
* `4`: GSR
* `5`: RS
* `6`: H22J
* `7`: H23U
* `8`: H22U
* `9`: Y7

---

## 📊 Measurement Units

| Key | Values | Unit Description |
| :--- | :--- | :--- |
| `mapUnit` | `0`=mBar, `1`=Bar, `2`=inHgG, `3`=inHg, `4`=psi, `5`=kPa | Manifold Absolute Pressure |
| `tempUnit` | `0`=Celsius, `1`=Fahrenheit | Coolant & Intake Temp |
| `speedUnit` | `0`=KMH, `1`=MPH | Vehicle Speed |

---

## 🔌 Hardware & Sensors

### O2 Input (`O2Input`)
Defines which ECU pin is used for the wideband/oxygen sensor signal:
* `0`: **O2** (Standard Pin D14)
* `1`: **ELD** (Pin D10)
* `2`: **EGR** (Pin D12)
* `3`: **B6** (Pin B6)

### Wideband Type (`widebandType`)
* `0`: **Voltage** (Standard 0-5V analog signal)
* `1`: **Zeitronix** (Specific Zeitronix digital protocol/scaling)

---

## 💾 Logging & Power

| Key | Default | Description |
| :--- | :--- | :--- |
| `logToSD` | `1` | Enable/Disable automatic data logging to SD card. |
| `logRpmThreshold` | `1000` | Start logging when RPM exceeds this value. |
| `logTpsThreshold` | `50` | Start logging when Throttle Position is above this %. |

---

## 🌐 Connectivity (WiFi & MQTT)

| Key | Description |
| :--- | :--- |
| `syncTime` | (`1`/`0`) Synchronize internal clock with internet time via NTP. |
| `sendMqtt` | (`1`/`0`) Send battery voltage to your MQTT broker every hour. |
| `wifi_ssid` | Your WiFi network name (SSID). |
| `wifi_password` | Your WiFi password. |
| `mqtt_server` | IP address of your MQTT Broker (e.g., `192.168.0.8`). |
| `mqtt_server_topic` | The topic name for the MQTT client (default: `CivicDashClient`). |

---

## ⚠️ Battery Safety Modes
The system monitors the battery voltage automatically to protect your car's battery:

1. **Normal Mode:** Every hour the ESP32 wakes up, checks voltage, logs to SD, and syncs via WiFi/MQTT.
2. **Low Voltage (< 11.8V):** Red LED alerts and "ACCU SPANNING LAAG" message is displayed.
3. **Storage Mode (< 11.0V):** WiFi is disabled to save power and the hourly timer is stopped. The ESP32 will only wake up when the physical ignition is turned on to prevent deep discharge.

---

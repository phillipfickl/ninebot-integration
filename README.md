# Ninebot Scooter integration for Home Assistant

Connects to Ninebot/Segway electric scooters via Bluetooth LE to read battery status, mileage, speed, temperature, and other sensor data.

## Supported models

E-series (E22, E25, E45), MAX/G30 series, F-series (F20, F25, F30, F40, F60), and other Ninebot scooters that use the standard BLE protocol with manufacturer ID 16974.

## Available sensors

- **Battery**: remaining capacity (%), voltage, current, health, temperature
- **Mileage**: total, single trip, actual remaining, predicted remaining
- **Speed**: average speed, speed limits
- **Device info**: firmware versions, serial number, error/alarm codes
- **Status**: locked, speed limited, operating mode, KERS level, cruise control, tail light

## Installation via HACS

1. Open HACS in Home Assistant
2. Go to **Integrations** > three-dot menu > **Custom repositories**
3. Add `https://github.com/phillipfickl/ninebot-integration` as an **Integration**
4. Search for "Ninebot Scooter" and install it
5. Restart Home Assistant

## Manual installation

1. Copy the `custom_components/ninebot_scooter` directory into your `<config_dir>/custom_components/`
2. Restart Home Assistant

## Setup

After installation, your scooter should be auto-discovered via Bluetooth. If not:

1. Go to **Settings** > **Devices & Services** > **Add Integration**
2. Search for "Ninebot Scooter"
3. Select your scooter from the list of discovered devices

Make sure your scooter is powered on and within Bluetooth range of your Home Assistant instance.

## Requirements

- Home Assistant 2023.12.0 or newer
- A Bluetooth adapter accessible to Home Assistant
- A supported Ninebot/Segway scooter powered on and in range

## Troubleshooting

- **Scooter not discovered**: Ensure the scooter is powered on (not in sleep mode) and within BLE range. You may need to wake it by briefly pressing the power button.
- **Timeout errors**: The scooter may go to sleep between polls. This is normal; data will refresh when the scooter is next awake and in range.
- **First connection**: Some scooters require you to press the power button during initial pairing.

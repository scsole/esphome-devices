# ESPHome Configs

My personal configs for ESPHome devices.

## Quick Start

### Under an existing ESPHome installation

1. Clone this repo and use it as the ESPHome config folder: e.g., `git clone https://github.com/scsole/esphome-devices.git esphome && cd esphome`
2. Create a valid secrets file: `cp secrets.yaml.example secrets.yaml`
3. Start building configs

### Manual ESPHome Installation

Install [uv](https://github.com/astral-sh/uv) if you haven't already done so.

1. Clone this repo
2. Create a valid secrets file
3. Create a virtual environment
4. Activate the virtual environment
5. Install the [esphome requirements](https://esphome.io/guides/installing_esphome.html)
6. Start building configs

```bash
git clone https://github.com/scsole/esphome-devices.git
cd esphome-devices
cp secrets.yaml.example secrets.yaml
uv venv
source .venv/bin/activate # .venv\Scripts\activate under Windows
uv pip install wheel # only needed under Windows and macOS
uv pip install esphome
esphome dashboard ./
```

## Useful Notes

### Renaming Devices

1. Append the following wifi section to the config using the device's current name as the `old_name`
2. Update the name and other desired values under `substitutions`
3. Compile and upload to device
4. Remove the wifi section from the config

```yaml
wifi:
  use_address: old_name.local
```

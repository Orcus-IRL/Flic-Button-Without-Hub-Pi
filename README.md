# Flic Button Without Hub (Raspberry Pi)

![Flic Button](https://www.google.com/imgres?q=Flic%20Button&imgurl=https%3A%2F%2Fstatic.ffx.io%2Fimages%2F%24zoom_1%252C%24multiply_0.4057%252C%24ratio_1.777778%252C%24width_1972%252C%24x_28%252C%24y_44%2Ft_crop_custom%2Fq_86%252Cf_auto%2F0638a1b81082c890ad56ed83aec4fb02aa060cbd&imgrefurl=https%3A%2F%2Fwww.smh.com.au%2Ftechnology%2Finternet-of-things-giving-buttons-the-flic-20170620-gwuhd8.html&docid=RFuVB7jUvz_XtM&tbnid=rYQh4_Iit0fIAM&vet=12ahUKEwiDs6z9w9yGAxV5zDgGHeRHBoUQM3oECH4QAA..i&w=800&h=450&hcb=2&ved=2ahUKEwiDs6z9w9yGAxV5zDgGHeRHBoUQM3oECH4QAA)

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Hardware Requirements](#hardware-requirements)
- [Software Requirements](#software-requirements)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This project demonstrates how to use a Flic button without a hub, using a Raspberry Pi. The Flic button is a versatile Bluetooth button that can be used to control various devices and services with a simple press.

## Features

- Connect a Flic button directly to a Raspberry Pi.
- Configure actions for single press, double press, and long press.
- No need for the official Flic Hub.
- Lightweight and easy to set up.

## Hardware Requirements

- Raspberry Pi (any model with Bluetooth capability)
- Flic button(s)
- MicroSD card (with Raspbian OS installed)
- Power supply for Raspberry Pi

## Software Requirements

- Raspbian OS (latest version recommended)
- Python 3.x
- `fliclib` Python package

## Installation

1. **Update and Upgrade your Raspberry Pi:**
   ```bash
   sudo apt update
   sudo apt upgrade

2. **Install required packages:** 
   ```bash
   sudo apt install python3 python3-pip git

3. **Clone this repository:**
   ```bash
   git clone https://github.com/carloslopezjr/Flic-Button-Without-Hub-Pi.git
   cd Flic-Button-Without-Hub-Pi

4. **Install python dependencies:**
   ```bash
   pip3 install -r requirements.txt


## Configuration

1. **Enable Bluetooth on your Raspberry Pi:**
    ```bash
    sudo systemctl enable bluetooth
    sudo systemctl start bluetooth

2. **Pair your Flic button with the Raspberry Pi:**
    - Follow the instructions to put your Flic button in pairing mode and use the Bluetooth manager on Raspbian to pair the button.

3. **Edit the `config.py` file:**
{
    "button_id": "XX:XX:XX:XX:XX:XX",
        "actions": {
            "single_press": "your_script_single_press.sh",
            "double_press": "your_script_double_press.sh",
            "long_press": "your_script_long_press.sh"
        }
}
Replace "XX:XX:XX:XX:XX:XX" with your Flic button's Bluetooth MAC address and specify the scripts to be executed for each action.

## Usage

1. **Run the Flic server:**
    ```bash
    sudo ./start_flicd.sh

2. **start the script to listen for button presses:**
    ```bash
    python3 flic_button_listener.py

3. **Press your Flic button and watch the actions execute based on your configuration.**

## Troubleshooting

- **Button not responding:** Ensure the Flic button is paired correctly and the Bluetooth service is running on your Raspberry Pi.
- **Scripts not executing:** Check the file permissions of the scripts and ensure they are executable(`chmod +x your_script.sh`).

## Contributing

Contributions are welcome! Please fork the repository, make your changes, and submit a pull request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.



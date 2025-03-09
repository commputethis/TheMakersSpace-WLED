# Install and Configure WLED on an ESP8266 NodeMCU

## Requirements

- ESP8266 NodeMCU board
- USB to Micro-USB cable
- Computer with Windows, macOS, or Linux
- Connect your computer to `TheMakersSpace` Wi-Fi using password `Godisthemastermaker`

## Step 1: Install WLED Using the Web Installer

1. Open a browser and visit [https://install.wled.me](https://install.wled.me).
   - ![install.wled.me](./images/install.wled.me.png)
2. Connect the ESP8266 to your computer via USB.
   - ![esp_connected_to_computer](./images/esp8266_connected_to_pc.jpg)
3. Click "Install" and select your ESP8266 device from the list.
   - ![select_port](./images/select.port.png)
4. Follow the on-screen instructions to flash WLED to your device.
   - ![device_dashboard](./images/device_dashboard.png)
   - ![install_confirmation](./images/install_confirmation.png)
   - ![preparing](./images/preparing.png)
   - ![installing](./images/installing.png)
   - ![installing2](./images/installing2.png)
   - ![installing3](./images/installing3.png)
   - ![install_complete](./images/install_complete.png)
   - The following is what came up on my Ubuntu machine to configure Wi-Fi.
     - ![configure_wifi](./images/configure_wifi.png)
     - ![wifi_configured](./images/wifi_configured.png)
   - If your's went through the Wi-Fi configuration, you can skip to [Step 1a: Configuring WLED](#step-1a-configuring-wled)
   - If your's did not have the option to configure Wi-Fi, move onto [Step 1b: Connect to WLED](#step-1b-connect-to-wled)

## Step 1a: Update Wi-Fi settings

1. Click "VISIT DEVICE".
   - ![wifi_configured](./images/wifi_configured.png)
2. Click "Config".
   - ![clickconig](./images/clickconfig.png)
3. Click "WiFi Setup".
   - ![click_wifi_setup](./images/click_wifi_setup.png)
4. Scroll down and update mDNS address and AP SSID
   - Update mDNS name.
     - ![wifi_setup2](./images/wifi_setup2.png)
   - Update AP SSID.
     - ![wifi_setup3](./images/wifi_setup3.png)
   - Click "Save & Connect".
     - ![saveandconnect](./images/saveandconnect.png)

## Step 1b: Connect to WLED

1. After flashing, restart the ESP8266.
   - ![esp_disconnected_from_computer](./images/esp8266_disconnected_from_pc.jpg)
   - ![esp_reconnected_to_computer](./images/esp8266_reconnected_to_pc.jpg)
2. It will create a Wi-Fi network named `WLED-AP`.
   - ![wled-ap](./images/wled-ap.png)
3. Connect to `WLED-AP` using password `wled1234`.
   - ![wled-ap_passowrd](./images/wled-ap_password.png)
4. Open a browser and go to `http://4.3.2.1` to access the WLED web interface.
   - ![4321_warning](./images/4321_warning.png)
   - ![4321](./images/4321.png)
5. Configure your Wi-Fi settings and restart the device.
   - ![wifi_setup](./images/wifi_setup.png)
   - Enter Wi-Fi SSID and Passphrase Manually or use Scan button and select.
     - ![wifi_setup_scan_manual](./images/wifi_setup_manual.png)
     - ![wifi_setup_scan](./images/wifi_setup_scan.png)
   - Update mDNS name.
     - ![wifi_setup2](./images/wifi_setup2.png)
   - Update AP SSID.
     - ![wifi_setup3](./images/wifi_setup3.png)
   - Click "Save & Connect".
     - ![saveandconnect](./images/saveandconnect.png)
6. Connect your computer to `TheMakersSpace` Wi-Fi using password `Godisthemastermaker`.
   - ![themakersspace](./images/themakersspace.png)

## Step 2: Configure WLED

1. Open a browser, if not already open, and go to `http://wled-{name}.local` where `{name}` is the name you entered in the `Update AP Name` above
   - ![connecting_warning](./images/connecting_warning.png)
   - ![connected](./images/connected.png)
2. Click "Config".
   - ![click_on_config](./images/click_on_config.png)
3. Click "LED Preferences".
   - ![led_preferences](./images/led_preferences.png)
4. Set `Maximum PSU Current:` to the Amperage of our Power Supply, which is `10000`mA.
   - This will limit our power use to a safe amount within our power supply's limits.
   - Note: this power supply is much larger than we need for the 3' LED strips we are using and we can ignore the high current warning, but pay attention to it if you are using a longer strip later.
   - ![set_amperage](./images/set_amperage.png)
5. Verify `mA/LED"` is set to `55mA(typ. 5V WS281x)`.
   - If doing a project later, set it according to your LED's being used.
   - This setting helps in the calculation of power draw.
   - ![mA_LED](./images/mA_LED.png)
6. Note the `Color Order:` defaults to GRB (Green Red Blue).
   - If you are doing a project and colors are not correct, this may need changed to get the order of the LEDs correct.
   - ![color_order](./images/color_order.png)
7. Scroll down and set `Length:` to 60.
   - ![set_legnth](./images/set_length.png)
8. Note the `Data GPIO:` setting defaults to 2.
   - This is the GPIO pin the green wire in our project is connected to.  Most ESP boards has this labeled as D4, but verify based on the board you have selected for your project.  The GPIO pin can be changed if needed. See the WLED documentation for more detail at the URL at the end of this document.
9. Click "Save".
   - ![click_save](./images/click_save.png)
10. Click "User Interface".
    - ![user_interface](./images/user_interface.png)
11. Update `Server description:`.
    - This is used in the mobile app and automation systems for the name of the device.
    - ![server_description](./images/server_description.png)
12. Click "Save".
    - ![web_setup_save](./images/web_setup_save.png)
13. Click "Back".
    - This will take you out of the Config Menu.
    - ![exit_config](./images/exit_config.png)

## Troubleshooting

- If the ESP8266 is not detected, try using a different USB cable or port.
- Make sure you are using a compatible browser (Chrome or Edge recommended).
- If the device does not start WLED, try reinstalling via [https://install.wled.me](https://install.wled.me).

For more details, visit the WLED Knowledge Base: [https://kno.wled.ge](https://kno.wled.ge)

Enjoy your WLED-powered lighting setup!

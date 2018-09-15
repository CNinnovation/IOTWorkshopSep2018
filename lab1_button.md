# Azure Button

## Create the IoT Hub in Azure

Create the new IoT Hub in Azure, use the S1 pricing tier

## Configure the Device Twin

Install [SetupDeviceExplorer](https://github.com/Azure/azure-iot-sdks/releases)

Start the *device explorer* app.

From the IoT Hub, select *shared access policies* and copy the connection string for the  *iothubowner*. Configure this connection string with the *device explorer*.

Create a new device (e.g. named Button1) on the *Management* tab. Verify that the device is created in the IoT Hub. Copy the connection string for the device from the *Management* tab.

## Configure the Button Device

Configure WiFi and JSON data for the button.

Hold the power button for 5 sec. LED changes from green flash to yellow, then red flash. The device is in AP mode. From your PC, connect to the device via WiFi (SSID: ESP_...). Open the IP address 192.168.4.1. and configure WiFi for the button.
Configure User JSON to be sent from the button, e.g.

```json
{"ButtonId": "Christian"}
```

Enter the IoT Hub Configuration

Shutdown the button to save the settings.

Details: [Azure Button](https://aka.ms/button)

## Use the Button

Click on the button (verify the green light). Check if the key press is visible in the Device Twin in the IoT Hub.

# AzureDataSender_Wio_Terminal_Eth

AzureDataSender for Wio Terminal using ENC28 Ethernet module

Transfer telemetry sensor data to Azure Storage Tables. App running on the Wio Terminal developed on PlatformIO using Arduino Code, Microsoft Azure C SDK.

This is a modification of the App 'AzureDataSender_Wio_Terminal', which works with the WiFi module of the Wio Terminal.
Since the original version with the WiFi Module showed occasional hangs and occasional stopping of http requests I developed this version
which uses an Ethernet Enc28 module. Preliminary tests showed no issues. The App works with http and https requests.  


See the detailed explantion of the App 'AzureDataSender_Wio_Terminal' on www.hackster.io

https://www.hackster.io/RoSchmi/wio-terminal-app-sending-sensor-data-to-azure-storage-tables-dbb08e

and the video on Youtube:

https://youtu.be/yVkcU8m84jY

 
The stored data can be visualized in table form with the App 'AzureTabStorClient' or as line charts with the App 'Charts4Azure'. https://azuretabstorclient.wordpress.com/ https://azureiotcharts.home.blog/

Before you start, install the latest firmware (actually v2.1.1) for the Wio Terminal WiFi module. https://wiki.seeedstudio.com/Wio-Terminal-Network-Overview/ https://wiki.seeedstudio.com/Wio-Terminal-Wi-Fi/

When you have cloned the repository 'AzureDataSender_Wio_Terminal' in your working directory proceed as follows:

Copy the file

include/config_secret_template.h
to a file named

include/config_secret.h
Open config_secret.h and enter the Credentials of your Azure Storage Account. Open the file include/config.h and enter some settings (esp. the send interval, your timezone and daylightsavings offset) according to your needs.

Now you should be able to compile and deploy the App to the Wio Terminal. The App should automatically create a table in your Azure Storage Account and start to create new rows.

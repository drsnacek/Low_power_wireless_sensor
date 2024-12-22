# Low power wireless sensor
The intention is to build up a sensor powered by the batteries and wirelessly communicate with a server.

The first version is based on ESP8266 with the wifi connection to the server.
The DHT11 temprature/humidity sensor is powered through a NPN tranzistor that is controlled via the SW to unconnect the sensor power when the ESP is in the deep standby mode. MCP1700 is used to provide 3.3V for ESP, C2 is powering the ESP power peaks. TP4056 battery charger with the battery protection (BMS) built in is used togerther with Li-ion 18650 4.7V battery. R8 and R7 are a divider for measuring the battery state.

All components should provide very low power consumption in the deep standby mode to prolong the battery charnging needs as much as possible.


Component	Standby(µA)	Active(mA)

TP4056	50 µA (with LED: 2mA)	N/A
MCP1700	1,6 µA	250 mA (max)
ESP-12F	20-40 µA (deep sleep)	70-150 mA (Wi-Fi)
BMS	10 µA	N/A
Total energy consumption (standby)	~80-100 µA


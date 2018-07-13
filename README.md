# OutDootSensor

Code to collect out door temperatur, humidity, light intensity, barometric pressure/altitude sensor data.
5 in 1 Sensor from Wingoneer using i2c communication to read temperature, humidity, light intesity and barometric pressure.
In addition having a separate light intensity resistor to have a common value for light intensity (not lux).

## Wingoneer Sensores (Strinity Sensor Clobber v. 0.1)
WINGONEER® trademark Reg.NO:012678447

Beschreibung:
Vin: 3 / 5VDC
Logik: 3 / 5V-kompatibel
Schnittstelle: I2C
Druckmessbereich: 300-1100 hPa (9000m bis -500m über dem Meeresspiegel)
Bis zu 0,03 hPa / 0.25 m Auflösung
Temperaturbereich: -40 bis + 85 ° C Betriebsbereich, + -2 °
Dynamikumfang (Lux): 0.1 bis 40.000 Lux
Luftfeuchtigkeitsauflösung: typ% RH
Luftfeuchtigkeit Genauigkeit Bedingung 25 ° C ± 3% RH
Wiederholbarkeit ± 0.1

### Sonsoren
* TSL2561
  * Lightintensity (LUX)
  * Address: 0x39
* BMP 180
  * Airpreassure
  * Temperature
  * Address: 0x77
* AM2321
  * Temperature
  * Humidity
  * Address: 0x5c

## Attiny85 and I2C
(http://www.instructables.com/id/Using-an-I2C-LCD-on-Attiny85/)
The attiny85 can simulate I2C on PB2 (pin 7) (SCL) and PB0 (pin 5) (SDA). The 'Wire' library that is used to read and write bytes from and to the I2C port on the arduino doesn't work on the attiny. It needs the TinyWireM library to act as an I2C master.
Depending libraries have to be adapted to also use the TinyWireM: http://www.instructables.com/id/Serial-I2C-HD44780-compatible-LCD-for-ATTINY85/

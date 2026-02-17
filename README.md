# Temperature-Sensor-code

/*
 * Environment Monitor (Temp/Humidity)
 * Sensor: DHT11
 * Controller: ESP32
 * Dawnload the DHT Sensor liabrary by Adafruit
 */

#include "DHT.h"

// Define the pin and sensor type
#define DHTPIN 27   
#define DHTTYPE DHT11   

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  Serial.begin(115200);
  dht.begin();
}

void loop() {
  // Wait 2 seconds (DHT11 is slow!)
  delay(2000);

  // Read the data
  float humidity = dht.readHumidity();
  float temperature = dht.readTemperature();

  // Print to Serial Monitor
  Serial.print("Humidity: ");
  Serial.print(humidity);
  Serial.print("% | Temperature: ");
  Serial.print(temperature);
  Serial.println("°C");
}

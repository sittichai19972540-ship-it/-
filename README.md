
ตู้จ่ายยาอัตโนมัติผู้ป่วยอัลไซเมอร์

  Rotate a servo using a slider!

  App dashboard setup:
    Slider widget (0...180) on V3


/* Fill-in information from Blynk Device Info here */
#define BLYNK_TEMPLATE_ID           "TMPL6hxr5hWWB"
#define BLYNK_TEMPLATE_NAME         "Quickstart Device"
#define BLYNK_AUTH_TOKEN            "tY7F7vSWDgr0squszs0hkXi8rukzedHl"

/* Comment this out to disable prints and save space */
#define BLYNK_PRINT Serial


#include <ESP8266WiFi.h>
#include <BlynkSimpleEsp8266_SSL.h>
#include <Servo.h>

// Your WiFi credentials.
// Set password to "" for open networks.
char ssid[] = "OPPO A54";
char pass[] = "1234567890";

Servo servo;

BLYNK_WRITE(V3)
{
  servo.write(param.asInt());
}

void setup()
{
  // Debug console
  Serial.begin(115200);

  Blynk.begin(BLYNK_AUTH_TOKEN, ssid, pass);
  // You can also specify server:
  //Blynk.begin(BLYNK_AUTH_TOKEN, ssid, pass, "blynk.cloud", 443);
  //Blynk.begin(BLYNK_AUTH_TOKEN, ssid, pass, IPAddress(192,168,1,100), 8443);

  servo.attach(9);
}

void loop()
{
  Blynk.run();
}

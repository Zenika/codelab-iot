---
title: "TP 7 : Code réponse"
nav_exclude: true
schema: true
---

# TP 7 : Code

## Appel en HTTP

Exemple provenant de _File_ > _Examples_ > _ESP8266HTTPClient_ > _BasicHTTPClient_

```c
#include <Arduino.h>

#include <ESP8266WiFi.h>
#include <ESP8266WiFiMulti.h>

#include <ESP8266HTTPClient.h>

#include <WiFiClient.h>

ESP8266WiFiMulti WiFiMulti;

void setup() {

  Serial.begin(115200);

  Serial.println();
  Serial.println();
  Serial.println();

  for (uint8_t t = 4; t > 0; t--) {
    Serial.printf("[SETUP] WAIT %d...\n", t);
    Serial.flush();
    delay(1000);
  }

  WiFi.mode(WIFI_STA);
  WiFiMulti.addAP("SSID", "PASSWORD");

}

void loop() {
  // wait for WiFi connection
  if ((WiFiMulti.run() == WL_CONNECTED)) {

    WiFiClient client;

    HTTPClient http;

    Serial.print("[HTTP] begin...\n");
    if (http.begin(client, "{{ site.endpoint.http }}")) {


      Serial.print("[HTTP] GET...\n");
      // start connection and send HTTP header
      int httpCode = http.GET();

      // httpCode will be negative on error
      if (httpCode > 0) {
        // HTTP header has been send and Server response header has been handled
        Serial.printf("[HTTP] GET... code: %d\n", httpCode);

        // file found at server
        if (httpCode == HTTP_CODE_OK || httpCode == HTTP_CODE_MOVED_PERMANENTLY) {
          String payload = http.getString();
          Serial.println(payload);
        }
      } else {
        Serial.printf("[HTTP] GET... failed, error: %s\n", http.errorToString(httpCode).c_str());
      }

      http.end();
    } else {
      Serial.printf("[HTTP} Unable to connect\n");
    }
  }

  Serial.println("Wait 10s before next round...");
  delay(10000);
}
```

Exemple de sortie :
```
[SETUP] WAIT 3...
[SETUP] WAIT 2...
[SETUP] WAIT 1...
[HTTPS] begin...
[HTTPS] GET...
[HTTPS] GET... code: 200
Hello devfest
Wait 10s before next round...
```

## Appel en HTTPs

Exemple provenant de _File_ > _Examples_ > _ESP8266HTTPClient_ > _BasicHTTPSClient_
```c
/**
   BasicHTTPSClient.ino

    Created on: 20.08.2018

*/

#include <Arduino.h>

#include <ESP8266WiFi.h>
#include <ESP8266WiFiMulti.h>

#include <ESP8266HTTPClient.h>

#include <WiFiClientSecureBearSSL.h>
// Here we replace the finger print by the SHA-1 sign of the mockbin web server certificate
// Use the char* attended fingerprint type since it's more convinient to copy and past the sha-1 signature from the browser
const char* fingerprint = "72:25:52:2D:BE:73:13:61:77:AE:26:5D:D3:16:B8:56:37:BE:FD:E3";

ESP8266WiFiMulti WiFiMulti;

void setup() {

  Serial.begin(115200);
  // Serial.setDebugOutput(true);

  Serial.println();
  Serial.println();
  Serial.println();

  for (uint8_t t = 4; t > 0; t--) {
    Serial.printf("[SETUP] WAIT %d...\n", t);
    Serial.flush();
    delay(1000);
  }

  WiFi.mode(WIFI_STA);
  WiFiMulti.addAP("SSID", "PASSWORD");
}

void loop() {
  // wait for WiFi connection
  if ((WiFiMulti.run() == WL_CONNECTED)) {

    std::unique_ptr<BearSSL::WiFiClientSecure>client(new BearSSL::WiFiClientSecure);

    client->setFingerprint(fingerprint);
    // Or, if you happy to ignore the SSL certificate, then use the following line instead:
    // client->setInsecure();

    HTTPClient https;

    Serial.print("[HTTPS] begin...\n");
    if (https.begin(*client, "{{ site.endpoint.https }}")) {  // HTTPS

      Serial.print("[HTTPS] GET...\n");
      // start connection and send HTTP header
      int httpCode = https.GET();

      // httpCode will be negative on error
      if (httpCode > 0) {
        // HTTP header has been send and Server response header has been handled
        Serial.printf("[HTTPS] GET... code: %d\n", httpCode);

        // file found at server
        if (httpCode == HTTP_CODE_OK || httpCode == HTTP_CODE_MOVED_PERMANENTLY) {
          String payload = https.getString();
          Serial.println(payload);
        }
      } else {
        Serial.printf("[HTTPS] GET... failed, error: %s\n", https.errorToString(httpCode).c_str());
      }

      https.end();
    } else {
      Serial.printf("[HTTPS] Unable to connect\n");
    }
  }

  Serial.println("Wait 10s before next round...");
  delay(10000);
}
```

Exemple de sortie :
```
[SETUP] WAIT 3...
[SETUP] WAIT 2...
[SETUP] WAIT 1...
[HTTPS] begin...
[HTTPS] GET...
[HTTPS] GET... code: 200
Hello devfest
Wait 10s before next round...
```

Dans l'exemple ci-dessus, vous aurez remarqué qu'il est bien sûr possible de ne pas vérifier les certificats SSL avec `client->setInsecure();` 😱.

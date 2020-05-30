#include <ESP8266WiFi.h>

const char* ssid = "    "; SSID or WIFI name
const char* password = "     "; SSID password
const char* host = "maker.ifttt.com";

void setup() {
    Serial.begin(115200);

    Serial.println("Email from Node Mcu");
    delay(100);

    Serial.print("Connecting to ");
    Serial.println(ssid);
    
    WiFi.begin(ssid, password);
    
    while (WiFi.status() != WL_CONNECTED) {
      delay(500);
      Serial.print(".");
    }
  
    Serial.println("");
    Serial.println("IP address: ");
    Serial.println(WiFi.localIP());  

            



}

void loop() {  
      
    float  temperature=36 ;
           WiFiClient client; 
           const int httpPort = 80;  
            if (!client.connect(host, httpPort)) {  
                  Serial.println("connection failed");  
            return;} 
          if(Serial.available()){
            
            char a=Serial.read();
            
            if (a=='y'){
    
          
                    String url = "/trigger/Temperature_alarm/with/key/p6FTqbEsTpK1b9fsdNehaY8DPUwzrBPCd8cC4b00PW1"; 

          
                    Serial.print("Requesting URL: ");
                    Serial.println(url);
                 
                     client.print(String("GET ") + url + String("?value1=") + temperature + " HTTP/1.1\r\n" + 
                                    "Host: " + host + "\r\n" + 
                                           "Connection: close\r\n\r\n");    
                                    } 
          
          else{
            Serial.println("Correct character not pressed.Try again");
            
          }
          }
          
          delay(1000);
          
      
}

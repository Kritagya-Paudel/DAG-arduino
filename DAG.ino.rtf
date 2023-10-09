{\rtf1\ansi\ansicpg1252\cocoartf2709
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fnil\fcharset0 HelveticaNeue;}
{\colortbl;\red255\green255\blue255;}
{\*\expandedcolortbl;;}
\margl1440\margr1440\vieww11520\viewh8400\viewkind0
\deftab560
\pard\pardeftab560\slleading20\partightenfactor0

\f0\fs26 \cf0 \
\
#include <Arduino.h>\
#if defined(ESP32)\
#include <WiFi.h>\
#include <FirebaseESP32.h>\
#elif defined(ESP8266)\
#include <ESP8266WiFi.h>\
#include <FirebaseESP8266.h>\
#elif defined(PICO_RP2040)\
#include <WiFi.h>\
#include <FirebaseESP8266.h>\
#endif\
// #include <Wire.h>\
// #include <Adafruit_GFX.h>\
// #include <Adafruit_SSD1306.h>\
\
// #define SCREEN_WIDTH 128 // OLED display width, in pixels\
// #define SCREEN_HEIGHT 64 // OLED display height, in pixels\
\
// // Declaration for an SSD1306 display connected to I2C (SDA, SCL pins)\
// Adafruit_SSD1306 display(SCREEN_WIDTH, SCREEN_HEIGHT, &Wire, -1);\
\
\
// Provide the token generation process info.\
#include <addons/TokenHelper.h>\
\
// Provide the RTDB payload printing info and other helper functions.\
#include <addons/RTDBHelper.h>\
\
/* 1. Define the WiFi credentials */\
#define WIFI_SSID "HeHeHe_2.4_plus"\
#define WIFI_PASSWORD "Juttakhane#1234*"\
\
// For the following credentials, see examples/Authentications/SignInAsUser/EmailPassword/EmailPassword.ino\
\
/* 2. Define the API Key */\
#define API_KEY "AIzaSyCFnvtdTVkQZzfvhzOukWH7RpzY7ioen8Y"\
\
/* 3. Define the RTDB URL */\
#define DATABASE_URL "https://esp32-fb-dfd3a-default-rtdb.firebaseio.com" //<databaseName>.firebaseio.com or <databaseName>.<region>.firebasedatabase.app\
\
/* 4. Define the user Email and password that alreadey registerd or added in your project */\
#define USER_EMAIL "paudelkritagya1@gmail.com"\
#define USER_PASSWORD "Kittu.123"\
\
// Define Firebase Data object\
FirebaseData fbdo;\
\
FirebaseAuth auth;\
FirebaseConfig config;\
\
\
unsigned long sendDataPrevMillis = 0;\
\
unsigned long count = 0;\
\
void setup()\
\{\
\
  Serial.begin(115200);\
\
  WiFi.begin(WIFI_SSID, WIFI_PASSWORD);\
  Serial.print("Connecting to Wi-Fi");\
  while (WiFi.status() != WL_CONNECTED)\
  \{\
    Serial.print(".");\
    delay(300);\
  \}\
  Serial.println();\
  Serial.print("Connected with IP: ");\
  Serial.println(WiFi.localIP());\
  Serial.println();\
\
  Serial.printf("Firebase Client v%s\\n\\n", FIREBASE_CLIENT_VERSION);\
\
  /* Assign the api key (required) */\
  config.api_key = API_KEY;\
\
  /* Assign the user sign in credentials */\
  auth.user.email = USER_EMAIL;\
  auth.user.password = USER_PASSWORD;\
\
  /* Assign the RTDB URL (required) */\
  config.database_url = DATABASE_URL;\
\
  /* Assign the callback function for the long running token generation task */\
  config.token_status_callback = tokenStatusCallback; // see addons/TokenHelper.h\
\
  // Or use legacy authenticate method\
  // config.database_url = DATABASE_URL;\
  // config.signer.tokens.legacy_token = "<database secret>";\
\
  // To connect without auth in Test Mode, see Authentications/TestMode/TestMode.ino\
\
  //////////////////////////////////////////////////////////////////////////////////////////////\
  // Please make sure the device free Heap is not lower than 80 k for ESP32 and 10 k for ESP8266,\
  // otherwise the SSL connection will fail.\
  //////////////////////////////////////////////////////////////////////////////////////////////\
\
  Firebase.begin(&config, &auth);\
\
  // Comment or pass false value when WiFi reconnection will control by your code or third party library\
  Firebase.reconnectWiFi(true);\
\
  Firebase.setDoubleDigits(5);\
\
  /** Timeout options.\
\
  //WiFi reconnect timeout (interval) in ms (10 sec - 5 min) when WiFi disconnected.\
  config.timeout.wifiReconnect = 10 * 1000;\
\
  //Socket connection and SSL handshake timeout in ms (1 sec - 1 min).\
  config.timeout.socketConnection = 10 * 1000;\
\
  //Server response read timeout in ms (1 sec - 1 min).\
  config.timeout.serverResponse = 10 * 1000;\
\
  //RTDB Stream keep-alive timeout in ms (20 sec - 2 min) when no server's keep-alive event data received.\
  config.timeout.rtdbKeepAlive = 45 * 1000;\
\
  //RTDB Stream reconnect timeout (interval) in ms (1 sec - 1 min) when RTDB Stream closed and want to resume.\
  config.timeout.rtdbStreamReconnect = 1 * 1000;\
\
  //RTDB Stream error notification timeout (interval) in ms (3 sec - 30 sec). It determines how often the readStream\
  //will return false (error) when it called repeatedly in loop.\
  config.timeout.rtdbStreamError = 3 * 1000;\
\
  Note:\
  The function that starting the new TCP session i.e. first time server connection or previous session was closed, the function won't exit until the\
  time of config.timeout.socketConnection.\
\
  You can also set the TCP data sending retry with\
  config.tcp_data_sending_retry = 1;\
\
  */\
  // if(!display.begin(SSD1306_SWITCHCAPVCC, 0x3C)) \{ // Address 0x3D for 128x64\
  //   Serial.println(F("SSD1306 allocation failed"));\
  //   for(;;);\
  // \}\
  // delay(2000);\
  // display.clearDisplay();\
\
  // display.setTextSize(1);\
  // display.setTextColor(WHITE);\
  // display.setCursor(0, 10);\
  // // Display static text\
  // display.println("Hello, world!");\
  // display.display(); \
\}\
\
void loop()\
\{\
\
  // Firebase.ready() should be called repeatedly to handle authentication tasks.\
\
  if (Firebase.ready() && (millis() - sendDataPrevMillis > 500 || sendDataPrevMillis == 0))\
  \{\
    sendDataPrevMillis = millis();\
\
    Serial.printf("%s\\n", Firebase.getString(fbdo, F("message")) ? fbdo.to<const char *>() : fbdo.errorReason().c_str());\
    \
\
    // For generic set/get functions.\
\
    // For generic set, use Firebase.set(fbdo, <path>, <any variable or value>)\
\
    // For generic get, use Firebase.get(fbdo, <path>).\
    // And check its type with fbdo.dataType() or fbdo.dataTypeEnum() and\
    // cast the value from it e.g. fbdo.to<int>(), fbdo.to<std::string>().\
\
    // The function, fbdo.dataType() returns types String e.g. string, boolean,\
    // int, float, double, json, array, blob, file and null.\
\
    // The function, fbdo.dataTypeEnum() returns type enum (number) e.g. fb_esp_rtdb_data_type_null (1),\
    // fb_esp_rtdb_data_type_integer, fb_esp_rtdb_data_type_float, fb_esp_rtdb_data_type_double,\
    // fb_esp_rtdb_data_type_boolean, fb_esp_rtdb_data_type_string, fb_esp_rtdb_data_type_json,\
    // fb_esp_rtdb_data_type_array, fb_esp_rtdb_data_type_blob, and fb_esp_rtdb_data_type_file (10)\
  \}\
\
\}\
}
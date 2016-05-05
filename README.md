# GY-273 Library

#Example

##Wiring
<img src="media/sample.png">

##Code
```c
#include <GY273.h>

int x, y, z;

void setup()
{
        Serial.begin(9600);
        while (GY273Setup() != GY273_SUCCESS)
        {
                Serial.println("failed to initiate the GY-273 setup process. Retrying in 1 second...");
                delay(1000);
        }
}

void loop()
{
        GY273Read(GY273_X, &x);
        GY273Read(GY273_Y, &y);
        GY273Read(GY273_Z, &z);
        Serial.print("x=");
        Serial.print(x, DEC);
        Serial.print(" ");
        Serial.print("y=");
        Serial.print(y, DEC);
        Serial.print(" ");
        Serial.print("z=");
        Serial.print(z, DEC);
        Serial.println();
        delay(60);
}
```

#Author
[Fadi Hanna Al-Kass](http://github.com/alkass)

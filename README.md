# GY-273 Library

#Example

##Wiring
<img src="media/sample.png">

##Arduino Code
```c
#include <GY273.h>

template<class T> inline Print &operator <<(Print &obj, T arg)
{
	obj.print(arg);
	return obj;
}

#define cout Serial
#define endl "\n\r"

int x, y, z;

void setup()
{
        Serial.begin(9600);
        while (GY273Setup() != GY273_SUCCESS)
        {
                cout << "GY-273 setup process has failed. Retrying in 1 second..." << endl;
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

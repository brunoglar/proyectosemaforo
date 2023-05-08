# **<span style="color:white">Documentación de Arduino en Tinkercad👨‍💻**

---

![Arduino](https://d1e4pidl3fu268.cloudfront.net/1e27d448-be48-4a6a-97e9-855e2321ad37/images.crop_222x168_38,0.preview.png)

##     **<span style="color:yellow">Integrantes:**
---
* ### <span style="color:white">**Bruno Gaston Luna**


## **<span style="color:yellow">Proyecto: Estaciones de SUBTE**
---

![Tinkercad](https://1drv.ms/i/s!Alay7t3_GjB9ln3ZG5XhGJcuO8RH?e=CByN3N)


## **<span style="color:yellow">Consigna SUBTE:**
---
<span style="color:white">La empresa  “UTN FRA Robotics” ganó la licitación de un proyecto, y deberá Implementar un sistema que permita al usuario saber a qué estación de subte está llegando, aparte  el sistema muestra las estaciones que faltan hasta llegar a destino, para ello debemos utilizar 4 LEDs y el display de 7 segmentos. Esta vez el buzzer deberá emitir un sonido diferente cada vez que se llegue a una estación.
El sistema deberá arrancar apagado, luego de presionar el botón empezará y hará lo pedido.


---


## **<span style="color:yellow">Función principal**
<span style="color:white">La **funcionalidad** del código a continuación, es la encargada de encender los **leds** y el **buzzer** simulando las estaciones del **subte** tal como pide la consigna mediante un **switch**.

>**<span style="color:green">A, B, C, D, E, F, G, ledConsti, ledSanJuan, ledIndependencia, ledMoreno, buzzer, SWITCH**



<span style="color:white">Son **#define** que utilizamos para asignar los leds y buzzer a cada pin en la placa de Arduino, a continuación una breve parte del código. Si desea ver el código completo en su totalidad, acceda mediante el link brindado al final del proyecto.

# 👨‍💻
```
#define A 13
#define B 12
#define C 11
#define D 10
#define E 9
#define F 8
#define G 7
#define ledConsti 5
#define ledSanJuan 4
#define ledIndependencia 3
#define ledMoreno 2
#define buzzer 6
#define SWITCH A0

int timer = 1000; 

void setup()
{
    pinMode(A, OUTPUT);
    pinMode(B, OUTPUT);
  	pinMode (ledConsti, OUTPUT);
  	pinMode (buzzer, OUTPUT);
  	pinMode (SWITCH, INPUT_PULLUP);
}
void loop()
{
  int estado = digitalRead(SWITCH);
    if(estado == 0){
    	
    		inicializarContador();
    
  	}
}

void inicializarContador()
{
	
    for (int contador = 3; contador > -1; contador--)
    {
        switch (contador){
        

        case 3:
            digitalWrite(A, HIGH);
            digitalWrite(B, HIGH);
            digitalWrite(C, HIGH);
            digitalWrite(D, HIGH);
            digitalWrite(G, HIGH);
          	digitalWrite(ledConsti, HIGH);
          	tone(buzzer, 250);
            delay(timer);
          	digitalWrite(ledConsti, LOW);
            apagarDisplay();
          	break;
		}
	}
}
```


# 🤖 *<span style="color:white">ENLACES A GDB Y TINKERCAD*
>**Apreta en el link para acceder al código en 
[GDB](https://onlinegdb.com/TfaMQRrgf)**
---
>**Apreta en el link para acceder al proyecto y visualizar su funcionamiento en 
[TinkerCad](https://www.tinkercad.com/things/jCwcsqkiEle-ejercicio-estacion-de-subte/editel?sharecode=n3iPHVnVO5O6R1Ly03omNiraLAmwxyKL4AQDS0MX5T4)**

# **Proyecto: Sistema de Incendio con Arduino**
![Tinkercad](img\imagenproyecto.png)

## Integrantes 
- Brenda Candy

## Descripción
El objetivo de este proyecto es diseñar un sistema de incendio utilizando Arduino que pueda detectar cambios de temperatura y activar un sistema de respuesta en caso de detectar un incendio. Además, se mostrará el nivel de temperatura en un display de 7 segmentos y el estado del sistema por consola.

## Función principal
### LeerSistema()
Esta funcion se encarga de detectar el estado en el que se encuentra el sistema una vez activado. En caso de estar en emergencia nos devuelvo true y caso contrario false. 

~~~ C++ (lenguaje en el que esta escrito)
bool leerSistema()
{
  int temperatura = map(analogRead(SENSOR),20,358,-40,125);//CONFIGURA LOS VALORES 
  if (temperatura >= 60)
  {
    if (temperatura >= 60 && temperatura <= 64)
    {
      proyectarAlarma(7);
    }
    else if (temperatura >= 65 && temperatura <= 69)
    {
      proyectarAlarma(8);
    }
    else if (temperatura >= 70)
    {
      proyectarAlarma(9);
    }
    return true;
  }
  else
  {
    if (temperatura < 30)
    {
      dibujarNum(0);
    }
    else if (temperatura >= 30 && temperatura <= 34)
    {
      dibujarNum(1);
    }
    else if (temperatura >= 35 && temperatura <= 39)
    {
      dibujarNum(2);
    }
    else if (temperatura >= 40 && temperatura <= 44)
    {
      dibujarNum(3);
    }
    else if (temperatura >= 45 && temperatura <= 49)
    {
      dibujarNum(4);
    }
    else if (temperatura >= 50 && temperatura <= 54)
    {
      dibujarNum(5);
    }
    else if (temperatura >= 55 && temperatura <= 59)
    {
      dibujarNum(6);
    }
    return false;
  }
}
~~~
## Componentes
### *Buzzer*
![buzzer](img\buzzer.png)

Un tipo de zumbador que emite ruido en distintas frecuencias. En este proyecto lo utilizamos como alarma una vez que la temperatura supera los 60°C.
### *Sensor de Temperatura*
![sensor](img\sensortemp.png)

Un sensor que genera voltajes segun la temperatura ambiente.
### *Display 7 Segmentos*
![display](img\display.png)

Un único LED de 7 segmentos para mostrar una serie de numeros.Lo utilizamos para mostrar los niveles de temperatura a partir de los cuales se considera que hay un incendio
### *Leds*
![leds](img\leds.png)

Los dos led cumplen un patron de luces solo cuando la alarma suena.
### *Pulsador*
![pulsador](img\botones.png)

Un conmutador que cierra un circuito cuando se presiona. Agregamos dos pulsadores para manejar el activamiento y desactivamiento del sistema.

## :boom: Link al proyecto
- [Proyecto](https://www.tinkercad.com/things/kAZI1C36ndZ-powerful-wolt-esboo/editel?sharecode=1X8me1LjPom2ZBCnSIGeGLGrA3SEeX9YH_ETNIKZUJM)

---

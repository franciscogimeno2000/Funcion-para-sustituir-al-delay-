# Funcion para sustituir al delay() de Arduino
Esta funcion hace una parada en milisegudos sin usar delay. El micro sigue activo.
Esta funcion tal cual esta construida no tiene problemas de desbordamientos ni de cuando se asignan y evaluan los
valores de la funcion Millis()




void pausa(unsigned int milisegundos)

{

volatile unsigned long compara=0;

volatile int contador=0;


do

{

if (compara != millis())

{

contador++;

compara = millis();

}

} while (contador <= milisegundos);

return;

}


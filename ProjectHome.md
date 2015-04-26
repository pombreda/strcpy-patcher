This Python script takes a PE file with a buffer overflow vulnerability through the strcpy standard function and modifies the call to the function for a call to a modified strcpy function that is not vulnerable. The script takes as arguments: A) Path to the PE file, B) Maximum of characters that will be allowed to copy de new strcpy function, C) Location of the call to the original strcpy function in the PE file (in hex).

The script will insert the not vulnerable strcpy in the DOS Stub part of the PE Header of (A), using (B) as max copy boundary. Then, it will go to (C) and will insert the offset to the DOS Stub in the call, so the vulnerability will be fixed.

Usage: python strcpy-patcher.py (A) (B) (C)


---


Este script de Python toma un binario ejecutable del tipo Portable Executable con una vulnerabilidad de desbordamiento de memoria mediante la llamada a la función "strcpy" y suplanta la llamada a dicha función por una llamada a una versión no vulnerable de la misma. Toma como argumentos: A) Path hacia el binario con la vulnerabilidad, B) El máximo de caracteres que soportará el nuevo strcpy, C) La dirección de la llamada a strcpy en el binario (en hexadecimal).

El script inyectará la función strcpy no vulnerable en la sección DOS Stub del PE header de (A), usando como medida máxima de caracteres de copiado (B). Posteriormente irá a la dirección (C) e insertará el offset hacia el DOS Stub, de tal forma que la vulnerabilidad haya sido remediada.

Uso: python strcpy-patcher.py (A) (B) (C)
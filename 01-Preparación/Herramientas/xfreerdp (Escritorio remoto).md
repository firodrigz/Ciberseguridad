### xfreerdp

xfreerdp es un cliente de protocolo de escritorio remoto (RDP) de código abierto para sistemas Unix y similares a Unix, como Linux. Forma parte del proyecto FreeRDP, que es una implementación libre y de código abierto del protocolo RDP de Microsoft. RDP permite a los usuarios conectarse a otro ordenador a través de la red y utilizar su escritorio de manera remota.

**Conexión Básica a un Escritorio Remoto**:
  
```BASH
xfreerdp /v:servidor_remoto /u:usuario /p:'contraseña' /dynamic-resolution
```
  
   - `/v:` especifica la dirección del servidor remoto.
   - `/u:` especifica el nombre de usuario.
   - `/p:` especifica la contraseña.


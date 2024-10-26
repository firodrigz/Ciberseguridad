`wget` es otra herramienta de línea de comandos que se utiliza para descargar archivos desde la web. Al igual que `curl`, `wget` es ampliamente utilizado en entornos de línea de comandos y scripts para realizar transferencias de archivos de manera eficiente. Algunas de las características y usos comunes de `wget` incluyen:

1. **Descarga de archivos:**
   - Puedes utilizar `wget` para descargar archivos desde la web. Por ejemplo:

    ```bash
    wget https://www.ejemplo.com/archivo.txt
    ```

2. **Descarga recursiva:**
   - `wget` puede descargar recursivamente, lo que significa que puede seguir enlaces y descargar todos los archivos vinculados a una página web.

    ```bash
    wget -r https://www.ejemplo.com/directorio
    ```

3. **Continuar descargas interrumpidas:**
   - Si una descarga se interrumpe, `wget` permite continuarla desde donde se detuvo.

    ```bash
    wget -c https://www.ejemplo.com/archivo_grande.zip
    ```

4. **Espejo de sitios web:**
   - Puedes usar `wget` para crear un espejo de un sitio web, descargando todo su contenido y manteniendo la estructura de directorios.

    ```bash
    wget --mirror -p --convert-links -P ./sitio_espejo https://www.ejemplo.com
    ```

5. **Descarga en segundo plano:**
   - Puedes ejecutar `wget` en segundo plano, lo que es útil para descargas largas o en scripts.

    ```bash
    wget -b https://www.ejemplo.com/archivo_largo.zip
    ```

En resumen, `wget` es una herramienta versátil para la descarga de archivos y la gestión de descargas desde la línea de comandos. Aunque comparte algunos propósitos con `curl`, tienen características y opciones específicas que los hacen más adecuados para ciertos escenarios.

[[COMANDO CURL]]
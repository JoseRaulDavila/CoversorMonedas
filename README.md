# Conversor de Monedas en Java

Este proyecto implementa un conversor de monedas en Java que permite realizar conversiones entre diferentes divisas de manera interactiva. 
El programa ofrece opciones predefinidas para convertir entre monedas comunes, así como la posibilidad de ingresar monedas personalizadas para convertir entre ellas.

## Funcionalidades
- **Menú interactivo** para seleccionar conversiones predefinidas (por ejemplo, Dólar a Peso Argentino, Real Brasilero a Dólar, etc.).
- **Opción personalizada** para convertir entre cualquier par de monedas.
- **Opción para salir** del programa.

El programa sigue un ciclo que permite realizar múltiples conversiones hasta que el usuario decide salir.

## Ejecución
1. Selecciona una opción de conversión del menú.
2. Si eliges una opción personalizada, ingresa las monedas de origen y destino.
3. El programa muestra el monto convertido según la tasa de cambio actual.
4. El ciclo continúa hasta que eliges la opción para salir.

## Manejo de Errores
El programa maneja excepciones para capturar entradas no válidas y evitar fallos durante la ejecución.

## Código Class Principal
![image](https://github.com/user-attachments/assets/3b2203e7-8b18-45a3-b5eb-a449854a6455)

- **Condiciones**
  
![image](https://github.com/user-attachments/assets/57f6275a-b76d-4037-8d8c-b4f5d2bb99ee)

- **Resultados**

![image](https://github.com/user-attachments/assets/b1f1f138-570a-483b-b3f5-3adf51817971)


# Conversor de Monedas

Este programa permite convertir un monto de una moneda base a una moneda destino utilizando tasas de cambio actuales. 
Los usuarios ingresan las monedas de origen y destino, y el programa calcula y muestra el valor convertido.

## Funcionalidades
- **convertir**: Solicita al usuario un monto en la moneda base, realiza la conversión a la moneda destino usando la tasa de cambio actual y muestra el resultado.
- **ConvertirOtraMoneda**: Solicita al usuario las monedas de origen y destino, luego llama al método "convertir" para realizar la conversión.

El programa depende de las clases **ConsultaCambio** y **Cambio** para obtener las tasas de conversión y realizar los cálculos.

## Ejecución
1. Ingrese las monedas de origen y destino según las opciones disponibles.
2. El programa calcula el monto convertido utilizando la tasa de cambio actual.
3. Se puede realizar múltiples conversiones hasta que el usuario decida salir.

## Código Class ConversorMonedas
![image](https://github.com/user-attachments/assets/1b37e931-49f8-4c36-a05c-526c32f16960)

# ConsultaCambio - Clase para Obtener Tasas de Cambio

La clase **ConsultaCambio** obtiene la tasa de cambio entre dos monedas utilizando la API **ExchangeRate-API**.

## Funcionalidades:
**buscaCambio(String baseCode, String monedaCambio)**:
  - **Realiza** una solicitud HTTP para obtener la tasa de cambio entre dos monedas.
  - **Convierte** la respuesta JSON en un objeto **Cambio** usando la librería **Gson**.
  - **Guarda el objeto** "Cambio" como un archivo JSON con la ayuda de la clase **GeneradorArchivo**.

## Código Class buscaCambio

![image](https://github.com/user-attachments/assets/334bebd8-fbe9-425c-a026-e89228231203)

# GeneradorArchivo - Clase para Guardar Objetos

La clase **GeneradorArchivo** guarda un objeto **Cambio** como un archivo JSON con formato legible.

## Funcionalidad:
- **guardarJson(Cambio cambio)**:
  - Convierte un objeto Cambio a formato JSON usando **Gson**.
  - Guarda el JSON en un archivo con el nombre de la moneda base (por ejemplo, USD.json).
  - Utiliza **GsonBuilder** para generar un JSON con formato "pretty printing", lo que mejora la legibilidad.

## Requisitos:
- **Gson** para la conversión de objetos Java a JSON.
- Excepciones **IOException** para el manejo de errores al escribir el archivo.

El archivo JSON generado facilita el almacenamiento y visualización de las tasas de cambio de manera estructurada.

## Código Class GeneradorArchivo

![image](https://github.com/user-attachments/assets/edeea731-fa8a-4fd8-a044-610bbc6455a1)


